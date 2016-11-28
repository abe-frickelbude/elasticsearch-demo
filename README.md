# Basic Elasticsearch demo with DOCKER and Spring

---

## Pre-requisits

* git
* docker and docker-compose
* the most expensive thing of 'em all (Time & Patience!)

## Minimal HOWTO
1. clone the **elasticsearch-head** plugin : https://github.com/mobz/elasticsearch-head
2. clone the project 
3. go to /es-docker-image and do `docker build . -t es-demo`
4. go back to the main dir and run `docker-compose up` to fire up a 3-node ES cluster, 
	or `docker-compose up es-master-node` to start a standalone ES node.
5. Open the index.html from previously cloned **elasticsearch-head** in your fav'rite browser (this is a standalone web-app)
6. type http://localhost:9200 into the box next to the connect button and hit **"Connect"**



## Notes 
* The node configuration attemps to be at least partially resource-friendly, default max java heap size per node is 512MB
(Can be adjusted in the *elasticsearch.yml* file via the ES_JAVA_OPTS environment variable)