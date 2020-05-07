.. docker documentation master file, created by
   sphinx-quickstart on Thu May  7 19:14:32 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to docker's documentation!
==================================

Here I have made a documentation for docker image/container for **esajpip** server under **Summer of Code in Space program 2019**

Check my container at https://hub.docker.com/r/dhiraj240/dockeresa

**Points to ponder while developing docker image:**

1. To reduce container size use
	``FROM alpine``
	``Inside Dockerfile``

2. To optimize the Dockerfile structure use the process of building a script first like below
	Inside script.sh use
		``#! /bin/sh``
		``<follow up the script development>``

- You can check my script.sh at https://github.com/Dhiraj240/dockeresa/blob/master/script.sh

- Don't forget to make the script executable using
		``chmod +x script.sh``

3. Then use below boilerplate in Dockerfile
	``COPY script.sh /script.sh``
	``CMD  ["/script.sh"]``

- Then do below thing inside your Dockerfile directory
	``docker build .``

4. There may be the case you face Docker Daemon error while executing ``docker build .``

- Don't worrry use below command
	``sudo chmod 666 /var/run/docker.sock``

5. Put your container on Docker Hub for that use below process
	- First signup on Docker Hub and create repository name.
	- Use ``docker login``
	- Then use docker images
		It will list the docker image name and image id which you need to copy.
	- Now use ``docker tag <image id> <username>/<reponame>:<tag>``
		Here tag could be like 01, 1.0 etc.
	- Finally do ``docker push <username>/<reponame>``
