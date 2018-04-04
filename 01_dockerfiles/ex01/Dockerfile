FROM debian:wheezy

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install wget -y
RUN apt-get install tar -y
RUN apt-get install bzip2 -y
RUN apt-get install ca-certificates -y
EXPOSE 9987/udp
EXPOSE 30033
EXPOSE 10011
EXPOSE 41144
ENV TS3SERVER_LICENSE=accept
RUN useradd teamspeak
WORKDIR /home/teamspeak3
RUN wget http://teamspeak.gameserver.gamed.de/ts3/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN tar -xvjf teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN rm -rf teamspeak3-server_linux_amd64-3.1.1.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
COPY ts3server.ini /home/teamspeak3/teamspeak3-server_linux-amd64/ts3server.ini
USER teamspeak
ENTRYPOINT ["/bin/sh", "ts3server_minimal_runscript.sh", "inifile=ts3server.ini"]
