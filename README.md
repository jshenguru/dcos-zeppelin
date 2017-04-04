# dcos-zeppelin docker

This is the docker build for Zeppelin on DC/OS, as well as the JSON file to add Marathon app.

## Documentation

There is no need to build a package for DC/OS 1.8.0. All you need is a docker image, such as jshenguru/dcos-zeppelin:0.7.0, and a json file (located in the config folder of this fork), then run command like below

```sh
./dcos marathon app add <PATH_TO_THE_CLONED_DIR>/config/zeppelin-0.7.0.json
```
A custom HDFS config can be passed through spark.mesos.uris. This moves those config files into the standard directory. In DCOS, the CLI reads the "SPARK_HDFS_CONFIG_URL" marathon lable in order to set spark.mesos.uris.

## Building

In stead of using my pre-built docker image, you can add your own custom stuff to the Dockerfile and build your own.
```sh
cd docker
docker build -t jshenguru/dcos-zeppelin:<version> .
```
You can change the "jshenguru" to your own Docker hub name.

## Installing

DC/OS 1.8.0 does not need to configure the load balancer to access to the Zeppelin. Just type the following in your web browser

```sh
https://<YOUR_DCOS_LOAD_BALANCER_URL>/service/zeppelin/
```
