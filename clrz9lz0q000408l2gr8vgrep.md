---
title: "Day 0 - What is TS and Setup"
datePublished: Mon Jan 29 2024 18:30:26 GMT+0000 (Coordinated Universal Time)
cuid: clrz9lz0q000408l2gr8vgrep
slug: day-0-what-is-ts-and-setup
tags: tutorial, nodejs, npm, learning, typescript, setup

---

## What is TypeScript?

TypeScript is a programming language built on top of JavaScript to give it extra features. Primarily to add types to the values.

The key difference between JS and TS is JS allows the variable to be changed once it is given a type whereas in TS once a variable is defined with datatype it cannot be changed in the future. This immutability provides many benefit over JS

### Benefits of typescript

* **Detect errors:** In TypeScript we define the types of each value. This allows our editor to detect errors before execution.
    
* **Better autocompletion and code hints:** Since each value type is predefined. Now Editors can autosuggest functions related to those types. Whereas in JavaScript we do not define types for variables.
    
* **Custom Types:** We can also define Custom types that can be further used in functions. These types can be made using interfaces, classes, and type aliases.
    

### Setup

We can perform the setup by running the following command in the terminal.

```powershell
npm install -g typescript
```

NOTE: This is for global installation. To get further details visit TypeScript Download Page [here.](https://www.typescriptlang.org/download)

If you don't have npm visit npm docs [here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) for node.js and npm installation.

### Sources

These notes are made by watching the Net Ninjas TypeScript Crash course. Checkout the first article in this series to find link for Net Ninja youtube channel and TypeScript Crash course as well.