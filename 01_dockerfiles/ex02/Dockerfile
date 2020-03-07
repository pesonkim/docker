# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: kpesonen <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/03/06 18:05:18 by kpesonen          #+#    #+#              #
#    Updated: 2020/03/07 21:23:26 by kpesonen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM ruby:2.6.2

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y nodejs

RUN gem install rails --version 5.2.3

RUN mkdir -p /opt/app/

COPY ./app /opt/app

ONBUILD WORKDIR /opt/app 
ONBUILD RUN bundle install
ONBUILD RUN rake db:create
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

#HAVE THE APP BEFORE RUNNING THIS DOCKERFILE

#https://iridakos.com/programming/2019/04/04/creating-chat-application-rails-websockets

#RubyGems: a package manager for ruby
#gem: a self-cointained format for ruby programs and libraries
#rails: a web app development tool for ruby
#rake: a make-like program for ruby
#bundle: tracks and installs gem dependencies (exact gems and their versions needed)

#nodejs needed for a javascript runtime (when creating the database)
#nodejs is not needed for ruby directly, but a rails app requires it

#ONBUILD: execute commands after the current Dockerfile completes (instructions for the next)
#bundle install: install the current environment (app dir) to the system

#BUILDING IMAGE
#docker build -t ft-rails:on-build .
#continue in the child dir
#docker build -t ex02 .
#docker run -it --rm -p 3000:3000 ex02
#docker-machine ip Char
#visit <Char ip>:3000 on browser to confirm

#CREATING A BLANK RAILS APP
#docker run -it --rm -v $PWD/app:/app -p 3000:3000 ruby:2.6.2 sh
#apt-get update && apt-get upgrade -y && apt-get install -y nodejs
#cd /app (empty if needed)
#echo "ruby-2.6.2" > .ruby-version
#echo "app" > .ruby-gemset
#gem install rails --version 5.2.3
#rails new .
#yes to overwrite if needed
