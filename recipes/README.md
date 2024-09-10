Docker **compose.yaml** file to run the three docker images of a *recipes* multi-tier application:
1. mongodb/mongodb-community-server:latest - a mongodb database
1. craigfoote/rest.recipes:latest - a Spring Boot rest service, depending on mongodb
1. craigfoote/ng.recipes:latest - an Angular web page, depending on the rest service

The mongodb database shares a host folder at `/opt/mongodb/data` to store its data (to persist between restarts) and listens on port 27017.

The rest service shares a host folder for logs at `/opt/rest.recipes/logs`. It listens on port 9000 and communicates with the mongodb on port 27017.

The angular UI listens on port 9001 and communicates with the rest servie on port 9000.

Start with `docker compose --verbose up -d` and test with http://localhost:9001.
