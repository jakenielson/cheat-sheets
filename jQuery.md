# jQuery

$(document).ready(function(){
  // This gets run after the DOM is parsed
  });

## Table of Contents
0. [Basics](#part0)
1. [Selectors, Animations, and Filters](#part1)

## Basics <a name="part0"></a>

The `$` character is used to represent `jQuery`.

You can wait until the document is ready before using jQuery to find elements.

```
$(document).ready(function(){
  // This gets run after the DOM is parsed
  });

$(document).ready(function(){
  // This does too
  });
```

## Selectors, Animations, and Filters <a name="part1"></a>

### Basic Selectors

```
// Grabs all the <p> elements and gives them the 'border' css property
// with the value '4px solid red'
$('p').css('border', '4px solid red');

// Grabs all the <p> elements within an <li> element
$('li p').css('border', '4px solid red');

// Grabs all the <p> elements with the 'lead' class
$('p.lead').css('border', '4px solid red');

// Grabs the element with ID 'lesson1'
$('#lesson1').css('border', '4px solid red');

// Grabs the first element with the 'box' class
$('.box:first').css('border', '4px solid red');

// Grabs everything
$('*'').css('border', '4px solid red');
```

### Basic Animations

```
// Hide the first box over 500ms
$('.box:first').hide(500);

// Show the box over 500ms
$('.box:first').show(500);

// Hide then show
$('.box:first').hide(500).show(500);

// Hide, wait, show
$('.box:first').hide(500).delay(300).show(500);

// More
$('.box:first').slideUp(500);
$('.box:first').slideDown(500);
$('.box:first').fadeOut(500);

// The animate method works with any property that works in css animations
$('.box:first').animate({height: '200px'}, 300);
```

### Index Filters
