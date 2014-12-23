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
ADD index-playbook.yml /opt/playbook/index-playbook.yml
ADD elasticsearch.yml.j2 /opt/playbook/elasticsearch.yml.j2
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /opt/playbook/index-playbook.yml
RUN echo "Done provisioning index cluster"
EXPOSE 9200
EXPOSE 9300
ENTRYPOINT ["/bin/bash", "-c", "/usr/share/elasticsearch/bin/elasticsearch -Des.default.config=/etc/elasticsearch/elasticsearch.yml -Des.default.path.home=/usr/share/elasticsearch -Des.default.path.logs=/var/log/elasticsearch -Des.default.path.data=/var/lib/elasticsearch -Des.default.path.work=/tmp/elasticsearch -Des.default.path.conf=/etc/elasticsearch"]



