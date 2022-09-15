# Part IV: Implementing Method Chaining with OOP

## Example of method chaining

Implementations in defferent languages:

- JavaScript: <https://lodash.com/docs/4.17.15#chain>
- PHP: <https://laravel.com/docs/9.x/collections>

```js
collect([1, 2, 3])
  .map((v: number) => v * 2)
  .filter((v: number) => v < 5)
  .toArray();
```

## Create test case for "map" function

Create an `index.test.ts` file in `src` folder.

```js
import { test, expect } from 'vitest';
import { collect } from './index';

test('map should work', () => {
  const actual = collect([1, 2, 3, 4, 5])
    .map((v: number) => v * 2)
    .toArray();
  const expected = [2, 4, 6, 8, 10];

  expect(actual).toStrictEqual(expected);
});
```

Run `test` command.

```bash
npm run test

🔴 FAIL  src/index.test.ts > method chaining
TypeError: collect is not a function
```

## Implement "map" function

Create an `index.ts` file in `src` folder, and create a `Collection` class.

```js
class Collection {
  private items;

  constructor(items: Array<any>) {
    this.items = items;
  }
}
```

Implement a `map` function for the class, and return the class itself.

```js
import {
  map,
} from './modules';

class Collection {
  private items;

  constructor(items: Array<any>) {
    this.items = items;
  }

  map(callable: Function) {
    this.items = map(this.items, callable);
    return this;
  }
}
```

Implement a `toArray` function for the class, and return the array data.

```js
class Collection {
  // ...

  toArray() {
    return this.items;
  }
}
```

Create a `collect` helper function, and return a `Collection` instance.

```js
// ...

const collect = (items: Array<any>): Collection => new Collection(items);

export {
  collect,
};
```

Run `test` command.

```bash
npm run test

🟢 PASS  Waiting for file changes...
```

## Implement more functions

Implement more functions for the class with TDD:

- map ✅
- every
- filter
- find
- forEach
- includes
- reduce
- reject
- size
- some

Finally, run `coverage` command.

```bash
npm run coverage
```
