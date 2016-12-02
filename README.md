# Basic Elasticsearch demo with DOCKER and Spring

---


## Pre-requisites

* git
* docker and docker-compose
* the most expensive thing of 'em all (Time & Patience!)

## Official ES documentation

* https://www.elastic.co/guide/index.html
* https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html

## Minimal HOWTO
1. clone the **elasticsearch-head** plugin : https://github.com/mobz/elasticsearch-head
2. clone the project 
3. go to /es-docker-image and do `docker build . -t es-demo`
4. **important**: edit the `etc/sysctl.conf` file and add the following: `vm.max_map_count=262144` (without it, ES will refuse to start)
5. restart the system (simply logging out / back in is insufficient!)
6. go back to the main dir and run `docker-compose up` to fire up a 3-node ES cluster, 
	or `docker-compose up es-master-node` to start a stand-alone ES node.
7. Open the index.html from previously cloned **elasticsearch-head** in your fav'rite browser (this is a stand-alone web-app)
8. type **http://localhost:9200** into the box next to the connect button and hit **"Connect"**
9. Optionally, clone **ElasticsearchHQ** application: https://github.com/royrusso/elasticsearch-HQ
This allows for more comprehensive and user-friendly administration of the cluster (compared e.g. to elasticsearch-head)
10. Ready to go!

## Sample data source

The accompanying elasticsearch-demo-app (available here: https://github.com/abe-frickelbude/elasticsearch-demo-app.git) can
be used to create sample content for experimenting with basic ES features. 

### Pre-requisites

* maven
* jdk8 (preferrably oracle jdk)

### HOW-TO

1. clone the source
2. go into the base directory and do `mvn clean package`
3. go to `target` dir and do `java -jar elasticsearch-demo-app-1.0.jar`

The app will be available at `localhost:8080`

Available commands are currently:
* `/cluster_status` - shows cluster health
* `/sample-data/clear` - drops all sample indices
* `/sample-data/fill?num_samples=<n>`- prepares sample indices, n is the desired number of samples
* `sample-data/find/<index>/<id>`- find a dataset by index name and ID
* `sample-data/find/<index>/<type>/<id>` - ditto, but with type information as well

Check out the source code (based on Spring Boot) for more details - it is quite straightforward :)

## Notes 
* The node configuration attempts to be at least partially resource-friendly, default max java heap size per node is 256MB
(Can be adjusted in the *elasticsearch.yml* file via the ES_JAVA_OPTS environment variable)