# &lt;koa-button&gt;

It is a button.

### Demo

* Demo with [paper-button](https://elements.polymer-project.org/elements/paper-button?view=demo).
* Demo with [ios-button](https://kingofapp.github.io/ios-button).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--button` | Mixin applied to the button | `{}`
`--button-disabled` | Mixin applied to the disabled button. Note that you can also use the `koa-button[disabled]` selector | `{}`
`--button-keyboard-focus` | Mixin applied to a button after it's been focused using the keyboard | `{}`
`--button-link-keyboard-focus` | Mixin applied to a link button after it's been focused using the keyboard | `{}`
`--button-big-keyboard-focus` | Mixin applied to a big button after it's been focused using the keyboard | `{}`

---

### [KoaButtonBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-button-behavior.html) offers

#### Behaviors

##### [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState) contains

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `false`

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState) contains

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

#### Host attributes

Attribute | Value
----------|------
***role*** | `'button'`
***tabindex*** | `0`

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***big*** | `Boolean` | If true, the button should be bigger. | `false`
***link*** | `Boolean` | If true, the button should have a link appearance. | `false`
