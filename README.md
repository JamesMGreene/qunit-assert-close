# QUnit Close assertion plugin

This plugin for [QUnit](https://github.com/jquery/qunit) adds `close` and `notClose` assertion methods
to test that a number is approximately equal (or not) to an expected number, within a given tolerance.

### Usage ###

```js
assert.close(actual, expected, maxDifference, message);
assert.notClose(actual, expected, minDifference, message);
```

Where:
 - `maxDifference`: the maximum inclusive difference allowed (tolerance) between the `actual` and `expected` numbers
 - `minDifference`: the minimum exclusive difference allowed (tolerance) between the `actual` and `expected` numbers
 - `actual`, `expected`, `message`: The usual

### Example ###
```js
test('Example unit test', function(assert) {
  assert.close(3.141, Math.PI, 0.001);
  assert.notClose(3.1, Math.PI, 0.001);
}
```

For more examples, refer to the unit tests.