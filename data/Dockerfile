FROM lgueye/mysql
MAINTAINER louis.gueye@gmail.com
ADD data-playbook.yml /tmp/data-playbook.yml
ADD data-vars.yml /tmp/data-vars.yml
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /tmp/data-playbook.yml
RUN echo "Done configuring data component"

