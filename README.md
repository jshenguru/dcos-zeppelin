# zeppelin-docker

This is the docker build for Zeppelin on DC/OS.

## Documentation

There is no need to build a package for DC/OS 1.8.0. All you need is a docker image, such as jshenguru/zeppelin:0.7.0, and a json file, then run command like below

```sh
./dcos marathon app add zeppelin-0.7.0.json
```

## Building

```sh
cd docker
docker build -t jshenguru/zeppelin:<version> .
```
You can change the "jshenguru" to your own Docker hub name.

## Installing

DC/OS 1.8.0 does not need to configure the load balancer to access to the Zeppelin. Just type the following in your web browser

```sh
https://<YOUR_DCOS_LOAD_BALANCER_URL>/service/zeppelin/
```
