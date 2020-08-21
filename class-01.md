# Read-01 Respoonsive web design and floats.

[Home](https://sayefdeen.github.io/reading-notes301/)

## Responsive Web Design

Responsive web designe is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile of desktop.

Responsive vs. Adaption vs. Mobile.

Responsive means to react quickly and positively to any change, while adapting means to be easily modified for a new purpose of situation, such as change.

With responsive design websites continually and fluidly change based in different factors. A combination of the two is ideal, providing the prefect formula for functional websites, which term is used specifically dosen't make a huge difference.

Currently the most popular technique lies within responsive web design, favoring design that dynamically adapts to different browser and device viewports, changing layout and content along the way. This solution has the benefits of being all three, responsive, adaptive, and mobile.

## Flexible Layouts

Responsive web design is broken down into three main components, including flexible layouts, media queries, and flexible media. The first part, flexible layouts, is the practice of building the layout of a website with a flexible grid, capable of dynamically resizing to any width. Flexible grids are built using relative length units, most commonly percentages or em units. These relative lengths are then used to declare common grid property values such as width, margin, or padding.

CSS3 introduced some new relative length units, specifically related to the viewport size of the browser or device.

- vw : Viewports width

- vmin : Minimum of the viewport's height and width.

- vh : Viewports height.

- vmax : Minimum of the viewport's height and width.

Flexible layouts do not advocate the use of fixed measurement units, such as pixels or inches. Reason being, the viewport height and width continually change from device to device, by taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element.

        target ÷ context = result
        element ÷ parent = result

## Media Queries

There are a couple different ways to use media queries, using the `@media` rule inside of an existing style sheet, importing a new style sheet using the `@import` rule, or by linking to a separate style sheet from within the HTML document. Generally speaking it is recommend to use the `@media` rule inside of an existing style sheet to avoid any additional HTTP requests.

```css
/* @media Rule */
@media all and (max-width: 1024px) {
  ...;
}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {
  ...;
}
```

Each media query may include a media type followed by one or more expression, Common media types include `all,screen,print,tv,braille`. The HTML5 specification includes new media types, even including 3d-glasses. Should a media type not be specified the media query will default the media type to `screen`.

## Logical Operators in Media Queries.

Logical operators in media queries help build powerful expressions. There are three different logical operators available for use within media queries, including `and`, `not`, and `only`.

## Viewport.

Mobile devices generally do a pretty decent job of displaying websites these days. Sometimes they could use a little assistance though, particularly around identifying the viewport size, scale, and resolution of a website. To remedy this, Apple invented the viewport `meta` tag.

- Viewport Height and Width.

Using the viewport meta tag with either the height of width values will define the heigth o width of the viewport respectively.

```html
<!-- Takes the device width -->`
<meta name="viewport" content="width=device-width" />
```

- Viewport Scale.

To control how a website is scaled on a moblie device, and how users can continue to scale a website, use the `minimum-scale, maximum-scale, initial-scale` and `user-scalable` properties, Values if `initial-scale` should always be a positive integer between 0 and 10.

```html
<meta name="viewport" content="initial-scale=2" />
<meta name="viewport" content="minimum-scale=0" />
```

Turning off the ability to scale a website is a **bad idea**. It harms accessibility and usability, preventing those with disabilities from viewing a website as desired.

Note: You can combine more than one viewport content in the same `meta` tag.

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

### CSS Viewport Rule.

Since the `viewport` meta tag revolves so heavily around setting the style of how a website should be rendered it has been recommend to move the viewport from a meta tag with HTML to an `@` rule within CSS.

Currently some browsers have already implemented the `@viewport rule, however support isn't great across the board, The previously recommended`viewport` meta tag would look like this.

```css
@viewport {
  width: device-width;
  zoom: 1;
}
```

## Flexible Media.

The final, equally important aspect to responsive web design involves flexible media. As viewports begin to change size media doesn’t always follow suit. Images, videos, and other media types need to be scalable, changing their size as the size of the viewport changes.

```css
img,
video,
canvas {
  max-width: 100%;
}
```

The code upove will make the media scalable by using the `max-width` properity, Doing this to ensure that as the iewport get smaller any media will scale down according to its container width.

---

## Float

Float is a CSS positioning property, in page layout programs, the boxes that hold the text can be told to honer the text wrap, or to ignore it. Ignoring the text wrap will allow the words to flow right over the image like it wasn't even there. This is the difference between that image being part of the flow of the page/or not. _Web designe is very similar_.

Float is different form the position property, Float keeps the element in the same flow of the page which means that the other elements will be affected by it, on the other hand the position (absolute/relative) will remove the element from the flow of the page, which means other elemens will never be affected by it regadless if they touch it or not.

There are four valid values for the float porperty, **Left** and **Right**, **None** (the default) ensure the element will not float, and **Inherit** which will assume the float value from that elements parent element.

## Clearing the Float.

An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.

Clear has four values as well, **Both** is most commonly used which clears floats comming from either dierction repectibely, **None** is the default, which is typically unnecessary unless remiving a clear calue from a cascade, **Inherite** would be the fifth, but is strangely not supported in Internet Explorer. Clearing only the left or right float, while less commonly seen in the wild, definitely has its uses.

## Ways To Clear Foat

- **The Empty Div Method** : is a quite literally, an empty div `<div style="clear:both;"></div>`, div is used because it has no browser default styling, doesn't have any special function, and is unlikely to generically styled with CSS.

- **The Overflow Method** : relies on setting the overflow CSS property on a parent element, If this property is set to auto or hidden on the parent element, the parent will expand to contain the floats, effectively clearing it for succeeding elements.

- **The Easy Clearing Method** : uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent, you apply an additional class like “clearfix” to it. Then apply this CSS.

```css
.clearfix:after {
  content: ".";
  visibility: hidden;
  display: block;
  height: 0;
  clear: both;
}
```
