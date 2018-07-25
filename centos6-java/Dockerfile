FROM centos:6

MAINTAINER aiisen <admin@aiisen.com>

ENV JAVA_VERSION_MAJOR=8 \
    JAVA_VERSION_MINOR=144 

RUN yum update -y && \
yum install -y gcc automake vim initscripts libtool make gcc-c++ wget curl && \
wget https://mirror.its.sfu.ca/mirror/CentOS-Third-Party/NSG/common/x86_64/jdk-8u144-linux-x64.rpm && \
yum localinstall -y jdk-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-x64.rpm && \
rm -f jdk-${JAVA_VERSION_MAJOR}u${JAVA_VERSION_MINOR}-linux-x64.rpm && \
rm -rf /var/cache/yum

# Set environment variables.
ENV HOME /root
ENV JAVA_HOME /usr/java/default
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["/bin/bash"]

#docker build -t centos6-java:8 .

