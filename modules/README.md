# King of App Modules

A King of App modules are composed of [AngularJS](https://www.polymer-project.org) logic and presented with our custom Polymer elements.

## The module structure

* File structure, directives, filters,
* Config structure
* Point that allows external Dependencies
* Types of Modules
* Access to StructureService

Each element must have its own directory. The directory´s name must be formed with the name of the theme and the name of the tag, separated by a dash (-). Inside the directory, you must have an HTML file with the same name, and the folder `demo` with the example.

For example, if the theme is called AwesomeTheme, `koa-button` element would have the following structure:

```
testmodule
├── locale
│   ├── locale-en.json
│   └── ...
├── controller.js
└── index.html
```

## Multi language modules

## Simple modules

## Container modules

## Menu modules

## Dependencies in modules

## Presenting data in modules
