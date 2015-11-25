# &lt;koa-item&gt;

It is an interactive list item.

### Demo

* Demo with [paper-item](https://elements.polymer-project.org/elements/paper-item?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--item-min-height` | Minimum height of the item | `48px`
`--item` | Mixin applied to the item | `{}`
`--item-selected-weight` | The font weight of a selected item | `bold`
`--item-selected` | Mixin applied to selected items | `{}`
`--item-disabled-color` | The color for disabled items | `--disabled-text-color`
`--item-disabled` | Mixin applied to disabled items | `{}`
`--item-focused` | Mixin applied to focused items | `{}`
`--item-focused-before` | Mixin applied to :before focused items | `{}`

---

### [KoaItemBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-item-behavior.html) offers

#### Behaviors

##### [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `false`

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

#### Host attributes

Attribute | Value
----------|------
***role*** | `'option'`
***tabindex*** | `0`
