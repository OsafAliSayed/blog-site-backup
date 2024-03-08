---
title: "Day 6 - Union Types and Union Guards"
datePublished: Fri Mar 08 2024 18:30:47 GMT+0000 (Coordinated Universal Time)
cuid: cltizsmoa000409l39pzc5kvf
slug: day-6-union-types-and-union-guards
tags: javascript, web-development, typescript, basics

---

Sometimes we want to allow more than one type in a variable, This can be easily done using Union Types. We simply add "|" symbol between the types that we define and viola!

```typescript
var x: number | string;
x = 2;
x = "1"; // both types are valid now because of union types

// we can also combine this with Type aliases to make the code little bit 
// more pretty
Type n = number | string;
let anothernum: n;
anothernum = 1;
anothernum = "whatever";
```

However, there is one specific pitfall that we might face while using union types, which occurs while creating a function

```typescript
function swapIdTypes(id: n): n {
    // Here we can only use props and methods common to both number and String
    //parseInt(id); // Therefore this parseint is not allowed 
}
```

### Type Guards

To avoid this issue we check the type of variable inside the function using Type Guards as follows.

```typescript
function swapIdTypes(id: n): n {
    if (typeof id === 'string') {
        // You can now use string methods here
        return parseInt(id);
    }
    else {
        // You can use number methods and props here 
        return id.toString();
    }
}
```

### Conclusion

This completes our TypeScript course. All thanks to NetNinja I finally have a good grasp of TypeScript. Make sure you watch his course on YouTube as it is way more interactive and easy to understand than these notes.

However, you can refer to these notes in case you want to revise a concept.