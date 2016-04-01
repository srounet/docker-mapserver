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

This image expose port 80 for Mapserver

    sudo docker run -d -P -v /usr/local/mapserver:/maps --name mapserver mapserver

or if you want to bind it to a custom port

    sudo docker run -d -p HOST_CUSTOM_PORT:80 -v /usr/local/mapserver:/maps --name mapserver mapserver


## Debug docker-mapserver using docker interactive shell

Sometimes, you may want to run a shell within docker-mapserver, to look around, check logs and so on...
To achieve that, you can use docker interactive shell that way:

   sudo docker exec -i -t mapserver bash


## Test it

http://HOST_IP:HOST_80_OR_CUSTOM_PORT/cgi-bin/mapserv
