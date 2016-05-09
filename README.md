# postgresqldatabase_tripsys
This is a database dump of the Tripsys tables used by Tripodmaps Chui edition


Extracting the files
-----------

Use <b>7zip</b> to Extract the files. Start with the file ending with <b>.001</b>


Restoring the PostgreSQL database backup
----------------------------------------
1. Install <b>PostgreSQL 9.5</b> on Ubuntu or Windows

2. Install <b>pgAdmin 1.22.1</b>

3. Install <b>Postgis</b> on the 9.5, and make sure you let it install the template database. Please install <b>Postgis 2.2.x</b>, x denoting the highest number of the edition

4. Using pgAdmin III, create a database called <b>tripsys</b> in the 9.5 database server. Before clicking OK make sure you select the <b>Definitions</b> tab,

5. On the Definitions tab, from the <b>template</b> list select the <b>postgis</b> database installed by default. The template will have the name postgis or postgis_2.x. Selection of a template lets you avoid the need to run CREATE extension postgis; and other related functions to enable the database to be spatial

6. Right click on <b>tripsys</b> and select <b>Restore</b>

7. Navigate to the location where you downloaded the Extracted/Downloaded file

9. Select <b>postgres</b> from the <b>role name</b> list

10. Click OK to restore the database


Other sources of this file
--------------------------
This file is also available on Dropbox via the link below.

https://dl.dropboxusercontent.com/u/313489686/Postgresql/postgres_tripsys_db_rolenamepostgres.backup


Using certificates
------------
REF: http://ubuntuforums.org/showthread.php?t=735020

It is important to include SSL verification early on in your system. The instructions below will help you with setting up Postgresql servers with SSL. This certificate(s) can also be used for your software applications as well.

    openssl req -new -text -out server.req
    openssl rsa -in privkey.pem -out server.key
    rm privkey.pem
    openssl req -x509 -in server.req -text -key server.key -out server.crt
    chmod og-rwx server.key
    chown postgres : postgres server.key


