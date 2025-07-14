FROM ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive

ENV WORK_DIR /home

# Atualizando o servidor
RUN apt-get update && apt-get -y upgrade --fix-missing && apt-get -y -f install && apt-get -y auto-remove && apt-get -y autoclean && apt-get -y clean

# Instalando os pacotes
RUN apt-get install -y apache2 curl git npm

RUN if [ ! -d "$WORK_DIR"]; then mkdir $WORK_DIR; fi
WORKDIR $WORK_DIR

EXPOSE 80
CMD /usr/sbin/apache2ctl -D FOREGROUND
