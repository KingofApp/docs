# &lt;koa-badge&gt;

It is a text badge that is displayed on the top right corner of an element, representing a status or a notification.

### Demo

* Demo with [paper-badge](https://elements.polymer-project.org/elements/paper-badge?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--badge-background` | The background color of the badge | `--accent-color`
`--badge-opacity` | The opacity of the badge | `1.0`
`--badge-text-color` | The color of the badge text | `white`
`--badge-width` | The width of the badge circle | `22px`
`--badge-height` | The height of the badge circle | `22px`
`--badge-margin-left` | Optional spacing added to the left of the badge. | `0px`
`--badge-margin-bottom` | Optional spacing added to the bottom of the badge. | `0px`
`--badge` | Mixin applied to the badge | `{}`

---

### [KoaBadgeBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-badge-behavior.html) offers

#### Host attributes

Attribute | Value
----------|------
***role*** | `'status'`
***tabindex*** | `0`

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***for*** | `String` | The id of the element that the badge is anchored to. This element must be a sibling of the badge. |
***label*** | `String` | The label displayed in the badge. The label is centered, and ideally should have very few characters. |
***target*** |  | Returns the target element that this badge is anchored to. It is either the element given by the for attribute, or the immediate parent of the badge.
