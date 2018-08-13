Usage example in `.stylelintrc`:

```
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
