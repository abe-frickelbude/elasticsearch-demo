# Basic Elasticsearch demo with DOCKER and Spring

---


## Pre-requisites

* git
* docker and docker-compose
* the most expensive thing of 'em all (Time & Patience!)

## Minimal HOWTO
1. clone the **elasticsearch-head** plugin : https://github.com/mobz/elasticsearch-head
2. clone the project 
3. go to /es-docker-image and do `docker build . -t es-demo`
3a. **important**: edit the _etc/sysctl.conf_ and add the following: **vm.max_map_count=262144** (without it, ES will refuse to start)
3b. restart the system (simply logging out / back in is insufficient!)
4. go back to the main dir and run `docker-compose up` to fire up a 3-node ES cluster, 
	or `docker-compose up es-master-node` to start a stand-alone ES node.
5. Open the index.html from previously cloned **elasticsearch-head** in your fav'rite browser (this is a stand-alone web-app)
6. type http://localhost:9200 into the box next to the connect button and hit **"Connect"**
7. Optionally, clone **ElasticsearchHQ** application: https://github.com/royrusso/elasticsearch-HQ
This allows for more comprehensive and user-friendly administration of the cluster (compared e.g. to elasticsearch-head)


## Notes 
* The node configuration attempts to be at least partially resource-friendly, default max java heap size per node is 256MB
(Can be adjusted in the *elasticsearch.yml* file via the ES_JAVA_OPTS environment variable)