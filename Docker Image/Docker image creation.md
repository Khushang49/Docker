**Docker Images**

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

 From Dockerfile

  For Dockerfile you need to create one file as Dockerfile. In this file you need to mention some parameteres. Then create image with docker build command. 
  Always use capital letter to mention parameter in Dockerfile

  Dockerfile parameters:
  
  FROM == Image name or any refernce. It will be at start only.
  
  LABEL
  
  RUN == To run any command, To create a layer in Image
  
  CMD == Execute command while creation of Container.
  
  EXPOSE == Tp expose any port as per application or as per software requiremnt.
  
  ENV == To set any variable.
  
  ADD or COPY == To copy any files from server. In COPY you can copy any file from Server whereas ADD will also have same feature but it will also can download 
                 from internet as well as it can extract TAR file from source machine. Beacuse sometime packages are zip files hence ADD will be useful.
  
  ENTRYPOINT == If you want to prioratize any command then you mention in Entrypoint it is same as CMD. But it has more priority.
  
  VOLUME
  
  USER
  
  WORKDIR == Where you want to work or whenever you run container then which directory is required.
  
  ONBUILD

  MAINTAINER == Only to reference who is managing image as TAG.

  ARG == Argument.

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


 
