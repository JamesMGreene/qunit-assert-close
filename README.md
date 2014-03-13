[![Build Status](https://travis-ci.org/JamesMGreene/qunit-assert-close.png)](https://travis-ci.org/JamesMGreene/qunit-assert-close) [![NPM version](https://badge.fury.io/js/qunit-assert-close.png)](http://badge.fury.io/js/qunit-assert-close)

# QUnit Close assertion plugin

This plugin for [QUnit](https://github.com/jquery/qunit) adds `close`, `notClose`, `close.percent`, and `notClose.percent`
assertion methods to test that a number is approximately equal (or not) to an expected number, within a given tolerance.

## Usage

```js
assert.close(actual, expected, maxDifference, message);
assert.notClose(actual, expected, minDifference, message);
assert.close.percent(actual, expected, maxPercentDifference, message);
assert.notClose.percent(actual, expected, minPercentDifference, message);
```

Where:
 - `maxDifference`: the maximum inclusive difference allowed (tolerance) between the `actual` and `expected` numbers
 - `minDifference`: the minimum exclusive difference allowed (tolerance) between the `actual` and `expected` numbers
 - `actual`, `expected`, `message`: The usual

## Examples

### Example 1: Number differences
```js
QUnit.test('Example number unit test', function(assert) {
  assert.close(3.141, Math.PI, 0.001);
  assert.notClose(3.1, Math.PI, 0.001);
});
```

### Example 2: Percentage differences
```js
QUnit.test('Example percentage unit test', function(assert) {
  assert.close.percent(155, 150, 3.4);     // Difference is ~3.33%
  assert.notClose.percent(156, 150, 3.5);  // Difference is 4.0%
});
```

For more examples, refer to the unit tests.