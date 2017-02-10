## Invocation

To run from within a vessel container:

To deploy a galera cluster:

* docker build vessel
* docker tag resulting-id galera-vessel
* docker run -e TOKEN=$(oc whoami -t) -e TASK=deploy-cluster -e CLUSTER_SIZE=3 -v /var/run/docker.sock:/var/run/docker.sock --privileged -t galera-vessel

To grow your existing galera cluster:
* docker run -e TOKEN=$(oc whoami -t) -e TASK=grow-cluster -e CLUSTER_SIZE=5 -v /var/run/docker.sock:/var/run/docker.sock --privileged -t galera-vessel

## TODO:
* add shrink-cluster
* add heal cluster
* use an image with packages already installed to speed up deploy process
* parameterize server address. right now it's hard coded to https://10.1.2.2
* parameterize project/namespace. right now it does everything in the galera project/namespace
* ???
* Profit
