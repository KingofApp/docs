# Autoconfig feature for modules and services

King of App modules now have an autoconfig feature that helps users through the configuration steps, such as:
* Obtaining Tokens, ids ...
* Interacting with APIs

#### Table of contents
* [ Files and configuration ](#files-and-configuration)
* [ Interacting with data ](#interacting-with-data)
* [ Demo modules list ](#demo-modules-list)


## Files and configuration

A new type of button is available inside the modules config:

```json
{
  ...
  "config": [{
    "type": "frame",
    "templateOptions": {
      "url": "/modules/moduleid/builder/#/config",
      "label": "Iframe config button",
      "buttonText": "Config Service",
      "description": "",
      "width": "",
      "height": ""
    }
  },
  ...
  ],
  ...
}
```

Key | Description | Default value
----------------|-------------|--------
`type` | Formly element type | "frame"
`templateOptions.url` | Url used for the iframe | ""
`templateOptions.label` | Element label | ""
`templateOptions.buttonText` | Button text | ""
`templateOptions.description` | Element description | Optional
`templateOptions.width` | Iframe width | Optional
`templateOptions.height` | Iframe height | Optional

### File structure

We strongly recommend to store the config files in a folder inside the module. We will store and serve your files in our servers. Anyway you can point your `templateOptions.url` from the [config.json](#files-and-configuration) file to any url of your preference.

```
koapp-module-facebookfeed
├── builder
│   ├── js
│   │    ├── app.js
│   │    ├── config.controller.js
│   │    ├── router.config.js
│   │    └── translate.config.js
│   │
│   ├── locale
│   │    ├── config.en_US.json
│   │    └── config.en_ES.json
│   │
│   ├── config.html
│   │
│   ├── error.html
│   │
│   ├── index.html
│   │
│   ├── main.js
│   │
│   └── style.css
│   
├── config.json
│
└── ...
```

For Api interactions checkout the [Iframe requests section](https://github.com/KingofApp/docs/tree/master/modules/iframeRequests)

## Interacting with data

Communications between parent and iframe are done using the [koapp widget communicator](https://github.com/KingofApp/koapp-widget-communicator)

Configuration workflow:
1. Controller listens to data incoming from the parent (King Of App Builder).
2. The user data can be captured inside the `data.plugin.scope` if defined in the builder or asked for it during the process inside the iframe.
3. Once the configuration phase has finished, the `data.plugin.scope` should be altered and passed back to the parent (King Of App builder).


### Listening to the data.
Inside the `js/config.controller.js` file we can find:
```javascript
koappComm.iframe.ready();
koappComm.iframe.onData(function(data){
  if(data._id && data.lang && data.accessToken){
    //Set language to the one used in builder
    $translate.use(data.lang);
    $translate.refresh();
    console.log("Data is: ", data);
  }
});
```


Received data object example:
```json
{
  "data" : {
    "_id": "YYYY",
    "accessToken": "XXXX",
    "lang": "es_ES",
    "name": "App Name",
    "packageName": "com.kingofapp.STRedXXXX",
    "plugin": {
      "_id": "ZZZZ",
      "identifier": "moduleid",
      "name": "Module Name",
      "scope": {
        "variable": "data",
        "variable2": "data2"
      },
      "uniqueId": "module-XYZY",
      ...
    },
    ...
  }
}
```


### Returning the data to the King Of App builder.
Inside the `js/config.controller.js` file we can find:
```javascript
//Send back data object.
koappComm.iframe.sendData(data);
//Signal to close iframe popup in builder.
koappComm.iframe.close();
```

Key | Description | Default value
----------------|-------------|--------
`data._id` | Application id | ""
`data.accessToken` | Builder platform login token used in [Iframe requests](https://github.com/KingofApp/docs/tree/master/modules/iframeRequests)| ""
`data.lang` | Language used in builder | ""
`data.name` | App name | ""
`data.packageName` | Unique app package name | ""
`data.plugin` | Module config | {}
`data.plugin._id` | Module id | ""
`data.plugin.identifier` | Module identifier | ""
`data.plugin.name` | Module name | ""
`data.plugin.scope` | Module config variables | {}
`data.plugin.uniqueId` | Unique builder id | ""



## Demo modules list
* [Facebook feed](https://github.com/KingofApp/koapp-module-facebookfeed)
