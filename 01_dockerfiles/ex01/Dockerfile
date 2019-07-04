FROM debian

EXPOSE 9987/udp 10011 30033
RUN  apt-get update &&  apt-get -y upgrade && apt -y install curl bzip2
RUN adduser --disabled-login teamspeak
RUN su teamspeak && cd /home/teamspeak && curl -O https://files.teamspeak-services.com/releases/server/3.9.0/teamspeak3-server_linux_amd64-3.9.0.tar.bz2 && tar -xjf teamspeak3-server_linux_amd64-3.9.0.tar.bz2; rm teamspeak3-server_linux_amd64-3.9.0.tar.bz2; apt-get -y remove curl bzip2; chown -R teamspeak:teamspeak .
ENV TS3SERVER_LICENSE='accept'
WORKDIR /home/teamspeak/teamspeak3-server_linux_amd64/
ENTRYPOINT su teamspeak && sh ts3server_minimal_runscript.sh