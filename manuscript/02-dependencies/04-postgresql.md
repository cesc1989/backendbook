### PostgreSQL

PostgreSQL is a ORDBMS([Object-Relational](https://en.wikipedia.org/wiki/Object-relational_database) Database Management System).

#### What is this for?

Storing and accessing data through the Structured Query Language(SQL).

#### How to install it?

Create a file `$ nano install_postgresql.sh` and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install libpq-dev postgresql
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`.

Then run it

```bash
$ sudo bash install_postgresql.sh
```

#### Verify

You can check PostgreSQL is up and running by issuing `$ sudo service postgresql status` command in your terminal. It should return the version and port the database server is working.

#### Docs

A full list of PostgreSQL manuals can be found [their official site](https://www.postgresql.org/docs/manuals/).
