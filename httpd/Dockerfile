#
# MAINTAINER        Carson,C.J.Zeong <zcy@nicescale.com>
# DOCKER-VERSION    1.6.2
#
# Dockerizing CentOS7: Dockerfile for building CentOS images
#
FROM       hub.c.163.com/public/centos:7.2.1511
MAINTAINER yangbk <www.361way.com>

ENV TZ "Asia/Shanghai"
ENV TERM xterm
ENV http_proxy 10.212.186.250:3128
#ENV https_proxy 10.212.186.250:3128

RUN rm -rf /etc/yum.repos.d/*
ADD base.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

RUN yum install -y httpd supervisor && \
    yum clean all

ADD httpd.ini /etc/supervisord.d/httpd.ini
ADD html.tar /var/www/html

EXPOSE 80

#CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"] 
#ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
CMD ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
