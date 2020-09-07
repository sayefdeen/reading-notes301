# EJS Partials

[Home](https://sayefdeen.github.io/reading-notes301/)

Partials come in handy when you want to reuse the same HTML across multiple views. Think of partials as functions, they make large websites easier to maintain as you don’t have to go and change a piece of text in every page it appears in. Instead, you define that reusable bundle of code in a file andinclude it wherever you need it.

For Example :

Most of the web sites has the same navbar and the same footer, so insted of repeating the HTML DOM for the them inside each HTML page we can just put them in **ejs** files and include these files whereever we want.

Imagin if we have two ejs files inside the views folders, inside the partials subfolder

- navbar.ejs
- footer.ejs

we can include both of them by using the ejs symbol

```HTML
<%- include('partials/navbar') %>
<%- include('partials/footer') %>
```

by using the **include** keyword, wiht the path of the file you want to add.
