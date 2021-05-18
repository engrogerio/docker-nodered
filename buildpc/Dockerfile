# Raspberry Valley image for Node-RED dashboard, based on the official docker image of Node-RED
# To learn more, visit our github repository: https://github.com/raspberryvalley/docker-nodered
# Image available on Docker Hub: https://cloud.docker.com/u/raspberryvalley/repository/docker/raspberryvalley/nodered
#
# Raspberry Valley is a makerspace in Sweden, Karlskrona. You can visit our sites and check what's developing: 
# * Knowledge base: https://raspberry-valley.azurewebsites.net
# * Github pages: https://github.com/raspberryvalley
# * Docker hub: https://hub.docker.com/u/raspberryvalley
# * Follow on Twitter: https://twitter.com/RaspberryValley

FROM nodered/node-red

LABEL maintainer = "raspberryvalley@outlook.com"

# Install Node-RED Dashboard (global setup)
RUN npm install node-red-dashboard
# Install Aedes MQTT: Learn more here https://flows.nodered.org/node/node-red-contrib-aedes
RUN npm install node-red-contrib-aedes

# Create volume for Node-RED storage
VOLUME /root/.node-red/

# Expose ports 1880 for Node-RED and Node-RED Dashboard, 1883 and 1884 for Aedes MQTT
# Learn how to use here: http://raspberry-valley.azurewebsites.net/Node-RED-on-Docker/
EXPOSE 1880
EXPOSE 1883
EXPOSE 1884
