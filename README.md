# Reusable CSS components
A simple reusable library of components. To use, copy the the `static/scss/components` folder into your own scss folder, and import what you need from there. Yeah it's dirty, because this repo is intended for personal use. Installable package will be made soon.

```
Note: This library is a work in progress. More components will be added over time, do keep checking it out!
```

## Component breakdown
### cleanup.scss
A super simple cleanup file that 
* Removes borders and padding around body tags
* Sets the default font-family to `Arial, Helvetica, sans-serif;`
* A bunch of other useful stuff picked up from the famous normalise.css

### images.scss
A bunch of classes for common styles on images:

*   **.roundedimage**
    This class rounds the `img` that it is added to. Note that, however, you need to set the size of the image manually. This is an extra step, but is deliberate because the size of rounded images can be anything based on use cases.  

    Usage:
    ```html
    <img src="static/img/converted_DSCN0079.jpg" class="roundedimage my-image">
    ```
    ```scss
    @import 'components/images';

    .my-image{
        width: 15rem;
        height: 15rem;
    }
    ```

### elements.scss
Styling for various single elements on a page:

*   **.buttonlink**
    This class simply makes a link look like a fancy button with a rounded border around it and some padding. For all those times when wrapping a button with an `a` and then styling it becomes a pain.  

    Usage:
    ```html
    <a href="https://google.com" class="buttonlink">GOOGLE</a>
    ```

## Customising Colors
This library uses a color scheme similar to that of old-school android. It assumes your standard webpage with a dominating color for large sections like footers, a lighter version of that for unimportant but good-to-know stuff, and an accent color, for styling links, buttons and stuff like that.

The variable names are:

Variable | Purpose
---------|--------
$primary_color|Large dominating areas
$secondary_color|Subtitles, captions and other less important stuff
$accent_color|For flair across the page, like links, buttons, etc

Here's how these value can be customised. Make sure ``colors.scss`` is the first thing imported in your scss file. Then, **before importing anything else,** set your own values for these colors. To change the accent color to `tomato`,

```scss
@import 'components/colors';
$accent_color: tomato;

@import 'components/cleanup';
@import 'components/images';
@import 'components/elements';
/* 
OTHER ELEMENTS
AND REMAINING STYLESHEET
*/
```