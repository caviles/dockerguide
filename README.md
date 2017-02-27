# Docker Guide

# File Layers


Things you need to know to get started with docker:

There are many open source community shared images online:
[Docker Images] (https://hub.docker.com/)

Use the search control on docker hub to find an image. For example if you search Hello World. You will find a results page which contains hello world hits. [Hello World Image] (https://hub.docker.com/_/hello-world/)

On left hand side you'll notice a div titled Docker Pull Command. You can use that command to pull down the hello world image.




A few common commands

     # to use terminal window other than quick start terminal use
     
     $ docker-machine env default
     $ docker ps
     
     # show running docker VMs
     
     $ docker-machine ls 
     
     # show running docker VM IPs
     
     $ docker-machine ip 
     
     # show running docker IP for default docker VM
     
     $ docker-machine ip default 
     
     # show running docker VMs status
     
     $ docker-machine status 
     
     # start a docker VM
     
     $ docker-machine start
     
     # stop a docker VM
     
     $ docker-machine stop
    
     # Docker pull command - grab an image from docker hub
     
     $ docker pull hello-world
     
     # show all installed images
     
     $ docker images
     
     # create a container
     $ docker run <image name> 
     example: $ docker run hello-world
     (notice 80:80 in the command below this tells nginx listen on 80:80 and forward traffic to 80)
     example run on specific port docker run -p 80:80 kitematic/hello-world-nginx:latest
     
     # show all containers - this will also give you the container IDs needed to remove the container
     $ docker ps -a
     
     #delete container
     docker rm <container id from command above>
    
     #delete container
     $ docker rmi hello-world
     #
     
    
     
     
     
    
