FROM ubuntu:14.04
MAINTAINER louis.gueye@gmail.com
RUN apt-get update
RUN apt-get install -y python-software-properties
RUN apt-get install -y software-properties-common
RUN apt-get update
RUN apt-add-repository ppa:ansible/ansible
RUN apt-get update
RUN apt-get install -y ansible
RUN mkdir /opt/playbook
ADD data-playbook.yml /opt/playbook/data-playbook.yml
ADD my.cnf.j2 /opt/playbook/my.cnf.j2
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /opt/playbook/data-playbook.yml
RUN echo "Done installing data cluster"
EXPOSE 3306
ENTRYPOINT ["/usr/bin/mysqld_safe"]

