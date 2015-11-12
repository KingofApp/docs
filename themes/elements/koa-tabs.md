# &lt;koa-tabs&gt;

## &lt;koa-tabs&gt;

It makes it easy to explore and switch between different views or functional aspects of an app, or to browse categorized data sets.

### Demo

* Demo with [paper-tabs](https://elements.polymer-project.org/elements/paper-tabs?view=demo).
* Demo with [ios-tabs](https://kingofapp.github.io/ios-tabs).

### Behaviors

* [Polymer.IronMenuBehavior](https://elements.polymer-project.org/elements/iron-menu-behavior?active=Polymer.IronMenuBehavior): `focusedItem`, `items`, `multi`, `selectable`, `selected`, `selectedAttribute`, `selectedClass`, `selectedItem`, `selectedItems`, `selectedValues`, `select(value)`, `selectNext()`, `selectPrevious()`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***focusedItem*** | `Object` | Returns the currently focused item. |
***items*** | `Array` | The list of items from which a selection can be made. | `[]`
***multi*** | `Boolean` | If true, multiple selections are allowed. | `false`
***selectable*** | `String` | This is a CSS selector string. If this is set, only items that match the CSS selector are selectable. |
***selected*** | `String` | Gets or sets the selected element. The default is to use the index of the item. |
***selectedAttribute*** | `String` | The attribute to set on elements when selected. | `null`
***selectedClass*** | `String` | The class to set on elements when selected. | `iron-selected`
***selectedItem*** | `Object` | Returns the currently selected item. |
***selectedItems*** | `Array` | Returns an array of currently selected items. |
***selectedValues*** | `Array` | Gets or sets the selected elements. This is used instead of `selected` when `multi` is true. |

### Methods

Name | Description
-----|------------
*select(value)* | `value`: `String`. The value to select.<br/><br/>Selects the given value. If the multi property is true, then the selected state of the value will be toggled; otherwise the value will be selected.
*selectNext()* | Selects the next item.
*selectPrevious()* | Selects the previous item.

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--tabs-selection-bar-color` | Color for the selection bar | `--accent-color`
`--tabs` | Mixin applied to the tabs | `{}`


## &lt;koa-tab&gt;

It is styled to look like a tab. It should be used in conjunction with `koa-tabs`.

### Behaviors

* [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState): `active`, `pressed`, `toggles`.
* [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState): `disabled`, `focused`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `false`

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--tab` | Mixin applied to the tab | `{}`
`--tab-content` | Mixin applied to the tab content | `{}`
`--tab-content-unselected` | Mixin applied to the tab content when the tab is not selected | `{}`
