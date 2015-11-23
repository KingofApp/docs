# &lt;koa-menu-button&gt;

It allows one to compose a designated "trigger" element with another element that represents "content", to create a dropdown menu that displays the "content" when the "trigger" is clicked.

### Demo

* Demo with [paper-menu-button](https://elements.polymer-project.org/elements/paper-menu-button?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--menu-button-dropdown-background` | Background color of the menu-button dropdown | `#fff`
`--menu-button` | Mixin applied to the menu-button | `{}`
`--menu-button-disabled` | Mixin applied to the menu-button when disabled | `{}`
`--menu-button-dropdown` | Mixin applied to the menu-button dropdown | `{}`

### Methods

Name | Description
-----|------------
***close()*** | Hide the dropdown content.
***open()*** | Make the dropdown content appear as an overlay positioned relative to the dropdown trigger.

---

### [KoaMenuButtonBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-menu-button-behavior.html) offers

#### Behaviors

##### [Polymer.IronControlState](https://elements.polymer-project.org/elements/iron-behaviors?active=Polymer.IronControlState)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*disabled* | `Boolean` | If true, the user cannot interact with this element. | `false`
*focused* | `Boolean` | If true, the element currently has focus. | `false`

##### [Polymer.IronA11yKeysBehavior](https://elements.polymer-project.org/elements/iron-a11y-keys-behavior?active=Polymer.IronA11yKeysBehavior)

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***opened*** | `Boolean` | True if the content is currently displayed. | `false`
