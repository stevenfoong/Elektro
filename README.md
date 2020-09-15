# [Elektro](https://hub.docker.com/r/stevenfoong/elektro)
![alt text](https://img.shields.io/docker/automated/stevenfoong/elektro.svg)

## What?
Hubot base personal assistance

This hubot is to connect with Rocketchat so that user can issue command from Rocketchat.

## Running this image with docker-compose

The volumes are set to keep the scripts persistent.

```
version: '3'
services:
  skype-rocketchat-bridge:
    image: stevenfoong/elektro
    container_name: elektro
    restart: always
    environment:
     -e ROCKETCHAT_URL=<your rocketchat instance>:<port>
     -e ROCKETCHAT_ROOM='general' 
	   -e RESPOND_TO_DM=true 
	   -e ROCKETCHAT_USER=botname 
	   -e ROCKETCHAT_PASSWORD=botpass 
	   -e HUBOT_NAME=elektro
	   -e EXTERNAL_SCRIPTS=hubot-help,hubot-diagnostics 
    volumes:
     - /data/elektro:/home/hubot/scripts
```

## Need Help ?

If you have any question or facing any issue setup the container, raise an [issue](https://github.com/stevenfoong/Elektro/issues), i will try my best to answer your question or help you out.
