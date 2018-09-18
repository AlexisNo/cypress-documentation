---
title: after:test:run
---

The `after:test:run` event fires after the test and all **afterEach** and **after** hooks run.

# Environment

Event | {% url "Browser" catalog-of-events#Browser-Events %} | {% url "Background Process" background-process %}
--- | --- | ---
{% url `after:test:run` after-test-run-event %} | {% fa fa-check-circle green %} | {% fa fa-check-circle green %}

# Arguments Received

* test attributes **(Object)**

# Usage

## In the browser

```javascript
// in a test or cypress/support/index.js

Cypress.on('after:test:run', (test) => {
  // test looks something like this:
  // {
  //   body: 'function () {\nexpect('login').to.work;\n}',
  //   title: 'login works',
  //   type: 'test',
  //   // ...more properties...
  // }
})
```

## In the background process

```javascript
// cypress/background/index.js

module.exports = (on, config) => {
  on('after:test:run', (test) => {
  // test looks something like this:
  // {
  //   body: 'function () {\nexpect('login').to.work;\n}',
  //   title: 'login works',
  //   type: 'test',
  //   // ...more properties...
  // }
  })
}
```