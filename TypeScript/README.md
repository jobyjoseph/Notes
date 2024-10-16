Next: https://www.typescriptlang.org/docs/handbook/2/narrowing.html

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

### bigint
```typescript
const oneHundred: bigint = BigInt(100);

const anotherHundred: bigint = 100n;
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

## Type Alias

Example of a type alias:
```typescript
type Point = {
    x: number;
    y: number;
}
```
Type alias can be reused. It can be exported.

## Interfaces

An interface declaration is another way to name an object type.

### Extending interface

```typescript
interface Animal {
  name: string;
}

interface Bear extends Animal {
  honey: boolean;
}

const bear = getBear();
bear.name;
bear.honey;
```

### Extending type

```typescript
type Animal = {
  name: string;
}

type Bear = Animal & { 
  honey: boolean;
}

const bear = getBear();
bear.name;
bear.honey;
```

### Adding new fields

An interface can add new fields to it.

A type cannot add new fields to it. A type cannot be changed after being created

## Type Assertions

`document.getElementById("main_canvas")` returns a `HTMLElement` type. The return type can be asserted as `HTMLCanvasElement` to use canvas specific properties and methods in code.

```typescript
const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
```

Here is a different syntax for Type Assertion:
```typescript
const myCanvas = <HTMLCanvasElement>document.getElementById("main_canvas");
```

## Literal types

```typescript
let age = 30;
```

Typescript sets the type of `age` as `number` by reading its value.

```typescript
const age = 30
```

Since it is `const`, TypeScript assigns the type as `30` that cannot be changed. `30` is called literal type.

### Setting an enum

```typescript
let align: "left" | "right" | "center";
```

## null and undefined

To mark a variable that does not have `null` or `undefined`, use `!`.

```typescript
function liveDangerously(x?: number | null) {
  // No error
  console.log(x!.toFixed());
}
```

## Narrowing

Narrowing type to `number` before performing a logic:
```typescript
if(typeof age == "number"){
    // do something
}
```

## References
- [The TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
