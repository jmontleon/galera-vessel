## Invocation

To run from within a vessel container:

To deploy a galera cluster:

* docker build vessel
* docker tag resulting-id galera-vessel
* docker run -v /var/lib/ansible-container:/var/lib/ansible-container -v /var/run/docker.sock:/var/run/docker.sock --privileged -t galera-vessel -e TOKEN=$(oc whoami -t) -e TASK=deploy-cluster -e CLUSTER_SIZE=3

To grow your existing galera cluster:
* docker run -v /var/lib/ansible-container:/var/lib/ansible-container -v /var/run/docker.sock:/var/run/docker.sock --privileged -t galera-vessel -e TOKEN=$(oc whoami -t) -e TASK=grow-cluster -e CLUSTER_SIZE=5 

To destroy the cluster - Use with caution. Right now this deletes the entire namesapce. Very overly destructive and WIP
* docker run -v /var/lib/ansible-container:/var/lib/ansible-container -v /var/run/docker.sock:/var/run/docker.sock --privileged -t galera-vessel -e TOKEN=$(oc whoami -t) -e TASK=destroy-cluster

## Parameters
CLUSTER_SIZE: Number of Replica to deploy.
MARIADB_DATABASE: database name to create, Default: mysql
MARIADB_PASSWORD: password for the database. Default: foo
MARIADB_ROOT_PASSWORD: root password. Used for galera sync as well. Default: sesame
MARIA_DB_USERNAME: username for the database. Default: admin
NAMESPACE: Namespace to deploy the cluster in. Default: galera
OPENSHIFT_SERVER_URL: URL for the Openshift server. Default: https://10.1.2.2:8443
TASK: Task to perform.
TOKEN: Token used to authenticate. You can find your token by running 'oc whoami -t'

## TODO:
* add shrink-cluster
* add heal cluster
* ???
* Profit
