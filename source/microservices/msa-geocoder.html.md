---
title: msa-geocoder
---

<a href="https://github.com/TheMicroservicesAgency/msa-geocoder"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Reverse geocoding as a simple offline service.

For a given latitude,longitude returns the matching country code, the administrative region and the name of the closest city (cities with population of 1000+, data from the [GeoNames project](http://www.geonames.org/).

Built using [reverse-geocoder](https://github.com/thampiman/reverse-geocoder), an updated version of [reverse_geocode](https://pypi.python.org/pypi/reverse_geocode/1.0).

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9908:80 msagency/msa-geocoder

## Example(s)

    $ curl "http://localhost:9908/geocoder?lat=45.5017&lon=-73.5673"
    {
      "admin1": "Quebec",
      "admin2": "Montreal",
      "cc": "CA",
      "lat": "45.50884",
      "lon": "-73.58781",
      "name": "Montreal"
    }

With a geojson Point :

    $ curl -X POST -H "Content-Type: application/json" "http://localhost:9908/geocoder" -d '{
      "coordinates": [
        15.087,
        37.503
      ],
      "type": "Point"
    }'

    {
      "admin1": "Sicily",
      "admin2": "Catania",
      "cc": "IT",
      "lat": "37.49223",
      "lon": "15.07041",
      "name": "Catania"
    }

## Endpoints

- GET [/geocoder?lat=XX.XX&lon=XX.XX](http://demo.microservices.agency:9908/geocoder?lat=45.536&lon=-73.620) : returns the location data for the given lat, lon
- POST [/geocoder]() : returns the location data for the given geojson Point

## Standard endpoints

- GET [/ms/version](http://demo.microservices.agency:9908/ms/version) : returns the version number
- GET [/ms/name](http://demo.microservices.agency:9908/ms/name) : returns the name
- GET [/ms/readme.md](http://demo.microservices.agency:9908/ms/readme.md) : returns the readme (this file)
- GET [/ms/readme.html](http://demo.microservices.agency:9908/ms/readme.html) : returns the readme as html
- GET [/swagger/swagger.json](http://demo.microservices.agency:9908/swagger/swagger.json) : returns the swagger api documentation
- GET [/swagger/#/](http://demo.microservices.agency:9908/swagger/#/) : returns swagger-ui displaying the api documentation
- GET [/nginx/stats.json](http://demo.microservices.agency:9908/nginx/stats.json) : returns stats about Nginx
- GET [/nginx/stats.html](http://demo.microservices.agency:9908/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
