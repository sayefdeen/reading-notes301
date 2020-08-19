# Read-01 Respoonsive web design and floats.

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
