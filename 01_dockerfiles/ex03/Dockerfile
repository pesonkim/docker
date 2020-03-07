# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: kpesonen <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/03/07 12:41:35 by kpesonen          #+#    #+#              #
#    Updated: 2020/03/07 19:05:25 by kpesonen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM debian

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y curl openssh-server ca-certificates postfix

RUN	curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash

RUN apt-get install gitlab-ce

EXPOSE 443 80 22

ENTRYPOINT service ssh start && (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && gitlab-ctl tail

#https://about.gitlab.com/install/#debian?version=ce

#/opt/gitlab/embedded/bin/runsvdir-start &
#gitlab-ctl reconfigure

#docker build -t ex03 .

#docker run -it -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03

#http://192.168.99.100:8080
