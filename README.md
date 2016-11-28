# Basic Elasticsearch demo with DOCKER and Spring

---

## Pre-requisits

* git
* docker and docker-compose
* the most expensive thing of 'em all (Time & Patience!)

## Minimal HOWTO
1. close the **elasticsearch-head** plugin : https://github.com/mobz/elasticsearch-head
2. clone the project
3. go to /es-docker-image and do `docker build . -t es-demo`
4. go back to the main dir and run `docker-compose up` to fire up a 3-node ES cluster, 
	or `docker-compose up es-master-node` to start a standalone ES node.




