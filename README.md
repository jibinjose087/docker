# docker

What is Docker?

Docker is a software container platform.

Developers use Docker to eliminate “works on my machine” problems when collaborating on code with co-workers.
Operators use Docker to run and manage apps side-by-side in isolated containers to get better compute density.
Enterprises use Docker to build agile software delivery pipelines to ship new features faster, more securely and with confidence for both Linux and Windows Server apps

Images

A docker images is the "cooking recipe" for a container. It contains all the definitions how to boot up the linux environment. Typically one Docker image is there to fulfill specifically one task. For instance one image would define your webserver and another image would define the underlying database.

Containers

Containers are the instantiations of images. They are one form of the image. Compare it to object oriented programming, then your class would be an image and instance of the class a container. Another comparison would be to real containers on ship.

containers are not persistent. As soon as you don't use them anymore they get stoped (or even deleted)
a container only lives for the time a process runs inside it which does not get killed (of course you could run processess which never send an exit command)

containers can include data however it's also not persistent. If you want to make it persistent, you can use volumes.
to communicate between containers, use the same protocolls as you would use to communicate between computers (e.g. tcp/ip)

Volumes

Volumes can be used as underlying data layer. They can be used between as many containers as you want. All data stored in here could be used by all containers connected to it.

Networks

Docker comes with its own networking capabilities. The name of a container is its hostname. The easiest way to try this is to have two containers running and ping one container from inside the other container. Docker Compose will raise its own subnet.

# Basic Docker commands:

 docker run <image>
  
 docker start/stop <name/id>

 docker ps [-a to list all the runnin containers including stopped]

 docker rm <name/id>

 docker build -t image-name - to build a docker image

 docker run -it image-name bash - to start a docker image

 docker exec -it <container name> /bin/bash - to login to running container
 
The CMD keyword is for what will run as soon as you start up the container (could be any .sh script of course to make it more elaborated)

The RUN keyword is if you want to install anything inside your container

http://takacsmark.com/getting-started-with-docker-in-your-project-step-by-step-tutorial/
