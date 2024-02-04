---
title: "Day 2 - Arrays & Object Literals"
datePublished: Sun Feb 04 2024 18:30:29 GMT+0000 (Coordinated Universal Time)
cuid: cls7u94va000208jvhjzw7r9b
slug: day-2-arrays-object-literals
tags: javascript, typescript, guide, course, array, objects, notes

---

Arrays and object literals have the same implicit and explicit declarations as primitive datatypes.

We can define an array of strings in TypeScript like this:

```typescript
let names: string[] = ["EL", "Dorado"]
```

Here we defined the type to be string so no other datatype can be put into this array. However we can define an array with no datatype, this allows us to store any type of value in the array:

```typescript
let temp = [22, "anything", true];
```

Also, in the above example there are only three datatypes, so implicitly we cannot push any other data type into this array.

If we want our variable to be an object, and satisfy a specific type, we can do that as follows:

```typescript
let obj: {name: string, age: number, id: number} = {
    name = "wow",
    age = 22,
    id = 23233434
};
```

here is an example of implicit declaration as well:

```typescript
let obj = {
    name = "wow",
    age = 22,
    id = 23233434
}
```

### Sources

These notes are made by watching the Net Ninjas TypeScript Crash course. Checkout the first article in this series to find link for Net Ninja youtube channel and TypeScript Crash course as well.