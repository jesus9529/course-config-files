FROM ubuntu

LABEL creator="Jesus Hernandez​"
LABEL version="1.0.0"

RUN apt-get update

RUN apt-get install apache2 -y

RUN echo "<h1>Apache desde Docker</h1>" > /var/www/html/index.html

EXPOSE 80

ENTRYPOINT apache2ctl -D FOREGROUND