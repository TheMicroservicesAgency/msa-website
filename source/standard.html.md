---
title: The Standard
---

Every microservice from the MSA should have the following
characteristics :

# 1. Fast installation / deployement

It should take less than five minutes to be able to try out a new microservice.

By providing the microservices in the form of containers, they should be executable with a single command. Download of the containers images may take some time, but no additionnal configuration should be required.

# 2. Documentation and examples

Every microservice will have a README.md file, explaining what is the  microservice and what it does with a few examples.

The README.md should serve as a quick guide, but machine-readable API documentation such as Swagger.json files should be the comprehensive reference.


# 3. Standardized APIs

All the functionality of the microservices will be provided via RESTful APIs.

Each microservice will have a different API depending on functionality, but all of them will share a few common endpoints :

[/version]() : return the version number of the service

[/name]() : return the name of the service

[/readme]() : return the Readme of the service

[/swagger]() :

[/swagger/swagger.json]() :

[/nginx/status]() :

[/nginx/status.json]() :
