# Performance

## Minify, Compress, Cache!

Minifying, compressing, and caching files can all make a difference in performance. Minifying and compressing reduce the number of bytes fetched, and caching reduces the frequency of fetching.

### Minify

Minification is the process of removing all unnecessary characters from source code without changing the functionality of the code. Stripping the parts of the code that make it readable can make it more performant.

Use Google to find a minifying service you like.

### Compress

Compression takes minification a step further by condensing your code to as few characters as possible without changing the functionality of the code. Compressed code must be uncompressed first before execution, unlike minified code which is still valid.

Use Google to find a compression service you like.

### Cache

Caching is a tool the browser uses to access previously fetched files without having to go and retrieve them again. The browser does this by itself, but there are a few ways you can work with the browser to optimize caching.

You can use the Expires header to set when the webpage expires:
* Expires: Wed, 21 Oct 2015, 19:28:00

You can use the Cache Control superheader to control if and for how long a page is cached:
* Cache-Control: max-age = 86400 (seconds)
* Cache-Control: no-store
* Cache-Control: no-cache
* Cache-Control: public
* Cache-Control: private

## Controlling Linked CSS with Media Queries

The media attribute can be added to a css link to control if and when that file is fetched.

```
<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="style-print.css" media="print">
```

## Controlling Script Timing

You can fire scripts on the onLoad event if they don't modify the DOM or CSSOM. This allows your page to completely load before being bogged down by the scripts.

You can also use async scripts, which run separately from the render path. You can make a script async by adding the async attribute:
`<script src="app.js" async></script>`

## RAIL

RAIL stands for Response, Animation, Idle, Load. Each of these events have a unique window for work to be done:
* Response: 100ms
* Animation: 16ms (10-12ms)
* Idle 50ms
* Load 1s

Since the browser has some housekeeping to do, you realistically only have 10-12ms to do work for an animation to maintain 60 fps.

## requestAnimationFrame

The requestAnimationFrame function is used to ensure that code is run at the beginning of each frame:
```
function animate(){
    //Do Animation Work
    requestAnimationFrame(animate);
}
requestAnimationFrame(animate);
```

The animation is initialized by calling requestAnimationFrame with the animate function as a parameter. The animation continues when animate re-calls requestAnimationFrame. This creates a loop that iterates at the start of every frame.

## Web Workers

Web workers are special javascript files that take care of work away from the main thread, in a "worker" thread. This allows heavy lifting to be done without affecting performance.

The following example creates a worker that multiplies two numbers and returns the result:
```
//main.js

var myWorker = new Worker('worker.js'); //spawn the worker

first.onChange = function(){
    myWorker.postMessage([first.value, second.value]); //post a message to the worker with the numbers
}
second.onChange = function(){
    myWorker.postMessage([first.value, second.value]); //post a message to the worker with the numbers
}

myWorker.onMessage = function(e){
    result.textContent = e.data; //write the result to an element
}
```
```
//worker.js

onMessage = function(e){
    var workerResult = 'Result ' + (e.data[0]*e.data[1]); //calculate the result
    postMessage(workerResult); //post the result
}
```

## Forced Synchronous Layout

Really look out for forced synchronous layout in your javascript files. You don't want to trigger layout in loops, and you don't want to trigger layout before you trigger styles. Both of these will cause unnecessary backtracking in the CRP.

You can find a list of which properties trigger which CRP components at https://csstriggers.com/.

## Forcing New Layers

Sometimes moving an element to its own layer can help reduce paint calls. You do this by adding the will-change attribute to a class, or by utilizing the null transform hack:
```
//will-change
.circle {
    will-change: transform;
}

//null transform hack
.circle {
    transform: translateZ(0);
}
```
