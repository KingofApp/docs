//TODOOOoOOOOOOOO
* Application config structure sample

* Simple modules


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
│   ├── locale-en_US.json
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
Inside [the module file structure](#the-module-structure) a folder locale will contain the different translation files with the following file syntax : locale-{language}.json based on [Module language support](#module-language-support).

For an example using locale-en_US.json with the identifier moduletest:
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

To avoid conflicts with other modules, it's recommended to use {identifier}.variable inside the locale-en_US.json.

## Simple modules
TODO

This is a html module example:

### The module scope

### Structure service inside modules

Accessible structureService service within the module controller:

Functions | Description | Expects | Returns
----------------|-------------|--------|--------
`get()` | Returns the [application object](#application-config-structure-sample).  | null | JSON Object
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

## Get started

## Samples

### Application config structure sample
structure.json:

```json
{

}
```

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
