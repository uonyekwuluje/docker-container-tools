FROM ubuntu:20.04

MAINTAINER Augustine Ike <augustineike@gmail.com>

ENV MAVEN_VERSION=3.6.3

RUN apt update && \
    apt install -y curl jq git openssl unzip wget && \
    cd /tmp && \
    mkdir /opt/apache-maven && \
    wget https://www-us.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz && \
    tar -zxvf apache-maven-${MAVEN_VERSION}-bin.tar.gz -C /opt/apache-maven --strip-components=1 && \
    rm /tmp/apache-maven-${MAVEN_VERSION}-bin.tar.gz && \
    mkdir /opt/jdk-15 && \
    wget --no-check-certificate -c --header "Cookie: oraclelicense=accept-securebackup-cookie" https://download.oracle.com/otn-pub/java/jdk/15.0.1+9/51f4f36ad4ef43e39d0dfdbaf6549e32/jdk-15.0.1_linux-x64_bin.tar.gz && \
    tar -zxvf jdk-15.0.1_linux-x64_bin.tar.gz  -C /opt/jdk-15 --strip-components=1 && \
    rm jdk-15.0.1_linux-x64_bin.tar.gz && \
    rm -rf /tmp/* 

ENV JAVA_HOME=/opt/jdk-15
ENV MAVEN_HOME=/opt/apache-maven
ENV PATH $PATH:$JAVA_HOME/bin:$PATH
ENV PATH $PATH:$MAVEN_HOME/bin:$PATH


CMD [""]
