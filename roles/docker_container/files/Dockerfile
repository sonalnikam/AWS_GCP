FROM ubuntu:18.04

# Install dependencies
RUN apt-get update && \
 apt-get -y install apache2

# Install apache and write hello world message
RUN echo '<!DOCTYPE html> \
<html> \
   <head> \
      <title>HTML Meta Tag</title> \
      <meta http-equiv = "refresh" content = "1; url = https://xebialabs.com/periodic-table-of-devops-tools/" />\
   </head> \
   <body> \
      <p>Redirecting to another URL</p> \
   </body> \
</html>' > /var/www/html/index.html
# Configure apache
RUN echo '. /etc/apache2/envvars' > /root/run_apache.sh && \
 echo 'mkdir -p /var/run/apache2' >> /root/run_apache.sh && \
 echo 'mkdir -p /var/lock/apache2' >> /root/run_apache.sh && \ 
 echo '/usr/sbin/apache2 -D FOREGROUND' >> /root/run_apache.sh && \ 
 chmod 755 /root/run_apache.sh

EXPOSE 80

CMD /root/run_apache.sh

