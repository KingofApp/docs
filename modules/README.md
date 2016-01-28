# King of App Modules

King of App modules are composed of [AngularJS](https://angularjs.org/) logic and presented with our custom [Polymer elements](https://github.com/KingofApp/docs/tree/master/themes).

#### Table of contents
* [ The module structure ](#the-module-structure)  
* [ Multi language modules ](#multi-language-modules)  
* [ Simple modules ](#simple-modules)  
* [ Container modules ](#container-modules)  
* [ Menu modules ](#menu-modules)  
* [ Dependencies in modules ](#dependencies-in-modules)  
* [ Presenting data in modules ](#presenting-data-in-modules)
* [ Module config in builder ](#module-config-in-builder)  
* [ Get started ](#get-started)
* [ The advertising module ](#get-started)  
* [ Module list ](#module-list)  

## The module structure
Modules are composed of [files](#the-module-files) and [libs](#the-module-libs) that read from a [config structure json](#the-module-config-structure).

### The module config structure

For a module called testmodule this would be the config structure:

```json
{
  "name"       : "Test module",
  "identifier" : "testmodule",
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
    "menu"     : "true",
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
  "config"     : []
}
```

Key | Description | Default value
----------------|-------------|--------
`name` | Module name | ""
`identifier` | A unique name for your module that will be used to register the module and it's files. | ""
`type` | Currently our modules only support Angular | A
`version` | Version control | 0.0.1
`author` | Author name | ""
`category` | Categories to which your module belongs. [ Check-out our list ](#module-category-list)  | "others"
`requires` | Certain modules require other modules to work properly. [ Youtube gallery module ](https://github.com/KingofApp/koa-module-youtubegallery)  | []
`canContain` | Set to true if the module can adopt other modules inside them.[Check-out the  container module](#container-modules) type. | False
`showOn.menu` | Property defined by user in the KingOfApp builder| True
`showOn.market` | Property to make the module selectable by the users in our market. | True
`showOn.dragDrop` | Property to disable the drag and drop option from the KingOfApp builder | True
`view` | Main view file | "modules/{identifier}/index.html"
`files` | Array of files that will be loaded. [Check-out the module files section](#the-module-files) | []
`libs` | Array of bower dependencies used in the module. [Check-out the module scope section](#the-module-scope) | []
`deps` | Array of phonegap dependencies. | []
`scope` | Data Object that will be accessible from the module. | {}
`config` | Formly based config for the KingOfApp builder. [ Check-out module config in builder ](#module-config-in-builder)| {}

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
* [Directives](https://docs.angularjs.org/guide/directive) - Sample
* [Filters](https://docs.angularjs.org/guide/filter) - Sample
* [Services / factories](https://docs.angularjs.org/guide/services) - Sample
* Run - Sample
* [Controllers](https://docs.angularjs.org/guide/controller) - Sample

Other files supported:

* Css files (.css) - Sample
* jQuery files (.js) - Sample


### The module libs

Dependencies that get loaded along with the modules files can be:

* AngularJs modules (.js) - Sample
* Polymer components (.html) - Sample

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
    "menu": true,
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

NOTE: Remember to specify the `requires` property in [ the module config structure ](#the-module-config-structure) if your module requires any other module. Example: [Youtube gallery module](https://github.com/KingofApp/koa-module-youtubegallery)

### Inside module events
```javascript
$rootScope.$on("koaAppRendered",function() {
  //Your code here

});
```
Checkout our [simplegallery module](https://github.com/KingofApp/koa-module-simplegallery).

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

[Firebase module](https://github.com/KingofApp/koa-module-firebase)
This module acts as a parent module [connector](#connector-modules)

[Firebase list module](https://github.com/KingofApp/koa-module-list)
This module uses the Firebase module's service to make the requests to firebase.

NOTE: The idea of using parent module connectors is to enable children modules to obtain data from different sources.

In this case, the firebase list module requires the firebase module, so it will have the `requires` property in [ the module config structure ](#the-module-config-structure) set to firebase.
In the other hand, the firebase connector module will have the showOnmenu to false by default.

### Menu modules

Menus can be built with polymer elements or angular.

Polymer menu particularities:
* Specific controller
* Directive to pass the menu items to polymer
* Access to the toolbar scope within the view

[Polymer menu Example](https://github.com/KingofApp/koa-module-polymermenu)

Angular menu particularities:
* Specific controller
* Specific styles.html to read the templates color variables
* Access to the toolbar scope within the view

[Angular menu Example](https://github.com/KingofApp/koa-module-angularmenu)

### Connector modules

[Firebase connector example](https://github.com/KingofApp/koa-module-firebase)

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
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope.
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
`key` | Same key used in the [module config structure](#the-module-config-structure) inside scope.
`templateOptions.type` | Formly element type
`templateOptions.label` | Visible field name
`templateOptions.pattern` | Regular expression validation
`templateOptions.required` | Validation for required fields
`templateOptions.maxlength` | Character max length
`templateOptions.description` | Visible description under input

#### Select

...ToDo...

#### WYSIWYG editor

...ToDo...

## Getting started

1. Install the [com.kingofapp.visualizer](#).

  ```
  npm install com.kingofapp.visualizer
  ```

2. Files of interest.
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

3. Serve all the files with a basic HTTP serve.

  For example with [serve](https://www.npmjs.com/package/serve):

  ```
  npm install -g serve
  ```
  Run serve inside the com.kingofapp.visualizer folder.

  ```
  serve
  ```

### Application config structure sample

The main configuration file is located in `/app/core/structure.json`

A structure.json app example:

```json
{
  "config": {
    "index": "/menu-abcd/home-abcd",
    "theme": "koa-paper-theme",
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
    "lang": [
      "en_US"
    ]
  },
  "modules": {
    "/menu-abcd": {
      "name": "Menu Module",
      "identifier": "polymermenu",
      "type": "A",
      "showOn": {
        "menu": false,
        "market": true,
        "dragDrop": true
      },
      "canContain": true,
      "view": "modules/polymermenu/index.html",
      "files": ["modules/polymermenu/controller.js"],
      "libs": [{
        "bower": {
          "polymer/polymer": "^1.0.0"
        },
        "src": "bower_components/polymer/polymer.html"
      }, {
        "bower": {
          "PolymerElements/paper-drawer-panel": "^1.0.0"
        },
        "src": "bower_components/paper-drawer-panel/paper-drawer-panel.html"
      }, {
        "bower": {
          "PolymerElements/paper-header-panel": "^1.0.0"
        },
        "src": "bower_components/paper-header-panel/paper-header-panel.html"
      }, {
        "bower": {
          "PolymerElements/paper-menu": "^1.0.0"
        },
        "src": "bower_components/paper-menu/paper-menu.html"
      }, {
        "bower": {
          "PolymerElements/paper-scroll-header-panel": "^1.0.0"
        },
        "src": "bower_components/paper-scroll-header-panel/paper-scroll-header-panel.html"
      }, {
        "bower": {
          "PolymerElements/paper-item": "^1.0.0"
        },
        "src": "bower_components/paper-item/paper-item.html"
      }],
      "scope": {
        "path": "/menu-abcd"
      }
    },
    "/menu-abcd/home-abcd": {
      "name": "Home",
      "identifier": "html",
      "type": "A",
      "showOn": {
        "menu": true,
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
      "name": "Google Map Example",
      "identifier": "googlemap",
      "type": "A",
      "showOn": {
        "menu": true,
        "market": true,
        "dragDrop": true
      },
      "view": "modules/googlemap/index.html",
      "files": ["modules/googlemap/controller.js", "modules/googlemap/directive.js"],
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

Explanation: In this example there are 3 modules. First of all there is a menu using the [polymer menu module](https://github.com/KingofApp/koa-module-polymermenu) with a [showOn.menu](#the-module-config-structure) property set to false so it wont appear as a menu element. Then an [html module](https://github.com/KingofApp/koa-module-html) used as the home screen configured in the `config.index` of the application config structure and a third [google map module](https://github.com/KingofApp/koa-module-googlemap).

## Module List
* [koa-module-list](https://github.com/KingofApp/koa-module-list)
* [koa-module-angularmenu](https://github.com/KingofApp/koa-module-angularmenu)
* [koa-module-contact](https://github.com/KingofApp/koa-module-contact)
* [koa-module-embed](https://github.com/KingofApp/koa-module-embed)
* [koa-module-facebookfeed](https://github.com/KingofApp/koa-module-facebookfeed)
* [koa-module-firebase](https://github.com/KingofApp/koa-module-firebase)
* [koa-module-flickrfeed](https://github.com/KingofApp/koa-module-flickrfeed)
* [koa-module-googlemap](https://github.com/KingofApp/koa-module-googlemap)
* [koa-module-grouplist](https://github.com/KingofApp/koa-module-grouplist)
* [koa-module-html](https://github.com/KingofApp/koa-module-html)
* [koa-module-instagramfeed](https://github.com/KingofApp/koa-module-instagramfeed)
* [koa-module-pdfviewer](https://github.com/KingofApp/koa-module-pdfviewer)
* [koa-module-polymermenu](https://github.com/KingofApp/koa-module-polymermenu)
* [koa-module-rss](https://github.com/KingofApp/koa-module-rss)
* [koa-module-simplegallery](https://github.com/KingofApp/koa-module-simplegallery)
* [koa-module-twitterfeed](https://github.com/KingofApp/koa-module-twitterfeed)
* [koa-module-vimeovideo](https://github.com/KingofApp/koa-module-vimeovideo)
* [koa-module-youtubegallery](https://github.com/KingofApp/koa-module-youtubegallery)
* [koa-module-youtubevideo](https://github.com/KingofApp/koa-module-youtubevideo)
* [koa-module-ads](https://github.com/KingofApp/koa-module-ads)

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
