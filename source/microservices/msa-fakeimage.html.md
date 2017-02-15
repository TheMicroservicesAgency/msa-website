---
title: msa-fakeimage
---

<a href="https://github.com/TheMicroservicesAgency/msa-fakeimage"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

Dynamic image generator. Can generate png, jpg and gif images at various resolutions.

Built with the [fakeimage](https://github.com/xxx/fakeimage) ruby app.

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9905:80 msagency/msa-fakeimage

## Example(s)

To get a png image of dimensions 850x50, just specify the size (width x height) in the url :

[/fakeimage/850x100.png](http://demo.microservices.agency:9905/fakeimage/850x100.png)

![Example 1](http://demo.microservices.agency:9905/fakeimage/850x100)

Specify the background color with the color parameter, specify either a color name (the full list is available on the [imagemagick ](http://www.imagemagick.org/script/color.php#color_names) website) :

[/fakeimage/850x100.png?color=DeepSkyBlue](http://demo.microservices.agency:9905/fakeimage/850x100.png?color=DeepSkyBlue)

![Example 2](http://demo.microservices.agency:9905/fakeimage/850x100.png?color=DeepSkyBlue)

Or you can use a hex code, starting with ! instead of # :

[/fakeimage/50x500.jpg?color=!4bfc57](http://demo.microservices.agency:9905/fakeimage/850x100.jpg?color=!4bfc57)

![Example 3](http://demo.microservices.agency:9905/fakeimage/850x100.jpg?color=!4bfc57)

You can also change the text color with the textcolor parameter :

[/fakeimage/850x100.jpg?color=black&textcolor=!43ff00](http://demo.microservices.agency:9905/fakeimage/850x100.jpg?color=black&textcolor=!43ff00)

![Example 4](http://demo.microservices.agency:9905/fakeimage/850x100.jpg?color=black&textcolor=!43ff00)

## Endpoints

- GET [/fakeimage/:resolution](http://demo.microservices.agency:9905/fakeimage/500x500) : Returns a png image
- GET [/fakeimage/:resolution.png](http://demo.microservices.agency:9905/fakeimage/500x500.png) : Returns a png image
- GET [/fakeimage/:resolution.jpg](http://demo.microservices.agency:9905/fakeimage/500x500.jpg)  : Returns a jpg image
- GET [/fakeimage/:resolution.gif](http://demo.microservices.agency:9905/fakeimage/500x500.gif)  : Returns a gif image


## Standard endpoints

- GET [/ms/version](http://demo.microservices.agency:9905/ms/version) : returns the version number
- GET [/ms/name](http://demo.microservices.agency:9905/ms/name) : returns the name
- GET [/ms/readme.md](http://demo.microservices.agency:9905/ms/readme.md) : returns the readme (this file)
- GET [/ms/readme.html](http://demo.microservices.agency:9905/ms/readme.html) : returns the readme as html
- GET [/swagger/swagger.json](http://demo.microservices.agency:9905/swagger/swagger.json) : returns the swagger api documentation
- GET [/swagger/#/](http://demo.microservices.agency:9905/swagger/#/) : returns swagger-ui displaying the api documentation
- GET [/nginx/stats.json](http://demo.microservices.agency:9905/nginx/stats.json) : returns stats about Nginx
- GET [/nginx/stats.html](http://demo.microservices.agency:9905/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
