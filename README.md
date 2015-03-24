docker-mapserver 7
===================

The purpose of this project is to provide a WMS server using mapserver 7 (github master)

## Mapserver

MapServer is an Open Source platform for publishing spatial data and interactive mapping applications to the web. Originally developed in the mid-1990’s at the University of Minnesota, MapServer is released under an MIT-style license, and runs on all major platforms (Windows, Linux, Mac OS X). MapServer is not a full-featured GIS system, nor does it aspire to be.

## Building docker-mapserver

Running this will build a docker image with mapserver 7

    git clone https://github.com/srounet/docker-mapserver
    cd docker-mapserver
    docker build -t mapserver .


## Running docker-mapserver

This image expose three ports 22 for ssh and 80 for Mapserver

    sudo docker run -d -P -v /usr/local/mapserver:/maps --name mapserver mapserver

## Image active users

The root password is `toor`.


## Test it

http://HOST_IP:DOCKER_80_PORT/cgi-bin/mapserv