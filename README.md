[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://beta.webcomponents.org/element/sbonnick/feature-toggle)

# \<feature-toggle\>

support feature toggles for polymer components. 
The intent of this component is allow for toggling on/off a set of components with the ability to maintain the state of such toggles. 
This component leverages `stamping` and `dom-if` to isolate toggled off components instead of just hiding them.
to mainstain state of the toggles, `localStorage` is used. Toggle settings can be set by writing directly to the localStorage following a JSON format.

## localStorage Format
The format of the feature toggles in localStorage is a key matchign the feature toggle set containing a JSON string.
The JSON string should be a list of features set to true or false. if a feature toggle is used in code but not set in localStorage, it will used the defined default.

```
Key:   feature-set-name
Value: { feature-name: true|false, ... }
```

## Usage

Refer to demo and API Docs for more examples

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="feature-toggle.html">
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<feature-toggle set="demo-toggles" feature="newStuff">
  <p>New feature that is hidden by default</p>
</feature-toggle>

<feature-toggle set="demo-toggles" feature="newStuff" invert-toggle>
  <p>Old feature that is shown by default</p>
</feature-toggle>
```


## Development

### Install the Polymer-CLI

First, make sure you have the [Polymer CLI](https://www.npmjs.com/package/polymer-cli) installed. Then run `polymer serve` to serve your application locally.

### Viewing Your Application

```
$ polymer serve
```

### Building Your Application

```
$ polymer build
```

This will create a `build/` folder with `bundled/` and `unbundled/` sub-folders
containing a bundled (Vulcanized) and unbundled builds, both run through HTML,
CSS, and JS optimizers.

You can serve the built versions by giving `polymer serve` a folder to serve
from:

```
$ polymer serve build/bundled
```

### Running Tests

```
$ polymer test
```

Your application is already set up to be tested via [web-component-tester](https://github.com/Polymer/web-component-tester). Run `polymer test` to run your application's test suite locally.
