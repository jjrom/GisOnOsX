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
    
Install PHP 5.3

    brew tap homebrew/dupes
    brew tap josegonzalez/homebrew-php
    brew install php53 --with-pgsql
    
Install SOLR

    brew install solr
    brew install php53-solr
    
Install mapserver 6.2

    brew install freetype gd libpng
    brew install https://raw.github.com/mapserver/packaging/master/homebrew/mapserver.rb
    
    
Configuration
=============

Configure your ~/.bash_profile :

    # Homebrew PATH
    export PATH=/usr/local/sbin:/usr/local/bin:$PATH

    # Postgres path
    export PGDATA='/usr/local/var/postgres/'

    # Homebrew PHP 5.3
    export PATH="$(brew --prefix josegonzalez/php/php53)/bin:$PATH"

If using Apache, you will need to update the `LoadModule` call. For convenience, simply comment out the old PHP version:

    # /etc/apache2/httpd.conf
    # ...
    LoadModule php5_module    /usr/local/Cellar/php53/5.3.17/libexec/apache2/libphp5.so
