<p align="center">
  <img
    src="http://res.cloudinary.com/vidsy/image/upload/v1503160820/CoZ_Icon_DARKBLUE_200x178px_oq0gxm.png"
    width="125px"
    alt="City of Zion logo">
</p>

<h1 align="center">neo-local</h1>

<p align="center">
  Quickly setup a local environment for NEO smart contract development.
</p>

<p align="center">
  <a href="https://travis-ci.org/CityOfZion/neo-local">
    <img src="https://img.shields.io/travis/CityOfZion/neo-local/master.svg">
  </a>
</p>

## What?

Developing smart contracts for the NEO blockchain requires a local 
[private network](https://hub.docker.com/r/cityofzion/neo-privatenet/) to be running. This project 
sets this up for you, along with a number of other utility [services](#services) to help with development.

![image](https://user-images.githubusercontent.com/2796074/36632958-9247f8ba-198d-11e8-8055-f096141902d9.png)

## Install

Before being able to use **neo-local**, you will need to install **Docker** and **Docker Compose**.

For MacOS and Windows users, both are bundled together:

- [Docker for Mac](https://docs.docker.com/docker-for-mac/install/)
- [Docker for Windows](https://docs.docker.com/docker-for-windows/install/)

For Linux users, you will have two seperate things to install:

1. [Docker (Community Edition)](https://store.docker.com/search?offering=community&operating_system=linux&q=&type=edition)
1. [Docker Compose](https://docs.docker.com/compose/install/#install-compose)

## Usage

MacOS or Linux users can make use of the **Makefile**:

```
make start
```
```
make stop
```

Windows users must run the **Docker commands manually**:

```
docker-compose up -d --build --remove-orphans
```
```
docker exec -it neo-python np-prompt -p -v
```

## Block Explorer

View what is happening on your local blockchain: [http://localhost:4000](http://localhost:4000)

## Services

The [Docker Compose](https://docs.docker.com/compose/) stack is made up of the following
services:

- [neo-privatenet](https://hub.docker.com/r/cityofzion/neo-privatenet/) (consensus nodes)
- [neo-python](https://github.com/CityOfZion/neo-python) (development CLI)
- [neo-scan](https://github.com/CityOfZion/neo-scan) (block explorer)

## Troubleshooting

ERROR: Couldn't connect to Docker daemon. You might need to start Docker for Mac.

docker-machine create default
