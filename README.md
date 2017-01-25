# K8s MariaDB Galera init container

Docker image of initialization container to initialize [MariaDB][mariadb-image] cluster as Kubernetes StatefulSet.

Based on Alpine Linux. Uses [peer-finder.go][peer-finder] util from Kibernetes contrib.

## Settings

Arguments:
 
 * `-service=mysql` - The service name to lookup peers passed to [peer-finder]. 

Environment variables and defaults:

* `POD_NAMESPACE` - The namespace, e.g. `default`
* `GALERA_CONFIG=/etc/mysql/conf.d/galera.cnf` - The location of galera config file.
* `CLUSTER_NAME=mysql` - The cluster name.

[peer-finder]: https://github.com/kubernetes/contrib/blob/master/pets/peer-finder/peer-finder.go
[mariadb-image]: https://hub.docker.com/_/mariadb/
