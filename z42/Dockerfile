FROM centos:latest
MAINTAINER Kane Blueriver <kxxoling@gmail.com>

RUN yum -y update
RUN yum -y install epel-release
RUN yum -y install hg
RUN yum -y install nginx
RUN yum -y install python-pip

RUN mkdir -p /www/
ADD requirements.txt /www/
RUN hg clone https://hg@bitbucket.org/z42/z42#angelcrunch /www/z42

WORKDIR /www/
RUN pip install -r requirements.txt

RUN yum clean all

EXPOSE 27017
ENTRYPOINT ["/bin/sh"]
