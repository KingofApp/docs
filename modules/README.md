AQUI PONER UN INDICE

# King of App Modules

A King of App modules are composed of [AngularJS](https://angularjs.org/) logic and presented with our custom Polymer elements.

#### Table of contents
[ The module structure ](#the-module-structure)  
[ Multi language modules ](#multi-language-modules)  
[ Simple modules ](#simple-modules)  
[ Container modules ](#container-modules)  
[ Menu modules ](#menu-modules)  
[ Dependencies in modules ](#dependencies-in-modules)  
[ Presenting data in modules ](#presenting-data-in-modules)
[ Module config in builder ](#module-config-in-builder)  

## Application sample
TODO
## The module structure

* File structure, directives, filters,
* Config structure
* Point that allows external Dependencies
* Types of Modules
* Access to StructureService

### The module config structure

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

Key | Description | Default
----------------|-------------|--------
`name` | Module name |
`identifier` | A unique name for your module that will be used to register the module and it's files. |
`type` | Currently our modules only support Angular | A
`version` | Version control |
`author` | Author name |
`category` | Categories which your module belongs to. [ Check-out our list ](#module-category-list)  |
`requires` | Module name |
`canContain` | Module name | False
`showOn.menu` | Module name | True
`showOn.market` | Module name | True
`showOn.dragDrop` | Module name | True
`view` | Module name | "modules/{identifier}/index.html"
`files` | Module name |
`libs` | Module name |
`scope` | Module name |
`config` | Module name  [ Check-out module config in builder ](#module-config-in-builder)|

### The module file structure

For a module called testmodule this would be the structure:

```
testmodule
├── locale
│   ├── locale-en.json
│   └── ...
├── controller.js
└── index.html
```

## Multi language modules
To avoid conflicts with other modules, it's recommended to use moduleid.variable inside the locale json.

## Simple modules

StructureService functions:

Functions | Description | Expects | Returns
----------------|-------------|--------
`get()` | TODO | null | JSON Object
`getModule(path, callback)` | TODO | path - "/route" | JSON Object
`getCurrentModules($location, callback)` | TODO | $location | JSON Object
`getChildren()` | TODO | TODO | JSON Object

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
