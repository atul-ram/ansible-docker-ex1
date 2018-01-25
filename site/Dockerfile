FROM centos:7

CMD rm -rf /etc/yum.repos.d/*.repo
ADD CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo

RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs install httpd && \
    yum clean all

EXPOSE 80

# Simple startup script to avoid some issues observed with container restart
ADD run-httpd.sh /run-httpd.sh
RUN chmod -v +x /run-httpd.sh

CMD ["/run-httpd.sh"]

