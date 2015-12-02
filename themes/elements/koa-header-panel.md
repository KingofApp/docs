# &lt;koa-header-panel&gt;

It contains a header section and a content panel section.

**Important**: It will not display if its parent does not have a height.

### Demo

* Demo with [paper-header-panel](https://elements.polymer-project.org/elements/paper-header-panel?view=demo).
* Demo with [ios-header-panel](https://kingofapp.github.io/ios-header-panel).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--header-panel-standard-container` | Mixin for the container when the mode is standard | `{}`
`--header-panel-scroll-container` | Mixin for the container when the mode is scroll | `{}`

---

### [KoaHeaderPanelBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-header-panel-behavior.html) offers

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***mode*** | `String` | Controls header and scrolling behavior. Options are `standard` and `scroll`.<br/><br/>`standard`: The header is a step above the panel. The header will consume the panel at the point of entry, preventing it from passing through to the opposite side.<br/>`scroll`: The header keeps its seam with the panel, and is pushed off screen. | `standard`

#### Methods

Name | Description
-----|------------
*header()* | Returns the header element.
*scroller()* | Returns the scrollable element.
