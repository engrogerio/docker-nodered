# Raspberry Valley image for Node-RED dashboard, based on the official docker image of Node-RED
# To learn more, visit our github repository: https://github.com/raspberryvalley/docker-nodered
# Image available on Docker Hub: https://cloud.docker.com/u/raspberryvalley/repository/docker/raspberryvalley/nodered

FROM nodered/node-red-docker

LABEL maintainer = "raspberryvalley@outlook.com"

# Install Node-RED Dashboard (global setup)
RUN npm install node-red-dashboard

# Create volume for Node-RED storage
VOLUME /root/.node-red/

# Expose port 1880
EXPOSE 1880
