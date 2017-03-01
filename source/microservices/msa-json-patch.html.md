---
title: msa-json-patch
---

<a href="https://github.com/TheMicroservicesAgency/msa-json-patch"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Microservice to generate a diff ([RFC 6902](https://tools.ietf.org/html/rfc6902)) between two json documents A & B, that can be also used to transform/patch document A into document B.

If you have a given JSON document with a series of updates, this can be used to reduce the amount of data to send over the wire.

Built using [jsonpatch](https://pypi.python.org/pypi/jsonpatch).

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9909:80 msagency/msa-json-patch

## Example(s)


    $ curl -X POST "http://localhost:9909/json/diff" -H "Content-Type: application/json" \
    -d '[{"name": "test","val": 10}, {"name": "test","val": 20}]'
    {
      "data": "[{\"op\": \"replace\", \"value\": 20, \"path\": \"/val\"}]"
    }

    $ curl -X POST "http://localhost:9909/json/patch" -H "Content-Type: application/json" \
    -d '[{"name": "test","val": 10}, [{ "op": "replace","path": "/val", "value": 20}]]'
    {
      "data": {
        "name": "test",
        "val": 20
      }
    }

## Endpoints

- POST [/json/diff]() : Returns a diff between two JSON documents A and B. Expected input is [A,B]
- POST [/json/patch]() : Returns the generated document B from patching the document A. Expected input is [A, patch]

## Standard endpoints

- GET [/ms/version](http://demo.microservices.agency:9909/ms/version) : returns the version number
- GET [/ms/name](http://demo.microservices.agency:9909/ms/name) : returns the name
- GET [/ms/readme.md](http://demo.microservices.agency:9909/ms/readme.md) : returns the readme (this file)
- GET [/ms/readme.html](http://demo.microservices.agency:9909/ms/readme.html) : returns the readme as html
- GET [/swagger/swagger.json](http://demo.microservices.agency:9909/swagger/swagger.json) : returns the swagger api documentation
- GET [/swagger/#/](http://demo.microservices.agency:9909/swagger/#/) : returns swagger-ui displaying the api documentation
- GET [/nginx/stats.json](http://demo.microservices.agency:9909/nginx/stats.json) : returns stats about Nginx
- GET [/nginx/stats.html](http://demo.microservices.agency:9909/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
