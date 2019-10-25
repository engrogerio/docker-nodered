# Node-RED docker image for Raspberry Pi

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

## Development image for Windows

We have bundled a dockerfile to this repository, which allows you to create a quick and dirty Windows image, for development of concepts. This image is based on the official [node-red-docker](https://hub.docker.com/r/nodered/node-red-docker) image (latest) and bundles in Node-RED Dashboard. Use as you would on a Raspberry Pi, just substitute the **rpi** tag with **pc**.

## About

Raspberry Valley is a maker community in Karlskrona, Sweden, sponsored by [Dynapac](https://dynapac.com/en). We run makerspaces every week, working with Raspberry Pis, Arduinos and other interesting hardware.

This repository is here to support our community of makers. A lot of our achievements are based and inspired by the community at large. We wish to pay back and share our experiences and lessons learned. Join us!

You can find our pages here: [Raspberry Valley](https://raspberry-valley.azurewebsites.net). You can also join us on [Twitter](https://twitter.com/RaspberryValley) or check [Docker Hub](https://hub.docker.com/r/raspberryvalley/) for images of interest.

## Links

Raspberry Valley makerspace links

* [Raspberry Valley](https://raspberry-valley.azurewebsites.net) - Other things we make and do
* [Raspberry Valley on Twitter](https://twitter.com/RaspberryValley)
* [Raspberry Valley on Github](https://github.com/raspberryvalley)
* [Raspberry Valley Docker Hub Images](hub.docker.com/r/raspberryvalley/)
