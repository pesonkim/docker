# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: kpesonen <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/03/07 23:13:42 by kpesonen          #+#    #+#              #
#    Updated: 2020/03/08 00:37:09 by kpesonen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM debian

RUN apt-get update && \
	apt-get install -y apt-transport-https ca-certificates curl gnupg2 software-properties-common

RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
	add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian buster stable"

RUN apt-get update && \
	apt-get install -y docker-ce

COPY ./docker /docker/

#cp -r ./../../ ~/temp/ && mv ~/temp $PWD/docker && rm -rf ./docker/.git
#docker build -t dind .
#docker run -it --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock dind
