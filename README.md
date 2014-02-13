# Overview

Apache Syncope is an Open Source system for managing digital identities in enterprise environments, implemented in JEE technology and released under Apache 2.0 license.

This charm provides [Apache Syncope](http://syncope.apache.org).

# Usage

Step by step instructions on using the charm:

```
$ juju deploy syncope
```

then

```
$ juju deploy postgresql
$ juju add-relation syncope postgresql:db
```

or

```
$ juju deploy mysql
$ juju add-relation syncope mysql
```

and finally

```
$ juju expose syncope
```

## Scale out Usage

# Configuration

# Contact Information

## Apache Syncope

- [Official ASF site](http://syncope.apache.org)
- [Tirasa support site](http://syncope.tirasa.net)
