# &lt;koa-card&gt;

It is a container with a drop shadow.

### Demo

* Demo with [paper-card](https://elements.polymer-project.org/elements/paper-card?view=demo).
* Demo with [ios-card](https://kingofapp.github.io/ios-card).

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--card-header-color` | The color of the header text | `#000`
`--card-header` | Mixin applied to the card header section | `{}`
`--card-header-text` | Mixin applied to the title in the card header section | `{}`
`--card-header-image` | Mixin applied to the image in the card header section | `{}`
`--card-content` | Mixin applied to the card content section| `{}`
`--card-actions` | Mixin applied to the card action section | `{}`
`--card` | Mixin applied to the card | `{}`

---

### [KoaCardBehavior](https://github.com/KingofApp/koa-behaviors/blob/master/koa-card-behavior.html) offers

#### Properties

Name | Type | Description | Default
-----|------|-------------|--------
***fadeImage*** | `Boolean` | When `preloadImage` is true, setting `fadeImage` to true will cause the image to fade into place. | `false`
***heading*** | `String` | The title of the card. | `''`
***image*** | `String` | The url of the title image of the card. | `''`
***preloadImage*** | `Boolean` | When `true`, any change to the image url property will cause the `placeholder` image to be shown until the image is fully rendered. | `false`
