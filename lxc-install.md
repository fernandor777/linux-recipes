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

View avalaible templates:

	# ls -alh /usr/share/lxc/templates/


