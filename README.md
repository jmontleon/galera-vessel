## Invocation

export TASK=deploy-cluster
export CLUSTER_SIZE=3
ansible-playbook vessel.yml

## TODO:
* Currently only goes as far as building three misconfigured containers
* Need to build a bootstrap container
* Run it
* Fix the my.cnf configuration for each of the cluster hosts
* Do the current build work
* Deploy the cluster
* Package up ansible-container, ansible, and this work into a 'vessel' container


Full process in theory would be:
* deploy the vesssel using ansible-container.
* invoke the vessel with parameters like '{"task":"deploy" "containers":3}'
* it builds the bootstrap container and bootstraps the db
* waits until the bootstrap process is done
* builds the cluster hosts and deploys them
* Add some other example of what can be done
 - add 2 nodes to the existing cluster
 -  subtract?
 - heal a broken db
