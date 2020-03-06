# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: kpesonen <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/03/06 12:32:44 by kpesonen          #+#    #+#              #
#    Updated: 2020/03/06 16:49:54 by kpesonen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

#From a debian image you will add the appropriate sources to create a TeamSpeak
#server, that will launch along with your container. It will be deemed valid if at least
#one user can connect to it and engage in a normal discussion (no far-fetched setup), so
#be sure to create your Dockerfile with the right options. Your program should get the
#sources when it builds, they cannot be in your repository

FROM debian

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y wget bzip2 && \
	adduser --disabled-login --gecos "" teamspeak && \
	wget https://files.teamspeak-services.com/releases/server/3.11.0/teamspeak3-server_linux_amd64-3.11.0.tar.bz2 && \
	tar -xvf teamspeak3-server_linux_amd64-3.11.0.tar.bz2 && \
	mv teamspeak3-server_linux_amd64 teamspeak && \
	chown -R teamspeak:teamspeak /teamspeak && \
	touch /teamspeak/.ts3server_license_accepted

EXPOSE 9987/udp 10011 30033
	
WORKDIR teamspeak

ENTRYPOINT sh ts3server_minimal_runscript.sh 

#https://www.rosehosting.com/blog/how-to-set-up-a-teamspeak-server-on-ubuntu-16-04/
#https://hub.docker.com/_/teamspeak
#docker build . -t ex01
#docker image ls
#docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01

#By default only works locally, to allow other people to join:
#docker-machine stop Char
#Virtualbox settings:network>adapter 3>enable>bridged>en0 ethernet>advanced>type: intel desktop>ok
#docker-machine start Char
#docker-machine regenerate-certs Char
#Copy external ip from Char: docker-machine ssh Char > ip a> copy inet addr from eth2 > exit
#run the container
#connect with new ip and token
#others can now join with this new ip
