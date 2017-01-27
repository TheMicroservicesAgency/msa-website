---
title: msa-string-similarity
---

<a href="https://github.com/TheMicroservicesAgency/msa-string-similarity"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Various algorithms to mesure the similarity of N strings.

Built with [Harry](https://github.com/rieck/harry), licensed under the GPLv3. From the Harry documentation :

> The tool supports several common distance and kernel functions for strings as well as some excotic similarity measures. The focus of Harry lies on implicit similarity measures, that is, comparison functions that do not give rise to an explicit vector space. Examples of such similarity measures are the Levenshtein distance, the Jaro-Winkler distance or the spectrum kernel.

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9906:80 msagency/msa-string-similarity

## Examples

If no algorithm is specified, the program will use dist_levenshtein by default.
From wikipedia :

> In information theory and computer science, the Levenshtein distance is a string metric for measuring the difference between two sequences. Informally, the Levenshtein distance between two words is the minimum number of single-character edits (i.e. insertions, deletions or substitutions) required to change one word into the other.


    curl -XPOST 'localhost:9906/similarity' \
    -H 'Content-Type: application/json' \
    -d '[ "string1", "string2" ]'

    [[0.0, 1.0], [1.0, 0.0]]

The result is a matrix of the computed similarity values, in JSON.

To get the list of supported algorithms, get the /similarity/algorithms url :

    curl http://localhost:9906/similarity/algorithms

    {
      "algorithms": [
        {
          "algorithm": "kern_subsequence",
          "name": "Subsequence kernel",
          "reference": "Lodhi, Saunders, Shawe-Taylor, Cristianini, and Watkins...",
          "reference-url": "/similarity/references/kern_subsequence.pdf"
        },
        {
          "algorithm": "dist_damerau",
          "name": "Damerau-Levenshtein distance for strings",
          "reference": "Damerau. A technique for computer detection...",
          "reference-url": "/similarity/references/dist_damerau.pdf"
        },
      ...


To change the algorithm, just add the algorithm name as a parameter to the request :

    curl -XPOST 'localhost:9906/similarity?algorithm=dist_hamming' \
    -H 'Content-Type: application/json' \
    -d '[ "this is a string", "this is another string" ]'

    [[0.0, 12.0], [12.0, 0.0]]

Another example, but this time with the Jaro–Winkler distance and the granularity parameter. See [Bytes, Bits and Tokens](https://github.com/rieck/harry/blob/master/examples/TUTORIAL.md#bytes-bits-and-tokens) in the Harry documentation.

    curl -XPOST 'localhost:9906/similarity?algorithm=dist_jarowinkler&granularity=bits' \
    -H 'Content-Type: application/json' \
    -d '[ "this is a test string", "this is also a test string" ]'

    [[0.0, 0.0035714285913854837], [0.0035714285913854837, 0.0]]


## Endpoints

- [/similarity]() : computes the similarity between N strings
- [/similarity/algorithms](http://demo.microservices.agency:9906/similarity/algorithms) : list the supported algorithms
- [/similarity/references/:algorithm](http://demo.microservices.agency:9906/similarity/references/dist_levenshtein.pdf) : documentation available for a given algorithm


## Standard endpoints

- [/ms/version](http://demo.microservices.agency:9906/ms/version) : returns the version number
- [/ms/name](http://demo.microservices.agency:9906/ms/name) : returns the name
- [/ms/readme.md](http://demo.microservices.agency:9906/ms/readme.md) : returns the readme (this file)
- [/ms/readme.html](http://demo.microservices.agency:9906/ms/readme.html) : returns the readme as html
- [/swagger/swagger.json](http://demo.microservices.agency:9906/swagger/swagger.json) : returns the swagger api documentation
- [/swagger/#/](http://demo.microservices.agency:9906/swagger/#/) : returns swagger-ui displaying the api documentation
- [/nginx/stats.json](http://demo.microservices.agency:9906/nginx/stats.json) : returns stats about Nginx
- [/nginx/stats.html](http://demo.microservices.agency:9906/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
