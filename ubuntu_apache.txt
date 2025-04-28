FROM ubuntu:latest

RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean


EXPOSE 80


ENTRYPOINT ["apachectl", "-D", "FOREGROUND"]

