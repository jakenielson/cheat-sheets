# CSS

## Table of Contents
1. [Basics](#basics)
2. [Color](#color)

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
