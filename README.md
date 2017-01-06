#ArcScrubber

This is a proof-of-concept application of traversing an element along the path of an arc. The traversing element (dot), is contained by its parent element (box), which is anchored via absolute positioning to the arc.

It's cross-browser friendly back to IE 10, and has successfully tested on iOS devices and Android (emulators).

The core formula for connecting the dot, box, and arc is:

    dotPosY = ((boxHeight - (arcTop - boxTop)) - (arcRadius - Math.sqrt(arcRadius^2 - mosPos^2))) - dotHalfWidth

In this case, the dot is moved via `translate3d()`, so `dotPosY` must be negative. `dotHalfWidth` is to center the dot along the arc.

For a live example, please visit [michaelshiplet.com/projects/arcscrubber/](https://michaelshiplet.com/projects/arcscrubber/)

**Note:** the `(arcTop - boxTop)` is for an optional vertical offset between the top of the box and the top of the arc. If using this offset, make sure that
```
html, body {
    height: 100%;
    width: 100%;
}
```
Otherwise the offset will not be calculated correctly.
