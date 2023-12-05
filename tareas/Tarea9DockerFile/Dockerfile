FROM ubuntu:22.04

ENV TERM linux
ENV DEBIAN_FRONTEND noninteractive

#COPY ./index.html /usr/share/apache2/htdocs

RUN apt-get update
RUN apt-get install -y emacs iproute2 dnsutils iputils-ping

CMD ["/bin/bash"]