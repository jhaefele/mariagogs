FROM centos:latest

ENV ADMIN_USER_CREATE true
ENV ADMIN_USER_NAME admin
ENV ADMIN_USER_EMAIL admin@mocyber.io
ENV ADMIN_USER_PASSWORD 5OBTe2j5NjjaIrDb
ENV GOGS_SECURITY__INSTALL_LOCK true
ENV GOGS_DATABASE__DB_TYPE mysql
ENV GOGS_RUN_USER gogs
ENV GOGS_RUN_MODE prod

RUN yum -y install --setopt=tsflags=nodocs git openssh && \ 
    yum -y update && yum clean all
RUN useradd gogs
RUN mkdir -p /opt/gogs-repositories/

VOLUME ["/opt/gogs-repositories/"]

EXPOSE 3000

ADD https://cdn.gogs.io/gogs_v0.9.13_linux_386.tar.gz /opt/
RUN mkdir -p /opt/gogs/custom/conf
ADD app.ini /opt/gogs/custom/conf/app.ini

USER gogs 
CMD ["/opt/gogs/gogs", "web"]
