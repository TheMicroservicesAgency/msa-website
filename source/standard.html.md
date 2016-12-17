---
title: The Standard
---

Every microservice from the MSA should have the following
characteristics :

# 1. Fast installation / deployement

It should take less than five minutes to try out a new microservice.

By providing the microservices in the form of containers, they will be executable with a single command. Download of the containers images may take some time, but no additional configuration should be required.

# 2. Documentation and examples

Every microservice will have a README.md file, explaining what is the  microservice and what it does with a few examples.

The README.md will serve as a quick guide, but machine-readable API documentation such as Swagger.json files will be the comprehensive reference.


# 3. Standardized APIs

All the functionality of the microservices will be provided via RESTful APIs.

Each microservice will have a different API depending on functionality, but all of them will share a few common endpoints :

[/ms/version]() : return the version number of the service

[/ms/name]() : return the name of the service

[/ms/readme.md]() : return the readme of the service in markdown format

[/ms/readme.html]() : return the readme of the service in html format

[/swagger/swagger.json]() : returns the swagger api documentation

[/swagger/#/]() : returns swagger-ui displaying the api documentation

[/nginx/stats.html]() : returns a dashboard displaying the stats from Nginx

[/nginx/stats.json]() : returns stats about Nginx in json
