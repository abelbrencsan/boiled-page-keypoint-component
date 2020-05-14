# Boiled Page keypoint component

Keypoint SCSS component for Boiled Page frontend framework. It is intended to create wrapped boxes to highlight a value or icon.

## Install

Place `_keypoint.scss` file to `/assets/css/components` directory, and add its path to components block in `assets/css/app.scss` file.

## Usage

### Classes

Class name | Description | Example
---------- | ----------- | -------
`keypoint` | Applies a keypoint. | `<div class="keypoint"></div>`

### Examples

#### Example 1

The following example shows a keypoint with the value of 12.

```html
<div class="keypoint" aria-hidden="true">12</div>
```

### Extension ideas

#### Small keypoint

```scss
/* Keypoint component extensions */
div.keypoint {

  // Small keypoint
  &.keypoint--small {
    font-size: ($normal-font-size * 1.5);
  }
}
```

#### Large keypoint

```scss
/* Keypoint component extensions */
div.keypoint {

  // Large keypoint
  &.keypoint--large {
    font-size: ($normal-font-size * 2.5);
  }
}
```

#### Circle keypoint

```scss
/* Keypoint component extensions */
div.keypoint {

  // Circle keypoint
  &.keypoint--circle {
    border-radius: 50%;
  }
}
```

#### Scheme colored keypoints

Add `generate-keypoint` to each scheme in SCSS variables with the value of true or false. Then you can use kepoints in colors of enabled schemes.

```scss
/* Keypoint component extensions */
div.keypoint {

  // Scheme colored keypoints
  @each $scheme in map-keys($schemes) {
    @if (map-val($schemes, $scheme, generate-keypoint)) {
      &.keypoint--#{$scheme} {
        background-color: map-val($schemes, $scheme, bg-color);
        color: map-val($schemes, $scheme, fg-bold-color) !important;
      }
    }
  }
}
```