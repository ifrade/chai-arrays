# chai-arrays
a simple chai plugin for better array assertions

---

## Installation
```
npm install chai-arrays
```

---

## Usage

### plug-in

```
const chai = require('chai');
const assertArrays = require('chai-arrays');
chai.use(assertArrays);
```

### array

Asserts that the type of `actual` is `Array`.

```
expect([1, 2, 3]).to.be.array();
expect('foobar').not.to.be.array();
```

### ofSize

Asserts that the size of `actual` is equal to `expected`.

```
expect([1, 2, 3]).to.be.ofSize(3);
expect([1, 2, 3]).not.to.be.ofSize(5);
```

### equalTo

Asserts that the `actual` is equal to `expected`.

```
expect([1, 2, 3]).to.be.equalTo([1, 2, 3]);
expect([1, 2, 3]).not.to.be.equalTo([1, 2, 5]);
```

### containing

Asserts that the `actual` is containing the `expected` element.

```
expect([1, 2, 3]).to.be.containing(1);
expect([1, 2, 3]).not.to.be.containing(5);
```

### containingAllOf

Asserts that the `actual` is containing all of the `expected` elements.

```
expect([1, 2, 3]).to.be.containingAllOf([1]);
expect([1, 2, 3]).to.be.containingAllOf([1, 3]);
expect([1, 2, 3]).to.be.containingAllOf([1, 2, 3]);
```

### containingAnyOf

Asserts that the `actual` is containing any of the `expected` elements.

```
expect([1, 2, 3]).to.be.containingAnyOf([1]);
expect([1, 2, 3]).to.be.containingAnyOf([6, 7, 3, 5]);
expect([1, 2, 3]).to.be.containingAnyOf([1, 2, 3]);
```

### sorted

Asserts that the `actual` array is sorted.

```
expect([1, 2, 3]).to.be.sorted();
expect([1, 2, 4, 3]).not.to.be.sorted();

expect([3, 2, 1]).to.be.sorted((prev, next) => prev < next); // sorting based on the provided function
```
