# Raspberry Valley image for Node-RED dashboard, based on the official docker image of Node-RED
# To learn more, visit our github repository: https://github.com/raspberryvalley/docker-nodered
# Image available on Docker Hub: https://cloud.docker.com/u/raspberryvalley/repository/docker/raspberryvalley/nodered
#
# Raspberry Valley is a makerspace in Sweden, Karlskrona. You can visit our sites and check what's developing: 
# * Knowledge base: https://raspberry-valley.azurewebsites.net
# * Github pages: https://github.com/raspberryvalley
# * Docker hub: hub.docker.com/r/raspberryvalley/
# * Follow on Twitter: https://twitter.com/RaspberryValley

FROM nodered/node-red-docker

LABEL maintainer = "raspberryvalley@outlook.com"

# Install Node-RED Dashboard (global setup)
RUN npm install node-red-dashboard

# Create volume for Node-RED storage
VOLUME /root/.node-red/

# Expose port 1880
EXPOSE 1880
