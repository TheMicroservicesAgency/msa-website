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

- [/faker/locales](http://demo.microservices.agency:9902/faker/locales) : Get the list of supported locales

Check out the [swagger docs](http://demo.microservices.agency:9902/swagger/#/) for the full list of endpoints. Here are the main ones :

- [/faker/name](http://demo.microservices.agency:9902/faker/name)
- [/faker/phone-number](http://demo.microservices.agency:9902/faker/phone-number)
- [/faker/address/city](http://demo.microservices.agency:9902/faker/address/city)
- [/faker/address/street-name](http://demo.microservices.agency:9902/faker/address/street-name)
- [/faker/address/zip-code](http://demo.microservices.agency:9902/faker/address/zip-code)
- [/faker/address/time-zone](http://demo.microservices.agency:9902/faker/address/time-zone)
- [/faker/address/state](http://demo.microservices.agency:9902/faker/address/state)
- [/faker/address/country](http://demo.microservices.agency:9902/faker/address/country)
- [/faker/business/credit-card/number](http://demo.microservices.agency:9902/faker/business/credit-card/number)
- [/faker/commerce/department](http://demo.microservices.agency:9902/faker/commerce/department)
- [/faker/company/name](http://demo.microservices.agency:9902/faker/company/name)
- [/faker/company/catch-phrase](http://demo.microservices.agency:9902/faker/company/catch-phrase)
- [/faker/company/duns](http://demo.microservices.agency:9902/faker/company/duns)
- [/faker/book/title](http://demo.microservices.agency:9902/faker/book/title)
- [/faker/book/author](http://demo.microservices.agency:9902/faker/book/author)
- [/faker/book/publisher](http://demo.microservices.agency:9902/faker/book/publisher)
- [/faker/educator/university](http://demo.microservices.agency:9902/faker/educator/university)
- [/faker/educator/secondary-school](http://demo.microservices.agency:9902/faker/educator/secondary-school)
- [/faker/team/name](http://demo.microservices.agency:9902/faker/team/name)
- [/faker/team/sport](http://demo.microservices.agency:9902/faker/team/sport)
- [/faker/bitcoin/address](http://demo.microservices.agency:9902/faker/bitcoin/address)
- [/faker/codes/isbn](http://demo.microservices.agency:9902/faker/codes/isbn)
- [/faker/codes/imei](http://demo.microservices.agency:9902/faker/codes/imei)
- [/faker/color/hex](http://demo.microservices.agency:9902/faker/color/hex)
- [/faker/color/rgb](http://demo.microservices.agency:9902/faker/color/rgb)
- [/faker/color/hsl](http://demo.microservices.agency:9902/faker/color/hsl)
- [/faker/internet/email](http://demo.microservices.agency:9902/faker/internet/email)
- [/faker/internet/domain-name](http://demo.microservices.agency:9902/faker/internet/domain-name)
- [/faker/internet/ipv4](http://demo.microservices.agency:9902/faker/internet/ipv4)
- [/faker/internet/ipv6](http://demo.microservices.agency:9902/faker/internet/ipv6)
- [/faker/file/name](http://demo.microservices.agency:9902/faker/file/name)
- [/faker/file/extension](http://demo.microservices.agency:9902/faker/file/extension)
- [/faker/file/mime-type](http://demo.microservices.agency:9902/faker/file/mime-type)
- [/faker/hacker/abbreviation](http://demo.microservices.agency:9902/faker/hacker/abbreviation)
- [/faker/crypto/md5](http://demo.microservices.agency:9902/faker/crypto/md5)
- [/faker/crypto/sha1](http://demo.microservices.agency:9902/faker/crypto/sha1)
- [/faker/crypto/sha256](http://demo.microservices.agency:9902/faker/crypto/sha256)
- [/faker/app/name](http://demo.microservices.agency:9902/faker/app/name)
- [/faker/slack-emoji](http://demo.microservices.agency:9902/faker/slack-emoji)
- [/faker/superhero/name](http://demo.microservices.agency:9902/faker/superhero/name)
- [/faker/starwars/character](http://demo.microservices.agency:9902/faker/starwars/character)
- [/faker/starwars/planet](http://demo.microservices.agency:9902/faker/starwars/planet)
- [/faker/space/planet](http://demo.microservices.agency:9902/faker/space/planet)
- [/faker/space/moon](http://demo.microservices.agency:9902/faker/space/moon)
- [/faker/space/agency](http://demo.microservices.agency:9902/faker/space/agency)
- [/faker/gameofthrones/character](http://demo.microservices.agency:9902/faker/gameofthrones/character)
- [/faker/pokemon/name](http://demo.microservices.agency:9902/faker/pokemon/name)
- [/faker/beer/name](http://demo.microservices.agency:9902/faker/beer/name)
- [/faker/beer/alcohol](http://demo.microservices.agency:9902/faker/beer/alcohol)
- [/faker/lorem/paragraphs](http://demo.microservices.agency:9902/faker/lorem/paragraphs)
- [/faker/hipster/paragraphs](http://demo.microservices.agency:9902/faker/hipster/paragraphs)

## Standard endpoints

- [/ms/version](http://demo.microservices.agency:9902/ms/version) : returns the version number
- [/ms/name](http://demo.microservices.agency:9902/ms/name) : returns the name
- [/ms/readme.md](http://demo.microservices.agency:9902/ms/readme.md) : returns the readme (this file)
- [/ms/readme.html](http://demo.microservices.agency:9902/ms/readme.html) : returns the readme as html
- [/swagger/swagger.json](http://demo.microservices.agency:9902/swagger/swagger.json) : returns the swagger api documentation
- [/swagger/#/](http://demo.microservices.agency:9902/swagger/#/) : returns swagger-ui displaying the api documentation
- [/nginx/stats.json](http://demo.microservices.agency:9902/nginx/stats.json) : returns stats about Nginx
- [/nginx/stats.html](http://demo.microservices.agency:9902/nginx/stats.html) : returns a dashboard displaying the stats from Nginx


## About

A project by the [Microservices Agency](http://microservices.agency).
