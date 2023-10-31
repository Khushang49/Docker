Docker Images

We require Docker Image to create container. There are three types to create Docker Image.
1. From Dockerhub or any repository
2. create from existing container
3. From Dockerfile

From Dockerhub
   Just pull any image or directly run container from Dockerhub.
   
   Command:
   
   #docker run ubuntu
   ![image](https://github.com/Khushang49/Docker/assets/95266353/3d9ab321-6005-4bd0-9e54-2d520c5b2a83)

From Existing Container

   Create new container and go inside that container using -it in command.

   #docker run -it          --name test1 ubnuntu /bin/bash
   
               |                 |       |         |

               interactive     name of   image    for shell
               terminal        container

![image](https://github.com/Khushang49/Docker/assets/95266353/e1d4c380-b25f-4efe-a368-738b2591109f)
