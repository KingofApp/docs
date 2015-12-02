# &lt;koa-radio-button&gt;

It is a button that can be either checked or unchecked. User can tap the radio button to check or uncheck it.

### Demo

* Demo with [paper-radio-button](https://elements.polymer-project.org/elements/paper-radio-button?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--radio-button-unchecked-background-color` | Radio button background color when the input is not checked | `transparent`
`--radio-button-unchecked-color` | Radio button color when the input is not checked | `--primary-text-color`
`--radio-button-checked-color` | Radio button color when the input is checked | `--default-primary-color`
`--radio-button-label-color` | Label color | `--primary-text-color`
`--radio-button-label-spacing` | Spacing between the label and the button | `10px`

---

### [KoaRadioButtonBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-radio-button-behavior.html) offers

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
***role*** | `'radio'`
***tabindex*** | `0`
