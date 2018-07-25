#From centos:version
FROM centos:6
MAINTAINER wuyang wuyang@aiisen.com

ENV JAVA_VERSION=jdk-8u144-linux-x64.rpm 

WORKDIR /app/

COPY ${JAVA_VERSION} /app/

#RUN yum update -y && \
RUN yum install -y gcc vim initscripts libtool make gcc-c++ wget curl && \
rpm -ivh /app/${JAVA_VERSION} && \
rm -f /app/${JAVA_VERSION} && \
rm -rf /var/cache/yum

# Set environment variables.
ENV JAVA_HOME /usr/java/default
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

CMD ["/bin/bash"]

#sudo docker build -t java:8 .