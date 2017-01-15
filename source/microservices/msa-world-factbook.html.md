---
title: msa-world-factbook
---

<a href="https://github.com/TheMicroservicesAgency/msa-world-factbook"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Semi structured API for the CIA World Factbook, a reference of information for 267 countries.

Built with the [factbook](https://github.com/factbook/factbook) ruby gem.

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9904:80 msagency/msa-world-factbook

## Example(s)

To get the list of countries :

    $ curl http://localhost:9904/factbook/codes
    {
      "codes": [
        {
          "code": "af",
          "name": "Afghanistan",
          "category": "Countries",
          "region": "South Asia"
        },
        {
          "code": "al",
          "name": "Albania",
          "category": "Countries",
          "region": "Europe"
        },
        ...

To get the list of attributes :

    $ curl http://localhost:9904/factbook/attributes
    {
      "background": "Background",
      "location": "Location",
      "coords": "Geographic coordinates",
      "map": "Map references",
      "area": "Area › total",
      "area-land": "Area › land",
      "area-water": "Area › water",
      "area-note": "Area › note",

All the data is in text format, but the app will try to extract the numbers from the text for convenience :

    $ curl http://localhost:9904/factbook/br/area
    {
      "country-code": "br",
      "country-name": "Brazil",
      "area": {
        "text": "8,515,770 sq km",
        "numbers": [
          8515770.0
        ]
      }


    $ curl http://localhost:9904/factbook/us/area
    {
      "country-code": "us",
      "country-name": "United States",
      "area": {
        "text": "9,833,517 sq km",
        "numbers": [
          9833517.0
        ]
      }

Without a specific attribute, a summary of all the data for this country will be returned :

    $ curl http://localhost:9904/factbook/br
    {
      "country-code": "br",
      "country-name": "Brazil",
      "data": {
        "Introduction": {
          "Background": {
            "text": "Following more than three centuries under Portuguese rule, ..."
          }
        },
        "Geography": {
          "Location": {
            "text": "Eastern South America, bordering the Atlantic Ocean"
          },
          "Geographic coordinates": {
            "text": "10 00 S, 55 00 W"
          },
          "Map references": {
            "text": "South America"
          },
          ...

## Endpoints

- [/factbook/codes](http://demo.microservices.agency:9904/factbook/codes) : Returns the list of country codes
- [/factbook/attributes](http://demo.microservices.agency:9904/factbook/attributes) : Returns the list of country attributes
- [/factbook/:code](http://demo.microservices.agency:9904/factbook/br) : Returns a summary of all the data for a given country
- [/factbook/:code/:attribute](http://demo.microservices.agency:9904/factbook/br/taxes) : Returns the data for the specified attribute for a given country

## Standard endpoints

- [/ms/version](http://demo.microservices.agency:9904/ms/version) : returns the version number
- [/ms/name](http://demo.microservices.agency:9904/ms/name) : returns the name
- [/ms/readme.md](http://demo.microservices.agency:9904/ms/readme.md) : returns the readme (this file)
- [/ms/readme.html](http://demo.microservices.agency:9904/ms/readme.html) : returns the readme as html
- [/swagger/swagger.json](http://demo.microservices.agency:9904/swagger/swagger.json) : returns the swagger api documentation
- [/swagger/#/](http://demo.microservices.agency:9904/swagger/#/) : returns swagger-ui displaying the api documentation
- [/nginx/stats.json](http://demo.microservices.agency:9904/nginx/stats.json) : returns stats about Nginx
- [/nginx/stats.html](http://demo.microservices.agency:9904/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
