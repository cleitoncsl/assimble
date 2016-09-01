1 - systemctl disable firewalld
2 - sestatus
3 - systemctl status firewalld
4 - SELINUX=disabled
5 - "yum install epel-release -y"
6 - "yum clean all ; yum update -y"
7 - "yum install java"
8 - "yum install pwgen"
8 - "rpm --import https://packages.elastic.co/GPG-KEY-elasticsearch"
9 -
"vim /etc/yum.repos.d/elasticsearch.repo

[mongodb-org-3.2]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.2/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.2.asc
"

10 - "yum install mongodb-org -y"

11 - systemctl daemon-reload
12 - systemctl enable mongod.service
13 - systemctl start mongod.service
14 - "rpm --import https://packages.elastic.co/GPG-KEY-elasticsearch"

15 - "vim /etc/yum.repos.d/elasticsearch.repo

[elasticsearch-2.x]
name=Elasticsearch repository for 2.x packages
baseurl=https://packages.elastic.co/elasticsearch/2.x/centos
gpgcheck=1
gpgkey=https://packages.elastic.co/GPG-KEY-elasticsearch
enabled=1
"

16 - "yum install elasticsearch -y"
17 - vim "/etc/elasticsearch/elasticsearch.yml"
18 - systemctl daemon-reload
19 - systemctl enable elasticsearch.service
20 - systemctl restart elasticsearch.service
21 - "rpm -Uvh https://packages.graylog2.org/repo/packages/graylog-2.1-repository_latest.rpm"
22 - "yum install graylog-server"
