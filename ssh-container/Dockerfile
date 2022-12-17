FROM debian:latest

EXPOSE 22

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qq update
RUN apt-get -qq install openssh-server
RUN apt-get -qq install krb5-user
RUN apt-get -qq install vim 
RUN apt-get -qq clean
RUN mkdir -p /run/sshd
 
# configuration for the SSH server
COPY sshd_config /etc/ssh/sshd_config
# configuration for the SSH client
COPY ssh_config /etc/ssh/ssh_config 
 
RUN ssh-keygen -t dsa -f /etc/ssh/ssh_host_dsa_key -N ""

