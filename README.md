# jasmine-fail-fast

This is a fork of [Uploader/jasmine-fail-fast](https://github.com/Updater/jasmine-fail-fast), with the following modifications:

 * works with Jasmine 2.1
 * only fails fast if a custom `expect().toFailFast(message)` is used inside a test
 
## Protractor setup:

In the Protractor conf file:

```javascript
onPrepare: function() {
  ...
  var failFast = require('jasmine-fail-fast');
  
  // First, add a reporter to watch for failed tests:
  jasmine.getEnv().addReporter(failFast.init());
  
  // Then, add a custom matcher to trigger the reporter:
  beforeEach(function () {
    jasmine.addMatchers(failFast.customMatchers);
  });
  ...
}
```
