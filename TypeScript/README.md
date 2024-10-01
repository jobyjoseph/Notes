# TypeScript v5.6

TypeScript is a tool that runs before your JS code runs (static) and ensures that the types of the program are correct (typechecked).

## TypeScript compiler(`tsc`)
TypeScript compiler(`tsc`) is installed from `typescript` node package.

## Emitting with Errors
`tsc` compiler by default compiles and generate a javascript file even there is a type error. To **prevent** generating output js file if an error exist, add `--noEmitOnError` flag.
```shell
tsc --noEmitOnError hello.ts
```

## Implicit types
TypeScript can even just infer (or “figure out”) the types for us even if we omit them. 
```typescript
let name = "Joby"; // TypeScript infers the type of `name` as string
```

## Target ES version
Source code:
```typescript
// hello.ts
const sum = (a, b) => a + b;
```
`tsc hello.ts` gives:
```javascript
// hello.js
var sum = function (a, b) { return a + b; };
```
`tsc --target es2015 hello.ts` gives:
```javascript
// hello.js
const sum = (a, b) => a + b;
```

## Types

### string
```typescript
let product: string = "car";
```

### number
```typescript
let age: number = 23;
```

### boolean
```typescript
let isDev: boolean = false;
```

### Arrays
A number array:
```typescript
let numArray: number[] = [1, 2, 3]; // one way
let numArray: Array<number> = [1, 2, 3] // another way
```

### any
`any` type is used when we do not know the type.

`noImplicitAny` flag is used to throw error for any implicit any type.
```typescript
// hello.ts
function sum(a, b) {
    return a + b;
}
```
`tsc hello.ts` works fine.

`tsc --noImplicitAny hello.ts` throws error.
```shell
hello.ts:1:14 - error TS7006: Parameter 'a' implicitly has an 'any' type.

1 function sum(a, b) {
               ~

hello.ts:1:17 - error TS7006: Parameter 'b' implicitly has an 'any' type.

1 function sum(a, b) {
                  ~
```

### functions
TypeScript allows you to specify the types of both the input and output values of functions.
```typescript
function sum(a: number, b: number): number {
  return a + b;
}
```

If the function returns a promise, the return type is set using `Promise` and the type of data the promise resolves.
```typescript
async function myPromise(): Promise<string> {
    return 'my promise'
}
```

### object
An object type with `name` and `age` properties:
```typescript
const obj: { name: string; age: number } = {
  name: "John",
  age: 30,
};
```

Making `age` optional:
```typescript
const obj: { name: string; age?: number } = {
  name: "John",
};
```

Always check if a value is present for optional properties.

## Union Types

A union type is a type formed from two or more other types.

`id` can be a string or number:
```typescript
const id: number | string = 5;
```
`number` and `string` are called union members.

When using union, ensure the type before using its methods.

## References
- [The TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
