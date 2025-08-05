# A script for setup FreeBSD jails

This script maybe useful for FreeBSD jail users especially who can't or don't use ZFS environment.

# Usage
## initial setup

```
setup_jail init
```

## Create a jail

```
setup_jail -j 80 -n www -4 192.0.2.80 -s 2g create
```

## Prepare for upgrading jail environment

```
setup_jail -R 14.3-RELEASE prepare
```

## Help
```
Usage: setup_jail [options] command
   options may include:
      -s: size of a jail image (e.g. 2g, 10g, 500m, see trancate(1))
      -n: name of the jail
      -j: id of the jail
      -4: ipv4 address of the jail
      -R: Release version of the FreeBSD
      -h: print this message

   command must be one of the followings:
      init   : initial setup for jails environmnent
      create : create a jail
      prepare: prepare for updating the base environment
```

# Configuration

- JAIL_CONF
  - path to jail.conf(5).
- FSTAB
  - path to fstab(5).
- DEVFS_RULES
  - path to devfs.rules(5).
- jail_base
  - A base directory for jails
- switch
  - The name of cloned interface, bridge(4).
- base_version
  - FreeBSD version for jails.
- zoneinfo
  - name of zoneinfo which will be copied as /etc/localtime
- jails_default_gw
  - default gagteway for jails
- jails_dns_servers
  - list of dns servers for jails. (e.g. jails_dns_servers="192.0.2.53 192 192.0.2.54")
