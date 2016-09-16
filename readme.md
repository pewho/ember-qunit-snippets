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
