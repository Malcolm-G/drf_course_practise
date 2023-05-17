# Django Rest Framework (DRF) Course
This is a project created while following a tutorial by Bobby Stearman, found on [youtube](https://www.youtube.com/watch?v=tujhGdn1EMI&t=1448s&ab_channel=freeCodeCamp.org).
The first part of this README entails the project setup and other deatils on the project that were written by Bobby Stearman. The second part entails notes written by myself that are not included in the project tutorial.

## Introduction
Welcome to this full Django Rest Framework (DRF)course. 
This course is perfect if you are looking to learn DRF and build your own API application.
***
***

## Prerequisites
- Python=>3.10

## Considerations
I have added optional docker containers to simplify the build. If you want to use the docker build you should install Docker and Docker Compose on your local machine.

We will be calling our API throughout the next 8 modules. I have written the requests in (Curl)[https://curl.se/] and (Httpie)[https://httpie.io/]. 

(Httpie)[https://httpie.io/] provides a clean terminal output which is handy for this type of project. You will need to install it locally if you want to use the commands.
>Note: (Httpie)[https://httpie.io/] is pre-installed in the docker container.
***
***

## Getting started
First you will need to clone down the first module.

1) Create a new directory on your local machine. I have called mine drf_course. This is your 'root directory'.

2) Open a terminal and cd into the root directory.

3) You can now clone the first module. You can do this a few different ways. I use SSH...

```
#option 1 - SSH
git clone --branch module_1 git@github.com:bobby-didcoding/drf_course.git .

#option 2 - Github CLI
gh repo clone bobby-didcoding/drf_course .
git checkout module_1

#option 3 - HTTPS
git clone --branch module_1 https://github.com/bobby-didcoding/drf_course.git .
```

***
***

## Following along
Each module has a walk through video. All videos can be found in my (Django Rest Framework Course)[https://www.youtube.com/playlist?list=PL5VlxT4gkOFAD2wpucxHY3X2sCzhha5Kz] playlist.

Please open /steps/module_1 to begin.
***
***


# My Notes on the course
While following the lesson on django framework there were new concepts that I cam across and problems that I encountered that were not necessarily explained during the course especially about docker. Below I shall highlight some of these points.

## Docker Notes
### <u> Before using docker</u>
Note that before you create a docker container, if you build an image, it will now need sudo access to edit any files made afterwards which is a pain.

### <u> Using docker for the tutorial</u>
To get docker to work as shown in the lesson video, one needs to first make the entrypoints.sh file an executable. The file is found in the path `backend/docker/entrypoints/entrypoint.sh`, to make the file executable cd into the entrypoints directory and run the command:

```
chmod +x entrypoint.sh
```

Then ensuring you have docker-compose installed in your system, run the following command to run docker, which will start 2 containers that are defined in the docker-compose.yml file found in root:

```
sudo docker-compose up -d --build
```
When you run the above command, Docker will look for a docker-compose.yml file in the current directory (unless a different file is specified with the -f flag). It will then read the configuration in the Compose file and perform the following actions:

1. Build any necessary Docker images based on the instructions in the Dockerfiles associated with the services defined in the Compose file.
2. Create and start the containers defined in the Compose file.
3. If the **-d** flag is used, the containers will run in the background, and you'll get the terminal prompt back.
4. If the **--build** flag is used, Docker will rebuild the images even if they already exist, ensuring that any changes in the Dockerfile or the build context are incorporated.

Overall, the command docker-compose up -d --build is commonly used when you want to build and start a multi-container application defined in a Docker Compose file.

If you wish to see the currently running containers in docker run the following command:

```
sudo docker ps
```
Take note of the name of the containers because to run the terminal of a particular container you'll need to run this command:
```
docker exec -it <container-name> bash
```
This would open a new terminal session inside the container, enabling you to run commands interactively.

By using docker exec, you can execute commands within a running Docker container, facilitating various operations and tasks within the container environment.

**Docker volumes** are also enabled allowing data created in the docker container to be persisted. That's why when one creates files when in the docker container they appear in the project's directory.

## Authentication
Anywhere where permission class is added in a view will enforce authentication, meaning you can't access without the token.
Find info on DRF authentication [here](https://www.django-rest-framework.org/api-guide/authentication/).

