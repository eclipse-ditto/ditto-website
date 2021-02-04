## Eclipse Ditto :: Documentation :: OpenAPI Specification

This folder contains the OpenAPI [OpenAPI](https://www.openapis.org) [Specification version 2](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md) documentation for Eclipse Ditto. 

You can view it as nicely rendered HTML by importing one of the files (for API version 1 or 2) into the [Swagger Online Editor](https://editor.swagger.io).

### Build api docs

1. Install `swagger-cli`: `$ cd sources && npm install`
2. Build bundled docs:
```
// go to sources
$ cd sources

// only v1
$ npm run build-v1

// only v2
$ npm run build-v2

// both
$ npm run build
```