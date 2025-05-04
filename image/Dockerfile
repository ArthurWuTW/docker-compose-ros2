FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

ARG HOSTUSER
ARG HOSTUID
ARG HOSTGID

RUN groupadd -g ${HOSTGID} ${HOSTUSER}
RUN useradd ${HOSTUSER} -u ${HOSTUID} -g ${HOSTGID} -m
RUN echo "${HOSTUSER}:pass" | chpasswd

RUN apt-get update -y
RUN apt-get install -y iputils-ping init wget curl git sudo vim
RUN usermod -aG sudo ${HOSTUSER}
RUN echo "${HOSTUSER} ALL=(ALL)  ALL" >> /etc/sudoers


CMD ["/sbin/init"]
