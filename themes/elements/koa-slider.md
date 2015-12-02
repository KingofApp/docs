# &lt;koa-slider&gt;

It allows user to select a value from a range of values by moving the slider thumb. The interactive nature of the slider makes it a great choice for settings that reflect intensity levels, such as volume, brightness, or color saturation.

### Demo

* Demo with [paper-slider](https://elements.polymer-project.org/elements/paper-slider?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--slider-bar-color` | The background color of the slider | `transparent`
`--slider-active-color` | The progress bar color | `--google-blue-700`
`--slider-secondary-color` | The secondary progress bar color | `--google-blue-300`
`--slider-knob-color` | The knob color | `--google-blue-700`
`--slider-disabled-knob-color` | The disabled knob color | `--google-grey-500`
`--slider-pin-color` | The pin color | `--google-blue-700`
`--slider-font-color` | The pin's text color | `#fff`
`--slider-disabled-active-color` | The disabled progress bar color | `--google-grey-500`
`--slider-disabled-secondary-color` | The disabled secondary progress bar color | `--google-grey-300`
`--slider-knob-start-color` | The fill color of the knob at the far left | `transparent`
`--slider-knob-start-border-color` | The border color of the knob at the far left | `#c8c8c8`
`--slider-pin-start-color` | The color of the pin at the far left | `#c8c8c8`
`--slider-height` | Height of the progress bar | `2px`

### Methods

Name | Description
-----|------------
***decrement()*** | Decreases value by step but not below `min`.
***increment()*** | Increases value by step but not above `max`.

---

### [KoaSliderBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-slider-behavior.html) offers

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

##### [Polymer.IronFormElementBehavior](https://elements.polymer-project.org/elements/iron-form-element-behavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*name* | `String` | The name of this element. |
*required* | `Boolean` | Set to true to mark the input as required. If used in a form, a custom element that uses this behavior should also use Polymer.IronValidatableBehavior and define a custom validation method. Otherwise, a required element will always be considered valid. It's also strongly recommended to provide a visual style for the element when its value is invalid. | `false`
*value* | `Number` | The number that represents the current value. | `0`

##### [Polymer.IronRangeBehavior](https://elements.polymer-project.org/elements/iron-range-behavior?active=Polymer.IronRangeBehavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*max* | `Number` | The number that indicates the maximum value of the range. | `100`
*min* | `Number` | The number that indicates the minimum value of the range. | `0`
*ratio* | `Number` | Returns the ratio of the value. | `0`
*step* | `Number` | Specifies the value granularity of the range's value. | `1`
*value* | `Number` | The number that represents the current value. | `0`

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***dragging*** | `Boolean` | True when the user is dragging the slider. | `false`
***editable*** | `Boolean` | If true, an input is shown and user can use it to set the slider value. | `false`
***expand*** | `Boolean` | If true, the knob is expanded | `false`
***immediateValue*** | `Number` | The immediate value of the slider. This value is updated while the user is dragging the slider. | `0`
***markers*** | `Array` |  | `[]`
***maxMarkers*** | `Number` | The maximum number of markers | `0`
***pin*** | `Boolean` | If true, a pin with numeric value label is shown when the slider thumb is pressed. Use for settings for which users need to know the exact value of the setting. | `false`
***secondaryProgress*** | `Number` | The number that represents the current secondary progress. | `0`
***snaps*** | `Boolean` | If true, the slider thumb snaps to tick marks evenly spaced based on the step property value. | `false`
