# Raspberry Valley image for Node-RED dashboard and accessories, based on the official node balena image
# To learn more, visit our github repository: https://github.com/raspberryvalley/docker-nodered
# Image available on Docker Hub: https://cloud.docker.com/u/raspberryvalley/repository/docker/raspberryvalley/nodered
#
# Raspberry Valley is a makerspace in Sweden, Karlskrona. You can visit our sites and check what's developing: 
# * Knowledge base: https://raspberry-valley.azurewebsites.net
# * Github pages: https://github.com/raspberryvalley
# * Docker hub: hub.docker.com/r/raspberryvalley/
# * Follow on Twitter: https://twitter.com/RaspberryValley

# FROM balenalib/raspberrypi4-64-node:latest
FROM balenalib/aarch64-ubuntu-node:latest

LABEL maintainer = "eng.rogerio@gmail.com"

# pre-requisites
RUN apt-get update && \
    apt-get install -y python3-pip python3-dev \
    build-essential apt-utils \
    python3-distutils \
    python3-rpi.gpio \
    rpi.gpio-common \
    rpi.gpio \
    && rm -rf /var/lib/apt/lists/*
    #apt-get install liblgpio-dev liblgpio1 python3-lgpio
RUN pip install RPi.GPIO

# RUN useradd -rm -d /home/nodered -s /bin/bash -g root -G sudo -u 1001 nodered

# Install Node-RED (global setup)
RUN npm install -g node-red && \
    npm install -g node-red-contrib-i2c && \
    npm install -g node-red-dashboard && \
    npm install -g node-red-contrib-msg-speed && \
    npm install -g node-red-contrib-counter && \
    npm install -g node-red-contrib-statistics && \
    npm install -g node-red-contrib-map && \
    npm install -g node-red-node-pi-gpio && \
    npm install -g node-red-node-pi-gpiod && \
    npm install -g node-red-node-random && \
    npm install -g node-red-node-ping && \
    npm install -g node-red-contrib-play-audio && \
    npm install -g node-red-node-smooth && \
    npm install -g node-red-node-serialport && \
    npm install -g node-red-contrib-buffer-parser && \
    npm install -g node-red-contrib-web-worldmap && \
    npm install -g node-red-contrib-boolean-logic-ultimate && \
    npm install -g node-red-contrib-bool-gate

ENV USER=root 

# for other OSs than Raspbian
RUN sudo apt-get install -y python3-pip python3-dev && \
    sudo pip install RPi.GPIO && \
    sudo addgroup gpio && \
    sudo usermod -aG gpio $USER
# RUN echo 'KERNEL=="gpiomem", NAME="%k", GROUP="gpio", MODE="0660"' | sudo tee /etc/udev/rules.d/45-gpio.rules
# RUN sudo udevadm control --reload-rules
# RUN sudo udevadm trigger

# Create volume for Node-RED storage
VOLUME /root/.node-red/

# Copy project
COPY ./project/* /root/.node-red/

EXPOSE 1880

# Server ui from the correct IP
#RUN sed -i "s|\/\/uiHost: \"127.0.0.1\",|uiHost: \"0.0.0.0\", |g" /root/.node-red/settings.js
RUN echo uiHost: "0.0.0.0" >> /root/.node-red/settings.js

RUN /usr/bin/entry.sh
# Setup start command
CMD node-red-pi --max-old-space-size=256
