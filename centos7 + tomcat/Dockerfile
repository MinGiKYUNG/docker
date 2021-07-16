FROM centos:7
LABEL maintainer=<mingi.kyung@gmail.com>

# openjdk1.8. 설치
RUN mkdir -p /apps && mkdir -p /bin && mkdir -p /src

WORKDIR /apps
RUN yum update -y
RUN yum install wget -y
RUN yum list java-1.8.0-openjdk-devel.x86_64
RUN yum install java-1.8.0-openjdk-devel.x86_64 -y
#RUN which javac
#RUN readlink -f /usr/bin/java

ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64
RUN java -version
RUN cd /apps
RUN echo "java install complete"

# Tomcat 설치
RUN wget http://mirror.apache-kr.org/tomcat/tomcat-8/v8.5.69/bin/apache-tomcat-8.5.69.tar.gz
RUN tar -xvf apache-tomcat-8.5.69.tar.gz
RUN mv apache-tomcat-8.5.69 /apps/tomcat
ENV CATALINA_HOME=/apps/tomcat
ENV CATALINA_BASE=/apps/tomcat
ENV JRE_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64
RUN echo "tomcat install complete"


EXPOSE 8080
# WORKDIR /app/tomcat/bin
CMD ["/apps/tomcat/bin/catalina.sh", "run"]