---
title: msa-faker
---

<a href="https://github.com/TheMicroservicesAgency/msa-faker"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Faker data generator, built around the [faker](https://github.com/stympy/faker) ruby gem.

Can generate names, addresses, phone numbers and much more. Also comes with support for various locales.

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9902:80 msagency/msa-faker

## Example(s)


    $ curl http://localhost:9902/faker/name
    Warren Bins

    $  curl http://localhost:9902/faker/name?locale=fr
    Noémie Clement

    $ curl http://localhost:9902/faker/address/city?locale=sv
    Östertuna


## Endpoints

The locale parameter can be optionally supplied to any endpoint to change the locality of the generated data. This has mainly an effect on the endpoints like **/faker/name** and **/faker/address**, but will probably not change anything on endpoints like **/faker/code** or **/faker/internet**. You can check the support for each locale at [https://github.com/stympy/faker/tree/master/lib/locales](https://github.com/stympy/faker/tree/master/lib/locales), and get the list with:

- GET [/faker/locales](http://demo.microservices.agency:9902/faker/locales) : Get the list of supported locales

Check out the [swagger docs](http://demo.microservices.agency:9902/swagger/#/) for the full list of endpoints. Here are the main ones :

- GET [/faker/name](http://demo.microservices.agency:9902/faker/name)
- GET [/faker/phone-number](http://demo.microservices.agency:9902/faker/phone-number)
- GET [/faker/address/city](http://demo.microservices.agency:9902/faker/address/city)
- GET [/faker/address/street-name](http://demo.microservices.agency:9902/faker/address/street-name)
- GET [/faker/address/zip-code](http://demo.microservices.agency:9902/faker/address/zip-code)
- GET [/faker/address/time-zone](http://demo.microservices.agency:9902/faker/address/time-zone)
- GET [/faker/address/state](http://demo.microservices.agency:9902/faker/address/state)
- GET [/faker/address/country](http://demo.microservices.agency:9902/faker/address/country)
- GET [/faker/business/credit-card/number](http://demo.microservices.agency:9902/faker/business/credit-card/number)
- GET [/faker/commerce/department](http://demo.microservices.agency:9902/faker/commerce/department)
- GET [/faker/company/name](http://demo.microservices.agency:9902/faker/company/name)
- GET [/faker/company/catch-phrase](http://demo.microservices.agency:9902/faker/company/catch-phrase)
- GET [/faker/company/duns](http://demo.microservices.agency:9902/faker/company/duns)
- GET [/faker/book/title](http://demo.microservices.agency:9902/faker/book/title)
- GET [/faker/book/author](http://demo.microservices.agency:9902/faker/book/author)
- GET [/faker/book/publisher](http://demo.microservices.agency:9902/faker/book/publisher)
- GET [/faker/educator/university](http://demo.microservices.agency:9902/faker/educator/university)
- GET [/faker/educator/secondary-school](http://demo.microservices.agency:9902/faker/educator/secondary-school)
- GET [/faker/team/name](http://demo.microservices.agency:9902/faker/team/name)
- GET [/faker/team/sport](http://demo.microservices.agency:9902/faker/team/sport)
- GET [/faker/bitcoin/address](http://demo.microservices.agency:9902/faker/bitcoin/address)
- GET [/faker/codes/isbn](http://demo.microservices.agency:9902/faker/codes/isbn)
- GET [/faker/codes/imei](http://demo.microservices.agency:9902/faker/codes/imei)
- GET [/faker/color/hex](http://demo.microservices.agency:9902/faker/color/hex)
- GET [/faker/color/rgb](http://demo.microservices.agency:9902/faker/color/rgb)
- GET [/faker/color/hsl](http://demo.microservices.agency:9902/faker/color/hsl)
- GET [/faker/internet/email](http://demo.microservices.agency:9902/faker/internet/email)
- GET [/faker/internet/domain-name](http://demo.microservices.agency:9902/faker/internet/domain-name)
- GET [/faker/internet/ipv4](http://demo.microservices.agency:9902/faker/internet/ipv4)
- GET [/faker/internet/ipv6](http://demo.microservices.agency:9902/faker/internet/ipv6)
- GET [/faker/file/name](http://demo.microservices.agency:9902/faker/file/name)
- GET [/faker/file/extension](http://demo.microservices.agency:9902/faker/file/extension)
- GET [/faker/file/mime-type](http://demo.microservices.agency:9902/faker/file/mime-type)
- GET [/faker/hacker/abbreviation](http://demo.microservices.agency:9902/faker/hacker/abbreviation)
- GET [/faker/crypto/md5](http://demo.microservices.agency:9902/faker/crypto/md5)
- GET [/faker/crypto/sha1](http://demo.microservices.agency:9902/faker/crypto/sha1)
- GET [/faker/crypto/sha256](http://demo.microservices.agency:9902/faker/crypto/sha256)
- GET [/faker/app/name](http://demo.microservices.agency:9902/faker/app/name)
- GET [/faker/slack-emoji](http://demo.microservices.agency:9902/faker/slack-emoji)
- GET [/faker/superhero/name](http://demo.microservices.agency:9902/faker/superhero/name)
- GET [/faker/starwars/character](http://demo.microservices.agency:9902/faker/starwars/character)
- GET [/faker/starwars/planet](http://demo.microservices.agency:9902/faker/starwars/planet)
- GET [/faker/space/planet](http://demo.microservices.agency:9902/faker/space/planet)
- GET [/faker/space/moon](http://demo.microservices.agency:9902/faker/space/moon)
- GET [/faker/space/agency](http://demo.microservices.agency:9902/faker/space/agency)
- GET [/faker/gameofthrones/character](http://demo.microservices.agency:9902/faker/gameofthrones/character)
- GET [/faker/pokemon/name](http://demo.microservices.agency:9902/faker/pokemon/name)
- GET [/faker/beer/name](http://demo.microservices.agency:9902/faker/beer/name)
- GET [/faker/beer/alcohol](http://demo.microservices.agency:9902/faker/beer/alcohol)
- GET [/faker/lorem/paragraphs](http://demo.microservices.agency:9902/faker/lorem/paragraphs)
- GET [/faker/hipster/paragraphs](http://demo.microservices.agency:9902/faker/hipster/paragraphs)

## Standard endpoints

- GET [/ms/version](http://demo.microservices.agency:9902/ms/version) : returns the version number
- GET [/ms/name](http://demo.microservices.agency:9902/ms/name) : returns the name
- GET [/ms/readme.md](http://demo.microservices.agency:9902/ms/readme.md) : returns the readme (this file)
- GET [/ms/readme.html](http://demo.microservices.agency:9902/ms/readme.html) : returns the readme as html
- GET [/swagger/swagger.json](http://demo.microservices.agency:9902/swagger/swagger.json) : returns the swagger api documentation
- GET [/swagger/#/](http://demo.microservices.agency:9902/swagger/#/) : returns swagger-ui displaying the api documentation
- GET [/nginx/stats.json](http://demo.microservices.agency:9902/nginx/stats.json) : returns stats about Nginx
- GET [/nginx/stats.html](http://demo.microservices.agency:9902/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
