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
RUN ansible-playbook --inventory-file=/etc/ansible/hosts /opt/playbook/app-playbook.yml
RUN echo "Done provisioning app cluster"
EXPOSE 8080
ENTRYPOINT ["/bin/bash", "-c", "java -jar /opt/service/target/cluster-app-0.0.1-SNAPSHOT.jar --spring.config.name=cluster-app --spring.config.location=/opt/service/"]

