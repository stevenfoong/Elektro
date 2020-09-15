FROM rocketchat/hubot-rocketchat

# hack added to get around owner issue: https://github.com/docker/docker/issues/6119

CMD node -e "console.log(JSON.stringify('$EXTERNAL_SCRIPTS'.split(',')))" > external-scripts.json && \
	npm install $(node -e "console.log('$EXTERNAL_SCRIPTS'.split(',').join(' '))") && \
	bin/hubot -n $BOT_NAME -a rocketchat
