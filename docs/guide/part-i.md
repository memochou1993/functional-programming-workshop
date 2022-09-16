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

Update `index.test.js` file.

```js
const practice = require('.');

test('case1 should get the first Huawei product in the list.', () => {
  const actual = practice.case1();
  const expected = {
    "id": 5,
    "title": "Huawei P30",
    "description": "Huawei’s re-badged P30 Pro New Edition was officially unveiled yesterday in Germany and now the device has made its way to the UK.",
    "price": 499,
    "discountPercentage": 10.58,
    "rating": 4.09,
    "stock": 32,
    "brand": "Huawei",
    "category": "smartphones",
    "thumbnail": "https://dummyjson.com/image/i/products/5/thumbnail.jpg",
    "images": [
      "https://dummyjson.com/image/i/products/5/1.jpg",
      "https://dummyjson.com/image/i/products/5/2.jpg",
      "https://dummyjson.com/image/i/products/5/3.jpg"
    ]
  };

  expect(actual).toStrictEqual(expected);
});

test('case2 should list all smartphones brands, without any duplicate.', () => {
  const actual = practice.case2();
  const expected = [
    'Apple',
    'Samsung',
    'OPPO',
    'Huawei',
  ];

  expect(actual).toStrictEqual(expected);
});

test('case3 should tell wether all fragrances products have stock over 100.', () => {
  const actual = practice.case3();
  const expected = false;

  expect(actual).toStrictEqual(expected);
});

test('case4 should get the title of the lowest rating product in home-decoration category.', () => {
  const actual = practice.case4();
  const expected = 'Plant Hanger For Home';

  expect(actual).toStrictEqual(expected);
});

test('case5 should tell whether there is any product lack of thumbnail.', () => {
  const actual = practice.case5();
  const expected = false;

  expect(actual).toStrictEqual(expected);
});

test('case6 should tell wether all products have discountPercentage.', () => {
  const actual = practice.case6();
  const expected = true;

  expect(actual).toStrictEqual(expected);
});

test('case7 should get the average rating for fragrances, round to 2 decimal places.', () => {
  const actual = practice.case7();
  const expected = 4.35;

  expect(actual).toStrictEqual(expected);
});

test('case8 should list the discount price for all smartphones, round to 0 decimal places.', () => {
  const actual = practice.case8();
  const expected = [
    71,
    161,
    193,
    50,
    53,
  ];

  expect(actual).toStrictEqual(expected);
});

test('case9 should determine that all products have one image at least.', () => {
  const actual = practice.case9();
  const expected = true;

  expect(actual).toStrictEqual(expected);
});

test('case10 should determine that there is a product which description says "no side effects".', () => {
  const actual = practice.case10();
  const expected = true;

  expect(actual).toStrictEqual(expected);
});

test('case11 should get the number of smartphones.', () => {
  const actual = practice.case11();
  const expected = 5;

  expect(actual).toStrictEqual(expected);
});

test('case12 should get the brand of products which get over 4.9 rating.', () => {
  const actual = practice.case12();
  const expected = [{ brand: 'fauji' }, { brand: 'Golden' }];

  expect(actual).toStrictEqual(expected);
});

test('case13 should get title of the first product of Dry Rose.', () => {
  const actual = practice.case13();
  const expected = 'Gulab Powder 50 Gram';

  expect(actual).toStrictEqual(expected);
});

test('case14 should get the total revenue when all the products sold without discount.', () => {
  const actual = practice.case14();
  const expected = 765200;

  expect(actual).toStrictEqual(expected);
});

test('case15 should get the top 3 highest discounted product brands.',  () => {
  const actual = practice.case15();
  const expected = ['Apple', 'OPPO', 'Boho Decor'];

  expect(actual).toStrictEqual(expected);
});

test('case16 should get the number of product brands.',  () => {
  const actual = practice.case16();
  const expected = 28;

  expect(actual).toStrictEqual(expected);
});
```

Create `index.js` file.

```js
const products = require('./products');

const practice = {
  case1() {
  },
  case2() {
  },
  case3() {
  },
  case4() {
  },
  case5() {
  },
  case6() {
  },
  case7() {
  },
  case8() {
  },
  case9() {
  },
  case10() {
  },
  case11() {
  },
  case12() {
  },
  case13() {
  },
  case14() {
  },
  case15() {
  },
  case16() {
  },
};

module.exports = practice;
```

Solve problems and run `test` command.

```bash
npm run test
```
