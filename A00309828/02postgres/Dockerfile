FROM ubuntu:16.04
MAINTAINER tebannew@gmail.com

#Install package
RUN apt-get update -y
RUN apt-get install postgresql -y
RUN apt-get install vim -y


#Configuracion del puerto de postgres
EXPOSE 5432
EXPOSE 5000

# Adjust PostgreSQL configuration so that remote connections to the
# database are possible.
RUN echo "host all  all    0.0.0.0/0  md5" >> /etc/postgresql/9.5/main/pg_hba.conf

# And add `listen_addresses` to `/etc/postgresql/9.5/main/postgresql.conf`
RUN echo "listen_addresses='*'" >> /etc/postgresql/9.5/main/postgresql.conf
#RUN echo "port=5000" >> /etc/postgresql/9.5/main/postgresql.conf
RUN sed -i '/port = 5432/c\port = 5000' /etc/postgresql/9.5/main/postgresql.conf








# Expose the PostgreSQL port
#EXPOSE 5000
#EXPOSE 5000


CMD postgresql -m http.server 5432
CMD postgresql -m http.server 5000
