**"USER" Parameter**

We use USER parameter if you want to run any command as user. If we login then it will login via that user.

Example:

FROM ubuntu

LABEL name=testdockerfile

ENV NAME=Khushang

RUN apt-get update && apt install nginx -y

RUN useradd -d /home/$NAME -p admin@1234567 $NAME

RUN whoami>/tmp/test1.txt

WORKDIR /tmp

USER $NAME

RUN whoami>/tmp/test2.txt

![image](https://github.com/Khushang49/Docker/assets/95266353/1a79e2da-ce1d-4af8-82be-bf2c8ebf8489)

Now Run container and check whether files where created or not.

![image](https://github.com/Khushang49/Docker/assets/95266353/eaf4db2d-4871-4e35-9f44-717fe212acdb)

**"COPY" Parameter**

If you want to copy any file from you host machine to your Container then we will use COPY parameter.

COPY HOSTFILE DOCKERFILEPATH

Example:

FROM ubuntu

LABEL name=testdockerfile

ENV NAME=Khushang

RUN apt-get update && apt install nginx -y

RUN useradd -d /home/$NAME -p admin@1234567 $NAME

RUN whoami>/tmp/test1.txt

WORKDIR /tmp

USER $NAME

RUN whoami>/tmp/test2.txt

RUN mkdir -p /tmp/test

COPY Dockerfile /tmp/test

![image](https://github.com/Khushang49/Docker/assets/95266353/22ca1a65-c4af-4314-b564-57ab2c1557a4)

Now create Container and test whether file is copied or not.

![image](https://github.com/Khushang49/Docker/assets/95266353/1e896f43-3105-4dca-a007-62bc20c05f1b)


