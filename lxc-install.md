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


