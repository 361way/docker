#
# MAINTAINER        yangbk <www.361way.com>
# DOCKER-VERSION    1.6.2
#
# Dockerizing Mariadb: Dockerfile for building Mariadb images
#
FROM       hub.c.163.com/public/centos:7.2.1511
MAINTAINER yangbk <www.361way.com>

ENV DATA_DIR /var/lib/mysql
ENV http_proxy 10.212.186.250:3128

# Install Mariadb
RUN yum install -y mariadb mariadb-server && \
    yum clean all

ADD mysqld_charset.cnf /etc/my.cnf.d/

COPY scripts /scripts
RUN chmod +x /scripts/start

EXPOSE 3306

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/start"]
