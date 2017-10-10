# distributed-systems-elasticsearch
Distributed Systems - Elasticsearch

## Download and install the .tar.gz package

```
$ sudo apt install openjdk-8-jdk 
$ wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.6.2.tar.gz
$ sha1sum elasticsearch-5.6.2.tar.gz 
$ tar -xzf elasticsearch-5.6.2.tar.gz
$ cd elasticsearch-5.6.2/ 
```

## Install Elasticsearch with Debian Package

```
$ wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
$ sudo apt-get install apt-transport-https
$ echo "deb https://artifacts.elastic.co/packages/5.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-5.x.list
$ sudo apt-get update && sudo apt-get install elasticsearch
```

## Docker

```
$ sudo docker pull docker.elastic.co/elasticsearch/elasticsearch:5.6.2
$ sudo docker pull docker.elastic.co/kibana/kibana:5.6.2
$ sudo docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:5.6.2
```
### Error: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

```
$ sudo sysctl -w vm.max_map_count=262144

$ echo "vm.max_map_count=262144" | sudo tee -a /etc/sysctl.conf > /dev/null
$ sudo echo "vm.max_map_count=262144" >> /etc/sysctl.conf
```

### elasticsearch.yml

```
network.host: 0.0.0.0
```

### kibana.yml

```
server.host: "0.0.0.0"
```
