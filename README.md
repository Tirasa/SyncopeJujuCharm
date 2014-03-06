# Overview

Apache Syncope is an Open Source system for managing digital identities in enterprise environments, implemented in JEE technology and released under Apache 2.0 license.

This charm provides [Apache Syncope](http://syncope.apache.org).

# Usage

Step by step instructions on using the charm (minimum 2GB RAM required):

```
$ juju deploy syncope --constraints mem=2G
```

then

```
$ juju deploy postgresql
$ juju add-relation syncope postgresql:db
```

and finally

```
$ juju expose syncope
```

This will [generate a new Apache Syncope project](https://cwiki.apache.org/confluence/display/SYNCOPE/Create+a+new+Syncope+project#CreateanewSyncopeproject-Createnewproject) from latest Maven archetype under `/usr/local/src/syncope-charm`, setup the JEE container and the DBMS, build and deploy Apache Syncope `core` and `console` and finally start up the JEE container.

At this point the Apache Syncope admin console is available at 

http://your.host:yourport/syncope-console/ 

where 

 * `your.host` is the IP address or hostname where the charm is reachable
 * `yourport` is the TCP port configured (defaults to 80)

You can reach it anyway at http://your.host:yourport/

## Destroying the service

In case you need to destroy the `syncope` service, be sure to first remove the database relation:

```
$ juju remove-relation syncope postgresql:db
$ juju destroy-service syncope
```

## Scale out Usage

To be implemented.

# Configuration

Several configuration options are available, including:
 * the port to which the HTTP service will be listening (default: `80`)
 * the bundles directory (default: `/opt/syncope/bundles`)
 * the log directory (default: `/opt/syncope/log`)

# Contact Information

Please send an e-mail to syncope@tirasa.net

## Apache Syncope

- [Official ASF site](http://syncope.apache.org)
- [Tirasa support site](http://syncope.tirasa.net)
