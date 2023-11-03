
If you are using any application on Docker but you want to use it to exteral users then you need to map the port to external users.

#docker run -p 80:80 -dit --name test1 httpd /bin/bash (for port host:container) (-p is for port)

To go inside running container

#docker exec -it contanername /bin/bash

To change name of contaner at running

#docker rename containername/id newname

To restart container 

#docker restart contanername/id

To go inside container

#docker attach containername/id

Difference between exec and attach
When a container is started using /bin/bash then it becomes the containers PID 1 and docker attach is used to get inside PID 1 of a container. So docker attach < container-id > will take you inside the bash terminal as it's PID 1 as we mentioned while starting the container. Exiting out from the container will stop the container.

Whereas in docker exec command you can specify which shell you want to enter into. It will not take you to PID 1 of the container. It will create a new process for bash. docker exec -it < container-id > bash. Exiting out from the container will not stop the container.

**Note**: If you have started your container with -d flag then exiting out of container will not stop the container,whether you use attach or exec to get inside.

To kill any container

#docker kill containername/id

To Wait any container. In this container will wait until any one will stop or got failed.

#docker wait containername/id

To Pause the container. To pause the processes in container

#docker pause containername/id
