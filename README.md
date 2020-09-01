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