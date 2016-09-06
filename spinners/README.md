# King of App spinners

A King of App spinner is an element built with [Polymer](https://www.polymer-project.org), like the [theme elements](../themes/README.md#list-of-elements).

#### Table of contents
* [ Spinner config ](#spinner-config)
* [ Creating spinner from scratch ](#creating-spinner-from-scratch)
* [ Available colors ](#available-colors)
* [ Demo spinner list ](#demo-spinner-list)
* [ Extended documentation ](#extended-documentation)



## Spinner config
Spinners are declared inside the structure.json of the [king of app visualizer](https://github.com/KingofApp/com.kingofapp.visualizer).

```json
{
  ...
  "config": {
    ...
    "spinner": {
      "identifier": "koapp-spinner-rotationplane",
      "path": "spinners/koapp-spinner-rotationplane/koapp-spinner-rotationplane.html"
    },
    ...
  }
  ...
}
```
Spinners config.json:
```json
{
  "name": "Rotation Plane",
  "identifier": "koapp-spinner-rotationplane",
  "description": {
    "en-US" : "",
    "es-ES" : ""
  },
  "version": "0.0.1",
  "author": "King of App",
  "category": [],
  "price": 0,
  "showOn": {
    "market": true
  },
  "main": "spinners/koapp-spinner-rotationplane/koapp-spinner-rotationplane.html"
}
```
Key | Description | Default value
----------------|-------------|--------
`name` | Spinner name | ""
`identifier` | A unique name for your module that will be used to register the module and it's files. (Only alphabetic characters allowed) | ""
`description` | Multilanguage supported description used in the KingOfApp builder | {}
`version` | Version control | 0.0.1
`author` | Author name | ""
`category` | Categories to which your spinner belongs.  | []
`price` | Purchase price displayed for the module in the KingOfApp builder | 0
`showOn.market` | Property to make the module selectable by the users in our market. | True
`main` | Url to the spinner | "spinners/koapp-spinner-{identifier}/koapp-spinner-{identifier}.html"

## Creating spinner from scratch
### File structure
```
koapp-spinner-template
├── .bowerrc
├── bower.json
├── config.json
└── koapp-spinner-template.html
```
`.bowerrc` file to ensure dependencies are downloaded in the correct directory inside the [king of app visualizer](https://github.com/KingofApp/com.kingofapp.visualizer):
```json
{
  "directory" : "../../bower_components"
}
```
`bower.json` file containing dependencies (Polymer and Koa Behaviors):
```json
{
  ...
  "dependencies": {
    "polymer": "Polymer/polymer#^1.2.0",
    "koa-behaviors": "KingofApp/koa-behaviors#^0.11.0"
  },
  "devDependencies": {
    "webcomponentsjs": "webcomponents/webcomponentsjs#^0.7.0"
  }
}
```
`koapp-spinner-template.html` Main polymer element file:
```html
<link rel="import" href="../../bower_components/polymer/polymer.html">
<link rel="import" href="../../bower_components/koa-behaviors/koa-spinner-behavior.html">

<dom-module id="koapp-spinner-template">
  <template strip-whitespace>
    <style>
      /* Css animations here */
    </style>

    <!-- Write your html template here -->

    <!-- end template -->
  </template>

  <script>
    Polymer({
      is: 'koapp-spinner-template',

      behaviors: [
        Polymer.KoaSpinnerBehavior
      ]
    });
  </script>
</dom-module>
```



## Available colors

Color property | Description
----------------|-------------
`--primary-text-color` | Primary text color is used as a general text color.
`--primary-background-color` | Background color is used in items, cards, dialogs, drop-downs or menus.
`--secondary-text-color` | Found in any text that does not display a primary information.
`--disabled-text-color` | Third type of text color, it is used to display disabled options.
`--divider-color` | Used in dividers like cards or items
`--primary-color` | The most used color in your app.
`--light-primary-color` | Modified version of primary color to highlight.
`--dark-primary-color` | Modified version of primary color to create shadows.
`--accent-color` | High contrast color that should be different from Primary Color, Text Color or Background Color.
`--light-accent-color` | Modified version of accent color to highlight.
`--dark-accent-color` | Modified version of accent color to create shadows.
`--background-color` | Color used for the application background.



## Demo spinner list

* [koapp-spinner-rotationplane](https://bitbucket.org/koapp/koapp-spinner-rotationplane).
* [koapp-spinner-rotationplane](https://bitbucket.org/koapp/koapp-spinner-rotationplane).

## Extended documentation

* Official [polymer paper-spinner.](https://elements.polymer-project.org/elements/paper-spinner?view=demo)

* [KoaSpinnerBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-spinner-behavior.html)
