# Docker Guide




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
     
     
# File Layers
    
  Images are read only when you want to write to a system you either bake the source code into an image or you put the source code into a container layer.  The container layer is blown away when you delete the container if you want the data/source you've created to stick around after you delete the container you will have to create a volume.
     
     #Data Volume
     They stick around when a container is deleted. When you write to a volume it writes to an alias that is mount to a mounted folder the volume. 
     
     # docker will magically make the mounted folder using the command below
     docker run  -p 80:3000 -v /var/www node
     # docker inspect will tell you where the file was created
     $docker inspect <containername>
     # The inspect command will return where the drive was mounted
     # "Type": "volume",
     #           "Name": "091b298f1c04405bfb8e622ad507b20b1b82aefd76bbbf72fa7531533e4bb331",
     #           "Source": #"/mnt/sda1/var/lib/docker/volumes/091b298f1c04405bfb8e622ad507b20b1b82aefd76bbbf72fa7531533e4bb331/_data",
                
     # if you don't like magic you can tell docker where to mount the folder. The example below mounts it to the current working directory
      docker run  -p 80:3000 -v $(pwd):/var/www node
      # now volume will use your current working directroy
      # "-v",
      #      "/Users/cesaraviles/Projects:/var/www"
      #To remove the volume
      docker rm <container> -v
      
      
     
#Source Code Management

    
