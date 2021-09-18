# README

Only setup this files:

- Edit config/webpack/environment.js

```js
const webpack = require('webpack')

environment.plugins.append('Provide', new webpack.ProvidePlugin({
    $: 'jquery',
    jQuery: 'jquery',
    Popper: ['popper.js', 'default']
}))
```

- Edit app/javascript/packs/application.js

```js
import * as bootstrap from 'bootstrap';
import "../stylesheets/application"

// config tooltip and popover globally
document.addEventListener("turbolinks:load", () => {
  var tooltipTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="tooltip"]'))
  var tooltipList = tooltipTriggerList.map(function (tooltipTriggerEl) {
    return new bootstrap.Tooltip(tooltipTriggerEl)
  })

  var popoverTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="popover"]'))
  var popoverList = popoverTriggerList.map(function (popoverTriggerEl) {
    return new bootstrap.Popover(popoverTriggerEl)
  })
})
```

- Create app/stylesheets/application.scss

```scss
@import "~bootstrap/scss/bootstrap";
```

## This project is using

- Ruby version 2.7

- Rails version 6.1

- Bootstrap 5.1
