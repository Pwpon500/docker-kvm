# docker-kvm

## debian-systemd

This Dockerfile takes a basic Debian Stretch Docker image and configures it so it can use systemd. This can be useful for running daemons that cannot function without systemd.

### Usage:

Starting the container:
`docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro pwpon500/debian-systemd`

Accessing console of container:
`docker exec -it <container_id> /bin/bash`

## debian-kvm

This Dockerfile takes the debian-systemd image and installs the base packages needed for libvirt to run.

### Usage:

Starting the container:
`docker run -d --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro pwpon500/debian-kvm`

Accessing console of container:
`docker exec -it <container_id> /bin/bash`
