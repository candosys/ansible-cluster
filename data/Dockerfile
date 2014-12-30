FROM lgueye/ansible
MAINTAINER louis.gueye@gmail.com
RUN mkdir /opt/playbook
ADD data-playbook.yml /opt/playbook/data-playbook.yml
ADD data-vars.yml /opt/playbook/data-vars.yml
ADD my.cnf.j2 /opt/playbook/my.cnf.j2
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /opt/playbook/data-playbook.yml
RUN echo "Done provisioning data cluster"
EXPOSE 3306
ENTRYPOINT ["/usr/bin/mysqld_safe"]

