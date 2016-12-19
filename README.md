# SYSCONF profile for an MongoDB service

This is a [SYSCONF](https://github.com/geonef/sysconf.base)
profile. SYSCONF is a method and tool to manage custom system files
for easy install, backup and sync.

This profile provides an [MongoDB](https://www.mongodb.com/) service.


## Services

```
# netstat -tlpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:27017           0.0.0.0:*               LISTEN      1834/mongod     
```

* The main service is MongoDB running on port 27017.


## Gitted import/export

This profile provides import/export for:
* Git's ```sysconf/``` directory <-> guest sysconf directory



## Gitted integration

* To create a new Gitted repository, follow the instructions at
  [How to setup Gitted for an tplication](http://gitted.io/tutorial/setup-gitted-sysconf/)
  
* Then add this Sysconf profile:
```
git subtree add -P sysconf.mongodb git@github.com:sysconf/sysconf.mongodb.git master
```

* Integrate it in the dependency chain, for example:
```
echo sysconf.gitted.mongodb >actual/deps
```

* Then push it to the container:
```
./gitted-target init lxc:mongodb
git push mongodb sysconf/master
```


## Authors

Written by Jean-Francois Gigand <jf@geonef.fr>. Feel free to contact me!
