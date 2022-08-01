# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
LABEL io.k8s.description="Child Container ONBUILD DEMO" \ 
      io.openshift.expose-services="8080:hhtp" \ 
      io.k8s.display-name="A Child Container" \
      io.openshift.tag="child, container build"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf 
RUN sed -i "s/#ServerName www.example.com:80/ServerName 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \ 
    chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001
	
EXPOSE 8080
