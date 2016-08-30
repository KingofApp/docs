# Iframe requests

King of App enables an api interceptor for developers to make use of protected variables through their process and partially hide responses. Examples:
* Service Tokens
* Publishing certs

#### Table of contents
* [ Configuration ](#configuration)
* [ File examples ](#file-examples)
* [ Request Object explained ](#request-object-explained)
* [ Registering protected variables ](#registering-protected-variables)

## Files and configuration


Inside the module / service config.json
```json
{
  ...
  "iframeRequests":{
    "urls":{
      "POST": ["https://externalurl.com/api/notifications", "https://externalurl.com/api/apps"],
      "GET": ["https://externalurl.com/api/notifications", "https://externalurl.com/api/apps"],
      "PUT": ["https://externalurl.com/api/apps"],
      "DEL": ["https://externalurl.com/api/apps"]
    },
    "vars": {
      "allowed": ["app.appleApnsp12", "app.appleApnsp12Pwd", "plugin.Token"],
      "blocked": ["secret","passwords"]
    }
  },
  "widget": {
    "title": "Admin - Module Name",
    "url": "/modules/moduleid/builder/#/widget"
  },
  ...
}
```

Key | Description | Data type
----------------|-------------|--------
`iframeRequests.urls.POST` | POST urls type | []
`iframeRequests.urls.GET` | GET urls type | []
`iframeRequests.urls.PUT` | PUT urls type | []
`iframeRequests.urls.DEL` | DEL urls type | []
`vars.allowed` | Plugin and system protected variables | []
`vars.blocked` | Blocked variables in the api response | []
`widget.title` | Toolbar title registered in the King Of App builder | ""
`widget.url` | Iframe url | ""

### iFrame Request
Iframe request `urls` contain a list of the allowed petitions that can be made within the module or service. Every other url used in a petition that is not listed here will not work.

`Blocked vars` are commonly used when interacting with third party apis. This variables will be intercepted by the King of app api interceptor and hide the content before delivering the object to the iframe.

`Allowed vars` prefix:

Key | Description
----------------|-------------
`app` | System variables (Ask the King Of App team)
`plugin` | Previously [registered](#registering-protected-variables) by module or service.

### Widget
The widget object registers a section in the King Of App builder with the `title` name which loads an iframe with the given `url`.



## File Examples

Main koaApiCall service:

```javascript
angular
  .module('koa.api.service', [])
  .service('koaApiCall', koaApiCall);

koaApiCall.$inject = ['$http', '$location'];

function koaApiCall($http, $location) {
  var urlBase = "";

  if ($location.absUrl().indexOf('dev.resources.kingofapp.com') !== -1) {
    urlBase = 'http://dev.api.kingofapp.com/iframe/request';
  } else {
    urlBase = 'http://api.kingofapp.com/iframe/request';
  }

  var headers = {
    'x-access-token': 'X',
    'content-type': 'application/json'
  };

  this.setHeaders = function (sessionToken) {
    headers['x-access-token'] = sessionToken;
  }

  this.callApi = function (data) {
      return $http.post(urlBase, data, { 'headers': headers});
  };

}
```

### KoaApiCall service usage


Asuming data was loaded with a previous `listener` found [here](https://github.com/KingofApp/docs/tree/master/modules/adminWidget#interacting-with-data) and [here](https://github.com/KingofApp/docs/tree/master/modules/autoconfig#interacting-with-data) . Passed along to a config function.

```javascript
var request = {};
var data = {};
function config(received) {
    data = received;
    //King Of App builder user session token
    koaApiCall.setHeaders(data.accessToken);
    request = {
      'appId': data._id,
      'moduleId': data.plugin._id,
      'request': {
      }
    };
  }
```

Making a request:
```javascript
function createObject() {
  request.request = {
    method : 'PUT',
    json : true,
    uri : 'https://external.com/api/apps/',
    body : {
      type: 'production',
      secret:':app.secret',
      apns_p12_password: data.plugin.scope.variable,
    },
    headers: { 'Authorization': 'Basic :plugin.oneSignalToken' }
  };
  return koaApiCall.callApi(request);
}
```

## Request Object explained
```json
{
  "appId": data._id,
  "moduleId": data.plugin._id,
  "request": {
    "method" : "PUT",
    "json" : true,
    "uri" : "https://external.com/api/apps/",
    "body" : {
      "type": "production",
      "secret":":app.secret",
      "apns_p12_password": data.plugin.scope.variable,
    },
    "headers": { "Authorization": "Basic :plugin.oneSignalToken" }
  }
}
```

Key | Description | Values
----------------|-------------|--------
`appId` | Application id variable | ""
`moduleId` | Module identifier, can also be Service id (serviceId)| ""
`request.method` | PUT, POST, GET, DEL | ""
`request.json` | Response type | true
`request.uri` | Third party url, petition destination. (Should be listed in the `iframeRequests.urls`) | ""
`request.body` | Variables that will be passed to the `request.uri` petition  | {}
`request.headers` | Headers that will be passed to the `request.uri` petition | {}


## Registering protected variables
...Under construction...
