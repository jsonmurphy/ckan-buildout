Ckan Buildout
=============

A Buildout configuration for the ckan platform. Works best and is tested for Ubuntu 12.04. For other distros, you will most likely need to change the configuration a bit (specifically for system dependency part).

Installation
--------------

Install virtualenv and git.
	sudo apt-get install git python-virtualenv

Clone the repository.
	git clone https://github.com/jsonmurphy/ckan-buildout.git

Create and initilize the virtual enviroment
	cd ckan-buildout
	virtualenv --no-site-packages .
	source bin/activate

Run the buildout
	python bootstrap.py
	buildout

Note: a couple of parts are using sudo commands so be prepared to enter your password, provided you actually have sudo access.

This should install ckan and all its dependecies then you can run the server by doing (still within ckan-buildout) :
	cd src/ckan
	paster serve development.ini

If you get the message "Could not start Jetty servlet engine because no Java Development Kit (JDK) was found". then you will have to edit the JAVA_HOME setting in /etc/default/jetty to point to your machine’s JDK install location. For example:
	JAVA_HOME=/usr/lib/jvm/java-6-openjdk-amd64/

or:
	JAVA_HOME=/usr/lib/jvm/java-6-openjdk-i386/
