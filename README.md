GisOnOsX
========

A step by step installation of GIS packages on Mac OS X 

Prerequesites
=============

Install latest XCode from Apple Store with "Command Line Tool" or only install the Command Line tool from XCode.
In this case you'll need a free developer login to access the download, login and look for "Command Line Tools for Xcode".


Packages manager
================

Install homebrew - http://mxcl.github.com/homebrew/

    => GDAL
    brew install gdal
    
    => PostGIS
    brew install postgresql
    brew install postgis
    
    => PHP 5.3
    brew tap homebrew/dupes
    brew tap josegonzalez/homebrew-php
    brew install php53 --with-pgsql
    
    => SOLR
    brew install solr
    brew install php53-solr
    
    => mapserver 6.2
    brew install https://raw.github.com/mapserver/packaging/master/homebrew/mapserver.rb
    
    
    
  