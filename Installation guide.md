# How to install the execution server (vpl-jail-service 2.x) in Ubuntu

This document describes the installation of the VPL execution server (vpl-jail-system) on Ubuntu.


#	Installing execution server on Ubuntu
Our tests indicate that the 32-bit version is more convenient than the 64 because the 32-bit implementation consumes less memory and CPU than the 64-bit version. The machine requirements are highly dependent on the software used, our experience is that a machine with only 2Gb of ram and 2 cores can support a class of 50 students online using Java.

per-requirement: Fresh/Clean installed ubuntu Operating System

The steps for installation 2.5.3 version of VLP and configuration are below:

1.	download vpl-jail-system-2.5.3.tar.gz (150 Kb) from here

2.	tar -xvf vpl_jail_system-2.5.3.tar.gz

3.	cd vpl_jail_system-2.5.3/

4.	for non-root user: sudo ./install-vpl-sh	
						or
	for root user: ./install-vpl-sh

5.	Then follow the steps which will be shown on the terminal, after finishing installation follow from 6. (sixth) step from below 
	documentation.

-----------------------------------------------------------------OR----------------------------------------------------------------

The steps for installation latest version of VLP and configuration are below:

1.	Install an Ubuntu server as clean as possible

2.	Search for the latest software version browsing http://vpl.dis.ulpgc.es/releases. Look at vpl-jail-system-[version].tar.gz
	files and select the hightest version. From here replace [version] by the the version selected.

3.	Download the latest version of the software (vpl-jail-system) with the command

    wget http://vpl.dis.ulpgc.es/releases/vpl_jail_system-[version].tar.gz
	
4.	Unzip and install the vpl-jail-system

    tar -xvf vpl_jail_system-[version].tar.gz

    cd vpl_jail_system-[version]
    
    sudo ./install-vpl-sh
	
5.	Follow the instructions and wait for the necessary downloads. The installation script will try to install the development
	software commonly used, but you may need to install some other by hand.	

6.	Stop the service with the command

    sudo service vpl- jail-system stop
	
7.	Edit the file /etc/vpl/vpl-jail-system.conf. Set the URLPATH that will be used as key in connections with your execution server

8.	Start the service

    sudo service vpl-jail-system start

#	Checking

You can check the availability of your execution server using the URL

http://server:PORT/OK and https://server:SECURE_PORT/OK

where server is the name of your execution server

The system must return a page with OK

#	Troubleshooting

You can obtain a detailed log of the service by starting it in debug mode with "service vpl-jail-system start -d 8". The logs will be written in "/var/log/syslog"

#	Using

The URL of the service in the general module configuration or in the local execution server settings of your Moodle server is

http://server:PORT/URLPATH or https://server:SECURE_PORT/URLPATH

:PORT and :SECURE_PORT can be omitted if using the standard ports.
