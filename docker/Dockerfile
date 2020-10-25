# VERSION 0.1

FROM ubuntu:groovy

LABEL maintainer="kodiak@firesmith.org"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update -q && apt upgrade -y && apt install -y tzdata

RUN ln -fs /usr/share/zoneinfo/America/New_York /etc/localtime

RUN dpkg-reconfigure --frontend noninteractive tzdata

RUN apt install -y gunicorn graphite-api

EXPOSE 8000/tcp

CMD /usr/bin/gunicorn3 --name=graphite-api graphite_api.app:app
