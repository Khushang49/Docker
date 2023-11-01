                                                                                       Docker basics

To check Modules in Docker

#docker --help

Below are main modules

Management Commands:
 
  builder     Manage builds
 
  buildx*     Docker Buildx (Docker Inc., v0.10.5)
  
  compose*    Docker Compose (Docker Inc., v2.18.1)
  
  container   Manage containers
  
  context     Manage contexts
  
  image       Manage images
  
  manifest    Manage Docker image manifests and manifest lists
  
  network     Manage networks
  
  plugin      Manage plugins
  
  system      Manage Docker
  
  trust       Manage trust on Docker images
 
  volume      Manage volumes


 Below are child Commands
  
| Commands     | Explaination|
| ------------- | ------------- | 
| attach |    Attach local standard input, output, and error streams to a running container|
|  commit  |    Create a new image from a container's changes|  
|cp  |        Copy files/folders between a container and the local filesystem|
|create|      Create a new container|
|diff   |     Inspect changes to files or directories on a container's filesystem| 
|events |     Get real time events from the server| 
|export   |   Export a container's filesystem as a tar archive|
| history   |  Show the history of an image|
| import    |  Import the contents from a tarball to create a filesystem image|  
|inspect  |   Return low-level information on Docker objects| 
|kill   |     Kill one or more running containers|
  
  load        Load an image from a tar archive or STDIN
  
  logs        Fetch the logs of a container
  
  pause       Pause all processes within one or more containers
  
  port        List port mappings or a specific mapping for the container
  
  rename      Rename a container
  
  restart     Restart one or more containers
  
  rm          Remove one or more containers
  
  rmi         Remove one or more images
  
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  
  start       Start one or more stopped containers
  
  stats       Display a live stream of container(s) resource usage statistics
  
  stop        Stop one or more running containers
  
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  
  top         Display the running processes of a container
  
  unpause     Unpause all processes within one or more containers
  
  update      Update configuration of one or more containers
  
  wait        Block until one or more containers stop, then print their exit codes

TO List all Images in Docker

#docker images

To delete images in Docker

#docker rmi imagename

To delete all images

#docker rmi $(docker images -q)

To Run a container

#docker run ubuntu(iamge name)

To check running container

#docker ps

To check all running container

#docker ps -a

To remove container

#docker rm container name

To remove all container

#docker rm $(docker ps --filter status=exited -q)


