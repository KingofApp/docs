# &lt;koa-input&gt; & &lt;koa-textarea&gt;

## &lt;koa-input&gt;

It is a single-line text field.

### Demo

* Demo with [paper-input](https://elements.polymer-project.org/elements/paper-input?view=demo).
* Demo with [ios-input](https://kingofapp.github.io/ios-input).

### Styling

See `<koa-input-container>` for a list of custom properties used to style this element.

---

### [Polymer.KoaInputBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html) offers

#### Behaviors

##### [Polymer.IronFormElementBehavior](https://elements.polymer-project.org/elements/iron-form-element-behavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*name* | `String` | The name of this element. |
*required* | `Boolean` | Set to true to mark the input as required. If used in a form, a custom element that uses this behavior should also use Polymer.IronValidatableBehavior and define a custom validation method. Otherwise, a required element will always be considered valid. It's also strongly recommended to provide a visual style for the element when its value is invalid. | `false`
*value* | `String` | The value for this element. |

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState) contains

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***accept*** | `String` | Bind this to the `<input is="iron-input">`'s `accept` property, used with type=file. |
***allowedPattern*** | `String` | Bind this to the `<input is="iron-input">`'s `allowedPattern` property. |
***autocapitalize*** | `String` | Bind this to the `<input is="iron-input">`'s `autocapitalize` property. | `none`
***autocomplete*** | `String` | Bind this to the `<input is="iron-input">`'s `autocomplete` property. | `off`
***autocorrect*** | `String` | Bind this to the `<input is="iron-input">`'s `autocorrect` property. | `off`
***autofocus*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `autofocus` property. |
***autosave*** | `String` | Bind this to the `<input is="iron-input">`'s `autosave` property, used with type=search. |
***autoValidate*** | `String` | Set to true to auto-validate the input value. Bind this to the input-container's `autoValidate` property. | `false`
***charCounter*** | `Boolean` | Set to true to show a character counter. | `false`
***disabled*** | `Boolean` | Set to true to disable this input. Bind this to both the `<koa-input-container>`'s and the input's `disabled` property. | `false`
***errorMessage*** | `String` | The error message to display when the input is invalid. Bind this to the `<koa-input-error>`'s content, if using. |
***inputmode*** | `String` | Bind this to the `<input is="iron-input">`'s `inputmode` property. |
***invalid*** | `Boolean` | Returns true if the value is invalid. Bind this to both the `<koa-input-container>`'s and the input's `invalid` property. | `false`
***label*** | `String` | The label for this input. Bind this to `<label>`'s content and `hidden` property, e.g. `<label hidden$="[[!label]]">[[label]]</label>` in your `template` |
***list*** | `String` | The datalist of the input (if any). This should match the id of an existing `<datalist>`. Bind this to the `<input is="iron-input">`'s `list` property. |
***max*** | `String` | The maximum (numeric or date-time) input value. Can be a String (e.g. "2000-1-1") or a Number (e.g. 2). Bind this to the `<input is="iron-input">`'s `max` property. |
***maxlength*** | `Number` | The maximum length of the input value. Bind this to the `<input is="iron-input">`'s `maxlength` property. |
***min*** | `String` | The minimum (numeric or date-time) input value. Bind this to the `<input is="iron-input">`'s `min` property. |
***minlength*** | `Number` | Bind this to the `<input is="iron-input">`'s `minlength` property. |
***multiple*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `multiple` property, used with type=file. |
***name*** | `String` | Bind this to the `<input is="iron-input">`'s `name` property. |
***pattern*** | `String` | A pattern to validate the input with. Bind this to the `<input is="iron-input">`'s `pattern` property. |
***placeholder*** | `String` | A placeholder string in addition to the label. If this is set, the label will always float. | `''`
***preventInvalidInput*** | `Boolean` | Set to true to prevent the user from entering invalid input. Bind this to the `<input is="iron-input">`'s `preventInvalidInput` property. |
***readonly*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `readonly` property. |
***required*** | `Boolean` | Set to true to mark the input as required. Bind this to the `<input is="iron-input">`'s `required` property. |  `false`
***results*** | `Number` | Bind this to the `<input is="iron-input">`'s `results` property, used with type=search. |
***size*** | `Number` | Bind this to the `<input is="iron-input">`'s `size` property. |
***step*** | `String` | Limits the numeric or date-time increments. Bind this to the `<input is="iron-input">`'s `step` property. |
***type*** | `String` | The type of the input. The supported types are text, number and password. Bind this to the `<input is="iron-input">`'s `type` property. |
***validator*** | `String` | Name of the validator to use. Bind this to the `<input is="iron-input">`'s `validator` |
***value*** | `String` | The value for this input. Bind this to the `<input is="iron-input">`'s `bindValue` property, or the `value` property of your input that is `notify:true`. |

#### Methods

Name | Description
-----|------------
***validate()*** | Validates the input element and sets an error style if needed.


## &lt;koa-textarea&gt;

It is a multi-line text field.

### Demo

* Demo with [paper-textarea](https://elements.polymer-project.org/elements/paper-input?view=demo).
* Demo with [ios-textarea](https://kingofapp.github.io/ios-input).

### Styling

See `<koa-input-container>` for a list of custom properties used to style this element.

---

### [Polymer.KoaTextareaBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-textarea-behavior.html) offers

#### Behaviors

##### [Polymer.KoaInputBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***accept*** | `String` | Bind this to the `<input is="iron-input">`'s `accept` property, used with type=file. |
***allowedPattern*** | `String` | Bind this to the `<input is="iron-input">`'s `allowedPattern` property. |
***autocapitalize*** | `String` | Bind this to the `<input is="iron-input">`'s `autocapitalize` property. | `none`
***autocomplete*** | `String` | Bind this to the `<input is="iron-input">`'s `autocomplete` property. | `off`
***autocorrect*** | `String` | Bind this to the `<input is="iron-input">`'s `autocorrect` property. | `off`
***autofocus*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `autofocus` property. |
***autosave*** | `String` | Bind this to the `<input is="iron-input">`'s `autosave` property, used with type=search. |
***autoValidate*** | `String` | Set to true to auto-validate the input value. Bind this to the input-container's `autoValidate` property. | `false`
***charCounter*** | `Boolean` | Set to true to show a character counter. | `false`
***disabled*** | `Boolean` | Set to true to disable this input. Bind this to both the `<koa-input-container>`'s and the input's `disabled` property. | `false`
***errorMessage*** | `String` | The error message to display when the input is invalid. Bind this to the `<koa-input-error>`'s content, if using. |
***inputmode*** | `String` | Bind this to the `<input is="iron-input">`'s `inputmode` property. |
***invalid*** | `Boolean` | Returns true if the value is invalid. Bind this to both the `<koa-input-container>`'s and the input's `invalid` property. | `false`
***label*** | `String` | The label for this input. Bind this to `<label>`'s content and `hidden` property, e.g. `<label hidden$="[[!label]]">[[label]]</label>` in your `template` |
***list*** | `String` | The datalist of the input (if any). This should match the id of an existing `<datalist>`. Bind this to the `<input is="iron-input">`'s `list` property. |
***max*** | `String` | The maximum (numeric or date-time) input value. Can be a String (e.g. "2000-1-1") or a Number (e.g. 2). Bind this to the `<input is="iron-input">`'s `max` property. |
***maxlength*** | `Number` | The maximum length of the input value. Bind this to the `<input is="iron-input">`'s `maxlength` property. |
***min*** | `String` | The minimum (numeric or date-time) input value. Bind this to the `<input is="iron-input">`'s `min` property. |
***minlength*** | `Number` | Bind this to the `<input is="iron-input">`'s `minlength` property. |
***multiple*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `multiple` property, used with type=file. |
***name*** | `String` | Bind this to the `<input is="iron-input">`'s `name` property. |
***pattern*** | `String` | A pattern to validate the input with. Bind this to the `<input is="iron-input">`'s `pattern` property. |
***placeholder*** | `String` | A placeholder string in addition to the label. If this is set, the label will always float. | `''`
***preventInvalidInput*** | `Boolean` | Set to true to prevent the user from entering invalid input. Bind this to the `<input is="iron-input">`'s `preventInvalidInput` property. |
***readonly*** | `Boolean` | Bind this to the `<input is="iron-input">`'s `readonly` property. |
***required*** | `Boolean` | Set to true to mark the input as required. Bind this to the `<input is="iron-input">`'s `required` property. |  `false`
***results*** | `Number` | Bind this to the `<input is="iron-input">`'s `results` property, used with type=search. |
***size*** | `Number` | Bind this to the `<input is="iron-input">`'s `size` property. |
***step*** | `String` | Limits the numeric or date-time increments. Bind this to the `<input is="iron-input">`'s `step` property. |
***type*** | `String` | The type of the input. The supported types are text, number and password. Bind this to the `<input is="iron-input">`'s `type` property. |
***validator*** | `String` | Name of the validator to use. Bind this to the `<input is="iron-input">`'s `validator` |
***value*** | `String` | The value for this input. Bind this to the `<input is="iron-input">`'s `bindValue` property, or the `value` property of your input that is `notify:true`. |

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***rows*** | `Number` | The initial number of rows. | `1`
***maxRows*** | `Number` | The maximum number of rows this element can grow to until it scrolls. 0 means no maximum. | `0`


## &lt;koa-input-container&gt;

It is a container for a `<label>`, an `<input is="iron-input">` or `<iron-autogrow-textarea>` and optional add-on elements such as an error message or character counter.

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
`--input-container-underline-focus` | Mixin applied to the underline when the input is focused | `{}`
`--input-container-underline-disabled` | Mixin applied to the underline when the input is disabled | `{}`
`--input-prefix` | Mixin applied to the input prefix | `{}`
`--input-suffix` | Mixin applied to the input suffix | `{}`

---

### [Polymer.KoaInputContainerBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html) offers

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***attrForValue*** | `String` | The attribute to listen for value changes on. | `'bind-value'`
***autoValidate*** | `Boolean` | Set to true to auto-validate the input value when it changes. | `false`
***focused*** | `Boolean` | True if the input has focus. | `false`
***invalid*** | `Boolean` | True if the input is invalid. This property is set automatically when the input value changes if auto-validating, or when the `iron-input-validate` event is heard from a child. | `false`


## &lt;koa-input-error&gt;

It is an error message for use with `<koa-input-container>`. The error is displayed when the `<koa-input-container>` is `invalid`.

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--input-container-invalid-color` | Label and underline color when the input is is invalid | `#db4437`
`--input-error` | Mixin applied to the error | `{}`

---

### [Polymer.KoaInputErrorBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html) offers

#### Behaviors

##### [Polymer.KoaInputAddonBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html)

###### Host attributes

Attribute | Value
----------|------
***add-on*** | `''`

###### Methods

Name | Description
-----|------------
***update()*** | The function called by `<koa-input-container>` when the input value or validity changes.

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***invalid*** | `Boolean` | True if the error is showing. |

#### Methods

Name | Description
-----|------------
***update()*** |


## &lt;koa-input-char-counter&gt;

It is a character counter for use with `<koa-input-container>`. It shows the number of characters entered in the input and the max length if it is specified.

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--input-char-counter` | Mixin applied to the element	| `{}`

---

### [Polymer.KoaInputCharCounterBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html) offers

#### Behaviors

##### [Polymer.KoaInputAddonBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html)

###### Host attributes

Attribute | Value
----------|------
***add-on*** | `''`

###### Methods

Name | Description
-----|------------
***update()*** | The function called by `<koa-input-container>` when the input value or validity changes.

#### Methods

Name | Description
-----|------------
***update()*** |



























---

---

---

---

---

## &lt;koa-input&gt;

It is a single-line text field.

### Demo

* Demo with [paper-input](https://elements.polymer-project.org/elements/paper-input?view=demo).
* Demo with [ios-input](https://kingofapp.github.io/ios-input).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--input-container-color` | Label and underline color when the input is not focused | `--secondary-text-color`
`--input-container-focus-color` | Label and underline color when the input is focused | `--default-primary-color`
`--input-container-invalid-color` | Label and underline color when the input is is invalid | `#db4437`
`--input-container-input-color` | Input foreground color | `--primary-text-color`
`--input-container` | Mixin applied to the container | `{}`
`--input-container-disabled` | Mixin applied to the container when it's disabled | `{}`
`--input-container-label` | Mixin applied to the label | `{}`
`--input-container-label-focus` | Mixin applied to the label when the input is focused | `{}`
`--input-container-input` | Mixin applied to the input | `{}`
`--input-container-underline` | Mixin applied to the underline | `{}`
`--input-container-underline-focus` | Mixin applied to the underline when the input is focused | `{}`
`--input-container-underline-disabled` | Mixin applied to the underline when the input is disabled | `{}`
`--input-prefix` | Mixin applied to the input prefix | `{}`
`--input-suffix` | Mixin applied to the input suffix | `{}`

---

### [KoaInputBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-input-behavior.html) offers

#### Behaviors

##### [Polymer.PaperInputBehavior](https://elements.polymer-project.org/elements/paper-input?active=Polymer.PaperInputBehavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*accept* | `String` | Bind this to the `<input is="iron-input">`'s `accept` property, used with type=file. |
*allowedPattern* | `String` | Bind this to the `<input is="iron-input">`'s `allowedPattern` property. |
*autocapitalize* | `String` | Bind this to the `<input is="iron-input">`'s `autocapitalize` property. | `none`
*autocomplete* | `String` | Bind this to the `<input is="iron-input">`'s `autocomplete` property. | `off`
*autocorrect* | `String` | Bind this to the `<input is="iron-input">`'s `autocorrect` property. | `off`
*autofocus* | `Boolean` | Bind this to the `<input is="iron-input">`'s `autofocus` property. |
*autosave* | `String` | Bind this to the `<input is="iron-input">`'s `autosave` property, used with type=search. |
*disabled* | `Boolean` | Set to true to disable this input. |
*focused* | `Boolean` | If true, the element currently has focus. |
*inputmode* | `String` | Bind this to the `<input is="iron-input">`'s `inputmode` property. |
*invalid* | `Boolean` | Returns true if the value is invalid. |
*list* | `String` | The datalist of the input (if any). This should match the id of an existing `<datalist>`. Bind this to the `<input is="iron-input">`'s `list` property. |
*max* | `String` | The maximum (numeric or date-time) input value. Can be a String (e.g. "2000-1-1") or a Number (e.g. 2). Bind this to the `<input is="iron-input">`'s `max` property. |
*maxlength* | `Number` | The maximum length of the input value. Bind this to the `<input is="iron-input">`'s `maxlength` property. |
*min* | `String` | The minimum (numeric or date-time) input value. Bind this to the `<input is="iron-input">`'s `min` property. |
*minlength* | `Number` | Bind this to the `<input is="iron-input">`'s `minlength` property. |
*multiple* | `Boolean` | Bind this to the `<input is="iron-input">`'s `multiple` property, used with type=file. |
*name* | `String` | Bind this to the `<input is="iron-input">`'s `name` property. |
*pattern* | `String` | A pattern to validate the input with. Bind this to the `<input is="iron-input">`'s `pattern` property. |
*placeholder* | `String` | A placeholder string in addition to the label. |
*preventInvalidInput* | `Boolean` | Set to true to prevent the user from entering invalid input. Bind this to the `<input is="iron-input">`'s `preventInvalidInput` property. |
*readonly* | `Boolean` | Bind this to the `<input is="iron-input">`'s `readonly` property. |
*required* | `Boolean` | Set to true to mark the input as required. Bind this to the `<input is="iron-input">`'s `required` pro
*results* | `Number` | Bind this to the `<input is="iron-input">`'s `results` property, used with type=search. |
*size* | `Number` | Bind this to the `<input is="iron-input">`'s `size` property. |
*step* | `String` | Limits the numeric or date-time increments. Bind this to the `<input is="iron-input">`'s `step` property. |
*type* | `String` | The type of the input. The supported types are text, number and password. Bind this to the `<input is="iron-input">`'s `type` property. |
*value* | `String` | The value for this input. Bind this to the `<input is="iron-input">`'s `bindValue` property, or the `value` property of your input that is notify:true. |

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***label*** | `String` | The label for this input. |

### Methods

Name | Description
-----|------------
***inputElement()*** | Returns a reference to the input element.


## &lt;koa-textarea&gt;

It is a multi-line text field.

### Demo

* Demo with [paper-textarea](https://elements.polymer-project.org/elements/paper-input?view=demo).
* Demo with [ios-textarea](https://kingofapp.github.io/ios-input).

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

---

### [KoaTextareaBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-textarea-behavior.html) offers

#### Behaviors

##### [Polymer.PaperInputBehavior](https://elements.polymer-project.org/elements/paper-input?active=Polymer.PaperInputBehavior)

###### Properties

The same as `koa-input` and:

Name | Type | Description | Default
-----|------|-------------|--------
***rows*** | `Number` | The initial number of rows. | `1`
***maxRows*** | `Number` | The maximum number of rows this element can grow to until it scrolls. 0 means no maximum. | `0`
