[![Join the chat at https://gitter.im/jeffutter/dokku-postgresql-plugin](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jeffutter/dokku-postgresql-plugin?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

PostgreSQL plugin for Dokku
---------------------------

Project: https://github.com/progrium/dokku


Installation
------------
```
cd /var/lib/dokku/plugins
git clone https://github.com/jeffutter/dokku-postgresql-plugin postgresql
dokku plugins-install
```


Commands
--------
```
$ dokku help
     postgresql:console <app> Launch a postgresql console for a given app
     postgresql:create <app>  Create a PostgreSQL database
     postgresql:delete <app>  Delete specified PostgreSQL database
     postgresql:list          List all databases
     postgresql:start         Start the PostgreSQL docker container if it isn't running
     postgresql:status        Shows status of PostgreSQL
     postgresql:stop          Stop the PostgreSQL docker container
```

Usage
------------

Start PostgreSQL:
```
$ dokku postgresql:start                 # Server side
..or..
$ ssh dokku@server postgresql:start      # Client side

Example Output:

9f3d9d19248c110fce9f8489482adafd2172834a0f1d2db9f0140141927501b9
```

Create a new DB (app with same name has to exist):
```
$ dokku postgresql:create foo            # Server side
..or..
$ ssh dokku@server postgresql:create foo # Client side

Example Output:

CREATE ROLE
CREATE DATABASE
GRANT
-----> Creating /home/dokku/foo/ENV
-----> Setting config vars and restarting foo
DATABASE_URL: postgres://foo:ultrastrongpassword@172.17.0.28:5432/foo
-----> Releasing foo ...
-----> Release complete!
-----> Deploying foo ...
-----> Deploy complete!
```
