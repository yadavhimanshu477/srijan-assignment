
## Description

This is an API project which Return data as an Array of Fizz Buzz Pattern. I have used nestjs framework(Typescript) for creating api and jest framework for unit, e2e testing.

#Appbuilder: I have created appBuilder so that all server dependency will install before creating the server
#DTO(Data Transfer Object): Used to validate incoming request body.
#pipes: Pipes will automatically be called on post request and will validate req body using DTO.
#Interceptor: In terceptor is used to create perfect and valid response object.
#Test: It will contain all unit and e2e test cases.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## ApiPath

```bash
  method                : POST
  url                   : localhost:3000/getFizzBuzzData
  requestBodyparameters : [count] 
```

## Curl Request Ex

```bash
curl -X POST \
  http://localhost:3000/getFizzBuzzData \
  -H 'Accept: */*' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Length: 7' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'Host: localhost:3000' \
  -H 'Postman-Token: ba95d0fc-f832-4b41-bffc-92ce04606f80,56664050-6d71-41c7-b767-82757fe08177' \
  -H 'User-Agent: PostmanRuntime/7.17.1' \
  -H 'cache-control: no-cache' \
  -d count=5
  ```

## Nodejs Native Ex

```bash
var qs = require("querystring");
var http = require("http");

var options = {
  "method": "POST",
  "hostname": [
    "localhost"
  ],
  "port": "3000",
  "path": [
    "getFizzBuzzData"
  ],
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "User-Agent": "PostmanRuntime/7.17.1",
    "Accept": "*/*",
    "Cache-Control": "no-cache",
    "Postman-Token": "ba95d0fc-f832-4b41-bffc-92ce04606f80,a5c7724c-f690-4cb6-85f7-8457fe96d5a0",
    "Host": "localhost:3000",
    "Accept-Encoding": "gzip, deflate",
    "Content-Length": "7",
    "Connection": "keep-alive",
    "cache-control": "no-cache"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(qs.stringify({ count: '5' }));
req.end();
```

## Test

```bash
# unit tests
$ npm run test:unit

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```