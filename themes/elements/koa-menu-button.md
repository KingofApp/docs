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
***closeAnimationConfig*** | `Object` | An animation config. If provided, this will be used to animate the closing of the dropdown. | `fade-out-animation`
***contentElement*** |  | The content element that is contained by the menu button, if any. |
***horizontalAlign*** | `String` | The orientation against which to align the menu dropdown horizontally relative to the dropdown trigger. | `'left'`
***horizontalOffset*** | `Number` | A pixel value that will be added to the position calculated for the given `horizontalAlign`. Use a negative value to offset to the left, or a positive value to offset to the right. | `0`
***ignoreSelect*** | `Boolean` | Set to true to disable automatically closing the dropdown after a selection has been made. | `false`
***noAnimations*** | `Boolean` | Set to true to disable animations when opening and closing the dropdown. | `false`
***openAnimationConfig*** | `Object` | An animation config. If provided, this will be used to animate the opening of the dropdown. | `fade-in-animation`
***opened*** | `Boolean` | True if the content is currently displayed. | `false`
***opened*** | `Boolean` | True if the content is currently displayed. | `false`
***verticalAlign*** | `String` | The orientation against which to align the menu dropdown vertically relative to the dropdown trigger. | `'top'`
***verticalOffset*** | `Number` | A pixel value that will be added to the position calculated for the given `verticalAlign`. Use a negative value to offset towards the top, or a positive value to offset towards the bottom. | `0`

#### Methods

Name | Description
-----|------------
***close()*** | Hide the dropdown content.
***open()*** | Make the dropdown content appear as an overlay positioned relative to the dropdown trigger.
