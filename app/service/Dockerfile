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
ADD app-playbook.yml /opt/playbook/app-playbook.yml
ADD cluster-app.yml /tmp/cluster-app.yml
ADD target/cluster-app-0.1-SNAPSHOT.jar /tmp/cluster-app.jar
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /opt/playbook/app-playbook.yml
RUN echo "Done installing app cluster"
EXPOSE 8080
ENTRYPOINT ["/bin/bash", "-c", "java -jar /tmp/cluster-app.jar --spring.config.name=cluster-app --spring.config.location=/tmp/"]

