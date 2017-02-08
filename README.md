## Invocation

export TASK=deploy-cluster
export CLUSTER_SIZE=3
ansible-playbook vessel.yml

* Currently only goes as far as building misconfigured bootstrap and cluster containers

To run from within a vessel container:
* docker build vessel
* docker run -e TASK=deploy-cluster -e CLUSTER_SIZE=3 -v /var/run/docker.sock:/var/run/docker.sock --privileged id

## TODO:
* Fix the my.cnf configuration for each of the boostrap and cluster hosts
* Do the current boostrap build work in the deploy-cluster playbook
* deploy the boostrap container
* wait for it to finish
* Do the current build work in the deploy-cluster playbook
* Deploy the cluster

Full process in theory would be:
* deploy the vesssel using ansible-container.
* invoke the vessel with parameters like '{"task":"deploy", "containers":3}'
* it builds the bootstrap container and bootstraps the db
* waits until the bootstrap process is done
* builds the cluster hosts and deploys them
* Add some other example of what can be done
 - add 2 nodes to the existing cluster '{"task":"add", "containers":2}'
 -  subtract?
 - heal a broken db
