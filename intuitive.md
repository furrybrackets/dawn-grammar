# Dawn Intuitive Grammar

This is an example-based grammar for the Dawn programming language. It provides both a syntactic explanation as well as the evaluation of said statement.

## Variable Declarations

> `VariableDeclaration`
>
> Used to declare variables.
>
> Format: `let|const <VarName>(: <TypeDeclaration>)(= <Expression>);`

### Examples:

```ts
let x; // initialize mutable variable, type will be determined on "true initialization".
const y; // create immutable variable.


// initialize variable with type annotation.
let z: i32;
const λ: string;

// initialize variable with value.
let θ: string = "100";
const π: f128 = 3.141592653589793238462643383;
```

## Module Imports

> `ImportDeclaration`
>
> Used to import external modules.
>
> Format: `import <ImportQualifier> from <ImportName> (as <ImportAlias>);`

### Examples:

```ts
import * from "std::io"; // imports everything from std::io.

import { Polynomial } from "std::math"; // imports only the Polynomial class from std::math;
/* 
// Usage of Polynomial import
let f: Polynomial = new Polynomial("3x^2+2x+1");
*/

import { ServerReference } from "std::web" as "Server"; // as keyword to change the reference.
/* 
// Usage of ServerReference as Server
const app: Server = new Server({
  port: 3000
})
*/
```

## Logical Branching (`if`, `else`, `else if`, `switch`)

### `if`, `else`, `else if`

> `IfStatement`
>
> Used for branching in code.
>
> Format `if (<Clause>) { <BodyExpression> } ([else|else if] { <BodyExpression> })...`

#### Examples:

```ts
import { AveragedSet } from "std::math";
import { print } from "std::io";

const Numbers: AveragedSet = [1,2,3,4,5,6,7,8,9,10]; // avg: 10*11/20=5.5

const avg: f32 = Numbers.avg(); // get average

if (avg > 5.5) {
  print("Average is: {f32}", avg);
} else if (avg > 2.2 && avg < 5.5) {
  print("2.2 < avg < 5.5: {bool}", avg > 2.2 && avg < 5.5);
} else {
  print("{f32}", avg);
};
```
