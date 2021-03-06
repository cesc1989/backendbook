### Redis

Redis is an [in-memory](https://en.wikipedia.org/wiki/In-memory_database) [data structure](https://en.wikipedia.org/wiki/Data_structure) store that can be used as a database, cache and/or message broker.

#### What is this for?

Regarding Ruby on Rails applications, Redis can be used as a database for storing background jobs data. Sidekiq is a popular gem that leverages Redis to work.

You can also use a Redis as a cache or message broker, however, solutions like RabbitMQ are better suited for this job as there have been issues about Redis losing data.

#### How to Install Redis

There packages available for many operating systems that make it easy to install Redis with just a couple of commands.

##### Ubuntu 14.04+

Run the following commands:

```bash
$ apt-get update
$ apt-get install -y redis-server
```

##### MacOS

If you Homebrew installed just run:

```bash
$ brew install redi
```

##### From Source

Create a file `$ nano install_redis.hs` and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install tcl8.5
curl -sSL http://download.redis.io/releases/redis-stable.tar.gz -o /tmp/redis.tar.gz
mkdir -p /tmp/redis
tar -xzf /tmp/redis.tar.gz -C /tmp/redis --strip-components=1
make -C /tmp/redis
make -C /tmp/redis install
echo -n | /tmp/redis/utils/install_server.sh
rm -rf /tmp/redis*
sysctl vm.overcommit_memory=1
sed -ie 's/# bind 127.0.0.1/bind 127.0.0.1/g' /etc/redis/6379.conf
service redis_6379 restart
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`, then run the instructions in the file

```bash
$ sudo bash install_redis.sh
```

and wait for redis to be installed on your machine.

> **NOTE**
> this way of install is called _from source_ and the main difference between this and installing from `apt-get` is getting up to date packages. Sometimes the apt packages are really outdated.

#### Verify Installation

Check redis is running with `sudo service redis_6379 status`. It should output something like _Redis is running (PORT NUMBER)_.

#### Docs

You can find all redis documentation in its [official page](http://redis.io/documentation).

Read more about [Redis feautures](https://redislabs.com/redis-features/redis).

About installing redis:

- [How to Install and configure Redis on Ubuntu 14.04](https://hostpresto.com/community/tutorials/how-to-install-and-configure-redis-on-ubuntu-14-04/)
- [Install and config Redis on Mac OS X via Homebrew](https://medium.com/@petehouston/install-and-config-redis-on-mac-os-x-via-homebrew-eb8df9a4f298#.6xbtma4ow)
