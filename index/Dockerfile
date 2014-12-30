FROM lgueye/elasticsearch
MAINTAINER louis.gueye@gmail.com
ADD index-playbook.yml /tmp/index-playbook.yml
ADD index-vars.yml /tmp/index-vars.yml
ADD elasticsearch.yml.j2 /tmp/elasticsearch.yml.j2
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /tmp/index-playbook.yml
RUN echo "Done configuring index component"



