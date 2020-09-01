# Nyx - Reusable CSS components
A simple reusable library of components. To use, copy the the `nyx` folder into your own scss folder, and import what you need from there. Yeah it's dirty, because this repo is intended for personal use. Installable package will be made soon.

Also, the library is minimal, but quite opinionated.

```
Note: This library is a work in progress. More components will be added over time, do keep checking it out!
```

## How To Use
### cleanup.scss
A super simple cleanup file that 
* Removes borders and padding around body tags
* Sets the default font-family to `Arial, Helvetica, sans-serif;`
* Makes the headers really huge for displays
* A bunch of other useful stuff picked up from the famous normalise.css

### navmenu.css
Provides a responsive navbar menu that displays items in a horizontal row on desktop, and a hamburger menu on mobile. The hamburger menu is also functional; you don't need any javascript to make it work! Tapping the hamburger slides out a full width menu from the right side of the screen. 

To implement the menu, first create the hamburger menu as follows:
```html
<a href="#navmenu" class="hamburger">
    <span></span>
    <span></span>
    <span></span>
</a>
```
The href points to the `id` of the menu we are about to create. The `hamburger` class is used by Nyx to render the three `span` elements as a hamburger icon.

Then, create a menu using the following syntax:
```html
<nav id="navmenu">
    <a href="#" class="closebutton">X</a>

    <ul>
        <li>
            <a href="https://sentient-pixels.com">Sentient-Pixels</a>
        </li>
        <li>
            <a href="https://github.com/theabdullahalam/nyx">Github</a>
        </li>
        <li>
            <a href="https://unsplash.com/abdullahalam">Unsplash</a>
        </li>                        
    </ul>
</nav>
```
The close button link must point to `#`.

And that's it! The menu should now work! In the demo, this menu is placed inside a full width header at the top, which is the most common implementation of such a menu. Here's the **full HTML** for that:

```html
<div id="header">

        <!-- PAGE TITLE -->
        <h1 id="title">Nyx CSS</h1>

        <!-- HAMBURGER ICON -->
        <a href="#navmenu" class="hamburger">
            <span></span>
            <span></span>
            <span></span>
        </a>

        <!-- THE MENU -->
        <nav id="navmenu">
            <a href="#" class="closebutton">X</a>

            <ul>
                <li>
                    <a href="https://sentient-pixels.com">Sentient-Pixels</a>
                </li>
                <li>
                    <a href="https://github.com/theabdullahalam/nyx">Github</a>
                </li>
                <li>
                    <a href="https://unsplash.com/abdullahalam">Unsplash</a>
                </li>                        
            </ul>
        </nav>
        
    </div>
```
Relevant CSS:
```scss
#header{
    background: teal;
    color: white;
    display: flex;
    align-items: center;
    padding-left: 2rem;
    padding-right: 2rem;    

    .hamburger{
        margin-left: auto;
    }

    #navmenu{
        margin-left: auto;
    }
    
}
```

*The left margin of both the hamburger and the menu is set to auto. This is so that whicher one is currently visible will stay on the right edge of header. This is a highly specific example for the demo; tweak it to your use case.*


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