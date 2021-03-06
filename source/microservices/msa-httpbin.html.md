---
title: msa-httpbin
---

<a href="https://github.com/TheMicroservicesAgency/msa-httpbin"><img style="zoom: 1.15; position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/e7bbb0521b397edbd5fe43e7f760759336b5e05f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f677265656e5f3030373230302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_green_007200.png"></a>

HTTP request & response service, useful to test various HTTP operations.

Based on [httpbin](https://github.com/Runscope/httpbin), licensed under the ISC.

## Quick start

Execute the microservice container with the following command :

    docker run -ti -p 9901:80 msagency/msa-httpbin

## Example(s)

    $ curl http://localhost:9901/user-agent
    {
      "user-agent": "curl/7.47.0"
    }

## Endpoints

- GET [/httpbin/](http://demo.microservices.agency:9901/httpbin/) : returns the httpbin original readme, listing all the URLs below :
- GET [/httpbin/ip](http://demo.microservices.agency:9901/httpbin/ip) returns the origin IP
- GET [/httpbin/user-agent](http://demo.microservices.agency:9901/httpbin/user-agent) returns the user-agent
- GET [/httpbin/headers](http://demo.microservices.agency:9901/httpbin/headers) returns the header dict
- GET [/httpbin/get](http://demo.microservices.agency:9901/httpbin/get) returns GET data
- POST [/post]() returns POST data
- PATCH [/patch]() returns PATCH data
- PUT [/put]() returns PUT data
- DELETE [/delete]() returns DELETE data
- GET [/httpbin/encoding/utf8](http://demo.microservices.agency:9901/httpbin/encoding/utf8) returns a page containing UTF-8 data
- GET [/httpbin/gzip](http://demo.microservices.agency:9901/httpbin/gzip) returns gzip-encoded data
- GET [/httpbin/deflate](http://demo.microservices.agency:9901/httpbin/deflate) returns deflate-encoded data
- GET [/httpbin/status/:code](http://demo.microservices.agency:9901/httpbin/status/418) returns given HTTP Status code
- GET [/httpbin/response-headers?key=val](http://demo.microservices.agency:9901/httpbin/response-headers?Server=httpbin&Content-Type=text%2Fplain%3B+charset%3DUTF-8) returns given response headers
- GET [/httpbin/redirect/:n](http://demo.microservices.agency:9901/httpbin/redirect/6) 302 redirects n times
- GET [/httpbin/redirect-to?url=foo](http://demo.microservices.agency:9901/httpbin/redirect-to?url=foo) 302 redirects to the foo URL
- GET [/httpbin/redirect-to?url=foo&status_code=307](http://demo.microservices.agency:9901/httpbin/redirect-to?url=foo&status_code=307) 307 redirects to the foo URL
- GET [/httpbin/relative-redirect/:n](http://demo.microservices.agency:9901/httpbin/relative-redirect/6) 302 relative redirects n times
- GET [/httpbin/absolute-redirect/:n](http://demo.microservices.agency:9901/httpbin/absolute-redirect/6) 302 absolute redirects n times
- GET [/httpbin/cookies](http://demo.microservices.agency:9901/httpbin/cookies) returns cookie data
- GET [/httpbin/cookies/set?name=value](http://demo.microservices.agency:9901/httpbin/cookies/set?k1=v1&k2=v2) sets one or more simple cookies
- GET [/httpbin/cookies/delete?name](http://demo.microservices.agency:9901/httpbin/cookies/delete?k1=&k2=) deletes one or more simple cookies
- GET [/httpbin/basic-auth/:user/:passwd](http://demo.microservices.agency:9901/httpbin/basic-auth/user/passwd) challenges HTTPBasic Auth
- GET [/httpbin/hidden-basic-auth/:user/:passwd](http://demo.microservices.agency:9901/httpbin/hidden-basic-auth/user/passwd) 404'd BasicAuth
- GET [/httpbin/digest-auth/:qop/:user/:passwd/:algorithm](http://demo.microservices.agency:9901/httpbin/digest-auth/auth/user/passwd/MD5) challenges HTTP Digest Auth
- GET [/httpbin/digest-auth/:qop/:user/:passwd](http://demo.microservices.agency:9901/httpbin/digest-auth/auth/user/passwd/MD5) challenges HTTP Digest Auth
- GET [/httpbin/stream/:n](http://demo.microservices.agency:9901/httpbin/stream/20) streams min(n, 100) lines
- GET [/httpbin/delay/:n](http://demo.microservices.agency:9901/httpbin/delay/3) delays responding for min(n, 10) seconds
- GET [/httpbin/drip?numbytes=n&duration=s&delay=s&code=code](http://demo.microservices.agency:9901/httpbin/drip?duration=5&code=200&numbytes=5) Drips data over a duration after an optional initial delay, then (optionally) returns with the given status code.
- GET [/httpbin/range/1024?duration=s&chunk_size=code](http://demo.microservices.agency:9901/httpbin/range/1024) streams n bytes, and allows specifying a Range header to select a subset of the data. Accepts a chunk_size and request duration parameter.
- GET [/httpbin/html](http://demo.microservices.agency:9901/httpbin/html) Renders an HTML Page
- GET [/httpbin/robots.txt](http://demo.microservices.agency:9901/httpbin/robots.txt) returns some robots.txt rules
- GET [/httpbin/deny](http://demo.microservices.agency:9901/httpbin/deny) denied by robots.txt file
- GET [/httpbin/cache](http://demo.microservices.agency:9901/httpbin/cache) returns 200 unless an If-Modified-Since or If-None-Match header is provided, when it returns a 304.
- GET [/httpbin/cache/:n](http://demo.microservices.agency:9901/httpbin/cache/60) sets a Cache-Control header for n seconds
- GET [/httpbin/bytes/:n](http://demo.microservices.agency:9901/httpbin/bytes/1024) generates n random bytes of binary data, accepts optional seed integer parameter
- GET [/httpbin/stream-bytes/:n](http://demo.microservices.agency:9901/httpbin/stream-bytes/1024) streams n random bytes of binary data, accepts optional seed and chunk_size integer parameters.
- GET [/httpbin/links/:n](http://demo.microservices.agency:9901/httpbin/links/10) returns a page containing n HTML links
- GET [/httpbin/image](http://demo.microservices.agency:9901/httpbin/image) returns a page containing an image based on sent Accept header
- GET [/httpbin/image/png](http://demo.microservices.agency:9901/httpbin/image/png) returns a page containing a PNG image
- GET [/httpbin/image/jpeg](http://demo.microservices.agency:9901/httpbin/image/jpeg) returns a page containing a JPEG image
- GET [/httpbin/image/webp](http://demo.microservices.agency:9901/httpbin/image/webp) returns a page containing a WEBP image
- GET [/httpbin/image/svg](http://demo.microservices.agency:9901/httpbin/image/svg) returns a page containing a SVG image
- GET [/httpbin/forms/post](http://demo.microservices.agency:9901/httpbin/forms/post) HTML form that submits to /post
- GET [/httpbin/xml](http://demo.microservices.agency:9901/httpbin/xml) returns some XML

## Standard endpoints

- GET [/ms/version](http://demo.microservices.agency:9901/ms/version) : returns the version number
- GET [/ms/name](http://demo.microservices.agency:9901/ms/name) : returns the name
- GET [/ms/readme.md](http://demo.microservices.agency:9901/ms/readme.md) : returns the readme (this file)
- GET [/ms/readme.html](http://demo.microservices.agency:9901/ms/readme.html) : returns the readme as html
- GET [/swagger/swagger.json](http://demo.microservices.agency:9901/swagger/swagger.json) : returns the swagger api documentation
- GET [/swagger/#/](http://demo.microservices.agency:9901/swagger/#/) : returns swagger-ui displaying the api documentation
- GET [/nginx/stats.json](http://demo.microservices.agency:9901/nginx/stats.json) : returns stats about Nginx
- GET [/nginx/stats.html](http://demo.microservices.agency:9901/nginx/stats.html) : returns a dashboard displaying the stats from Nginx

## About

A project by the [Microservices Agency](http://microservices.agency).
