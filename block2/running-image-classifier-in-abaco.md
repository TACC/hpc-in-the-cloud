# Running Classifier Image in Abaco

## Getting the Image Ready and Registering an Actor

### Lecture: Preparing our code for Abaco
To run our classifier docker image with Abaco, we will first need to create a script that will take the message sent to an actor and send it to our classifier script. This could be written in anything, including the original Python script; for simplicity, we'll write a short Bash script. 

### Exercise: Creating a shell script
Create a new file called `abaco.sh` and add the following content:

```bash
#!/bin/bash

# print the special MSG variable:
echo "Contents of MSG: "$MSG

python /app/classify_image.py --image_file=$MSG
```

NOTE: In this case, `--image_file` does not refer to a docker image, but a JPEG image. This tag expects a URL from the internet to a JPEG picture file. 

### Lecture: Changing the Dockerfile

Once we register our actor and sent it a message, Abaco will pass the contents of the message in the `$MSG` environment variable. We can use a bash script to capture it, and then run our classifier script with it.
Because we have added this wrapper script, we will need to update our Dockerfile before we create an Abaco actor.



Instead of our entrypoint being `classify_image.py` as it was in the example, it will need to be set to run our wrapper script, `abaco.sh`.

Another difference with running on Abaco is that Abaco will run our actor using the UID associated with our TACC account.
This ensures files created and modified by the actor are owned by the API user. 

In order for this to work, we need to ensure that our container can run properly as a non-root user. Running containers as 
a non-root user is good practice in general. To make it so that a non-root user can
write the downloaded file to the container's file system, we can `chmod 777` the `/app` directory:

```bash
RUN chmod -R 777 /app
```

### Exercise: Create the Dockerfile for Abaco

Begin by creating a new Dockerfile or overriding your previous Dockerfile. Your final Dockerfile should look like this:

```bash

# image: taccsciapps/abaco_classifier

FROM tensorflow/tensorflow:1.5.0-py3

# install requirements
RUN pip install requests

# add our app
RUN mkdir /app
ADD classify_image.py /app/classify_image.py
RUN chmod +x /app/classify_image.py
ADD abaco.sh /app/abaco.sh
RUN chmod +x /app/abaco.sh
RUN chmod -R 777 /app

CMD ["/app/abaco.sh"]

```

Once you have built your image, try pushing it to dockerhub. 

### Exercise: Creating an Abaco Actor

Once our new dockerfile is built and pushed to DockerHub, we can create our Abaco actor. 
```
$ curl -k -H "Authorization: Bearer $TOKEN" \
-H "Content-Type: application/json" \
-d '{"image": "taccsciapps/abaco_classifier", "name": "abaco_classifier", "description": "Using the image classifier with abaco."}' \
https://api.tacc.cloud/actors/v2
```

Take note of the actor ID that is returned, since you will need it to send the actor a message.

## Exercise: Executing Classifier with `curl`

To execute our Actor with our image classifier, we will need to send our actor a raw string message:

```
$ curl -k -H "Authorization: Bearer $TOKEN" -d "message=https://s3.amazonaws.com/cdn-origin-etr.akc.org/wp-content/uploads/2017/11/12231410/Labrador-Retriever-On-White-01.jpg" https://api.tacc.cloud/actors/v2/$ACTOR_ID/messages
```

To see the results of the execution, we can check the logs:
```
$ curl -k -H "Authorization: Bearer $TOKEN" https://api.tacc.cloud/actors/v2/$ACTOR_ID/executions/$EXECUTION_ID
```


## Exercise: Executing Classifier on Abaco using a Jupyter Notebook & TapisPy

See the jupyter notebook here: [Using tapispy to Execute Actor Containers on the Abaco Cloud.ipynb](../Using%20tapispy%20to%20Execute%20Actor%20Containers%20on%20the%20Abaco%20Cloud.ipynb)
