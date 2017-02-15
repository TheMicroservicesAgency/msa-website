---
title: msa-geohash
---

<a href="https://github.com/TheMicroservicesAgency/msa-geohash"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Base32 Geoashing as a service. From wikipedia:

> Geohash is a geocoding system invented by Gustavo Niemeyer and placed into the public domain. It is a hierarchical spatial data structure which subdivides space into buckets of grid shape.

> Geohashes offer properties like arbitrary precision and the possibility of gradually removing characters from the end of the code to reduce its size (and gradually lose precision).

Built with [pygeohash](https://pypi.python.org/pypi/pygeohash) and [geojson](https://pypi.python.org/pypi/geojson).

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9907:80 msagency/msa-geohash

## Example(s)

To get a geohash from a pair of coordinates, you can use the /encode url :

    $ curl 'http://localhost:9907/geohash/encode?lat=45.53617&lon=-73.62075'
    {
      "geohash": "f25eh9x52jq4"
    }

The same url also handles geojson points, via a http POST :

    $ curl -XPOST 'http://localhost:9907/geohash/encode' -H 'Content-Type: application/json' -d '{
      "coordinates": [
        -73.62075,
        45.53617
      ],
      "type": "Point"
    }'

    {
      "geohash": "f25eh9x52jq4"
    }

Decoding the geohash will return the coordinates, in geojson :

    $ curl 'http://localhost:9907/geohash/decode/f25eh9x52jq4'
    {
      "coordinates": [
        -73.62075,
        45.53617
      ],
      "type": "Point"
    }

Geohashes can be shortened to modify the area they cover, this can be evaluated with the /precision url :

    $ curl 'http://localhost:9907/geohash/precision/f25eh9x52jq4'
    {
      "precision": {
        "number": 0.6,
        "unit": "meters"
      }
    }

    $ curl 'http://localhost:9907/geohash/precision/f25eh9'
    {
      "precision": {
        "number": 610,
        "unit": "meters"
      }
    }

By default the /decode function will return the center of the geohash area, however it's possible to get a more accurate decoding with the **exact=true** parameter. With this parameter a geojson polygon will be returned instead of a point, taking into account the margin of error of the geohash :

    $ curl 'http://localhost:9907/geohash/decode/f25eh9?exact=true'
    {
      "coordinates": [
        [
          [
            -73.63037109375,
            45.538330078125
          ],
          [
            -73.63037109375,
            45.5328369140625
          ],
          [
            -73.619384765625,
            45.5328369140625
          ],
          [
            -73.619384765625,
            45.538330078125
          ],
          [
            -73.63037109375,
            45.538330078125
          ]
        ]
      ],
      "type": "Polygon"
    }


## Endpoints

- GET [/geohash/encode/?lat=XX.XX&lon=XX.XX ](http://demo.microservices.agency:9907/geohash/encode?lat=45.53617&lon=-73.62075) Compute a geohash from the given lat,lon
- POST [/geohash/encode]() Computes a geohash from the given geojson point
- GET  [/geohash/decode/:geohash](http://demo.microservices.agency:9907/geohash/decode/f25eh9x52jq4) Decode a geohash, returns a geojson point
- GET  [/geohash/decode/:geohash?exact=true](http://demo.microservices.agency:9907/geohash/decode/f25eh9x52jq4) Decodes a geohash, return a geojson polygon
- GET  [/geohash/precision/:geohash](http://demo.microservices.agency:9907/geohash/precision/f25eh9x52jq4) Estimate the precision of a geohash

## Standard endpoints

- GET  [/ms/version](http://demo.microservices.agency:9907/ms/version) : returns the version number
- GET  [/ms/name](http://demo.microservices.agency:9907/ms/name) : returns the name
- GET  [/ms/readme.md](http://demo.microservices.agency:9907/ms/readme.md) : returns the readme (this file)
- GET  [/ms/readme.html](http://demo.microservices.agency:9907/ms/readme.html) : returns the readme as html
- GET  [/swagger/swagger.json](http://demo.microservices.agency:9907/swagger/swagger.json) : returns the swagger api documentation
- GET  [/swagger/#/](http://demo.microservices.agency:9907/swagger/#/) : returns swagger-ui displaying the api documentation
- GET  [/nginx/stats.json](http://demo.microservices.agency:9907/nginx/stats.json) : returns stats about Nginx
- GET  [/nginx/stats.html](http://demo.microservices.agency:9907/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
