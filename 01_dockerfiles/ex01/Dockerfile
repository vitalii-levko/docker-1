FROM debian

ENV DEBIAN_FRONTEND=noninteractive
ENV TS3SERVER_LICENSE=accept

EXPOSE 9987:9987/udp
EXPOSE 10011:10011
EXPOSE 30033:30033
EXPOSE 41144:41144

RUN apt-get update -y
RUN apt-get install apt-utils -y
RUN apt-get install wget -y
RUN apt-get install bzip2 -y
RUN wget -P /root http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar -xf /root/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 -C /root
RUN rm -f /root/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2

WORKDIR /root/teamspeak3-server_linux_amd64

CMD ["bash", "ts3server_minimal_runscript.sh", "&"]

ENV DEBIAN_FRONTEND=teletype
# docker run -ti --rm -p 9987:9987/udp -p 30033:30033 -p 10011:10011 <image>
