FROM ubuntu:20.04
MAINTAINER MinGi KYUNG <mgkyung@wiseinfotech.co.kr>

# avoiding user interaction with tzdata
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y apache2 # Install Apache web server (Only 'yes')
RUN apt-get install -y software-properties-common
RUN apt-get install -y php
RUN apt-get update

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"] # D represenets Deamon