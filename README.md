# Viewport and Polyfills

## Overview

In this lesson we will discuss setting the the meta viewport properties as well as some scripts such as modernizer that allow us to add support for media queries in older browsers.

## Objectives

1. What is the viewport?
1. Setting Meta Viewport, and its purpose.
2. Additional support for older browsers using polyfills and shims.

## Relax Browser, Let Me Control The Layout

<iframe width="640" height="360" src="https://www.youtube.com/embed/videoseries?list=PLj148bJp5wiwFcWOZsmwGE8yaF3dL1jPQ" frameborder="0" allowfullscreen></iframe>

*Note: Slides for this lecture video are provided in the resources at the bottom of this lesson.*

### What Is The Viewport

Simply put, the viewport is the users visible area of the screen to display the web page. Diferent devices have different viewport sizes. On some devices the browser will try to zoom in or out if the width of the website differs from the width of the devieces viewport. This can cause the device to ignore our media queries. Let's look at ways to solve this issue.

### Controlling Viewport Zoom

Did you ever visit a website on a mobile device and notice the site pages came up very small and you had to zoom in to see the content? Or perhaps the opposite wher ethe website page appeared larger than the screen area and you had to drag the content around to see the missing parts jus out of view? We can correct these types of issues by prevneting the device from trying to zoom to fit the content to screen. In order to tell a devices browser not to zoom in or out, we need to set the meta viewport in the head section of our pages. This way, our media queries can do their thing without the device trying to to handle sizing content for us.

```html
<!DOCTYPE html>
<html>
  <head>
    ...
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
    ...
  </body>
</html>
``` 

Here in the head section on line 5 we set the `<meta>` element attribute `name="viewport"` this targets the devices viewport. Then we adjust the viewport content settings under the attribute `content="width=device-width, initial-scale=1.0"`. Here we set the width of the viewport to stay true to the width of the device. Rthen we set the initial-scale value to 1.0, meaning do not increase or decrease the initial scale of the site content, said another way it is asking the device not to zoom at all. This allows out media queries to properly detect the screen size and make the changes we wanted. This gives us the developer the control as opposed to giving the device control ove rthe layout.

### Support For Older Browsers

Another issue might be if a users browser is older and doesn't support media queries. This issue is less and less common and may not be neccesary to plan for in the coming years. It never hurts to provide support for older browsers though... It is easy to provide support for media queries by linking to a copy of Modernizr (a JavaScript polyfill and shim library) that provides support for outdated browsers. It essentially teaches old browsers how to support these new features. You want to first make sure the version of Modernizr you are linking to or downloading and linking to is includding the optional add on scripts for media queries. This is often a checkbox you can select on their website. On their current website which differs in aapperance a bit from the video recording above you can check the media queries box by clicking the circle with the plus sign on it next to the text "Media Queries" like in the screenshot below,

<img src="http://ironboard-curriculum-content.s3.amazonaws.com/front-end/lab-assets/modernizer.png" alt="Modernizr Site Screenshot">

Then click the pink "Build" button and then the "download" link. I had to move mine from my ~/Downloads folder into my website projects js/ folder, then link to modernizr in your head section,

```html
<!DOCTYPE html>
<html>
  <head>
    ...
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="js/modernizr-custom.js"></script>
  </head>
  <body>
    ...
  </body>
</html>
```

## Summary

- You should always set the meta viewport element for all responsive site pages.
- You can include scripts such as Modernizr to provide media query support for older browsers.

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1j_i5pGPB5lHbgr4fpdUDheRBv2kAeOk_yhfd1Uc2f3s/edit?usp=sharing)
- [Modernizr](https://modernizr.com/)
- [CSS Tricks - Meta Viewport](https://css-tricks.com/snippets/html/responsive-meta-tag/)

