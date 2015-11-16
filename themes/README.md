# King of App themes

A King of App theme is composed of a set of elements built with [Polymer](https://www.polymer-project.org).

## About elements

Each element must have its own directory. The directory´s name must be formed with the name of the theme and the name of the tag, separated by a dash (-). Inside the directory, you must have an HTML file with the same name, and the folder `demo` with the example.

For example, if the theme is called AwesomeTheme, `koa-button` element would have the following structure:

```
awesometheme-button
├── demo
│   └── index.html
└── awesometheme-button.html
```

Each element is composed by:

* **Host attributes**: Using [Polymer host attributes](https://www.polymer-project.org/1.0/docs/devguide/registering-elements.html#host-attributes), you can set HTML attributes on the element at create-time.
* **Properties**: Using [Polymer properties](https://www.polymer-project.org/1.0/docs/devguide/properties.html), you can add properties.
* **Styling**: Using [Polymer styling](https://www.polymer-project.org/1.0/docs/devguide/styling.html), you can use the custom properties and the mixins in CSS.
* **Methods**: Using Polymer methods, you can expose methods.
* **Behaviors**: Using [Polymer behaviors](https://www.polymer-project.org/1.0/docs/devguide/behaviors.html), you can inherit behaviors with their properties and methods.

You'll have to add all the properties, host attributes, styling, methods and behaviors of each element in yours.

Our [koa-theme generator](https://github.com/KingofApp/generator-koa-theme) give you a scaffold with all these things.

## List of elements

* [koa-badge](elements/koa-badge.md#koa-badge)
* [koa-button](elements/koa-button.md#koa-button)
* [koa-card](elements/koa-card.md#koa-card)
* [koa-checkbox](elements/koa-checkbox.md#koa-checkbox)
* [koa-dialog](elements/koa-dialog.md#koa-dialog)
* [koa-dropdown-menu](elements/koa-dropdown-menu.md#koa-dropdown-menu)
* [koa-header-panel](elements/koa-header-panel.md#koa-header-panel)
* [koa-icon-button](elements/koa-icon-button.md#koa-icon-button)
* [koa-input](elements/koa-input.md#koa-input) & [koa-textarea](elements/koa-input.md#koa-textarea)
* [koa-item](elements/koa-item.md#koa-item)
* [koa-menu-button](elements/koa-menu-button.md#koa-menu-button)
* [koa-menu](elements/koa-menu.md#koa-menu)
* [koa-progress](elements/koa-progress.md#koa-progress)
* [koa-radio-button](elements/koa-radio-button.md#koa-radio-button)
* [koa-slider](elements/koa-slider.md#koa-slider)
* [koa-spinner](elements/koa-spinner.md#koa-spinner)
* [koa-tabs](elements/koa-tabs.md#koa-tabs)
* [koa-toggle-button](elements/koa-toggle-button.md#koa-toggle-button)
* [koa-toolbar](elements/koa-toolbar.md#koa-toolbar)

## Getting started

1. Install the [koa-theme generator](https://github.com/KingofApp/generator-koa-theme).

  `npm install -g generator-koa-theme`

2. Create a new theme with the generator.

  `yo koa-theme name-of-the-theme`

  Note: `name-of-the-theme` will be the ID of the theme.

3. Begins to change all elements as you want!
