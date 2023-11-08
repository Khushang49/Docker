**Dokcer Volume**

If we want to use any storage to store as persistant. There are two types Bind mount and Volumes. 

Bind mount will use your host memry.

Volumes will be managed by docker.

Temp fs mount is only to use memory as temorary.

How to Check volumes

#docker volume ls

![image](https://github.com/Khushang49/Docker/assets/95266353/7f55a70b-d8e6-4451-b59c-a78381bb5c69)


How to chek wheteher Volume is used or not in image. Just inspect and check for volume block.

![image](https://github.com/Khushang49/Docker/assets/95266353/a116f3a5-13ec-42e4-bd96-af1b3a53fb5d)


Difference between Docker Volume and Bind Volume.

Docker Volume will be managed by Docker. Bind volume will be managed by end user as we are addind our directories to container.

**DOCKER VOLUME:**

To test this create container of mysql and create database in it. Whenever you create docker volume it is stored in **/var/lib/docker/volumes**.

#docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=123456 mysql

Now logn into container

#docker exec -it mysql bash

now create database.
![image](https://github.com/Khushang49/Docker/assets/95266353/dd5bb9e3-8d81-4095-a8d6-769ab1258869)

Now exit from container and check for volume. But if you create new container then it will not pick thos values. If you want to use same volume then you have to mention the volume while creating the container.

#docker run -d -v **volumeid:mentionthevolumepath** --name mysql2 mysql

