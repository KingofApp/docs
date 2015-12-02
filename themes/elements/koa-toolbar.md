# &lt;koa-toolbar&gt;

It is a horizontal bar containing items that can be used for label, navigation, search and actions.

### Demo

* Demo with [paper-toolbar](https://elements.polymer-project.org/elements/paper-toolbar?view=demo).
* Demo with [ios-toolbar](https://kingofapp.github.io/ios-toolbar).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--toolbar-title` | Mixin applied to the title of the toolbar | `{}`
`--toolbar-background` | Toolbar background color | `--default-primary-color`
`--toolbar-color` | Toolbar foreground color | `--text-primary-color`
`--toolbar-height` | Custom height for toolbar | `64px`
`--toolbar-sm-height` | Custom height for small screen toolbar | `56px`
`--toolbar` | Mixin applied to the toolbar | `{}`
`--toolbar-medium` | Mixin applied to medium height toolbar | `{}`
`--toolbar-tall` | Mixin applied to tall height toolbar | `{}`

---

### [KoaToolbarBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-toolbar-behavior.html) offers

#### Host attributes

Attribute | Value
----------|------
***role*** | `'toolbar'`

#### Properties

*bottomJustify* | `String` | Controls how the items are aligned horizontally when they are placed at the bottom. Options are `start`, `center`, `end`, `justified` and `around`. | `''`
*justify* | `String` | Controls how the items are aligned horizontally. Options are `start`, `center`, `end`, `justified` and `around`. | `''`
*middleJustify* | `String` | Controls how the items are aligned horizontally when they are placed in the middle. Options are `start`, `center`, `end`, `justified` and `around`. | `''`
