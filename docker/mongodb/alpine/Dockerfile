# Use the official MongoDB image as the base image
FROM alpine:3.21

RUN apk add --repository http://dl-cdn.alpinelinux.org/alpine/v3.9/main \
		--repository http://dl-cdn.alpinelinux.org/alpine/v3.9/community \
		--no-cache --update mongodb mongodb-tools yaml-cpp=0.6.2-r2
RUN mkdir -p /data/db && chown -R mongodb:mongodb /data/db

VOLUME /data/db
ENV MONGOMS_SYSTEM_BINARY=/usr/bin/mongod
WORKDIR /data
# Expose the default MongoDB port
EXPOSE 27017
# Set the default command to run when the container starts
CMD ["mongod", "--bind_ip", "0.0.0.0"]
