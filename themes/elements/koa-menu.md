# &lt;koa-menu&gt;

## &lt;koa-menu&gt;

It implements an accessible menu control.

### Demo

* Demo with [paper-menu](https://elements.polymer-project.org/elements/paper-menu?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--menu-background-color` | Menu background color | `--primary-background-color`
`--menu-color` | Menu foreground color | `--primary-text-color`
`--menu-disabled-color` | Foreground color for a disabled item | `--disabled-text-color`
`--menu` | Mixin applied to the menu | `{}`
`--menu-selected-item` | Mixin applied to the selected item | `{}`
`--menu-focused-item` | Mixin applied to the focused item | `{}`
`--menu-focused-item-after` | Mixin applied to the ::after pseudo-element for the focused item | `{}`

---

### [KoaMenuBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-menu-behavior.html) offers

#### Behaviors

##### [Polymer.IronMenuBehavior](https://elements.polymer-project.org/elements/iron-menu-behavior?active=Polymer.IronMenuBehavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*focusedItem* | `Object` | Returns the currently focused item. |
*items* | `Array` | The list of items from which a selection can be made. | `[]`
*multi* | `Boolean` | If true, multiple selections are allowed. | `false`
*selectable* | `String` | This is a CSS selector string. If this is set, only items that match the CSS selector are selectable. |
*selected* | `String` | Gets or sets the selected element. The default is to use the index of the item. |
*selectedAttribute* | `String` | The attribute to set on elements when selected. | `null`
*selectedClass* | `String` | The class to set on elements when selected. | `iron-selected`
*selectedItem* | `Object` | Returns the currently selected item. |
*selectedItems* | `Array` | Returns an array of currently selected items. |
*selectedValues* | `Array` | Gets or sets the selected elements. This is used instead of `selected` when `multi` is true. |

###### Methods

Name | Description
-----|------------
*select(value)* | `value`: `String`. The value to select.<br/><br/>Selects the given value. If the multi property is true, then the selected state of the value will be toggled; otherwise the value will be selected.
*selectNext()* | Selects the next item.
*selectPrevious()* | Selects the previous item.


## &lt;koa-submenu&gt;

It is a nested menu inside of a parent <koa-menu>. It consists of a trigger that expands or collapses another <koa-menu>.

### Demo

* Demo with Demo with [paper-submenu](https://elements.polymer-project.org/elements/paper-menu?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--menu-selected-item` | Mixin applied to the selected item | `{}`
`--menu-focused-item` | Mixin applied to the focused item | `{}`
`--menu-focused-item-after` | Mixin applied to the ::after pseudo-element for the focused item | `{}`

---

### [KoaSubmenuBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-submenu-behavior.html) offers

#### Behaviors

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***opened*** | `Boolean` | Set opened to true to show the collapse element and to false to hide it. | `false`

#### Methods

Name | Description
-----|------------
***close()*** | Collapse the submenu content.
***open()*** | Expand the submenu content.
