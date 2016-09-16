Ember-Qunit-Snippets
====================

A collection of userfull (i think) snippets to test model for Ember (with QUnit framework)

Test Model Snippets
-------------------

### [qattr] test presence of attribute

```js
test('it has an attribute: ${1:attr}', function(assert) {
  let model = this.subject();
  let hasAttr = Object.keys(model.toJSON()).indexOf("${1:attr}") > -1;
  assert.ok(hasAttr);
});
```
