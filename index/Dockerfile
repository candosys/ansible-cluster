FROM lgueye/oracle-jdk8
MAINTAINER louis.gueye@gmail.com
RUN mkdir /opt/playbook
ADD index-playbook.yml /opt/playbook/index-playbook.yml
ADD index-vars.yml /opt/playbook/index-vars.yml
ADD elasticsearch.yml.j2 /opt/playbook/elasticsearch.yml.j2
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /opt/playbook/index-playbook.yml
RUN echo "Done provisioning index cluster"
EXPOSE 9200
EXPOSE 9300
ENTRYPOINT ["/bin/bash", "-c", "/usr/share/elasticsearch/bin/elasticsearch -Des.default.config=/etc/elasticsearch/elasticsearch.yml -Des.default.path.home=/usr/share/elasticsearch -Des.default.path.logs=/var/log/elasticsearch -Des.default.path.data=/var/lib/elasticsearch -Des.default.path.work=/tmp/elasticsearch -Des.default.path.conf=/etc/elasticsearch"]



