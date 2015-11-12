# &lt;koa-dialog&gt;

It is a dialog. It provides styles for a header, content area, and an action area for buttons.

### Demo

* Demo with [paper-dialog](https://elements.polymer-project.org/elements/paper-dialog?view=demo).

### Behaviors

* [Polymer.IronOverlayBehavior](https://elements.polymer-project.org/elements/iron-overlay-behavior?active=Polymer.IronOverlayBehavior): `canceled`, `noCancelOnEscKey`, `noCancelOnOutsideClick`, `opened`, `withBackdrop`, `cancel()`, `center()`, `close()`, `open()`, `toggle()`.

### Properties

Name | Type | Description | Default
-----|------|-------------|--------
*canceled* | `Boolean` | True if the overlay was canceled when it was last closed. | `false`
*noCancelOnEscKey* | `Boolean` | Set to true to disable canceling the overlay with the ESC key. | `false`
*noCancelOnOutsideClick* | `Boolean` | Set to true to disable canceling the overlay by clicking outside it. | `false`
*opened* | `Boolean` | True if the overlay is currently displayed. | `false`
*withBackdrop* | `Boolean` | Set to true to display a backdrop behind the overlay. | `false`

### Methods

Name | Description
-----|------------
*cancel()* | Cancels the overlay.
*center()* | Centers horizontally and vertically if not already positioned. This also sets `position:fixed`.
*close()* | Close the overlay.
*open()* | Open the overlay.
*toggle()* | Toggle the opened state of the overlay.

### Styling

Custom property | Description | Default
----------------|-------------|--------
`--dialog-background-color` | Dialog background color | `--primary-background-color`
`--dialog-color` | Dialog foreground color | `--primary-text-color`
`--dialog` | Mixin applied to the dialog | `{}`
`--dialog-title` | Mixin applied to the title (`<h2>`) element | `{}`
`--dialog-button-color` | Button area foreground color | `--default-primary-color`
