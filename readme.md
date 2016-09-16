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
### [qrel] test presence of relationship

```js
test('${1:modelCible} relationship', function(assert) {
  let model = this.store().modelFor("${2:modelSource}");
  let relationship = Ember.get(model, 'relationshipsByName').get("${1:modelCible}");

  assert.equal(relationship.key, "${1:modelCible}");
  assert.equal(relationship.kind, "${3:belongsTo}");
});
```

Test Model - Validation Snippets
--------------------------------

These snippets requires "ember-validations" plugins.

### [qreq] Test attr who is required

To use this snippet, ```"ember-validations@validator:local/presence"` module is required on moduleForModel declaration.

```js
test('${1:attr} should be required', function(assert) {
  let model = this.subject();

  Ember.run(function() {
    model.set('${1:attr}', '');
  });

  assert.equal("model.isValid", false, 'Object is Valid without a ${1:attr}');
});
```
