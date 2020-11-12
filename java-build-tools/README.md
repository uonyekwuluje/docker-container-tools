# Docker Build Tools

## Build Image
Run the command below to build the image
```
docker build -t jdk15-mvn-image .
```

## List Image
List the images
```
docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED              SIZE
jdk15-mvn-image     latest              34f780d00ff6        About a minute ago   551MB
ubuntu              20.04               d70eaf7277ea        2 weeks ago          72.9MB
tomcat              8.0                 ef6a7c98d192        2 years ago          356MB
```

## Test Image
Create a container and test the image
```
docker run -ti jdk15-mvn-image bash

root@29960ad5f858:/# mvn --version
Apache Maven 3.6.3 (cecedd343002696d0abb50b32b541b8a6ba2883f)
Maven home: /opt/apache-maven
Java version: 15.0.1, vendor: Oracle Corporation, runtime: /opt/jdk-15
Default locale: en_US, platform encoding: ANSI_X3.4-1968
OS name: "linux", version: "5.4.0-52-generic", arch: "amd64", family: "unix"

root@29960ad5f858:/# java --version
java 15.0.1 2020-10-20
Java(TM) SE Runtime Environment (build 15.0.1+9-18)
Java HotSpot(TM) 64-Bit Server VM (build 15.0.1+9-18, mixed mode, sharing)
root@29960ad5f858:/# exit

exit
```
