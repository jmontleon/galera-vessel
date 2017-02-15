FROM docker.io/jmontleon/base-ansible-vessel:latest
MAINTAINER Vessel Maintainers

RUN git clone http://github.com/jmontleon/galera-vessel /vessel && cd /vessel && git checkout remove-ansible-container
   
CMD ["/usr/bin/ansible-playbook", "/vessel/vessel.yml"]
