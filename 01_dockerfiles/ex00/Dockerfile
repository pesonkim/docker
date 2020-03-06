# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: kpesonen <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/03/06 12:26:27 by kpesonen          #+#    #+#              #
#    Updated: 2020/03/06 13:03:46 by kpesonen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

#From an alpine image you’ll add to your container your favorite text editor, vim or
#emacs, that will launch along with your container.

FROM alpine

RUN apk update && apk upgrade && apk add vim

ENTRYPOINT vim

#docker build . -t ex00
#docker image ls
#docker run -it --rm ex00 (interactive mode is a must, otherwise you are stuck)
