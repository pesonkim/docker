# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: kpesonen <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/03/07 21:50:17 by kpesonen          #+#    #+#              #
#    Updated: 2020/03/08 00:26:04 by kpesonen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM debian

RUN apt-get update && apt-get install -y git cmake build-essential libncurses5 libncurses5-dev

RUN git clone https://github.com/mogria/msnake.git && \
	cd msnake && \
	mkdir build && \
	cd build && \
	cmake .. && \
	make && \
	make install

WORKDIR /usr/local/bin/

#docker build -t snake .
#docker run -it --rm snake
#./msnake
