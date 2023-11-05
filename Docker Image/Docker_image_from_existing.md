To Create Docker Image From Existing Container

Create Container

#docker run --name test1 -dit ubuntu

Then Go inside that container

#docker attach containername/id

Then create some files and delete some directories or files which was already present

#mkdir -p /tmp/test1 and #rm -rf /lib32

First check modification 

#docker diff contaniername

![image](https://github.com/Khushang49/Docker/assets/95266353/676c4cc2-0350-41c0-8200-808331b0cc94)


Now create image 

#docker commit containername newimagename

