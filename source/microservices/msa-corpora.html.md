---
title: msa-corpora
---

<a href="https://github.com/TheMicroservicesAgency/msa-corpora"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

A collection of small corpuses of interesting data, available via a REST API.

Data from [https://github.com/dariusk/corpora](https://github.com/dariusk/corpora), Licensed under CC0

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9903:80 msagency/msa-corpora

## Example(s)


    $ curl http://localhost:9903/corpora/data/mathematics/primes.json

    {
      "description": "The first 1000 prime numbers.",
      "primes": [
        2,
        3,
        5,
        7,
    ...

    $ curl http://localhost:9903/corpora/data/foods/vegetables.json
    {
      "description": "A list of vegetables.",
      "vegetables": [
        "acorn squash",
        "alfalfa sprout",
        "amaranth",
        "anise",
        "artichoke",
    ...


## Endpoints

The complete list can in found in the [swagger documentation](http://demo.microservices.agency:9903/swagger/#/).

Here are a few interesting ones :

- [/corpora/data/foods/sandwiches.json](http://demo.microservices.agency:9903/corpora/data/foods/sandwiches.json)
- [/corpora/data/foods/condiments.json](http://demo.microservices.agency:9903/corpora/data/foods/condiments.json)
- [/corpora/data/foods/fruits.json](http://demo.microservices.agency:9903/corpora/data/foods/fruits.json)
- [/corpora/data/foods/tea.json](http://demo.microservices.agency:9903/corpora/data/foods/tea.json)
- [/corpora/data/medicine/diagnoses.json](http://demo.microservices.agency:9903/corpora/data/medicine/diagnoses.json)
- [/corpora/data/medicine/drugs.json](http://demo.microservices.agency:9903/corpora/data/medicine/drugs.json)
- [/corpora/data/colors/palettes.json](http://demo.microservices.agency:9903/corpora/data/colors/palettes.json)
- [/corpora/data/colors/crayola.json](http://demo.microservices.agency:9903/corpora/data/colors/crayola.json)
- [/corpora/data/film-tv/netflix-categories.json](http://demo.microservices.agency:9903/corpora/data/film-tv/netflix-categories.json)
- [/corpora/data/film-tv/tv-shows.json](http://demo.microservices.agency:9903/corpora/data/film-tv/tv-shows.json)
- [/corpora/data/science/toxic-chemicals.json](http://demo.microservices.agency:9903/corpora/data/science/toxic-chemicals.json)
- [/corpora/data/science/elements.json](http://demo.microservices.agency:9903/corpora/data/science/elements.json)
- [/corpora/data/technology/programming-languages.json](http://demo.microservices.agency:9903/corpora/data/technology/programming-languages.json)
- [/corpora/data/technology/social-networking-websites.json](http://demo.microservices.agency:9903/corpora/data/technology/social-networking-websites.json)
- [/corpora/data/mythology/greek-gods.json](http://demo.microservices.agency:9903/corpora/data/mythology/greek-gods.json)
- [/corpora/data/mythology/greek-monsters.json](http://demo.microservices.agency:9903/corpora/data/mythology/greek-monsters.json)
- [/corpora/data/geography/london-underground-stations.json](http://demo.microservices.agency:9903/corpora/data/geography/london-underground-stations.json)
- [/corpora/data/geography/canadian-municipalities.json](http://demo.microservices.agency:9903/corpora/data/geography/canadian-municipalities.json)
- [/corpora/data/games/wrestling-moves.json](http://demo.microservices.agency:9903/corpora/data/games/wrestling-moves.json)
- [/corpora/data/games/pokemon.json](http://demo.microservices.agency:9903/corpora/data/games/pokemon.json)
- [/corpora/data/words/encouraging-words.json](http://demo.microservices.agency:9903/corpora/data/words/encouraging-words.json)
- [/corpora/data/words/personal-nouns.json](http://demo.microservices.agency:9903/corpora/data/words/personal-nouns.json)
- [/corpora/data/words/adjs.json](http://demo.microservices.agency:9903/corpora/data/words/adjs.json)
- [/corpora/data/words/verbs.json](http://demo.microservices.agency:9903/corpora/data/words/verbs.json)
- [/corpora/data/words/stopwords/en.json](http://demo.microservices.agency:9903/corpora/data/words/stopwords/en.json)

## Standard endpoints

- [/ms/version](http://demo.microservices.agency:9903/ms/version) : returns the version number
- [/ms/name](http://demo.microservices.agency:9903/ms/name) : returns the name
- [/ms/readme.md](http://demo.microservices.agency:9903/ms/readme.md) : returns the readme (this file)
- [/ms/readme.html](http://demo.microservices.agency:9903/ms/readme.html) : returns the readme as html
- [/swagger/swagger.json](http://demo.microservices.agency:9903/swagger/swagger.json) : returns the swagger api documentation
- [/swagger/#/](http://demo.microservices.agency:9903/swagger/#/) : returns swagger-ui displaying the api documentation
- [/nginx/stats.json](http://demo.microservices.agency:9903/nginx/stats.json) : returns stats about Nginx
- [/nginx/stats.html](http://demo.microservices.agency:9903/nginx/stats.html) : returns a dashboard displaying the stats from Nginx


## About

A project by the [Microservices Agency](http://microservices.agency).
