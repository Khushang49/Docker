In Docker file method you will create image from Scratch and will use some parameteres. Whenever you add parameter it will create Layer in that image.

**IN DOCKERFILE NEVER MENTION CHANGES AT START ALWAYS MENTION AT LAST.**

Mentioning all parameters.

 | Dockerfile     | Instruction	Explanation      | 
  | ------------- | ------------- | 
  | FROM        | We use “FROM” to specify the base image we want to start from.|
  | RUN	       | RUN is used to run commands during the image build process.| 
  | ENV		    | Sets environment variables within the image, making them accessible both during the build process and while the container is running. If you only need to   define             build-time variables, you should utilize the ARG instruction. Example ENV HTTP_PROXY="http://ip-address:port"|
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

  Create Dockerfile

  #vi Dockerfile

  Now mention the above parameters. Always mention FROm at start as we have to mention the images or base os.

  **"From" Prameter**
  
  FROM ubuntu
  
  ![image](https://github.com/Khushang49/Docker/assets/95266353/602fce65-01f0-4cdb-bcf7-bba0e495ea30)

  If we want to install any software while creation of Image.Here we have installed Git software.

  **"Run" Parameter**

  FROM ubuntu
  
  RUN apt-get update && apt install git -y

 ![image](https://github.com/Khushang49/Docker/assets/95266353/913e7f0d-2729-49c8-ae47-98cdb8ea80d9)

  Now just create Container and check whether GIT is there or not. You can use multiple RUN command in single Dockerfile.

  **"LABEL" Parameter**

  It is just type of tag which we provide to image. Just mention LABEL and any details.

  FROM ubuntu
  
  LABEL name=Khushang
  
  RUN apt-get update && apt install git -y

  ![image](https://github.com/Khushang49/Docker/assets/95266353/003a4af3-ecf9-412b-b634-cc433218c2b9)

  How to Check Labels used in Dockerfile.

  #docker inspect imagename/id

  ![image](https://github.com/Khushang49/Docker/assets/95266353/338df667-85d4-4fca-b189-6f4657cc1338)


  **"ENV" parameter**

  This is to pass any enviroment inside the container such as Proxy variable or any variable.
  
  FROM ubuntu
  
  LABEL name=Khushang
  
  RUN apt-get update && apt install git -y

  ENV NAME=KHUSHANG

  ENV http_proxy=http://10.10.10.10:80 
  
  ![image](https://github.com/Khushang49/Docker/assets/95266353/306282b1-2738-43b2-9670-2fbfc9c754b6)


  For Checking create new container and do env

  ![image](https://github.com/Khushang49/Docker/assets/95266353/b57058b8-151d-4237-8e1b-918837c92e96)


  


  

  

