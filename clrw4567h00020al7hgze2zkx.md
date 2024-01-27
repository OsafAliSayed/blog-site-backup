---
title: "Day 3 - Functions"
datePublished: Sat Jan 27 2024 13:34:06 GMT+0000 (Coordinated Universal Time)
cuid: clrw4567h00020al7hgze2zkx
slug: day-3-functions
tags: functions, software-development, javascript, typescript, basics

---

In TypeScript functions cannot be defined unless the variables are given a datatype.

```typescript
function helloWorld(a: string, b: string) {
    return true;
}
```

notice here function can return any datatype unless defined explicitly.

This can be done as follows:

```typescript
function helloWorld(a: string, b: string) : string {
    return a + b;
}
```

if we want our function to not return anything this can be done explicitly as follows:

```typescript
function helloWorld(a: string, b: string) : void {
    return true;
}
```

We can define an arrow function similar to how we defined a normal function.

```typescript
const helloWorld = (a: string, b: string): boolean => {
    return true;
}
```

### Sources

These notes are made by watching the Net Ninjas TypeScript Crash course. Checkout the first article in this series to find link for Net Ninja youtube channel and TypeScript Crash course as well.