# Part I: Practicing JavaScript ES6 Array Methods with Unit Testing

## Initialize a project

Create a new project. 

```bash
mkdir js-array-methods
cd js-array-methods
```

Open VS Code editor. [[?]](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line)

```bash
code .
```

Create a `package.json` file.

```bash
npm init --yes
```

## Unit test with Jest

Install dependencies. [[?]](https://jestjs.io/docs/getting-started)

```bash
npm install jest --save-dev
```

Update `package.json` file, add a `test` command to `scripts` field.

```json
{
  // ...
  "scripts": {
    "test": "jest"
  }
}
```

Create an `src` folder.

```bash
mkdir src
```

Create an `index.test.js` file in `src` folder.

```js
const sum = (a, b) => {
  return a + b;
};

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

Run `test` command.

```bash
npm run test

> js-array-methods@1.0.0 test
> jest

 PASS  src/index.test.js
  ✓ adds 1 + 2 to equal 3 (6 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        0.525 s, estimated 1 s
Ran all test suites.
```

## Unit test array methods

Create some test cases for JavaScript Array Methods.

```js
test('all number are less than 10', () => {
  const actual = [1, 2, 3, 4, 5].every((n) => n < 10);
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

Run `test` command.

```bash
npm run test
```

## Use fake data

Create a `products.js` file in `src` folder, and grab some fake data from [here](../products.json).

```js
const products = [
  // ...
];

module.exports = products;
```

Use fake data and create more test cases.

```js
test('all product prices are less than 5000', () => {
  const actual = products
    .every((product) => product.price < 5000);
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

Run `test` command.

```bash
npm run test
```

## Solve problems

### Group A

#### Problem 1

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 2

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 3

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 4

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 5

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 6

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 7

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 8

```js
test('...', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

### Group B

#### Problem 1

```js
test('all products have one image at least', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 2

```js
test('there is a product which description says "no side effects"', () => {
  const actual = products; // TODO
  const expected = true;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 3

```js
test('the number of smartphones is 5', () => {
  const actual = products; // TODO
  const expected = 5;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 4

```js
test('the products get over 4.9 rating are fauji and Golden', () => {
  const actual = products; // TODO
  const expected = [{ brand: 'fauji' }, { brand: 'Golden' }];

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 5

```js
test('the only product of Dry Rose is "Gulab Powder 50 Gram"', () => {
  const actual = products; // TODO
  const expected = 'Gulab Powder 50 Gram';

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 6

```js
test('the total revenue is 765,200 if all the products sold without discount', () => {
  const actual = products; // TODO
  const expected = 765200;

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 7

```js
test('the top 3 highest discounted product brand are Apple, OPPO and Boho Decor',  () => {
  const actual = products; // TODO
  const expected = ['Apple', 'OPPO', 'Boho Decor'];

  expect(actual).toStrictEqual(expected);
});
```

#### Problem 8

```js
test('the number of product brands is 28',  () => {
  const brands = {};
  products
    .forEach((product) => {
      // TODO
    });
  const actual = Object.keys(brands).length;
  const expected = 28;

  expect(actual).toStrictEqual(expected);
});
```
