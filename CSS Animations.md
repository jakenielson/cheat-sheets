# CSS Animations

## Transition

The transition property is used to give a sense of motion or change to an element. Instead of appying the change immediately, the change is made gradually over the declared duration.

```
//syntax
.element {
    transition: [property] [duration] [ease] [delay];
}
```
```
//example
.element {
    transition: opacity 300ms ease-in-out 1s;
}
```
You can trigger transitions in different ways. Here, we trigger a simple translate transition with the hover pseudoclass:

```
.element {
    transition: transform 300ms ease-in-out;
}

.element:hover {
    transform: translate(200px, 150px) rotate(20deg);
}
```
