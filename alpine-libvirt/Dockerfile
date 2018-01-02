FROM dockage/alpine-openrc

RUN apk add --no-cache qemu-system-x86_64 libvirt libvirt-daemon dbus polkit qemu-img

RUN ln -s /etc/init.d/dbus /etc/runlevels/default/dbus; \
	ln -s /etc/init.d/libvirtd /etc/runlevels/default/libvirtd

