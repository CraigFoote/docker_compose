Docker **compose.yaml** file to run the two docker images of a *galleries* multi-tier application:
1. craigfoote/rest.galleries:latest - a Spring Boot rest service accessing photos in the host
1. craigfoote/ng.web:latest - an Angular web page (Footeware.ca), depending on the rest service

The rest service shares a host folder for logs and another for storing data at `/opt/rest.galleries`.
Load that folder with subfolders containing pictures. The service listens on port 8000.

The Angular UI listens on port 443, communicating with the rest service on port 8000.

Start with `docker compose --verbose up -d` and test with http://localhost:8001.
