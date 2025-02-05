## [1.0.1](https://github.com/coveooss/json-schema-for-humans/compare/v1.0.0...v1.0.1) (2024-05-06)


### Bug Fixes

* Move types packages to dev-dependencies ([#242](https://github.com/coveooss/json-schema-for-humans/issues/242)) ([8050904](https://github.com/coveooss/json-schema-for-humans/commit/805090460bbbce5dccb5eb9a5d7c960a8cdae73e))

# [1.0.0](https://github.com/coveooss/json-schema-for-humans/compare/v0.47.5...v1.0.0) (2024-05-03)

# 0.48

(Issue #190) Now correctly display elements next to a `$ref` with reused nodes, e.g.:

```json
{
  "$schema": "https://json-schema.org/draft/2019-09/schema",
  "type": "object",
  "title": "Example",
  "properties": {
    "prop1": {
      "$ref": "#/$defs/a",
      "description": "Prop1",
      "examples": ["1"]
    },
    "prop2": {
      "$ref": "#/$defs/a",
      "description": "Prop2",
      "examples": ["2"]
    }
  },
  "$defs": {
    "a": {
      "type": "string",
      "maxLength": 5
    }
  }
}
```

Previously, `prop2` would have been a link to `prop1`, hiding the different example for `prop2`.

This may increase the size of rendered schemas in certain situations.
