FROM centos:latest
MAINTAINER Kane Blueriver <kxxoling@gmail.com>

RUN yum -y update
RUN yum -y install epel-release
RUN yum -y install hg
RUN yum -y install git
RUN yum -y install vim
RUN yum -y install python-pip

RUN mkdir -p /root/tmp/
RUN yum -y install zsh
ADD install.sh /root/tmp/
RUN chmod +x /root/tmp/install.sh
RUN ./root/tmp/install.sh

ADD spf13-vim3 /root/tmp/
RUN chmod +x /root/tmp/spf13-vim3
RUN ./root/tmp/spf13-vim3

RUN rm -r /root/tmp
RUN yum install -y nodejs npm --enablerepo=epel
RUN npm install cnpm
RUN npm install -g grunt-cli

RUN yum install -y gcc
RUN yum install -y tmux
RUN yum install -y ruby ruby-devel rubygems --enablerepo=epel
RUN yum install -y make
RUN gem sources --remove https://rubygems.org/
RUN gem sources -a https://ruby.taobao.org/
RUN gem install compass

RUN mkdir -p /code/

WORKDIR /code/

RUN yum clean all

EXPOSE 35729
ENTRYPOINT ["/bin/sh"]
