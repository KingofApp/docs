# &lt;koa-toggle-button&gt;

It provides a ON/OFF switch that user can toggle the state by tapping or by dragging the switch.

### Demo

* Demo with [paper-toggle-button](https://elements.polymer-project.org/elements/paper-toggle-button?view=demo).
* Demo with [ios-toggle-button](https://kingofapp.github.io/ios-toggle-button).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--toggle-button-unchecked-bar-color` | Slider color when the input is not checked | `#000000`
`--toggle-button-unchecked-button-color` | Button color when the input is not checked | `--paper-grey-50`
`--toggle-button-checked-bar-color` | Slider button color when the input is checked | `--default-primary-color`
`--toggle-button-checked-button-color` | Button color when the input is checked | `--default-primary-color`
`--toggle-button-unchecked-bar` | Mixin applied to the slider when the input is not checked | `{}`
`--toggle-button-unchecked-button` | Mixin applied to the slider button when the input is not checked | `{}`
`--toggle-button-checked-bar` | Mixin applied to the slider when the input is checked | `{}`
`--toggle-button-checked-button` | Mixin applied to the slider button when the input is checked | `{}`
`--toggle-button-label-color` | Label color | `--primary-text-color`

---

### [KoaToggleButtonBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-toggle-button-behavior.html) offers

#### Behaviors

##### [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `true`

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

##### [Polymer.IronCheckedElementBehavior](https://elements.polymer-project.org/elements/iron-checked-element-behavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*checked* | `Boolean` | Gets or sets the state, true is checked and false is unchecked. | `false`
*name* | `String` | The name of this element. |
*required* | `Boolean` | Set to true to mark the input as required. If used in a form, a custom element that uses this behavior should also use Polymer.IronValidatableBehavior and define a custom validation method. Otherwise, a required element will always be considered valid. It's also strongly recommended to provide a visual style for the element when its value is invalid. | `false`

#### Host attributes

Attribute | Value
----------|------
***role*** | `'button'`
***tabindex*** | `0`
