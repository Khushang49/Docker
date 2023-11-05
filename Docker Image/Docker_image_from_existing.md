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


Craete Image and send it to other 

If you want to share any image or convert to tar the use export

#docker export containername >imagename or docker export containername -o imagename

![image](https://github.com/Khushang49/Docker/assets/95266353/c0393690-d746-4641-b12a-d2f6d40de9a2)


After reciving this image you need to use then use IMPORT

#docker import foldername imagename or docker image import foldername imagename

![image](https://github.com/Khushang49/Docker/assets/95266353/40a82b89-574a-4431-ae4a-7957237e372f)

Same way you can use docker save and load. To convert into Tar file

#docker image save imagename >filename.tar

To load this image use 

#docker load image -i filename




