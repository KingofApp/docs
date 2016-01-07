# King of App Modules

King of App modules are composed of [AngularJS](https://angularjs.org/) logic and presented with our custom [Polymer elements](https://github.com/KingofApp/docs/tree/master/themes).

#### Table of contents
[ The module structure ](#the-module-structure)  
[ Multi language modules ](#multi-language-modules)  
[ Simple modules ](#simple-modules)  
[ Container modules ](#container-modules)  
[ Menu modules ](#menu-modules)  
[ Dependencies in modules ](#dependencies-in-modules)  
[ Presenting data in modules ](#presenting-data-in-modules)
[ Module config in builder ](#module-config-in-builder)  

## Application config structure
TODO
## The module structure
Modules are composed of files that read from a config json...

### The module config structure

For a module called testmodule this would be the config structure:

```json
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
"scope"      : {
  "data"  : "Sample data"
},
"config"     : []
```

Key | Description | Default value
----------------|-------------|--------
`name` | Module name |
`identifier` | A unique name for your module that will be used to register the module and it's files. |
`type` | Currently our modules only support Angular | A
`version` | Version control |
`author` | Author name |
`category` | Categories to which your module belongs. [ Check-out our list ](#module-category-list)  |
`requires` | Certain modules require other modules to work properly  | null
`canContain` | Set to true for [container module](#container-modules) type. | False
`showOn.menu` | Property defined by user in the KingOfApp builder| True
`showOn.market` | Property to make the module selectable by the users in our market. | True
`showOn.dragDrop` | Property to disable the drag and drop option from the KingOfApp builder | True
`view` | Main view file | "modules/{identifier}/index.html"
`files` | Array of files that will be loaded. Checkout [the module files section](#the-module-files) |
`libs` | Array of bower dependencies used in the module. Checkout [the module libs section](#the-module-libs) |
`scope` | Data Object that will be accessible from the module. | {}
`config` | Formly based config for the KingOfApp builder. [ Check-out module config in builder ](#module-config-in-builder)|

NOTE: Some modules may have a module dependency `Example: A list module with a Firebase module connector`.






### The module files


#### The module file structure

For a module called testmodule this would be the file structure:

```
testmodule
├── locale
│   ├── locale-en.json
│   └── ...
├── controller.js
└── index.html
```

### The module libs


## Multi language modules
To avoid conflicts with other modules, it's recommended to use moduleid.variable inside the locale json.

## Simple modules


This is a html module example:



Accesible structureService functions within the module controller:

Functions | Description | Expects | Returns
----------------|-------------|--------|--------
`get()` | Returns the [application object](#application-config-structure).  | null | JSON Object
`getModule(path, callback)` | Returns a module config structure from a given path. | path - "/route" | JSON Object
`getCurrentModules($location, callback)` | Returns an array with the modules used in the current location. `Useful for finding parent module` | $location | Array
`getChildren()` | Returns an array with all the children modules of the given path. | path - "/route" | Array

NOTE: Remember to specify the `requires` property in [ the module config structure ](#the-module-config-structure) if your module requires any other module.

NOTE: Remember to specify the `canContain` property in [ the module config structure ](#the-module-config-structure) if your module can contain other modules inside Example:menu modules.

## Container modules

## Menu modules

## Dependencies in modules

## Presenting data in modules

## Module config in builder


### Module category list

`social`
`news`
`forms`
`others`
`maps`
`media`
`menu`
