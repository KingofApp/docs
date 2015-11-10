# &lt;koa-header-panel&gt;

Demo with [paper-header-panel](https://elements.polymer-project.org/elements/paper-header-panel?view=demo).

Description of the koa-header-panel element.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***mode*** | `String` | Controls header and scrolling behavior. Options are `standard` and `scroll`.<br/><br/>`standard`: The header is a step above the panel. The header will consume the panel at the point of entry, preventing it from passing through to the opposite side.<br/>`scroll`: The header keeps its seam with the panel, and is pushed off screen. | `standard`

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--header-panel-standard-container` | Mixin for the container when the mode is standard | `{}`
`--header-panel-scroll-container` | Mixin for the container when the mode is scroll | `{}`
