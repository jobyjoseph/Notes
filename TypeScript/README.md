# TypeScript v5.6

TypeScript is a tool that runs before your JS code runs (static) and ensures that the types of the program are correct (typechecked).

## TypeScript compiler(`tsc`)
TypeScript compiler(`tsc`) is installed from `typescript` node package.

`tsc` compiler by default compiles and generate a javascript file even there is a type error. To **prevent** generating output js file if an error exist, add `--noEmitOnError` flag.
```shell
tsc --noEmitOnError hello.ts
```

TypeScript can even just infer (or “figure out”) the types for us even if we omit them. 
```
let name = "Joby"; // TypeScript infers the type of `name` as string
```




## References
- [The TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
