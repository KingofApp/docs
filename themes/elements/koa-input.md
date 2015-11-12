# &lt;koa-input&gt; & &lt;koa-textarea&gt;

## &lt;koa-input&gt;

It is a single-line text field.

### Demo

* Demo with [paper-input](https://elements.polymer-project.org/elements/paper-input?view=demo).
* Demo with [ios-input](https://kingofapp.github.io/ios-input).

### Behaviors

* [Polymer.PaperInputBehavior](https://elements.polymer-project.org/elements/paper-input?active=Polymer.PaperInputBehavior): `accept`, `allowedPattern`, `autocapitalize`, `autocomplete`, `autocorrect`, `autofocus`, `autosave`, `inputmode`, `invalid`, `list`, `max`, `maxlength`, `min`, `minlength`, `multiple`, `name`, `pattern`, `placeholder`, `preventInvalidInput`, `readonly`, `required`, `results`, `size`, `step`, `type`, `value`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***accept*** | `String` | Bind this to the `<input is="iron-input">`'s `accept` property, used with type=file. |
***allowedPattern*** | `String` | Bind this to the `<input is="iron-input">`'s `allowedPattern` property. |
***autocapitalize*** | `String` | Bind this to the `<input is="iron-input">`'s `autocapitalize` property. | `none`
***autocomplete*** | `String` | Bind this to the `<input is="iron-input">`'s `autocomplete` property. | `off`
***autocorrect*** | `String` | Bind this to the `<input is="iron-input">`'s `autocorrect` property. | `off`
***autofocus*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `autofocus` property. |
***autosave*** | `String` | Bind this to the `<input is="iron-input">`'s `autosave` property, used with type=search. |
***disabled*** | `Boolean` | Set to true to disable this input. |
***focused*** | `Boolean` | If true, the element currently has focus. |
***inputmode*** | `String` | Bind this to the `<input is="iron-input">`'s `inputmode` property. |
***invalid*** | `Boolean` | Returns true if the value is invalid. |
***label*** | `String` | The label for this input. |
***list*** | `String` | The datalist of the input (if any). This should match the id of an existing `<datalist>`. Bind this to the `<input is="iron-input">`'s `list` property. |
***max*** | `String` | The maximum (numeric or date-time) input value. Can be a String (e.g. "2000-1-1") or a Number (e.g. 2). Bind this to the `<input is="iron-input">`'s `max` property. |
***maxlength*** | `Number` | The maximum length of the input value. Bind this to the `<input is="iron-input">`'s `maxlength` property. |
***min*** | `String` | The minimum (numeric or date-time) input value. Bind this to the `<input is="iron-input">`'s `min` property. |
***minlength*** | `Number` | Bind this to the `<input is="iron-input">`'s `minlength` property. |
***multiple*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `multiple` property, used with type=file. |
***name*** | `String` | Bind this to the `<input is="iron-input">`'s `name` property. |
***pattern*** | `String` | A pattern to validate the input with. Bind this to the `<input is="iron-input">`'s `pattern` property. |
***placeholder*** | `String` | A placeholder string in addition to the label. |
***preventInvalidInput*** | `Boolean` | Set to true to prevent the user from entering invalid input. Bind this to the `<input is="iron-input">`'s `preventInvalidInput` property. |
***readonly*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `readonly` property. |
***required*** | `Boolean` | Set to true to mark the input as required. Bind this to the `<input is="iron-input">`'s `required` pro
***results*** | `Number` | Bind this to the `<input is="iron-input">`'s `results` property, used with type=search. |
***size*** | `Number` | Bind this to the `<input is="iron-input">`'s `size` property. |
***step*** | `String` | Limits the numeric or date-time increments. Bind this to the `<input is="iron-input">`'s `step` property. |
***type*** | `String` | The type of the input. The supported types are text, number and password. Bind this to the `<input is="iron-input">`'s `type` property. |
***value*** | `String` | The value for this input. Bind this to the `<input is="iron-input">`'s `bindValue` property, or the `value` property of your input that is notify:true. |

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--input-container-color` | Label and underline color when the input is not focused | `--secondary-text-color`
`--input-container-focus-color` | Label and underline color when the input is focused | `--default-primary-color`
`--input-container-invalid-color` | Label and underline color when the input is is invalid | `--google-red-500`
`--input-container-input-color` | Input foreground color | `--primary-text-color`
`--input-container` | Mixin applied to the container | `{}`
`--input-container-disabled` | Mixin applied to the container when it's disabled | `{}`
`--input-container-label` | Mixin applied to the label | `{}`
`--input-container-label-focus` | Mixin applied to the label when the input is focused | `{}`
`--input-container-input` | Mixin applied to the input | `{}`
`--input-container-underline` | Mixin applied to the underline | `{}`
`--input-container-underline-focus` | Mixin applied to the underline when the input is focued | `{}`
`--input-container-underline-disabled` | Mixin applied to the underline when the input is disabled | `{}`
`--input-prefix` | Mixin applied to the input prefix | `{}`
`--input-suffix` | Mixin applied to the input suffix | `{}`

### Methods

Name | Description
-----|------------
`inputElement()` | Returns a reference to the input element.


## &lt;koa-textarea&gt;

It is a multi-line text field.

### Demo

* Demo with [paper-textarea](https://elements.polymer-project.org/elements/paper-input?view=demo).
* Demo with [ios-textarea](https://kingofapp.github.io/ios-input).

### Behaviors

* [Polymer.PaperInputBehavior](https://elements.polymer-project.org/elements/paper-input?active=Polymer.PaperInputBehavior): `accept`, `allowedPattern`, `autocapitalize`, `autocomplete`, `autocorrect`, `autofocus`, `autosave`, `disabled`, `focused`, `inputmode`, `invalid`, `list`, `max`, `maxlength`, `min`, `minlength`, `multiple`, `name`, `pattern`, `placeholder`, `preventInvalidInput`, `readonly`, `required`, `results`, `size`, `step`, `type`, `value`.

### Properties

The same as `koa-input` and:

Name | Type | Description | Default
-----|------|-------------|--------
***rows*** | `Number` | The initial number of rows. | `1`
***maxRows*** | `Number` | The maximum number of rows this element can grow to until it scrolls. 0 means no maximum. | `0`

### Styling

`--input-container-color` | Label and underline color when the input is not focused | `--secondary-text-color`
`--input-container-focus-color` | Label and underline color when the input is focused | `--default-primary-color`
`--input-container-invalid-color` | Label and underline color when the input is is invalid | `--google-red-500`
`--input-container-input-color` | Input foreground color | `--primary-text-color`
`--input-container` | Mixin applied to the container | `{}`
`--input-container-disabled` | Mixin applied to the container when it's disabled | `{}`
`--input-container-label` | Mixin applied to the label | `{}`
`--input-container-label-focus` | Mixin applied to the label when the input is focused | `{}`
`--input-container-input` | Mixin applied to the input | `{}`
`--input-container-underline` | Mixin applied to the underline | `{}`
`--input-container-underline-focus` | Mixin applied to the underline when the input is focued | `{}`
`--input-container-underline-disabled` | Mixin applied to the underline when the input is disabled | `{}`
