# &lt;koa-tabs&gt;

## &lt;koa-tabs&gt;

It makes it easy to explore and switch between different views or functional aspects of an app, or to browse categorized data sets.

### Demo

* Demo with [paper-tabs](https://elements.polymer-project.org/elements/paper-tabs?view=demo).
* Demo with [ios-tabs](https://kingofapp.github.io/ios-tabs).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--tabs` | Mixin applied to the tabs | `{}`

---

### [KoaTabsBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-tabs-behavior.html) offers

#### Behaviors

##### [Polymer.IronMenubarBehavior](https://elements.polymer-project.org/elements/iron-menubar-behavior?active=Polymer.IronMenubarBehavior)

###### Behaviors

[Polymer.IronMenuBehavior](https://elements.polymer-project.org/elements/iron-menu-behavior?active=Polymer.IronMenuBehavior)

#### Host attributes

Attribute | Value
----------|------
***role*** | `'tablist'`

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*scrollable* | `Boolean` | If true, tabs are scrollable and the tab width is based on the label width. | `false`
*selected* | `String` | Gets or sets the selected element. The default is to use the index of the item. |


## &lt;koa-tab&gt;

It is styled to look like a tab. It should be used in conjunction with `koa-tabs`.

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--tab` | Mixin applied to the tab | `{}`
`--tab-content` | Mixin applied to the tab content | `{}`
`--tab-content-unselected` | Mixin applied to the tab content when the tab is not selected | `{}`

---

### [KoaTabBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-tab-behavior.html) offers

#### Behaviors

##### [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState)

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `false`

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState)

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

#### Host attributes

Attribute | Value
----------|------
***role*** | `'tab'`
