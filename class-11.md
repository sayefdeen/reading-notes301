# EJS

[Home](https://sayefdeen.github.io/reading-notes301/)

EJS is a simple templating language that lets you generate HTML matrkup with plain JavaScript, No religiousness about how to organize things. No reinvention of iteration and control-flow. **It's just plain JavaScript.**

1. Use plain JavaScript
2. Fast development time
3. Simple syntax
4. Speedy execution
5. Easy debugging
6. Active development

## Get Started

1. Install

```command
 npm install ejs
```

2. Use
   Pass EJS a template string and some data. BOOM, you've got some HTML.

```javascript
let ejs = require('ejs');
let people = ['geddy', 'neil', 'alex'];
let html = ejs.render('<%= people.join(", "); %>', { people: people });
```

3. CLI

```
ejs ./template_file.ejs -f data_file.json -o ./output.html
```

4. Browser support

```html
<script src="ejs.js"></script>
<script>
  let people = ['geddy', 'neil', 'alex'];
  let html = ejs.render('<%= people.join(", ");%>', { people: people });
</script>
```

You can see the [Documentaion](https://ejs.co/#install) By Clicking in the previous link.
