# GTFS to MySQL
Load GTFS into a MySQL database

## Overview

This sql file will read an unzipped [GTFS](https://developers.google.com/transit/gtfs/) (General Transit Feed Specification) file into a MySQL database. This is useful for making GTFS data queryable.

## Installation

* Start mysql locally
    mysqld --local-infile=1

* Place `gtfs_to_mysql.sql` in the folder with unzipped GTFS files.

* Create a MySQL database `gtfs` if it doesn't exist already
    mysql -u root --batch -e 'DROP DATABASE gtfs'
    mysql -u root --batch -e 'CREATE DATABASE gtfs'

* Import the GTFS files to your local database
    cat gtfs_to_mysql.sql | mysql -u root --local-infile

## License
This project is licensed under GNU General Public License v3.0.
