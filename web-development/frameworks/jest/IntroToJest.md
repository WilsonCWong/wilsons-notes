<b><a id="top" href="../../../README.md">< Back</a></b>

# Introduction to Jest<!-- omit in toc -->
- [Basic Setup](#basic-setup)
- [Matchers](#matchers)
  - [Testing Truthy Values Explicitly](#testing-truthy-values-explicitly)
  - [Number Comparison](#number-comparison)
  - [Match String Against Regular Expression](#match-string-against-regular-expression)
  - [Check If Array Contains Item](#check-if-array-contains-item)
  - [Test for Exception](#test-for-exception)


## Basic Setup
To begin, install jest with `yarn add --dev jest`.
In your `package.json`, add a script that runs jest like so:

```js
  "scripts": {
    "test": "jest"
  }
```

To create a test, you need to create `*.test.js` files containing the tests you want to run (called a test suite). Then, you will call `test(name, testFunc)`. You use **matchers** inside the test function to do your testing. Finally, you run your tests with `yarn test`.

## Matchers
Matchers allow you to test values in different ways.

The simplest test you could do is an exact equality test:
```js
test("two plus two is four minus one thats 3 quick maths", () => {
  expect(2 + 2 - 1).toBe(3);
})
```
`expect` returns an "expectation" object, which you use to call matchers on. The `toBe` matcher checks if two **objects** match with `Object.is`. To match the **value**, use `toEqual` instead.

```js
test('object assignment', () => {
  const data = { one: 1 };
  data['two'] = 2;
  expect(data).toEqual({ one: 1, two: 2 });
});
```
`toEqual` checks every field of an object or array recursively. You can also use `not` with matchers to check the opposite result.
```js
expect(foo + bar).not.toBe(0);
```
### Testing Truthy Values Explicitly
- `toBeNull` - match `null`
- `toBeUndefined` - match `undefined`
- `toBeDefined` - opposite of `toBeUndefined`.
- `toBeTruthy` - match values `if` statements consider true.
- `toBeFalsy` match values `if` statements consider false.

### Number Comparison
```js
  expect(value).toBeGreaterThan(3);
  expect(value).toBeGreaterThanOrEqual(3.5);
  expect(value).toBeLessThan(5);
  expect(value).toBeLessThanOrEqual(4.5);
```
`toBe` and `toEqual` are equivalent for numbers. Use `toBeCloseTo` instead of `toEqual` for float point numbers, to ignore rounding errors.

### Match String Against Regular Expression
```js
// Match against regexp
expect('Christoph').toMatch(/stop/);
```

### Check If Array Contains Item
```js
expect(shoppingList).toContain('beer');
```

### Test for Exception
```js
expect(compileAndroidCode).toThrow();
```