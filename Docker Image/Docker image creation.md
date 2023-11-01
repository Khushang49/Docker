 **Docker Images**

We require Docker Image to create container. There are three types to create Docker Image.
1. From Dockerhub or any repository
2. create from existing container
3. From Dockerfile

**From Dockerhub**
   
   Just pull any image or directly run container from Dockerhub.
   
   Command:
   
   #docker run ubuntu
   ![image](https://github.com/Khushang49/Docker/assets/95266353/3d9ab321-6005-4bd0-9e54-2d520c5b2a83)

**From Existing Container**

   Create new container and go inside that container using -it in command.

   #docker run -it          --name test1 ubnuntu /bin/bash
   
               |                 |       |         |

               interactive     name of   image    for shell
               terminal        container

![image](https://github.com/Khushang49/Docker/assets/95266353/e1d4c380-b25f-4efe-a368-738b2591109f)

   Now create file in that container.

   #cd /tmp
   
   #touch file1 file2 file3

   ![image](https://github.com/Khushang49/Docker/assets/95266353/fc5765d1-96db-48cd-a2e2-606c09a121dc)

   Then exit from container.

   Then check how many files added,appended,changed or deleted using docker diff command.

   #docker diff test1

            |     |

           find    container name
           differences
   ![image](https://github.com/Khushang49/Docker/assets/95266353/529cfd15-eb1a-40d3-a53c-668875c09e10)
   
   A == Append or Add
   
   C == Change
   
   D == Delete

   Now create image from this container using docker commit command

   #docker commit   test1      testimage

             |        |         |

             create   container  new image name
             new image
  ![image](https://github.com/Khushang49/Docker/assets/95266353/f4ddc0b3-4d96-448f-813f-2fee3fd18fe5)
   
   Now create container with new image
   
   #docker run -it --name test2 testimage /bin/bash
   ![image](https://github.com/Khushang49/Docker/assets/95266353/a33dfc70-5c61-4547-8466-240513953709)

 **From Dockerfile**

  For Dockerfile you need to create one file as Dockerfile. In this file you need to mention some parameteres. Then create image with docker build command. 
  Always use capital letter to mention parameter in Dockerfile

  Dockerfile parameters:
  
  | Dockerfile     | Instruction	Explanation      | 
  | ------------- | ------------- | 
  | FROM        | We use “FROM” to specify the base image we want to start from.|
  | RUN	       | RUN is used to run commands during the image build process.| 
  | ENV		    | Sets environment variables within the image, making them accessible both during the build process and while the container is running. If you only need to   define             build-time variables, you should utilize the ARG instruction. Example ENV HTTP_PROXY="http://<ip-address>:<port>"|
  | COPY		        | The COPY command is used to copy a file or folder from the host system into the docker image.|
  | EXPOSE		        | Used to specify the port you want the docker image to listen to at runtime.| 
  | ADD			        | An advanced form of COPY instruction. You can copy files from the host system into the docker image. You can also use it to copy files from a URL into a destination in      the       docker image. In fact, you can use it to copy a tarball from the host system and automatically have it extracted into a destination in the docker image.|
  | WORKDIR			        | It’s used to set the current working directory.|
  |VOLUME|	It is used to create or mount the volume to the Docker container.|
  |USER|	Sets the user name and UID when running the container. You can use this instruction to set a non-root user of the container.|
  |LABEL|	Specify metadata information of Docker image|
  |ARG|	Defines build-time variables using key-value pairs. However, these ARG variables will not be accessible when the container is running. To maintain a variable within a running container, use  ENV instruction instead.|
  |CMD|	Executes a command within a running container. Only one CMD instruction is allowed, and if multiple are present, only the last one takes effect.|
  |ENTRYPOINT|	Specifies the commands that will execute when the Docker container starts. If you don’t specify any ENTRYPOINT, it defaults to “/bin/sh -c”.|
  |ONBUILD| |
  |MAINTAINER| It is like Tag which we giving to understand|


  Example:
  
  Create Docker FILE:
   
   #vi Dockerfile
   
   FROM httpd:latest
   
   COPY ./index.html /usr/local/apache2/htdocs
  
   #docker build –t khushang .
  
   T= tag
  
   . == current directory
   
   RUN THAT CONTAINER
   
   Docker run –p –it 80:80 –name mywebsite khushang 

   ![image](https://github.com/Khushang49/Docker/assets/95266353/a1505380-c253-4174-9341-c3c3a21b7d38)


 
