# Admin Widgets

King of App enables modules to register their own section. Commonly used for `post publishing` experiences such as:
- Sending push notifications.
- Populating databases with content.
- Accessing registered user databases.

#### Table of contents
* [ Configuration ](#configuration)
* [ File structure ](#file-structure)
* [ Interacting with data ](#interacting-with-data)
* [ Demo modules list ](#demo-modules-list)

## Configuration


Inside the module / service config.json
```json
{
  ...
  "widget": {
    "title": "Admin - Module Name",
    "url": "/modules/moduleid/builder/#/widget"
  },
  ...
}
```

Key | Description | Data type
----------------|-------------|--------
`widget.title` | Toolbar title registered in the King Of App builder | ""
`widget.url` | Iframe url | ""


### Widget
The widget object registers a section in the King Of App builder with the `title` name which loads an iframe with the given `url`.

## File structure

We strongly recommend to store the widget files in a folder inside the module. We will store and serve your files in our servers. Anyway you can point your `widget.url` from the [config.json](#configuration) file to any url of your choice.

```
koapp-module-firebasefeed
├── builder
│   ├── js
│   │    ├── app.js
│   │    ├── widget.controller.js
│   │    ├── router.config.js
│   │    └── translate.config.js
│   │
│   ├── locale
│   │    ├── widget.en_US.json
│   │    └── widget.en_ES.json
│   │
│   ├── widget.html
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
1. Controller listens to data incoming from the parent (King Of App Builder) iframe.
2. Use the data received to enable new features with administration purposes inside the iframe.


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
    "isCompiled": ["iOS", "Android"],
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

Key | Description | Default value
----------------|-------------|--------
`data._id` | Application id | ""
`data.accessToken` | Builder platform login token used in [Iframe requests](https://github.com/KingofApp/docs/tree/master/modules/iframeRequests)| ""
`data.isCompiled` | Platforms list in which the app was compiled | []
`data.lang` | Language used in builder | ""
`data.name` | App name | ""
`data.packageName` | Unique app package name | ""
`data.plugin` | Module config | {}
`data.plugin._id` | Module id | ""
`data.plugin.identifier` | Module identifier | ""
`data.plugin.name` | Module name | ""
`data.plugin.scope` | Module config variables | {}
`data.plugin.uniqueId` | Unique builder id | ""


### Creating a new feature
Firebase admin controller example:
```javascript
//... under construction ...
```
## Demo modules list
<!-- * [Firebase RSS feed]() -->
