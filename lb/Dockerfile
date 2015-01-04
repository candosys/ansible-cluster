FROM lgueye/haproxy
MAINTAINER louis.gueye@gmail.com
ADD lb-playbook.yml /tmp/lb-playbook.yml
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /tmp/lb-playbook.yml
RUN echo "Done configuring lb component"

