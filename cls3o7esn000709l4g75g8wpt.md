---
title: "Day 1 - Type Basics and Better workflow with tsconfig"
datePublished: Thu Feb 01 2024 20:30:06 GMT+0000 (Coordinated Universal Time)
cuid: cls3o7esn000709l4g75g8wpt
slug: day-1-type-basics-and-better-workflow-with-tsconfig
tags: javascript, json, nodejs, npm, typescript, powershell, setup, tsc, tsconfig

---

When working with TypeScript we would want to define the type of each variable. This can be done explicitly or implicitly.

To explicitly define a variable type we can write the following code

```typescript
// We can clearly see we define type after the colon
let name: string = "Gottcha";
```

But this can also be done implicitly by simply giving the variable a value. TypeScript will automatically take the value as the initial value's type

```typescript
let email = "osafalisayed@gmail.com"
```

Here TypeScript automatically assumes the type as a string.

Here is a list of data types available in TypeScript

| Keyword | Description |
| --- | --- |
| number | It is used to represent both Integer as well as Floating-Point numbers |
| boolean | Represents true and false |
| string | It is used to represent a sequence of characters |
| void | Generally used on function return-types |
| null | It is used when an object does not have any value |
| undefined | Denotes value given to uninitialized variable |
| any | If a variable is declared with **any** data type then any type of value can be assigned to that variable |

### Executing .ts file

To execute .ts file we have to first compile it to js use tsc(TypeScript Compiler) compiler and then we can run that .js file.

```powershell
tsc index.ts
node index.js
```

this command compiles index.ts file and makes index.js file. then we can further run the file by using node.

to automate this process we can add tsconfig.json file which will allow us to continously monitor these files.

To create this tsconfig.json file we run the following command in terminal:

```powershell
tsc --init
```

this initializes tsconfig.json file in current directory. Now we give it path for input and output of the files. to do this we uncomment the rootDir variable and outDir variables. These variable define input and out directories and can be set as shown:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706351595444/df89e219-033d-49a2-b615-f274cb674b9c.png align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706351583795/c3df9bc7-08d0-4e77-98e8-d063e1a1ced4.png align="left")

Now we can simply run tsc to compile the files inside src and get our output in dist folder.

We can go one step further by automating this and keeping regular watch on our code. This will automatically compile js for this we run the following:

```powershell
tsc --watch
```

this keeps watch on our code and automatically updates it when there is a change in file.

But we still have to run "node dist/index.js" to see the output of the file. To take care of this we can run the following command to watch index.js file and easily detect changes in index.js file:

```typescript
node --watch dist/index.js
```

Notice, we have to run both the commands in two different terminal instances to keep watch on our code and run it as well.

### Sources

These notes are made by watching the Net Ninjas TypeScript Crash course. Checkout the first article in this series to find link for Net Ninja youtube channel and TypeScript Crash course as well.