GisOnOsX
========

A step by step installation of GIS packages on Mac OS X 

Prerequesites
=============

Install latest XCode from Apple Store with "Command Line Tool" or only install the Command Line tool from XCode.
In this case you'll need a free developer login to access the download, login and look for "Command Line Tools for Xcode".


Install homebrew
================

See http://mxcl.github.com/homebrew/


Packages installation
=====================

Install GDAL

    brew install gdal
    
Install PostGIS

    brew install postgresql
    brew install postgis
        
Install mapserver 6.2

    brew install mapserver
    
    
Configuration
=============

Configure your ~/.bash_profile :

    # Homebrew PATH
    export PATH=/usr/local/sbin:/usr/local/bin:$PATH

    # Postgres path
    export PGDATA='/usr/local/var/postgres/'
