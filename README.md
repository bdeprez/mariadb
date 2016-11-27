MariaDB Dockerfile
==================

Based on CentOS7 original mariadb Dockerfile, based on Stephen Tweedie's mariadb Dockerfile...

Updated FROM centos:centos7 to paas/rhel7.2 to use PaaS approved RHEL image.

Setup
-----

    # docker build --rm --tag <yourname>/mariadb55 .


Launching MariaDB
-----------------

To use a separate data volume for /var/lib/mysql:

Create a data volume

    # docker volume create mariadb

Then run the container

    # docker run --name mariadb -d -p 3306:3306 -v mariadb:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=<password> <yourname>/mariadb55

