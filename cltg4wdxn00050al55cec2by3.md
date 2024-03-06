---
title: "Day 5 - Interfaces and Type Aliases"
datePublished: Wed Mar 06 2024 18:30:22 GMT+0000 (Coordinated Universal Time)
cuid: cltg4wdxn00050al55cec2by3
slug: day-5-interfaces-and-type-aliases
tags: javascript, typescript, basics

---

### Interfaces

Interfaces are a way to define a structure that other data structures can adhere to. They can be classes, object literals, etc.

We can simply define an interface as follows:

```typescript
interface Author {
    name: string,
    avatar: string
}

//using an interface
const authorOne: Author = {name: "mario", avatar: "/image/mario.png"}
```

We can also use interfaces as types inside other interfaces

```typescript
interface Post {
    title: string,
    body: string,
    tags: string[],
    created_at: Date,
    author: Author //Here we are using previously created Author interface.
}

const newPost: Post = {
    title: "new Title",
    body: "New Body",
    tags: ["gemini", "trends"],
    created_at: new Date(),
    author: authorOne //Author object created previously
}
```

We can also pass interfaces as argument types in our functions

```typescript
function createPost(post: Post): void {
    console.log(`post says ${post.title}, by ${post.author.name}`);
    return;
}
```

Interfaces can be treated as datatypes in ts. Once we create them all the properties are followed through. You can even create arrays of interfaces to be used when needed.

### Type Aliases

Type aliases are pretty similar to interfaces but there is a difference in how to define them.

```typescript
Type Rgb = [number, number, number]

//it can also be an object
Type user = {
    name: string
    score: number
}
```

From this point on it is the same as the interface. you define functions, pass them in as arguments, etc just like in interfaces.