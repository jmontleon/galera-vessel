FROM centos:latest
MAINTAINER Vessel Maintainers

RUN yum install -y epel-release centos-release-openshift-origin
RUN yum install -y ansible \
                   git \
                   python-devel \
                   python-pip \
                   libyaml-devel \
                   gcc \
                   docker \
                   origin-clients
                  
RUN git clone http://github.com/jmontleon/vessel-scratch /vessel \
    && git clone http://github.com/ansible/ansible-container /ansible-container \
    && cd /ansible-container \
    && pip install --upgrade setuptools \
    && python ./setup.py install
   
CMD ["/usr/bin/ansible-playbook", "/vessel/vessel.yml"]
