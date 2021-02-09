docker-machine ls								#List your machines

docker-machine rm my-docker-machine				#remove each machine

docker build -t friendlyname .  				# Create image using this directory's Dockerfile

docker run -p 4000:80 friendlyname  			# Run "friendlyname" mapping port 4000 to 80

docker run -d -p 4000:80 friendlyname         	# Same thing, but in detached mode

docker run -it <image> /bin/bash				# run in interactive mode

docker run -d -P --name web -v /webapp training/webapp python app.py	# create a new volume inside a container at /webapp (in linux)

docker run -d -P --name web -v /src/webapp:/webapp training/webapp python app.py	# mount a directory from your Docker engine’s host into a container.

docker ps                      	# See a list of all running containers

docker stop <hash>             	# Gracefully stop the specified container

docker ps -a           			# See a list of all containers, even the ones not running

docker kill <hash>              # Force shutdown of the specified container

docker rm <hash>              	# Remove the specified container from this machine

docker rm $(docker ps -a -q)    # Remove all containers from this machine

docker images -a                # Show all images on this machine

docker rmi <imagename>          # Remove the specified image from this machine

docker rmi $(docker images -q)  # Remove all images from this machine

docker login            		# Log in this CLI session using your Docker credentials

docker tag <image> username/repository:tag  # Tag <image> for upload to registry.

docker push username/repository:tag         # Upload tagged image to registry

docker run username/repository:tag          # Run image from a registry

docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG] # to add a tag to a docker image. Tags typically will include the version of the code and the base operating system used for the image. For example the official Node.js Docker images are tagged using node:{Node_Version}-{Operating_System}.


####################containers as services################################


docker stack ls              			# List all running applications on this Docker host

docker stack deploy -c <composefile> <appname>  # Run the specified Compose file

docker stack services <appname>       	# List the services associated with an app

docker stack ps <appname>   			# List the running containers associated with an app

docker stack rm <appname>               # Tear down an application

#####################mounting volumes to containers###########################

docker inspect web								# locate the volume on the host by utilizing the docker inspect command

docker run -v c:\<path>:c:\<container path>		# On Windows, mount directories using (does not work, need to do the volume mount manually)	

docker volume ls								#	list

	
