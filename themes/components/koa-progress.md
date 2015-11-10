# &lt;koa-progress&gt;

Demo with [paper-progress](https://elements.polymer-project.org/elements/paper-progress?view=demo).

Description of the koa-progress element.

### Behaviors

* [Polymer.IronRangeBehavior](https://elements.polymer-project.org/elements/iron-range-behavior?active=Polymer.IronRangeBehavior): `max`, `min`, `ratio`, `step`, `value`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***disabled*** | `Boolean` | True if the progress is disabled. | `false`
***indeterminate*** | `Boolean` | Use an indeterminate progress indicator. | `false`
***max*** | `Number` | The number that indicates the maximum value of the range. | `100`
***min*** | `Number` | The number that indicates the minimum value of the range. | `0`
***ratio*** | `Number` | Returns the ratio of the value. | `0`
***secondaryProgress*** | `Number` | The number that represents the current secondary progress. | `0`
***secondaryRatio*** | `Number` | The secondary ratio | `0`
***step*** | `Number` | Specifies the value granularity of the range's value. | `1`
***value*** | `Number` | The number that represents the current value. | `0`

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--progress-container-color` | Mixin applied to container | `--google-grey-300`
`--progress-transition-duration` | Duration of the transition | `0.008s`
`--progress-transition-timing-function` | The timing function for the transition | `ease`
`--progress-transition-delay` | Delay for the transition | `0s`
`--progress-active-color` | The color of the active bar | `--google-green-500`
`--progress-secondary-color` | The color of the secondary bar | `--google-green-100`
`--progress-disabled-active-color` | The color of the active bar if disabled | `--google-grey-500`
`--progress-disabled-secondary-color` | The color of the secondary bar if disabled | `--google-grey-300`
`--progress-height` | The height of the progress bar | `4px`
