# &lt;koa-item&gt;

## &lt;koa-item&gt;

It is an interactive list item.

Use the `item-icon` property to make an item with icon. It is an interactive list item with a fixed-width icon area. This is useful if the icons are of varying widths, but you want the item bodies to line up. The child node with the attribute `item-icon` is placed in the icon area.

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


## &lt;koa-item-body&gt;

Use `<koa-item-body>` in a `<koa-item>` to make two- or three- line items. It is a flex item that is a vertical flexbox.

The child elements with the `secondary` attribute is given secondary text styling.

### Styling

Custom property | Description | Default
----------------|-------------|----------
`--item-body-two-line-min-height`   | Minimum height of a two-line item          | `72px`
`--item-body-three-line-min-height` | Minimum height of a three-line item        | `88px`
`--item-body-secondary-color`       | Foreground color for the `secondary` area  | `--secondary-text-color`
`--item-body-secondary`             | Mixin applied to the `secondary` area      | `{}`
