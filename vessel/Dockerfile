FROM docker.io/jmontleon/base-ansible-vessel:latest
MAINTAINER Vessel Maintainers

RUN git clone http://github.com/jmontleon/galera-vessel /vessel
   
CMD ["/usr/bin/ansible-playbook", "/vessel/vessel.yml"]
