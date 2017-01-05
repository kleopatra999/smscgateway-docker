[![Travis build status](https://travis-ci.org/nicosmaris/smscgateway-docker.png?branch=master)](https://travis-ci.org/nicosmaris/smscgateway-docker)

# smscgateway-docker

The last command below assumes that there is a cassandra at localhost, so if you have one already, you can skip the first command.

docker run --name db --net=host -p 127.0.0.1:9042:9042 -p 127.0.0.1:9160:9160 -d cassandra

docker run --name smsc --net=host -p 0.0.0.0:8080:8080 -d restcomm/smsc
 
# Environment variables

This docker is based on phusion/baseimage which comes with an init process /sbin/my_init. The file scripts/automate_conf.sh is added at the image as /etc/my_init.d/restcommautomate.sh and thus it runs upon startup.

Optionally, if the environment variable ENVCONFURL is given at 'docker run', this file download a script from the url ENVCONFURL and adds it at the terminal, otherwise it follows the default settings of  scripts/restcomm_smsc_service.sh

