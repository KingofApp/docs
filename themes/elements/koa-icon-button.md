# &lt;koa-icon-button&gt;

It is a button with an image placed at the center.

It includes a default icon set. Use `icon` to specify which icon from the icon set to use.

### Demo

* Demo with [paper-icon-button](https://elements.polymer-project.org/elements/paper-icon-button?view=demo).
* Demo with [ios-icon-button](https://kingofapp.github.io/ios-icon-button).

### Behaviors

* [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState): `active`, `pressed`, `toggles`.
* [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState): `disabled`, `focused`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
***alt*** | `String` | Specifies the alternate text for the button, for accessibility. | `false`
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`
***icon*** | `String` | Specifies the icon name or index in the set of icons available in the icon's icon set. If the icon property is specified, the src property should not be. |
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
***src*** | `String` | The URL of an image for the icon. If the src property is specified, the icon property should not be. |
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `false`

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--icon-button-disabled-text` | The color of the disabled button | `--disabled-text-color`
`--icon-button` | Mixin for a button | `{}`
`--icon-button-disabled` | Mixin for a disabled button | `{}`
