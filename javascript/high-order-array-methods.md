# High Order Array Methods

## forEach

## Map

```
// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map

const someNumbersArray = [1, 4, 9, 16];

// Pass a function to map
const afterMap = someNumbersArray.map(x => x * 2);

console.log(afterMap);
// Expected output: Array [2, 8, 18, 32]

// Array with Objects
const kvArray = [
  { key: 1, value: 10 },
  { key: 2, value: 20 },
  { key: 3, value: 30 },
];

const newArrayWithFormattedObjects = kvArray.map(({ key, value }) => ({ [key]: value }));

console.log(newArrayWithFormattedObjects); // [{ 1: 10 }, { 2: 20 }, { 3: 30 }]
console.log(kvArray);
// [
//   { key: 1, value: 10 },
//   { key: 2, value: 20 },
//   { key: 3, value: 30 }
// ]

```

## Filter

## Reduce
