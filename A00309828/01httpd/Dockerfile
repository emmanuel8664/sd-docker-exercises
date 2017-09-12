FROM ubuntu:16.04

RUN apt update -y && apt install -y apache2
EXPOSE 80

CMD service apache2 start && tail -f /var/log/apache2/access.log 
