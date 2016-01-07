//TODOOOoOOOOOOOO  
* Multilanguage- TEST LAST TRANSLATE DIRECTIVE
* The module files - validate jquery and css as libs not files

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
`name` | Module name | ""
`identifier` | A unique name for your module that will be used to register the module and it's files. | ""
`type` | Currently our modules only support Angular | A
`version` | Version control | 0.0.1
`author` | Author name | ""
`category` | Categories to which your module belongs. [ Check-out our list ](#module-category-list)  | "others"
`requires` | Certain modules require other modules to work properly  | null
`canContain` | Set to true for [container module](#container-modules) type. | False
`showOn.menu` | Property defined by user in the KingOfApp builder| True
`showOn.market` | Property to make the module selectable by the users in our market. | True
`showOn.dragDrop` | Property to disable the drag and drop option from the KingOfApp builder | True
`view` | Main view file | "modules/{identifier}/index.html"
`files` | Array of files that will be loaded. [Check-out the module files section](#the-module-files) | []
`libs` | Array of bower dependencies used in the module. [Check-out the module scope section](#the-module-scope) | []
`scope` | Data Object that will be accessible from the module. | {}
`config` | Formly based config for the KingOfApp builder. [ Check-out module config in builder ](#module-config-in-builder)| {}

NOTE: Some modules may have a module dependency `Example: A list module with a Firebase module connector`.

### The module file structure

For a module called testmodule this would be the file structure:

```
testmodule
├── locale
│   ├── locale-en.json
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

* Css files (THROUGH LIBS OR FILES???)
* jQuery files (THROUGH LIBS OR FILES????)


### The module libs

Dependencies that get loaded along with the modules files can be:

* AngularJs modules - Sample
* Polymer components - Sample

## Multi language modules

Using  [Angular translate](https://angular-translate.github.io/):

with a locale-en.json example:
```json
{
  "moduletest.text1": "First text",
  "moduletest.text2": "Second text",
  "moduletest.text3": "Third text",
  "moduletest.text4": "My name is: {{variable}}"
}

```

data can be translated in different ways:
```
<p>{{ "moduletest.text1" | translate }}</p>
<p translate>moduletest.text2</p>
<p translate>{{ "moduletest.text3" }}</p>
<p translate="moduletest.text4" translate-values="{ variable:'World' }"> </p>
```

To avoid conflicts with other modules, it's recommended to use moduleid.variable inside the locale json.

## Simple modules
TODO

This is a html module example:

### The module scope

### Structure service inside modules

Accessible structureService service within the module controller:

Functions | Description | Expects | Returns
----------------|-------------|--------|--------
`get()` | Returns the [application object](#application-config-structure).  | null | JSON Object
`getModule(path, callback)` | Returns a module config structure from a given path. | path - "/route" | JSON Object
`getCurrentModules($location, callback)` | Returns an array with the modules used in the current location. `Useful for finding parent module` | $location | Array
`getChildren()` | Returns an array with all the children modules of the given path. | path - "/route" | Array


## Container modules

NOTE: Remember to specify the `requires` property in [ the module config structure ](#the-module-config-structure) if your module requires any other module.

NOTE: Remember to specify the `canContain` property in [ the module config structure ](#the-module-config-structure) if your module can contain other modules inside Example:menu modules.

### Menu modules

## Dependencies in modules

## Presenting data in modules

## Module config in builder
Using  [Angular formly](http://angular-formly.com/):

### Module category list

`social`
`news`
`forms`
`others`
`maps`
`media`
`menu`
