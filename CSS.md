# CSS

## Table of Contents
1. [Basics](#basics)
2. [Color](#color)
3. [Text](#text)

## Basics <a name="basics"></a>

### Linking External CSS

```
<link href="css/styles.css" type="text/css" rel="stylesheet" />
```

### Using Internal CSS

```
<style type="text/css">
  // CSS
</style>
```

### Selectors

* Universal: `* {}`
* Type: `h1, h2, h3 {}`
* Class: `.note {}` `p.note {}`
* ID: `#introduction {}`
* Child: `li>a {}`
* Descendant: `p a {}`
* Adjacent sibling: `h1+p {}`
* General sibling: `h1~p {}`

### Cascading and Inheritance

**Last Rule**: If two selectors are identical, the latter takes precedence.

**Specificity**: If one selector is more specific than the others, it takes precedence.

**Inheritance**: The `inherit` value forces properties to inherit values from their parent elements: `padding: inherit;`

## Color <a name="color"></a>

### Foreground Color

The `color` property specifies the color of text inside an element.

```
h1 {
  color: DarkCyan;
}
h2 {
  color: #ee3e80;
}
h3 {
  color: rgb(100, 100, 90);
}
```

### Background Color

The `background-color` property specifies the color of the element's background.

```
body {
  background-color: DarkCyan;
}
h1 {
  background-color: rgb(100, 100, 90);
}
h2 {
  background-color: #ee3e80;
}
p {
  background-color: white;
}
```
### Opacity

The `opacity` property specifies the opacity of an element and any of its child elements. The value is a number between 0.0 and 1.0.

The rgba color property includes an `alpha` value that indicates opacity.

```
p.one {
  background-color: rgb(0,0,0);
  opacity: 0.5;
}
p.two {
  background-color: rgb(0, 0, 0); // You should offer an rgb fallback in case rgba isn't supported
  background-color: rgba(0, 0, 0, 0.5);
}
```

### HSL Colors

CSS3 includes a new way to specify colors called HSL (Hue, Saturation, Lightness).

**HUE** specifies an angle on a color wheel between 0 and 360.

**SATURATION** specifies the amount of gray in a color between 0% (full grey) and 100% (no gray).

**LIGHTNESS** specifies the amount of white or black in a color, from 0% (black) to 100% (white).

```
body {
  background-color: #C8C8C8; // Fallback
  background-color: hsl(0, 0%, 78%);
}
```

## Text <a name="text"></a>

### Specifying Typefaces

The `font-family` property specifies the typeface used for any text inside the element.

You can specify a list of fonts separated by commas to provide alternatives for the browser.

```
body {
  font-famiy: Georgia, Times, serif;
}
h1, h2 {
  font-family: Arial, Verdana, sans-serif;
}
.credits {
  font-family: "Courier New", Courier, monospace;
}
```

### Size of Type

The `font-size` property specifies the size of a font. This can be declared in px, %, or em.

```
body {
  font-family: Arial, Verdana, sans-serif;
  font-size: 12px;
}
h1 {
  font-size: 200%;
}
h2 {
  font-size: 1.3em;
}
```

### More Fonts

`@font-face` specifies a path to a font which will be downloaded if it is not on the user's machine.

```
@font-face {
  font-family: 'ChunkFiveRegular':
  src: url('fonts/chunkfive.eot');
  src: url('fonts/chunkfive.eot?#iefix') format('embedded-opentype'),
       url('fonts/chunkfive.woff') format('woff'),
       url('fonts/chunkfive.ttf') format('truetype'),
       url('fonts/chunkfive.svg#ChunkFiveRegular') format('svg');
}
```
