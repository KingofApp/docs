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

Each element is composed by one `KoaBehavior`:

* **KoaBehavior**: It is a [Polymer behavior](https://www.polymer-project.org/1.0/docs/devguide/behaviors.html) that contains most of the elements behavior: attributes, methods, etc.

And:

* **Behaviors**: Using [Polymer behaviors](https://www.polymer-project.org/1.0/docs/devguide/behaviors.html), you can inherit behaviors with their properties and methods.
* **Host attributes**: Using [Polymer host attributes](https://www.polymer-project.org/1.0/docs/devguide/registering-elements.html#host-attributes), you can set HTML attributes on the element at create-time.
* **Properties**: Using [Polymer properties](https://www.polymer-project.org/1.0/docs/devguide/properties.html), you can add properties.
* **Styling**: Using [Polymer styling](https://www.polymer-project.org/1.0/docs/devguide/styling.html), you can use the custom properties and the mixins in CSS.
* **Methods**: Using Polymer methods, you can expose methods.

You'll have to add all the properties, host attributes, styling, methods and behaviors of each element in yours.

Our [koa-theme generator](https://github.com/KingofApp/generator-koa-theme) give you a scaffold with all these things.

## List of elements

* [koa-badge](elements/koa-badge.md#koa-badge)
* [koa-button](elements/koa-button.md#koa-button)
* [koa-card](elements/koa-card.md#koa-card)
* [koa-checkbox](elements/koa-checkbox.md#koa-checkbox)
* [koa-dialog](elements/koa-dialog.md#koa-dialog)
* [koa-dropdown-menu](elements/koa-dropdown-menu.md#koa-dropdown-menu) (it uses `koa-input` and `koa-menu-button`)
* [koa-icon-button](elements/koa-icon-button.md#koa-icon-button)
* [koa-input](elements/koa-input.md#koa-input) (with [koa-textarea](elements/koa-input.md#koa-textarea))
* [koa-item](elements/koa-item.md#koa-item)
* [koa-menu](elements/koa-menu.md#koa-menu) (with [koa-submenu](elements/koa-menu.md#koa-submenu))
* [koa-menu-button](elements/koa-menu-button.md#koa-menu-button)
* [koa-progress](elements/koa-progress.md#koa-progress)
* [koa-radio-button](elements/koa-radio-button.md#koa-radio-button)
* [koa-slider](elements/koa-slider.md#koa-slider) (it uses `koa-input` and `koa-progress`)
* [koa-spinner](elements/koa-spinner.md#koa-spinner)
* [koa-tabs](elements/koa-tabs.md#koa-tabs) (with [koa-tab](elements/koa-tabs.md#koa-tab))
* [koa-toggle-button](elements/koa-toggle-button.md#koa-toggle-button)
* [koa-toolbar](elements/koa-toolbar.md#koa-toolbar)

## Getting started

1. If you haven't, install Yeoman and Bower. And the [koa-theme generator](https://github.com/KingofApp/generator-koa-theme).

  ```
  npm install -g bower
  ```

  ```
  npm install -g yo
  ```

  ```
  npm install -g generator-koa-theme
  ```

2. Create a new theme with the generator.

  ```
  yo koa-theme mythemename
  ```

  Note: `mythemename` will be the ID of the theme.

  Now, you have a scaffold like this:

  ```
  koa-mythemename-theme
  ├── dist
  │   └── koa-mythemename-theme.html
  ├── elements
  │   ├── mythemename-badge
  │   │    ├── demo
  │   │    │   └── index.html
  │   │    └── mythemename-badge.html
  │   ├── ...
  │
  ├── styles
  │   ├── default-theme.html
  │   └── main.css
  ├── .gitignore
  ├── bower.json
  ├── css-variables.json
  └── koa-mythemename-theme.html
  ```

3. Serve all the files with any HTTP server.

  For example with [serve](https://www.npmjs.com/package/serve):

  ```
  npm install -g serve
  ```

  ```
  serve koa-mythemename-theme
  ```

4. Begins to change all elements as you want!

## Edit one element

Each element has a structure like this:

```
mythemename-button
├── demo
│   └── index.html
└── mythemename-button.html
```

In the `mythemename-button.html` you change the element.
It has a structure like this:

```html
<!-- write your imports here -->

<dom-module id="mythemename-button">
  <template>
    <!-- write your styles here -->
    <style>

    </style>
    <!-- end styles -->

    <!-- write your template here -->

    <!-- end template -->
  </template>

  <script>
    Polymer({
      is: 'mythemename-button',

      behaviors: [
        Polymer.KoaButtonBehavior
      ],

      // Logic here. hostAttributes, behaviors: [], properties, methods, etc
    });
  </script>
</dom-module>
```

The generator give you imports, hostAttributes, behaviors, properties, methods, etc.

Example for the `koa-button`:

```html
<link rel="import" href="../../bower_components/polymer/polymer.html">
<link rel="import" href="../../bower_components/koa-behaviors/koa-button-behavior.html">

<dom-module id="mythemename-button">
  <template>
    <!-- write your styles here -->
    <style>

    </style>
    <!-- end styles -->

    <!-- write your template here -->

    <!-- end template -->
  </template>

  <script>
    Polymer({
      is: 'mythemename-button',

      behaviors: [
        Polymer.KoaButtonBehavior
      ]
    });
  </script>
</dom-module>
```

Now we can start to customize the element.

1. Add the template.

  ```html
  <content></content>
  ```

  Note: [`<content>`](https://www.polymer-project.org/1.0/docs/devguide/local-dom.html#dom-distribution) element provides an insertion point.

2. Add the styles

  ```css
  :host {
    cursor: pointer;
    display: inline-block;
    font-size: 14px;
    font-weight: 400;
    line-height: 1.42857143;
    margin-bottom: 0;
    padding: 6px 12px;
    text-align: center;
    vertical-align: middle;
    white-space: nowrap;
  }
  :host(:not[link]) {
    background-color: #fff;
    border-radius: 4px;
    border: 1px solid #ccc;
    color: #333;
  }
  :host([link]) {
    color: #23527c;
    text-decoration: underline;
  }
  :host([active]),
  :host([pressed]) {
    color: #333;
    background-color: #e6e6e6;
    border-color: #adadad;
  }
  :host([big]) {
    border-radius: 6px;
    font-size: 18px;
    line-height: 1.3333333;
    padding: 10px 16px;
  }
  :host([disabled]) {
    background-color: #e0e0e0;
    border-color: #ccc;
  }
  :host([focused]) {
    background-color: #e6e6e6;
    border-color: #8c8c8c;
    color: #333;
    text-decoration: none;
  }
  ```

  Note: `:host` selector selects himself.

Now we have the custom element:


```html
<link rel="import" href="../../bower_components/polymer/polymer.html">
<link rel="import" href="../../bower_components/koa-behaviors/koa-button-behavior.html">

<dom-module id="mythemename-button">
  <template>
    <!-- write your styles here -->
    <style>
      :host {
        cursor: pointer;
        display: inline-block;
        font-size: 14px;
        font-weight: 400;
        line-height: 1.42857143;
        margin-bottom: 0;
        padding: 6px 12px;
        text-align: center;
        vertical-align: middle;
        white-space: nowrap;
      }
      :host(:not[link]) {
        background-color: #fff;
        border-radius: 4px;
        border: 1px solid #ccc;
        color: #333;
      }
      :host([link]) {
        color: #23527c;
        text-decoration: underline;
      }
      :host([active]),
      :host([pressed]) {
        color: #333;
        background-color: #e6e6e6;
        border-color: #adadad;
      }
      :host([big]) {
        border-radius: 6px;
        font-size: 18px;
        line-height: 1.3333333;
        padding: 10px 16px;
      }
      :host([disabled]) {
        background-color: #e0e0e0;
        border-color: #ccc;
      }
      :host([focused]) {
        background-color: #e6e6e6;
        border-color: #8c8c8c;
        color: #333;
        text-decoration: none;
      }
    </style>
    <!-- end styles -->

    <!-- write your template here -->
    <content></content>
    <!-- end template -->
  </template>

  <script>
    Polymer({
      is: 'mythemename-button',

      behaviors: [
        Polymer.KoaButtonBehavior
      ]
    });
  </script>
</dom-module>
```

## CSS custom properties and mixins

The King of App themes uses CSS custom properties to styling.

### Set the CSS custom properties

In the `styles/default-theme.html` you set the value of variables. Example:

```css
:root {
  --primary-text-color: #636363;
  --primary-background-color: #ffffff;
  --secondary-text-color: #636363;
  --disabled-text-color: #2f2b16;
  --divider-color: #e0e0e0;
  --primary-color: #ff003c;
  --light-primary-color: #c5cae9;
  ...
}
```

Also, you need to set the value of variables in the `css-variables.json`. Example:

```json
{
  "primaryTextColor": "#636363",
  "primaryBackgroundColor": "#ffffff",
  "secondaryTextColor": "#636363",
  "disabledTextColor": "#2f2b16",
  "dividerColor": "#e0e0e0",
  "primaryColor": "#ff003c",
  "lightPrimaryColor": "#c5cae9",
  ...
}
```

### Use the CSS custom properties

In the `style` tag, you can use CSS custom properties. The syntax is:

```
var(variable, defaultValue)
```

```html
<style is="custom-style">
  :host {
    color: var(--button-text-color, #ffffff);
  }
</style>
```

Also, you can use another custom property as default value:


```html
<style is="custom-style">
  :host {
    color: var(--button-text-color, --primary-text-color);
  }
</style>
```

### Typography

For now, we only supports Google Fonts as external fonts.

Import the font in the `styles/default-theme.html` with `@import url()` and use it in the font-family CSS custom properties. Example:

```html
<style is="custom-style">
  @import url(https://fonts.googleapis.com/css?family=Roboto);

  :host {
    --primary-font-family: 'Roboto';
    --title-font-family: 'Verdana';
  }
</style>
```

### Background color and background image

Use it in the color CSS custom properties in the `styles/default-theme.html`. Example:

```html
<style is="custom-style">
  :host {
    --background-color: #f8ecc2;
    --background-image: url('images/background.png');
  }
</style>
```

### Colors

Use it in the color CSS custom properties in the `styles/default-theme.html`. Example:

```html
<style is="custom-style">
  :host {
    --primary-text-color: #636363;
    --primary-background-color: #ffffff;
  }
</style>
```
