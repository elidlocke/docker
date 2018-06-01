FROM debian

MAINTAINER elizabeth

ARG TEAMSPEAK_URL=http://dl.4players.de/ts/releases/3.2.0/teamspeak3-server_linux_amd64-3.2.0.tar.bz2
EXPOSE 9987/udp 10011 30033

RUN apt-get -y update
RUN apt-get -y install curl
RUN apt-get -y install bzip2

RUN curl "${TEAMSPEAK_URL}" >> server.tar.bz2
RUN tar -xvjf server.tar.bz2

WORKDIR teamspeak3-server_linux_amd64
CMD ["sh", "ts3server_minimal_runscript.sh"]
