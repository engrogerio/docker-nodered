# Raspberry Valley image for mkdocs, based on Alpine
# To learn more, visit our github repository: https://github.com/raspberryvalley/docker-mkdocs
# Image available on Docker Hub: https://cloud.docker.com/repository/docker/raspberryvalley/mkdocs/general

FROM balenalib/raspberrypi3-node:8-stretch-run

LABEL maintainer = "raspberryvalley@outlook.com"

# pre-requisites
RUN apt-get update && \
    apt-get install build-essential && \
    apt-get install python2.7 python-pip && \
    apt-get install rpi.gpio && \
    rm -rf /var/lib/apt/lists/*

# Install Node-RED (global setup)
RUN npm install -g node-red && \
    npm install -g node-red-dashboard

# Create volume for Node-RED storage
VOLUME /root/.node-red/

# Expose port 1880
EXPOSE 1880

# Setup start command
CMD node-red-pi --max-old-space-size=256