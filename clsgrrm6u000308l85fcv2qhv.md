---
title: "Day 4 - Any Type and Tuples"
datePublished: Sun Feb 11 2024 00:30:48 GMT+0000 (Coordinated Universal Time)
cuid: clsgrrm6u000308l85fcv2qhv
slug: day-4-any-type-and-tuples
tags: javascript, learning, typescript, software-engineering, learning-journey, tuples

---

Any type in TypeScript allows a variable to have any datatype. We revert to JavaScript if you use any keyword.

```typescript
// A variable of type any can take any value
let x: any;
x = 10;
x = false;
x = "string";
// We can put all these values because any type allows 
// every data type including objects
// However it is better to avoid this datatype because it can create ambiguity 
// or bug in code.
```

"any" type can also be used with arrays.

```typescript
let x: any[] = [25, false, "array"];
```

This way we can allow all datatypes to be used inside the array by using "any" keyword.

### Tuples

Tuples are a fixed-size array in which we can define the type of each of the values.

```typescript
let x: [number, string, number] = [23, "String", 24]
```

These properties are accessible just as array values are:

```typescript
console.log(x[0]) // returns 23 which is a number
```

This can be used maybe when we need to return the coordinates of something or to find an RGB color pattern etc. However, we don't know what each value means.

To allow developers to better understand this, we need to use **named tuples.**

```typescript
let coord: [x: number, y: number] = [55, 43] // x and y are coordinates
```

Now when the user hovers over the coord variable he will be able to see what values tuples must have.

### Sources

These notes are made by watching the Net Ninjas TypeScript Crash course. Check out the first article in this series to find the link for the Net Ninja YouTube channel and the TypeScript Crash course as well.