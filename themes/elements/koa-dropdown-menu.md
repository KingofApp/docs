# &lt;koa-dropdown-menu&gt;

It is similar to a native browser `select` element. It works with selectable content. The currently selected item is displayed in the control. If no item is selected, the label is displayed instead.

The child element with the class `dropdown-content` will be used as the dropdown menu.

### Demo

* Demo with [paper-dropdown-menu](https://elements.polymer-project.org/elements/paper-dropdown-menu?view=demo).

### Behaviors

* [Polymer.IronButtonState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronButtonState): `active`, `pressed`, `toggles`.
* [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState): `disabled`, `focused`.
* [Polymer.IronFormElementBehavior](https://elements.polymer-project.org/elements/iron-form-element-behavior): `name`, `required`, `value`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*active* | `Boolean` | If true, the button is a toggle and is currently in the active state. | `false`
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`
***label*** | `String` | The label for the dropdown. |
*name* | `String` | The name of this element. |
***opened*** | `Boolean` | True if the dropdown is open. Otherwise, false. | `false`
*pressed* | `Boolean` | If true, the user is currently holding down the button. | `false`
*required* | `Boolean` | Set to true to mark the input as required. If used in a form, a custom element that uses this behavior should also use Polymer.IronValidatableBehavior and define a custom validation method. Otherwise, a `required` element will always be considered valid. It's also strongly recommended to provide a visual style for the element when its value is invalid. | `false`
*selectedItem* | `Object` | The last selected item. An item is selected if the dropdown menu has a child with class `dropdown-content`, and that child triggers an `iron-select` event with the selected `item` in the `detail`. |
*selectedItemLabel* | `String` | The derived "label" of the currently selected item. This value is the label property on the selected item if set, or else the trimmed text content of the selected item. |
*toggles* | `Boolean` | If true, the button toggles the active state with each tap or press of the spacebar. | `false`
*value* | `String` | The value for this element that will be used when submitting in a form. It is read only, and will always have the same value as `selectedItemLabel`. |

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--dropdown-menu` | A mixin that is applied to the element host | `{}`
`--dropdown-menu-disabled` | A mixin that is applied to the element host when disabled | `{}`
`--dropdown-menu-button` | A mixin that is applied to the internal menu button | `{}`
`--dropdown-menu-input` | A mixin that is applied to the internal paper input | `{}`
`--dropdown-menu-icon` | A mixin that is applied to the internal icon | `{}`

### Methods

Name | Description
-----|------------
***close()*** | Hide the dropdown content.
***open()*** | Show the dropdown content.
