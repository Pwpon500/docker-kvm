FROM debian:stretch
# You can change the FROM Instruction to your existing images if you like and build it with same tag
ENV container docker
ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install systemd -y && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN cd /lib/systemd/system/sysinit.target.wants/; ls | grep -v systemd-tmpfiles-setup | xargs rm -f $1 \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*; \
rm -f /lib/systemd/system/plymouth*; \
rm -f /lib/systemd/system/systemd-update-utmp*;
RUN systemctl set-default multi-user.target
ENV init /lib/systemd/systemd
VOLUME [ "/sys/fs/cgroup" ]
# docker run -it --privileged=true -v /sys/fs/cgroup:/sys/fs/cgroup:ro 444c127c995b /lib/systemd/systemd systemd.unit=emergency.service
ENTRYPOINT ["/lib/systemd/systemd"]
