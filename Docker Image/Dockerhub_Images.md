We already have multiple Images on DokcerHub. If you want to use these images then we use pull or run. But for this require the docker account.

#docker login (use your credential)

After Login you will see multiple images. If you want specific version then mention version. To check images.

#docker search imagename

To pull specific versions

#docker pull ubuntu:latest (image:version)

Now push image to DockerHub but if you image will not have tag then add tag

#docker image tag image:tag image:newtag


Now push the image to dockerhub

#docker push imagename

Now Pull image from dockerhub

#docker pull imagename


To check hitsory of the image

#docker image history imagename

To remove image

#docker rmi imagename or docker image rm imagename (add -f to forefully delete)
