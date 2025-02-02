## PEARC19 Portable, Reproducible High Performance Computing In the Cloud

## Part 1: Welcome and Background
* [Welcome](./welcome/intro.md)

## Schedule

* 8:30AM - Introduction
* 9:00AM - Intro to Jupyter, Intro to Docker
* 10:00AM - Break
* 10:30AM - Intro to Docker(cont), Intro to Tapis and CLI, Intro to Abaco
* 12:00pm-1:30pm - Lunch
* 1:30PM - Using Abaco, Intro to Singularity
* 3:00PM - Break
* 3:30PM - Tapis Systems, Tapis Apps, Tapis Jobs
* 4:30PM - Workshop Wrap-up

## Workshop Introduction
Presenters: 
* Joe Stubbs (TACC)
* Julia Looney (TACC)
* Anagha Jamthe (TACC)
* Sean Cleveland (UH)

The resources you will be using today are provided by funding from the National Science Foundation:

* [Jetstream](https://jetstream-cloud.org/) is a cloud service for research that provides on-demand, user-controled, Virtual Machines (VMs) - you can request and account after the workshop using these [instructions](https://iujetstream.atlassian.net/wiki/spaces/JWT/pages/76150553/Get+a+Jetstream+Trial+Access+account).  
* Stampede2 is the flagship supercomputer at The University of Texas at Austin's Texas Advanced Computing Center (TACC). A strategic national resource, Stampede2 provides high-performance computing capabilities to thousands of researchers across the U.S.  To gain access after the workshop you need to request a [startup allocation](https://portal.xsede.org/allocations/startup) with an XSEDE portal account, you can [Request and Account](https://portal.xsede.org/my-xsede?p_p_id=58&p_p_lifecycle=0&p_p_state=maximized&p_p_mode=view&_58_struts_action=%2Flogin%2Fcreate_account) and then [Submit an Allocation request](http://portal.xsede.org/submit-request) - If you have question please contact us via the TACC-Cloud slack channel.

You should have recieved a paper with a training account for Stampede2 and a slip of paper with a Jetstream Virtual Machine(VM) IP with username and password for that VM.  These are the credentials that we will use today and are only valid for todays workshop.

The Jetstream VMs all have the same configuration running Ubuntu 18 with all required software (Docker, Singularity, Tapis-CLI, Tapis PY and Jupyterhub).

## Intro to Jupyter
* [Introduction to Jupyter](./block1/intro-to-jupyter.md)
  * [Starting a Jupyter Notebook](./block1/intro-to-jupyter.md#starting-up-your-jupyter-notebook-environment)
  * [Creating a Notebook](./block1/intro-to-jupyter.md#creating-a-notebook)
  * [Starting a Terminal](./block1/intro-to-jupyter.md#starting-a-terminal)


## Intro to Docker
* [Using Docker](./block1/intro-to-docker.md)
  * [What is a container?](./block1/intro-to-docker.md#what-is-a-container)
  * [Containers vs VMs](./block1/intro-to-docker.md#containers-vs-vms)
  * [The Docker Platform](./block1/intro-to-docker.md#the-docker-platform)
  * [Initial Setup](./block1/intro-to-docker.md#initial-setup)
  * [Docker Images and Tags, Docker Hub, and Pulling Images](./block1/intro-to-docker.md#docker-images-and-tags-docker-hub-and-pulling-images)
  * [Building Images from a Dockerfile](./block1/intro-to-docker.md#building-images-from-a-dockerfile)
  * [Running a Docker Container](./block1/intro-to-docker.md#running-a-docker-container)
  * [Removing Docker Containers](./block1/intro-to-docker.md#removing-docker-containers)

## Intro to Tapis (Agave)
* [Intro to Tapis(Agave)](./block3/tapis-intro.md)

* [Intro to Tapis CLI](./block3/tapis-cli.md)

## Using Abaco
* [Intro to Abaco](./block2/intro-to-abaco.md)
  * [What is Abaco?](./block2/intro-to-abaco.md#what-is-abaco)
  * [Using Abaco](./block2/intro-to-abaco.md#using-abaco)
  * [Registering an Actor](./block2/intro-to-abaco.md#registering-an-actor)
  * [Executing an Actor](./block2/intro-to-abaco.md#executing-an-actor)
  * [Executing Actors with Raw Strings](./block2/intro-to-abaco.md#executing-actors-with-raw-strings)
  * [Executing Actors with JSON](./block2/intro-to-abaco.md#executing-actors-by-passing-json)
  * [Retrieving the Logs](./block2/intro-to-abaco.md#retrieving-the-logs)

* [Running the Image classifier with Abaco](./block2/running-image-classifier-in-abaco.md)
  * [Preparing our Code for Abaco](./block2/running-image-classifier-in-abaco.md#preparing-our-code-for-abaco)
  * [Creating and Actor](./block2/running-image-classifier-in-abaco.md#creating-an-abaco-actor)
  * [Executing Actor with curl](./block2/running-image-classifier-in-abaco.md#executing-classifier-with-curl)
  * [Executing Actor with Python on the Abaco Cloud](./block2/Using%20tapispy%20to%20Execute%20Actor%20Containers%20on%20the%20Abaco%20Cloud.ipynb)
## Intro to Singularity
* [Intro to Singularity](./block3/intro-singularity.md)

## Tapis Systems
* [Intro to Tapis Systems](./block3/tapis-systems.md)

## Tapis Apps
* [Intro to Apps](./block4/apps.md)
  * [What is a Tapis(Agave) app?](./block4/apps.md#what-is-a-tapisagave-app)
  * [Tapis(Agave) Apps service](./block4/apps.md#tapisagave-apps-service)
  * [App Packaging](./block4/apps.md#app-packaging)
  * [Application metadata](./block4/apps.md#application-metadata)
  * [Registering App](./block4/apps.md#registering-an-app)
  * [List Apps](./block4/apps.md#list-apps)
  * [Managing App Permissions](./block4/apps.md#apps-permissions)

## Tapis Jobs
* [Intro to Tapis(Aloe) Jobs](./block4/jobs.md)
  * [Tapis(Aloe) Jobs Service](./block4/jobs.md#tapisaloe-jobs-service)
  * [Jobs Parameters](./block4/jobs.md#jobs-parameters)
  * [Submitting a Job ](./block4/jobs.md#submitting-a-job)
  * [Jobs List](./block4/jobs.md#jobs-list)
  * [Jobs Status](./block4/jobs.md#jobs-status)
  * [Jobs Output](./block4/jobs.md#jobs-output)
  * [Jobs Notifications](./block4/jobs.md#jobs-notifications)

* [Link to Templates](./block4/templates)
