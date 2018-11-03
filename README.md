# ansible-config
Ansible playbooks and config for three physical nodes running various containers and VMs

# Prerequisites

## LXD container host resolution
By default LXD containers do populate the LXD-specific dnsmasq built-in DNS, but not the host's
DNS resolution. To get this to work:
````
From https://gauvain.pocentek.net/name-resolution-lxc-containers.html, adjusted for LXD instead of LXC:

To make this setup really usable the host must be configured to redirect DNS queries to the LXD-related dnsmasq process. By default Ubuntu configures /etc/resolv.conf to use 127.0.1.1 as DNS resolver. A dnsmasq process takes care of forwarding the requests to the proper authoritative DNS.

To setup the forwarding, add the following line to /etc/dnsmasq.d/lxd:

server=/lxd/10.87.70.1

If you're running a desktop version of Ubuntu, you probably use Network Manager. Symlink this configuration file to /etc/NetworkManager/dnsmasq.d/lxd and restart Network Manager:

$ sudo ln -s /etc/dnsmasq.d/lxd /etc/NetworkManager/dnsmasq.d/
$ sudo service network-manager restart

````

## Inventories
### Physical Hosts
### LXD Containers
