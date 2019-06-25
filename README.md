# Node-RED docker image for Raspberry Pi

We are a maker community in Karlskrona, Sweden. See our site for other ideas and activities: [Raspberry Valley](https://raspberry-valley.azurewebsites.net).

This is yet another Node-RED image for use in our makerspace. It includes Node-RED Dashboard on top.

## Docker Image

Our Docker image is based on a [Balena base image](https://www.balena.io/docs/reference/base-images/base-images/) with Node. It is targeted at Raspberry Pi 3, you can check all available images [here](https://www.balena.io/docs/reference/base-images/base-images-ref/) (search for the 'Raspberry Pi 3' section).

The image contains also the following extras:

* Node-RED Dashboard

---

Please note that we provide only the Raspberry Pi image, tagged as **rpi**. We use the official, non-modified PC image for testing.

---

## Getting the Node-RED Image

You can pull the image from our [Raspberry Valley Docker Hub](https://cloud.docker.com/u/raspberryvalley/repository/docker/raspberryvalley/nodered). Simply type the following:

```bash
docker pull raspberryvalley/nodered:rpi
```

Note: This is an optional step which fits our workflow. If you don't pull the image, the run scripts below will do it for you.

## Running the image

First time, you need to create the container.

```bash
docker run -d -p 1880:1880 --name mynodered raspberryvalley/nodered:rpi
```

This launches your server in the background, exposing the appropriate port. Note that after a restart you need to start the container which was just created above.

## Building your own

If you don't want to use our pre-made image, simply build your own. This is a sign of sanity: be careful about using 3rd party images: a bit of paranoia helps.

To build your own image, follow the steps below:

* clone this repository
* Open up PowerShell (or the command prompt) and navigate to the repository build folder (where the Dockerfile is located)
* Update/modify the Dockerfile to your liking, then invoke the build command:

```bash
docker build -t "raspberryvalley/docker-nodered:rpi" .
```

## Links

Raspberry Valley makerspace links

* [Raspberry Valley](https://raspberry-valley.azurewebsites.net) - Other things we make and do
* [Raspberry Valley on Twitter](https://twitter.com/RaspberryValley)
* [Raspberry Valley on Github](https://github.com/raspberryvalley)
* [Raspberry Valley Docker Hub Images](hub.docker.com/r/raspberryvalley/)
