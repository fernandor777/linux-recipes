# Install LXC on Centos 7
https://www.tecmint.com/install-create-run-lxc-linux-containers-on-centos/


	$ yum install epel-release

	$ yum install debootstrap perl libvirt

	$ yum install lxc lxc-templates

	# systemctl status lxc.service
	# systemctl start lxc.service
	# systemctl start libvirtd 
	# systemctl status lxc.service

check LXC kernel virtualization status by issuing the below command.

    # lxc-checkconfig


## Create a container

View avalaible templates:

	$ ls -alh /usr/share/lxc/templates/

Syntax:

https://us.images.linuxcontainers.org/
	
	# lxc-create -n container_name -t container_template
	
	# lxc-create -n container_name -t container_template -- -R distro_release -a distro_architercture 
	
Examples:

	# lxc-create -n c7a -t centos -- -R 7 	

Output:

	Container rootfs and config have been created.
	Edit the config file to check/enable networking setup.

	The temporary root password is stored in:

			'/var/lib/lxc/c7a/tmp_root_pass'


	The root password is set up as expired and will require it to be changed
	at first login, which you should do as soon as possible.  If you lose the
	root password or wish to change it without starting the container, you
	can change it from the host by running the following command (which will
	also reset the expired flag):

			chroot /var/lib/lxc/c7a/rootfs passwd

	[root@localhost ~]#

Set new root password:

	chroot /var/lib/lxc/c7a/rootfs passwd

Containers can be deleted from your host with the lxc-destroy command issued against a container name.

	# lxc-destroy -n c7a
	
A container can be cloned from an existing container by issuing lxc-clone command:

	# lxc-clone c7a c7a-clone
	
And finally, all created containers reside in /var/lib/lxc/ directory. If for some reason you need to manually adjust container settings you must edit the config file from each container directory.

	# ls /var/lib/lxc
	
	

