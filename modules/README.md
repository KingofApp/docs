//TODOOOoOOOOOOOO
* Application config structure sample

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
`requires` | Certain modules require other modules to work properly. [Youtube gallery module] (#)  | null
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

NOTE: Remember to specify the `requires` property in [ the module config structure ](#the-module-config-structure) if your module requires any other module. Example: [Youtube gallery module](#)

## Container modules

Container modules share file structure, config structure and controller with simple modules. But has a different view ....


These modules can access the scope and services from the children - TOTEST
The children can access the scope and services from the parent - TOTEST

### Container module examples



NOTE: Remember to specify the `canContain` property in [ the module config structure ](#the-module-config-structure) if your module can contain other modules inside Example:menu modules.

### Menu modules

Polymer and angular menus supported, examples.

TODO: BRING BACK ANGULAR MODULE LINK TO SAMPLE

## Dependencies in modules

## Presenting data in modules

## Module config in builder
Using  [Angular formly](http://angular-formly.com/):

## Get started


### Application config structure sample

The main configuration file is located in `/app/core/structure.json`

A structure.json app example:

```json
{
  "config": {
    "index": "/home-abcd",
    "colors": {
      "--default-primary-color": "#ffffff",
      "--dark-primary-color": "#222222",
      "--light-primary-color": "#ececec",
      "--text-primary-color": "#000000",
      "--accent-color": "#b43322",
      "--primary-background-color": "#ffffff",
      "--primary-text-color": "#212121",
      "--secondary-text-color": "#727272",
      "--disabled-text-color": "#333532",
      "--divider-color": "#ececec"
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
      "name": "Html Example",
      "identifier": "googlemap",
      "type": "A",
      "showOn": {
        "menu": true,
        "market": true,
        "dragDrop": true
      },
      "view": "modules/googlemap/index.html",
      "files": ["modules/googlemap/controller.js"],
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

Explanation: In this example there are 3 modules. First of all there is a menu using the [polymer menu module](#) with a [showOn.menu](#the-module-config-structure) property set to false so it wont appear as a menu element. Then an [html module](#) used as the home screen configured in the `config.index` of the application config structure and a [third google map module](#).
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
