# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
	chmod -R g=u /var/log/httpd /var/run/httpd

LABEL io.openshift.expose-services="8080:http" \
	io.k8s.display-name="Apache HTTP Server" \
	io.openshift.tags="apache, httpd" \
	io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD"

USER 1001

EXPOSE 8080
