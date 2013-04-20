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

Install usefull packages

    brew install wget
    brew install cmake
    brew install fastcgi
    
Install GDAL

    brew install gdal
    
Install PostGIS

    brew install postgresql
    brew install postgis
        
Install mapserver 6.2

    brew install mapserver

Install mapcache

    brew install pixman
    
    # Create a temporary directory
    mkdir tmp
    cd tmp
    
    # Retrieve mapcache
    git clone git://github.com/mapserver/mapcache.git
    
    # Compilation
    cmake mapcache
    make
    sudo make install
    
    # Copy mapcache configuration file to /usr/local/etc
    cp mapcache/mapcache.xml /usr/local/etc/
    
    # Clean tmp directory
    rm tmp
    
Configuration
=============

Configure your ~/.bash_profile :

    # Homebrew PATH
    export PATH=/usr/local/sbin:/usr/local/bin:$PATH

    # Postgres path
    export PGDATA='/usr/local/var/postgres/'
    
Copy mapserver executable within Apache CGI directory

    sudo cp /usr/local/Cellar/mapserver/6.2.0/bin/mapserv .
    
Configure mapcache
    
    # Edit /etc/apache2/httpd.conf and add the following
    LoadModule mapcache_module   libexec/apache2/mod_mapcache.so
    <IfModule mapcache_module>
        <Directory /usr/local/etc/mapcache>
            Order Allow,Deny
            Allow from all
        </Directory>
        MapCacheAlias /mapcache "/usr/local/etc/mapcache/mapcache.xml"
    </IfModule>
    
    # Restart apache
    sudo apachectl restart
    
    

