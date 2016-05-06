# King of App Modules

King of App modules are composed of [AngularJS](https://angularjs.org/) logic and presented with our custom [Polymer elements](https://github.com/KingofApp/docs/tree/master/themes).

#### Table of contents
* [ The module structure ](#the-module-structure)
* [ Multi language modules ](#multi-language-modules)
* [ Simple modules ](#simple-modules)
* [ Using the storage service ](#using-the-storage-service)
* [ Container modules ](#container-modules)
* [ Menu modules ](#menu-modules)
* [ The menu standards ](#the-menu-standards)
* [ Working with APIs ](#working-with-apis)
* [ Dependencies in modules ](#dependencies-in-modules)
* [ Presenting data in modules ](#presenting-data-in-modules)
* [ Module config in builder ](#module-config-in-builder)
* [ Getting started ](#getting-started)
* [ Module list ](#module-list)
* [ Demo list ](#demo-list)

## The module structure
Modules are composed of [files](#the-module-files) and [libs](#the-module-libs) that read from a [config structure json](#the-module-config-structure).

### The module config structure

For a module called testmodule this would be the config structure:

```json
{
  "name"       : "Test module",
  "identifier" : "testmodule",
  "icon"       : "home",
  "description": {
    "es-ES": "Descripción del modulo",
    "en-US": "Module description"
  },
  "documentation": {
    "es-ES": "# Titulo Modulo\r\nConfiguración",
    "en-US": "# Module Title\r\nConfiguration"
  },
  "descriptionShort": {
    "es-ES": "Descripción corta",
    "en-US": "Short description"
  },
  "price"       : 0,
  "type"       : "A",
  "version"    : "1.0",
  "author"     : "King of App",
  "category"   : [
      "others"
  ],
  "requires"   : [
      "othermodule"
  ],
  "canContain" : false,
  "showOn"     : {
    "market"   : "true",
    "dragDrop" : "true"
  },
  "view"       : "modules/testmodule/index.html",
  "files"      : [
    "modules/testmodule/controller.js"
  ],
  "libs"       : [],
  "deps"       : [],
  "scope"      : {
    "data"  : "Sample data"
  },
  "config"     : [],
  "images": {
    "list": "modules/testmodule/images/list.png",
    "screenshots": [
      "modules/testmodule/images/screenshot01.png",
      "modules/testmodule/images/screenshot02.png"
    ],
    "popover": "modules/testmodule/images/popover.png",
    "banner": "modules/testmodule/images/banner.png",
    "logo": "modules/testmodule/images/logo.png"
  }
}
```

Key | Description | Default value
----------------|-------------|--------
`name` | Module name | ""
`identifier` | A unique name for your module that will be used to register the module and it's files. (Only alphabetic characters allowed) | ""
`icon` | Module default icon from [ Icon list ](https://elements.polymer-project.org/bower_components/iron-icons/demo/index.html) or a custom image using an URL | ""
`description` | Multilanguage supported description used in the KingOfApp builder | {}
`documentation` | Multilanguage supported documentation with [ markdown syntax ](https://guides.github.com/features/mastering-markdown/) used in the KingOfApp builder | {}
`descriptionShort` | Multilanguage supported short description used in the KingOfApp builder | {}
`price` | Purchase price displayed for the module in the KingOfApp builder | 0
`type` | Currently our modules only support Angular | A
`version` | Version control | 0.0.1
`author` | Author name | ""
`category` | Categories to which your module belongs. [ Check-out our list ](#module-category-list)  | "others"
`requires` | Certain modules require other modules to work properly. [ Youtube gallery module ](https://github.com/KingofApp/koapp-module-youtubegallery)  | []
`canContain` | Set to true if the module can adopt other modules inside them.[Check-out the  container module](#container-modules) type. | False
`showOn.market` | Property to make the module selectable by the users in our market. | True
`showOn.dragDrop` | Property to disable the drag and drop option from the KingOfApp builder | True
`view` | Main view file | "modules/{identifier}/index.html"
`files` | Array of files that will be loaded. [Check-out the module files section](#the-module-files) | []
`libs` | Array of bower dependencies used in the module. [Check-out the module libs section](#the-module-libs) | []
`deps` | Array of phonegap dependencies. | []
`scope` | Data Object that will be accessible from the module. [Check-out the module scope section](#the-module-scope)| {}
`config` | Formly based config for the KingOfApp builder. [ Check-out module config in builder ](#module-config-in-builder)| {}
`images.list` | Module list image used in the KingOfApp builder | ""
`images.screenshots` | Module screenshots images used in the KingOfApp builder | {}
`images.popover` | Module popover image used in the KingOfApp builder | ""
`images.banner` | Module banner image used in the KingOfApp builder | ""
`images.logo` | Required - Module logo image used in the KingOfApp builder | ""
NOTE: Some modules may have a module dependency `Example: A list module with a Firebase module connector`.

### The module file structure

For a module called testmodule this would be the file structure:

```
testmodule
├── locale
│   ├── en_US.json
│   └── ...
├── controller.js
└── index.html
```

### The module files
KingOfApp visualizer currently supports AngularJs modules, meaning modules can contain:
* [Directives](https://docs.angularjs.org/guide/directive) - [Youtubevideo sample](https://github.com/KingofApp/koapp-module-youtubevideo)
* [Filters](https://docs.angularjs.org/guide/filter)
* [Services / factories](https://docs.angularjs.org/guide/services) - [Firebase sample](https://github.com/KingofApp/koapp-module-firebase)
* Run
* [Controllers](https://docs.angularjs.org/guide/controller) - [Html sample](https://github.com/KingofApp/koapp-module-html)

Other files supported:

* Css files (.css) - [Simplegallery sample](https://github.com/KingofApp/koapp-module-simplegallery)
* jQuery files (.js) - [Simplegallery sample](https://github.com/KingofApp/koapp-module-simplegallery)
* Polymer style module (.html) - [Grouplist sample](https://github.com/KingofApp/koapp-module-grouplist)

### The module libs

Dependencies that get loaded along with the modules files can be:

* AngularJs modules (.js) - [Firebaselist sample](https://github.com/KingofApp/koapp-module-list)
* Polymer components (.html) - [Googlemap sample](https://github.com/KingofApp/koapp-module-googlemap)

Libs example:
```json
"libs": [{
  "bower": {
    "firebase": "2.2.4"
  },
  "src": "https://cdn.firebase.com/js/client/2.2.4/firebase.js"
}, {
  "bower": {
    "angularfire": "1.1.2"
  },
  "src": "https://cdn.firebase.com/libs/angularfire/1.1.2/angularfire.min.js"
}, {
  "bower": {
    "PolymerElements/paper-item": "^1.0.0"
  },
  "src": "bower_components/paper-item/paper-item.html"
}]
```

The module should include a .bowerrc and bower.json.

Upon each npm start from the visualizer, each module will have it's bower.json downloaded to the .bowerrc specified directory.

These libs should be included in the module's bower.json file like:

```json
{
  "name": "koapp-module-testmodule",
  "authors": "King of App",
  "description": "test module for King of App",
  "keywords": [
    "kingofapp",
    "module"
  ],
  "license": "MIT",
  "homepage": "http://kingofapp.com",
  "private": true,
  "dependencies": {
    "firebase": "firebase#2.2.4",
    "angularfire": "angularfire#1.1.2",
    "paper-item": "PolymerElements/paper-item#^1.0.0"
  }
}
```

[Checkout our polymermenu module](https://github.com/KingofApp/koapp-module-polymermenu) for bower libs example.

## Multi language modules

KingOfApp visualizer uses [Angular translate](https://angular-translate.github.io/) to provide multilingual modules.
Inside [the module file structure](#the-module-structure) a folder locale will contain the different translation files with the following file syntax : {language}.json based on [Module language support](#module-language-support).

For an example using en_US.json with the identifier moduletest:
```json
{
  "moduletest.text1": "First text",
  "moduletest.text2": "Second text",
  "moduletest.text3": "Third text",
  "moduletest.text4": "My name is: {{variable}}"
}

```

The data can be translated using different methods:
```html
<p>{{ "moduletest.text1" | translate }}</p>
<p translate>moduletest.text2</p>
<p translate>{{ "moduletest.text3" }}</p>
<p translate="moduletest.text4" translate-values="{ variable:'World' }"> </p>
```

To avoid conflicts with other modules, it's recommended to use {identifier}.variable inside the en_US.json.

## Simple modules
We understand simple modules as final modules, that can't relay their services or functionalities to other modules.

Let's see the html module with a basic configuration.
Html module file structure:



#### Html module config structure:
```json
{
  "name": "Html Example",
  "identifier": "html",
  "type": "A",
  "showOn": {
    "market": true,
    "dragDrop": true
  },
  "view": "modules/html/index.html",
  "files": ["modules/html/controller.js"],
  "scope": {
    "value": "<p style='color:#39a9d3'>Ut tortor mauris, ultrices quis </p><p style='color:#d36339'>Other color text</p>"
  }
}
```

NOTE: For the module to properly work in the KingOfApp builder it is very important to include the property config, although we haven't in this example to make it simple. For more information [check-out the module config in builder section](#module-config-in-builder section).

#### Html module controller
In this particular case we won't be using any logic, so the controller will have the minimum lines of code to register in the environment.

```javascript
angular
  .controller('htmlCtrl', loadFunction);

loadFunction.$inject = ['$scope', 'structureService', '$location'];

function loadFunction($scope, structureService, $location){
  //Register upper level modules
  structureService.registerModule($location,$scope,"html");

  //Your code goes here

}
```

#### Html module view:
The view will use the scope defined in the [Html module config structure](#html-module-config-structure) inside a [custom element](#presenting-data-in-modules) koa-card.
```html
<div ng-controller="htmlCtrl" class="module html">

  <koa-card>
    <div class="card-content">
      <div ng-bind-html="html.modulescope.value"></div>
    </div>
  <koa-card>

</div>
```

### The module scope

From the html module in the last example you can appreciate how the scope we had in the module structure config is passed along to the scope variable with the following syntax {identifier}.modulescope.

Also the same config structure can be accessed in the controller through $scope.{identifier}.modulescope.

### Structure service inside modules

Accessible structureService service within the module controller:

Functions | Description | Expects | Returns
----------------|-------------|--------|--------
`get()` | Returns the [application object](#application-config-structure-sample).  | null | JSON Object
`getModule(path, callback)` | Returns a module config structure from a given path. | path - "/route" | JSON Object
`getCurrentModules($location, callback)` | Returns an array with the modules used in the current location. `Useful for finding parent module` | $location | Array
`getChildren()` | Returns an array with all the children modules of the given path. | path - "/route" | Array

NOTE: Remember to specify the `requires` property in [ the module config structure ](#the-module-config-structure) if your module requires any other module. Example: [Youtube gallery module](https://github.com/KingofApp/koapp-module-youtubegallery)

### Using the storage service

The storage service works around the [angular-indexedDB](https://github.com/webcss/angular-indexedDB) serviceprovider and stores data in the [IndexedDB](https://www.w3.org/TR/IndexedDB) web api database.


Accessible storageService service within the module controller:

Functions | Description | Expects | Returns
----------------|-------------|--------|--------
`getAll()` | Promise - Returns all the objects for an object store.  |  | Array
`init(objectName)` | Can manually set a specific the object store  | objectName (default: modules) |
`del(key)` | Promise - Deletes a specific key and its data. | key |
`get(key)` | Promise - Returns the JSON Object from a specific key. | key | JSON Object
`set(key, data)` | Promise - Insert data for a specific key. | key, data | data

The following object stores are available:
* modules - Used by modules to store data
* services - Used by services to store data

[Demo module using the storage service](https://github.com/KingofApp/koapp-demo-storagesample)

### Inside module events
```javascript
$rootScope.$on("koaAppRendered",function() {
  //Your code here

});
```
Checkout our [simplegallery module](https://github.com/KingofApp/koapp-module-simplegallery).

## Container modules

Container modules share the same file structure, config structure and controller as simple modules. But with a different view, having an additional div where all children modules will be contained.

With a containermodule identifier view example will look like:

```html
<div ng-controller="containermoduleCtrl" class="module containermodule">
  <!-- Module html can be coded here -->

  <!-- Specific div for container modules -->
  <div ng-include="containermoduleTemplate">
    <!-- Do not code anything here, adopted modules will use this space -->
  </div>

</div>
```
In this type of modules, parents can:
* Inject services from children

and children can:

* Access parents scope
* Inject services from parent


NOTE: Remember to specify the `canContain` property in [ the module config structure ](#the-module-config-structure) if your module can contain other modules inside Example:menu modules.

### Container module examples

[Firebase module](https://github.com/KingofApp/koapp-module-firebase)
This module acts as a parent module [connector](#connector-modules)

[Firebase list module](https://github.com/KingofApp/koapp-module-list)
This module uses the Firebase module's service to make the requests to firebase.

NOTE: The idea of using parent module connectors is to enable children modules to obtain data from different sources.

In this case, the firebase list module requires the firebase module, so it will have the `requires` property in [ the module config structure ](#the-module-config-structure) set to firebase.

### Menu modules

Menus can be built with polymer elements or angular.

Polymer menu particularities:
* Specific controller
* Directive to pass the menu items to polymer
* Access to the toolbar scope within the view

[Polymer menu Example](https://github.com/KingofApp/koapp-module-polymermenu)

Angular menu particularities:
* Specific controller
* Specific styles.html to read the templates color variables
* Access to the toolbar scope within the view

[Angular menu Example](https://github.com/KingofApp/koapp-module-angularmenu)

### The menu standards

All menus should include at least these 3 features:

Key | Description | Example values
----------------|-------------|--------
`menuItems` | Array of elements in the menu | ["/menu-abcd/home-abcd", "/menu-abcd/elements-abcd", "/menu-abcd/map-abcd"]
`backgroundImages` | Array of images matched in index order | ["http://i.imgur.com/ZGEX2eX.jpg", "http://i.imgur.com/dd6Szc4.jpg", "http://i.imgur.com/3L11jbd.jpg"]
`backgroundColors` | Array of colors matched in index order | ["#ECECEC", "#FFFFFF", "#ECECEC"]

#### Formly config for menuItems
```json
{
  "key": "menuItems",
  "type": "multiInput",
  "templateOptions": {
    "label": "Menu items",
    "inputOptions": {
      "type": "select",
      "templateOptions": {
        "options": [],
        "label": "Normal Select"
      }
    }
  }
}
```

#### Formly config for backgroundImages
```json
{
  "key": "backgroundImages",
  "type": "multiInput",
  "templateOptions": {
    "inputOptions": {
      "type": "input"
    },
    "label": "Background image URLs",
    "pattern": "(https?://)([/\\w.()-]*).*"
  }
}
```

#### Formly config for backgroundColors
```json
{
  "key": "backgroundColors",
  "type": "multiInput",
  "templateOptions": {
    "inputOptions": {
      "type": "input"
    },
    "label": "Background colors"
  }
}
```

#### Menu go back feature
For menus with toolbar it is recommended to implement the `go back` feature.
[Checkout our Top Menu example](https://github.com/KingofApp/koapp-module-topmenu)

The controller piece of code that controls whether to show the back button:
```javascript
  $scope.showBack = false;

  if(structureService.getMenuItems().indexOf($location.$$path) === -1 && $rootScope.current != 'topmenu'){
    $scope.showBack = true;
  }
  $scope.goBack = function() {
    window.history.back()
  };
```

The toolbar in the view:
```html
  <koa-toolbar>
    <koa-icon-button icon="{{topmenu.icon}}" ng-if="!showBack" ng-click="showBoxMenu()"></koa-icon-button>
    <koa-icon-button icon="arrow-back" ng-click="goBack()" ng-if="showBack"></koa-icon-button>
    <img id="logo" ng-src="{{topmenu.modulescope.toolbarLogo}}" ng-if="topmenu.modulescope.toolbarLogo">
    <span class="title" ng-if="topmenu.modulescope.toolbarTitle">{{toolbar.title}}</span>
  </koa-toolbar>
```

### Working with APIs

Api modules mainly follow the same pattern. Data is obtained throught the controller.js controller, using an url source through a http request reading parameters from the [ scope ](#the-module-scope). Then iterated in the index.html view.

Taking a look at the facebook module controller:
```javascript
angular
  .controller('facebookFeedCtrl', loadFunction);

loadFunction.$inject = ['$http', '$scope', 'structureService', '$filter', '$location'];

function loadFunction($http, $scope, structureService, $filter, $location) {
  //Register upper level modules
  structureService.registerModule($location, $scope, 'facebookfeed');

  $http.get('https://graph.facebook.com/v2.4/' + $scope.facebookfeed.modulescope.pageid + '/posts', {
    params: {
      access_token: $scope.facebookfeed.modulescope.accesstoken,
      fields: 'object_id,message,link,full_picture'
    }
  })
  .success(function(data) {
    $scope.facebookfeed.items = data.data;
  }).error(function() {
    $scope.facebookfeed.message = $filter('translate')('facebookfeed.feed.error');
  });
}
```

The view simply uses angular directives to iterate the data, using our custom [Koa elements](https://github.com/KingofApp/docs/tree/master/themes#list-of-elements) to present the data:
```html
<koa-card image="{{item.full_picture}}" ng-repeat="item in facebookfeed.items">
  <div class="card-content">{{item.message}}</div>
</koa-card>
```

`For more advance examples working with ngRepeat and ngClick` [check-out our koapp-demo-ngrepeatclick](https://github.com/KingofApp/koapp-demo-ngrepeatclick)

For more examples on Api related modules checkout:
* [Facebook](https://github.com/KingofApp/koapp-module-facebookfeed)
* [Flickr](https://github.com/KingofApp/koapp-module-flickrfeed)
* [Youtube Gallery](https://github.com/KingofApp/koapp-module-youtubegallery)
* [RSS](https://github.com/KingofApp/koapp-module-rss)
* [Instagram](https://github.com/KingofApp/koapp-module-instagramfeed)

### The ads module
The ads module is a container module embracing all the other modules in the app, pay special attention to the route modules. All containing ´/ads´ prefix.

[Checkout the module documentation](https://bitbucket.org/koapp/koapp-service-ads)

### Connector modules

[Firebase connector example](https://github.com/KingofApp/koapp-module-firebase)

...Under construction...

## Dependencies in modules

Phonegap libraries used by modules.

...We are working on a Sample...

## Presenting data in modules
For templating features to work with modules we strongly recommend to use our custom [Koa elements](https://github.com/KingofApp/docs/tree/master/themes#list-of-elements) inside the view.html of the module.

## Module config in builder
Using  [Angular formly](http://angular-formly.com/):

Actually our King Of App builder has tested and supported the current configs:

#### Regular Input

```json
{
    "type" : "input",
    "key" : "limit",
    "templateOptions" : {
        "label" : "Limit chars",
        "pattern":"^[0-9]+$",
        "required":true,
        "maxlength": 2,
        "description" : "limit chars for the field"
    }
}
```

Functions | Description
----------------|-------------
`type` | Formly element type
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope
`templateOptions.label` | Visible field name
`templateOptions.pattern` | Regular expression validation
`templateOptions.required` | Validation for required fields
`templateOptions.maxlength` | Character max length
`templateOptions.description` | Visible description under input

#### MultiInput

```json
{
    "type" : "multiInput",
    "key" : "gallery",
    "templateOptions" : {
        "inputOptions" : {
            "type" : "input"
        },
        "label" : "Url",
        "pattern" : "(https?://)([/\\w.()-]*).*",
        "required" : true,
        "maxlength": 40,
        "description" : "Url list to include"
    }

}
```
Functions | Description
----------------|-------------
`type` | Custom type defined in builder by the king of app team.
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope
`templateOptions.inputOptions.type` | Formly element type
`templateOptions.label` | Visible field name
`templateOptions.pattern` | Regular expression validation
`templateOptions.required` | Validation for required fields
`templateOptions.maxlength` | Character max length
`templateOptions.description` | Visible description under input

#### Select

```json
{
  "type": "select",
  "key": "alignment",
  "templateOptions": {
    "label": "Alignment",
    "options": [
      {"name": "left", "value": "left"},
      {"name": "center", "value": "center"},
      {"name": "right", "value": "right"}
    ]
  }
}
```
Functions | Description
----------------|-------------
`type` | Formly element type
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope
`templateOptions.label` | Visible field name
`templateOptions.options` | Array of items to appear in the select

#### WYSIWYG editor

```json
{
    "type" : "wysiwyg",
    "key" : "value",
    "templateOptions" : {
        "label" : "Html",
        "required" : true,
        "description" : "Html editor"
    }
}
```
Functions | Description
----------------|-------------
`type` | Custom type defined in builder by the king of app team
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope
`templateOptions.label` | Visible field name
`templateOptions.required` | Validation for required fields
`templateOptions.description` | Visible description under input

#### Date Picker

```json
{
  "type": "datepicker",
  "key": "day",
  "templateOptions": {
    "label": "day",
    "type": "text",
    "datepickerOptions": {
      "format": "dd-MM-yyyy"
    }
  }
}
```
Functions | Description
----------------|-------------
`type` | Custom type defined in builder by the king of app team.
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope
`templateOptions.label` | Visible field name
`templateOptions.type` | Formly element type
`templateOptions.datepickerOptions.format` | Date format

## Getting started

1. Clone the [com.kingofapp.visualizer](https://github.com/KingofApp/com.kingofapp.visualizer/tree/dev) repository.

  ```
  git clone -b dev https://github.com/KingofApp/com.kingofapp.visualizer/tree/dev
  ```

2. Change directory to com.kingofapp.visualizer

  ```
  cd com.kingofapp.visualizer
  ```

3. Run the visualizer using [NPM](https://nodejs.org/en/download):

  ```
  npm start
  ```

4. Open the app in your browser using http://localhost:9001/app/

Files of interest.
  * [structure.json](#application-config-structure-sample)
  * modules folder with and html, polymermenu and googlemap module.

  ```
  com.kingofapp.visualizer
  ├── app
  │   ├── core
  │   │    ├── structure.json
  │   │    └── ...
  │   ├── modules
  │   │    ├── html
  │   │    ├── polymermenu
  │   │    ├── googlemap  
  │   │    └── ...
  │   └── ...
  │
  └── ...
  ```

### Application config structure sample

The main configuration file is located in `/app/core/structure.json`

A structure.json app example:

```json
{
  "config": {
    "index": "/menu-abcd/home-abcd",
    "theme": {
      "identifier": "koapp-theme-android",
      "path": "themes/koapp-theme-android/koapp-theme-android.html"
    },
    "colors": {
      "primaryTextColor": "#212121",
      "primaryBackgroundColor": "#ffffff",
      "secondaryTextColor": "#737373",
      "disabledTextColor": "#9b9b9b",
      "dividerColor": "#dbdbdb",
      "primaryColor": "#3f51b5",
      "lightPrimaryColor": "#c5cae9",
      "darkPrimaryColor": "#303f9f",
      "accentColor": "#ff4081",
      "lightAccentColor": "#ff80ab",
      "darkAccentColor": "#f50057",
      "backgroundColor": "#ffffff"
    },
    "images": {
      "background": ""
    },
    "fonts": {
      "primaryFontFamily": {
        "name": "Roboto",
        "url": "https://fonts.googleapis.com/css?family=Roboto"
      },
      "titleFontFamily": {
        "name": "Roboto",
        "url": "https://fonts.googleapis.com/css?family=Roboto"
      }
    },
    "iconset": "icons",
    "lang": [
      "en_US"
    ]
  },
  "modules": {
    "/menu-abcd": {
      "name": "Menu Module",
      "identifier": "polymermenu",
      "type": "A",
      "canContain": true,
      "icon": "menu",
      "showOn": {
        "market": true,
        "dragDrop": true
      },
      "view": "modules/polymermenu/index.html",
      "files": [
        "modules/polymermenu/controller.js",
        "modules/polymermenu/styles.html"
      ],
      "libs": [
        {
          "bower": {
            "PolymerElements/iron-flex-layout": "^1.3.0"
          },
          "src": "bower_components/iron-flex-layout/iron-flex-layout.html"
        },
        {
          "bower": {
            "PolymerElements/paper-drawer-panel": "^1.0.0"
          },
          "src": "bower_components/paper-drawer-panel/paper-drawer-panel.html"
        },
        {
          "bower": {
            "PolymerElements/paper-header-panel": "^1.0.0"
          },
          "src": "bower_components/paper-header-panel/paper-header-panel.html"
        },
        {
          "bower": {
            "PolymerElements/paper-menu": "^1.0.0"
          },
          "src": "bower_components/paper-menu/paper-menu.html"
        },
        {
          "bower": {
            "PolymerElements/paper-item": "^1.0.0"
          },
          "src": "bower_components/paper-item/paper-item.html"
        }
      ],
      "scope": {
        "menuItems": ["/menu-abcd/home-abcd", "/menu-abcd/elements-abcd", "/menu-abcd/map-abcd"],
        "backgroundImages": [],
        "backgroundColors": [],
        "path": "/menu-abcd",
        "headerShown": false,
        "headerBackgroundImage": "",
        "headerBackgroundColor": "",
        "headerReverse": false,
        "headerTitle": "",
        "headerTitleShown": true,
        "headerLogo": "",
        "headerLogoShown": true,
        "headerAlignment": "left",
        "showicons": true,
        "toolbarTitle": true,
        "toolbarLogo": ""
      }
    },
    "/menu-abcd/home-abcd": {
      "name": "Home",
      "identifier": "html",
      "type": "A",
      "icon": "home",
      "showOn": {
        "market": true,
        "dragDrop": true
      },
      "view": "modules/html/index.html",
      "files": ["modules/html/controller.js"],
      "scope": {
        "value": "<p style='color:#39a9d3'>Welcome to my </p><p style='color:#d36339'>APP</p>"
      }
    },
    "/menu-abcd/map-abcd": {
      "name": "Google Maps",
      "identifier": "googlemap",
      "type": "A",
      "icon": "room",
      "showOn": {
        "market": true,
        "dragDrop": true
      },
      "view": "modules/googlemap/index.html",
      "files": ["modules/googlemap/controller.js", "modules/googlemap/directive.js", "modules/googlemap/style.css"],
      "libs": [{
        "bower": {
          "GoogleWebComponents/google-map": "^1.1.7"
        },
        "src": "bower_components/google-map/google-map.html"
      }],
      "scope": {
        "lat": "39.8847281",
        "lon": "4.2540999",
        "zoom": "15"
      }
    }
  }
}

```

Key | Description | Default value
----------------|-------------|--------
`config.index` | The default route when opening the app | ""
`config.colors` | Object containing the different colors used by the app | {}
`config.lang` | Available languages for the app. [Check-out the language support](#module-language-support) | ["en_US"]
`modules` | Module configurations | {}

Explanation: In this example there are 3 modules. First of all there is a menu using the [polymer menu module](https://github.com/KingofApp/koapp-module-polymermenu) obtaining the elements list from the [menuItems](#the-menu-standards) property set to false so it wont appear as a menu element. Then an [html module](https://github.com/KingofApp/koapp-module-html) used as the home screen configured in the `config.index` of the application config structure and a third [google map module](https://github.com/KingofApp/koapp-module-googlemap).

## Module List
* [koapp-module-list](https://github.com/KingofApp/koapp-module-list)
* [koapp-module-contact](https://github.com/KingofApp/koapp-module-contact)
* [koapp-module-embed](https://github.com/KingofApp/koapp-module-embed)
* [koapp-module-facebookfeed](https://github.com/KingofApp/koapp-module-facebookfeed)
* [koapp-module-firebase](https://github.com/KingofApp/koapp-module-firebase)
* [koapp-module-flickrfeed](https://github.com/KingofApp/koapp-module-flickrfeed)
* [koapp-module-googlemap](https://github.com/KingofApp/koapp-module-googlemap)
* [koapp-module-grouplist](https://github.com/KingofApp/koapp-module-grouplist)
* [koapp-module-html](https://github.com/KingofApp/koapp-module-html)
* [koapp-module-instagramfeed](https://github.com/KingofApp/koapp-module-instagramfeed)
* [koapp-module-instagramhash](https://github.com/KingofApp/koapp-module-instagramhash)
* [koapp-module-pdfviewer](https://github.com/KingofApp/koapp-module-pdfviewer)
* [koapp-module-polymermenu](https://github.com/KingofApp/koapp-module-polymermenu)
* [koapp-module-fullmenu](https://github.com/KingofApp/koapp-module-fullmenu)
* [koapp-module-topmenu](https://github.com/KingofApp/koapp-module-topmenu)
* [koapp-module-boxmenu](https://github.com/KingofApp/koapp-module-boxmenu)
* [koapp-module-bottommenu](https://github.com/KingofApp/koapp-module-bottommenu)
* [koapp-module-angularmenu](https://github.com/KingofApp/koapp-module-angularmenu)
* [koapp-module-rss](https://github.com/KingofApp/koapp-module-rss)
* [koapp-module-simplegallery](https://github.com/KingofApp/koapp-module-simplegallery)
* [koapp-module-twitterfeed](https://github.com/KingofApp/koapp-module-twitterfeed)
* [koapp-module-vimeovideo](https://github.com/KingofApp/koapp-module-vimeovideo)
* [koapp-module-youtubegallery](https://github.com/KingofApp/koapp-module-youtubegallery)
* [koapp-module-youtubevideo](https://github.com/KingofApp/koapp-module-youtubevideo)
* [koapp-service-ads](https://bitbucket.org/koapp/koapp-service-ads)

## Demo List
* [Working with ngClick and ngRepeat](https://github.com/KingofApp/koapp-demo-ngrepeatclick)
* [Working with the storage service](https://github.com/KingofApp/koapp-demo-storagesample)

## Module category list

`social`
`news`
`forms`
`others`
`maps`
`media`
`menu`

## Module language support

```
ar
ar_EG
ar_IL
bg
ca
cs
da
de_AT
de_CH
de_DE
de_LI
el
en_AU
en_CA
en_GB
en_IE
en_IN
en_NZ
en_SG
en_US
en_ZA
es_ES
es_MX
es_US
fi
fr_BE
fr_CA
fr_CH
fr_FR
he
hi
hr
hu
id
it
ja
ko
lt
lv
ms
nb
nl
pl
pt_BR
pt_PT
ro
ru
sk
sl_SI
sr
sv
th
tl_PH
tr
uk
vi
zh_CN
zh_Hans
zh_Hant
zh_HK
zh_TW
```
