# &lt;koa-progress&gt;

The progress bars are for situations where the percentage completed can be determined. They give users a quick sense of how much longer an operation will take.

### Demo

* Demo with [paper-progress](https://elements.polymer-project.org/elements/paper-progress?view=demo).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--progress-container-color` | Mixin applied to container | `#e0e0e0`
`--progress-transition-duration` | Duration of the transition | `0.008s`
`--progress-transition-timing-function` | The timing function for the transition | `ease`
`--progress-transition-delay` | Delay for the transition | `0s`
`--progress-active-color` | The color of the active bar | `#0f9d58`
`--progress-secondary-color` | The color of the secondary bar | `#b7e1cd`
`--progress-disabled-active-color` | The color of the active bar if disabled | `#9e9e9e`
`--progress-disabled-secondary-color` | The color of the secondary bar if disabled | `#e0e0e0`
`--progress-height` | The height of the progress bar | `4px`

---

### [KoaProgressBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-progress-behavior.html) offers

#### Behaviors

##### [Polymer.IronRangeBehavior](https://elements.polymer-project.org/elements/iron-range-behavior?active=Polymer.IronRangeBehavior)

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*max* | `Number` | The number that indicates the maximum value of the range. | `100`
*min* | `Number` | The number that indicates the minimum value of the range. | `0`
*ratio* | `Number` | Returns the ratio of the value. | `0`
*step* | `Number` | Specifies the value granularity of the range's value. | `1`
*value* | `Number` | The number that represents the current value. | `0`

###### Host attributes

Attribute | Value
----------|------
***role*** | `'progressbar'`

###### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***disabled*** | `Boolean` | True if the progress is disabled. | `false`
***indeterminate*** | `Boolean` | Use an indeterminate progress indicator. | `false`
***secondaryProgress*** | `Number` | The number that represents the current secondary progress. | `0`
***secondaryRatio*** | `Number` | The secondary ratio | `0`
