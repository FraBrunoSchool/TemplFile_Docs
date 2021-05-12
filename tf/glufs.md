# GlusterFS

> The GlusterFS architecture aggregates compute, storage, and I/O resources into a global namespace. Each server plus attached commodity storage (configured as direct-attached storage, JBOD, or using a storage area network) is considered to be a node. Capacity is scaled by adding additional nodes or adding additional storage to each node. Performance is increased by deploying storage among more nodes. High availability is achieved by replicating data n-way between nodes.

### How To Install GlusterFS

``` bash
[sudo] nano /etc/hosts
"""
add this line
10.0.1.1        rpi1
10.0.1.2        rpi2
10.0.1.3        rpi3
"""
```

``` bash
# test the new configuration
[sudo] ping rpi1 -c 1
```

``` bash
# Installing GlusterFS
[sudo] apt-get install glusterfs-server
```

``` bash
# Installing GlusterFS
[sudo] apt-get install glusterfs-server
```

``` bash
# Starting the demon
[sudo] service glusterd start
```

``` bash
# Showing the status of the Gluster
[sudo] service glusterd status
```

``` bash
# Probing the peers
[sudo] gluster peer probe rpi1
```

``` bash
# Showing the status of the peer
[sudo] service gluster peer status
```


### How To Create a Volume

``` bash
gluster volume create  transport tcp server1:/exp1 server2:/exp2
gluster volume create  replica 2 transport tcp server1:/exp1 server2:/exp2
gluster volume create  stripe 2 transport tcp server1:/exp1 server2:/exp2

```