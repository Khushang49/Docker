                                                                                       Docker basics

To check Modules in Docker

#docker --help

TO List all Images in Docker

#docker images

To delete images in Docker

#docker rmi imagename

To delete all images

#docker rmi $(docker images -q)

To Run a container

#docker run ubuntu(iamge name)

To run container in background

#docker run -d(detach) ubuntu

To run container and go inside that Container

#docker run -it(interactive terminal) ubuntu /bin/bash (shell)

How to exit container without stopping the container. Inside container use

#ctrl+p+q

To check running container

#docker ps

To check all running container

#docker ps -a

To remove container

#docker rm container name

To remove all container

#docker rm $(docker ps --filter status=exited -q) or docker rm $(docker ps -aq) a== all q == quite

To Stop Container

#docker stop containername or ID

To Start Container

#docker start containername or ID

How to check any details related to container 
#docker inspect containername

How to check Logs of Container

#docker logs containername or id

How to check process by Container

#docker top contaner name or ID

To check memory CPU of container

#docker stats

