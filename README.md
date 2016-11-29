# DataStax Enterprise Docker
**NOTE**: Not for production use!

This is a simple way to get DataStax Enterprise running with Solr.

## Requirements
You will need Docker and Docker Compose.

You will need DataStax Academy credentials to download the files, [register here](https://academy.datastax.com/).

The versions have been removed from the file names to simplify the Dockerfile and upgrades, so download the version you wish to use.

Ensure you have [downloaded](https://downloads.datastax.com/enterprise/) the following files from DataStax Enterprise:

`dse-bin.tar.gz`

`opscenter.tar.gz`

You will also need to [download](http://debian.datastax.com/enterprise/pool/) the following deb:

`datastax-agent_all.deb`

Place all of these renamed files at the root of the project.

## Building

Build both Docker images:

Ops Center: 

`docker build . -t dse-ops -f OpscDockerfile`

DSE: 

`docker build . -t dse`

## Running Instructions
The provided compose file will setup a single cassandra node with Solr, run the following command from the project root:

`docker-compose up -d`

The data and logs will be persisted in `/opt/docker/dse`.

More advanced running instructions can be found [here](http://www.datastax.com/wp-content/uploads/resources/DataStax-WP-Best_Practices_Running_DSE_Within_Docker.pdf).
