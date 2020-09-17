# [Elektro](https://hub.docker.com/r/stevenfoong/elektro)
![alt text](https://img.shields.io/docker/automated/stevenfoong/elektro.svg)

## What?
Hubot base personal assistance

This hubot is to connect with Rocketchat so that user can issue command from Rocketchat.

## Running this image with docker-compose

The volumes are set to keep your custom scripts persistent.

```
version: '3'
services:
  elektro:
    image: stevenfoong/elektro
    container_name: elektro
    restart: always
    environment:
     - ROCKETCHAT_URL=<your rocketchat instance>:<port>
     - ROCKETCHAT_ROOM='general' 
     - RESPOND_TO_DM=true 
     - ROCKETCHAT_USER=botname 
     - ROCKETCHAT_PASSWORD=botpass 
     - HUBOT_NAME=elektro
     - EXTERNAL_SCRIPTS=hubot-help,hubot-diagnostics 
    volumes:
     - /data/elektro:/home/hubot/scripts
  automation-hook:
    image: stevenfoong/automation-hook
    container_name: automation-hook
    restart: always
    environment:
     - ENV = ENV VALUE
    volumes:
     - VOLUME : PATH

```

## Need Help ?

If you have any question or facing any issue setup the container, raise an [issue](https://github.com/stevenfoong/Elektro/issues), i will try my best to answer your question or help you out.
