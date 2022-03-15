# Docker

With Docker we now longer have to mess around with virtual environments. We can faithfully reproduce a production environment locally. And Docker can be shared among team members so everyone is working on the same setup.

## Install Docker
To install Docker we need to [download the desktop app](https://www.docker.com/get-started) on our computer and create a free account. The initial download of Docker might take some time to download. It’s a big file. Feel free to stretch your legs at this point!

Once Docker is done installing we can confirm the correct version is running. It should be at least version 19.
```
$ docker --version
Docker version 19.03.5, build 633a0ea
```

## Hello World

To confirm Docker installed correctly we can run our first command `docker run hello-world`. This will download an official image and then run the container. 

### Example:
```
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:9572f7cdcee8591948c2963463447a53466950b3fc15a247fcad1917ca215a2f
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 ```

## Images and Containers
Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.

A baking analogy we can use here is as follows:

- A Dockerfile is the recipe for a cake
- An image is a snapshot of the recipe at a given time
- A docker-compose.yml says how to make the cake
- The container is the actual, baked cake

## Create a local Image

First create a local directory on your computer for our code.
```
$ cd ~/Desktop
$ mkdir code && cd code
$ mkdir python3.7 && cd python3.7
```

Now to define the image with a Dockerfile. This is similar to a Pipenv or a requirements.txt file; it is a list of all the requirements needed to build our image. It is simpler to have them all in one place rather than install each manually line-by-line.

If you are on a Mac, you can create a new Dockerfile on the command line using the `touch command`.
```
$ touch Dockerfile
```
With your text editor add the following single line of code to the Dockerfile.
```
# Dockerfile
FROM python:3.7-alpine
```

Dockerfiles are read from top-to-bottom. The first instruction **must** be the `FROM` command which lets us import a base image to use for our image. This base image could be another Docker image or one we create entirely from scratch.

## Image Builds

To create an Image use:
```
$ docker image build .
```

## Image layers
Every image is made up of one or more image layers. The base layer is often a flavor of Linux, like alpine.

When we built the image for python:3.7-alpine this image had the id b2c276538711. But that image depended on five other images which were visible while building it:
```
c9b1b535fdd9: Pull complete
2cc5ad85d9ab: Pull complete
53a2fca3c2ea: Pull complete
30fce49de8b1: Pull complete
49bcb9571cc7: Pull complete
```

This is called image layering and it exists for two main reasons. First, each image layer is immutable–unchanged–like a git commit. This helps ensure consistency when two developers build the same image. The second reason is performance. Docker caches the steps in a Dockerfile to speed up subsequent builds. When a change is made to a step, all steps following it will be executed from scratch.

## Dockerized Django
After creating a [Django App](401/class-26-django.md), create a `Dockerfile` for our image which will completely replace our local dev environment, so this will have Python 3 and Django. Then we’ll add a `docker-compose.yml` for the container instructions. Make each file via the command line.

```
$ touch Dockerfile
$ touch docker-compose.yml
```

This Dockerfile has several commands. RUN, COPY, and ADD each create a new layer.

```
# Dockerfile

# Python version
FROM python:3.7-alpine

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set work directory
WORKDIR /code

# Install dependencies
COPY Pipfile Pipfile.lock /code/
RUN pip install pipenv && pipenv install --system

# Copy project
COPY . /code/
```

Order matters in Dockerfiles since they are executed from top-to-bottom. First we use `FROM` to install `python:3.7-alpine` as our base image and set two environment variables with `ENV`. The first, `PYTHONDONTWRITEBYTECODE` will remove .pyc files from our container which is a good optimization. The second, `PYTHONUNBUFFERED` will buffer our output so it will look “normal” within Docker for us.

Then we used the `WORKDIR` command to create and set /code as our default directory within Docker. That means if in the future we want to run a command like `python manage.py runserver` we don’t have to also specify it should be run in the /code folder.

The Pipfile contains information on our software packages so we copy that over, too. (Technically we could use `COPY Pipfile .` and because of the `WORKDIR` setting it would still go in the `/code` folder!)

And then we install `Pipenv` itself via pip and then run `pipenv install` to install the software packages in our Pipfile. Note that we added the --system tag so that software packages are available throughout the entire container, not within a virtual environment which is Pipenv’s default but doesn’t make sense here since the entire Docker container is a virtual environment.


