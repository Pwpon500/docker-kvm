# docker-kvm

## Usage:

Any of these images can be started and accessed via these steps:

Starting the container:
`docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro pwpon500/<image_name>`

Accessing console of container:
`docker exec -it <container_id> /bin/bash`

## alpine-libvirt

This Dockerfile takes the dockage/alpine-openrc docker image and installs all proper libvirt packages onto it. It also adds dbus and libvirt to the openrc default runlevel.

## libvirt-terraform

This Dockerfile takes the pwpon500/alpine-libvirt image and adds terraform to it. It also installs the terraform-libvirt-provider so that terraform can actually be used.

## debian-systemd

This Dockerfile takes a basic Debian Stretch Docker image and configures it so it can use systemd. This can be useful for running daemons that cannot function without systemd.

## debian-libvirt

This Dockerfile takes the pwpon500/debian-systemd image and installs the base packages needed for libvirt to run.

