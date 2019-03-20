# stylelint-block-as-partial

This plugin forces all styles within a file to be contain in one
top-level block. A component named `.Component` or `#Component` *must*
be styled in a file called `Component.scss` or `_Component.scss`.

This would fail:

```scss
/* thing.scss */
.thing {}
.another-thing {}
```
```scss
/* thing.scss */
.another-thing {}
```
```scss
/* thing.scss */
.thing { background: red; }

@media screen {
  .thing { background: blue; }
}
```

This is correct:

```scss
/* thing.scss */
.thing {}
```
```scss
/* another-thing.scss */
.another-thing {}
```
```scss
/* thing.scss */
.thing {
  background: red;

  @media screen {
    background: blue;
  }
}
```

## Installation and usage

```bash
npm install --dev stylelint-block-as-partial
```

Usage example in `.stylelintrc`:

```json
{
  "plugins": [
    "stylelint-block-as-partial"
  ],
  "rules": {
    "plugin/block-as-partial": ["always", {
      "skip": [
        "./node_modules/normalize.css/normalize.css",
        "src/base/page.css",
        "src/components/table.css"
      ]
    }]
  }
}
```
