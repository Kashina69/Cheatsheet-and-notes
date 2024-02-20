# Types

```ts
let firstName: string = "Dylan";
let marks: number = 100;
let isActive: boolean = true;
let marksUndefined: void = undefined;
let v: any = true;
```

# Array

```ts
const names: string[] = [];
const names: readonly string[] = ["Dylan"];
```

# Objects

```ts
const car: { type: string; model: string; year: number } = {
  type: "Toyota",
  model: "Corolla",
  year: 2009,
};
```

# Enums

```ts
enum Direction {
  Up,
  Down,
  Left,
  Right,
}
```

# Function

```ts
function getTime(): number {
  return new Date().getTime();
}

function printHello(): void {
  console.log("Hello!");
}
```

# Interfaces

```ts
interface Person {
  firstName: string;
  lastName: string;
  age: number;
  greet: () => void;
}

const person: Person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  greet: () => {
    console.log(`Hello, I'm ${person.firstName} ${person.lastName}!`);
  },
};
```

# Type Aliases

```ts
type Point = {
  x: number;
  y: number;
};

const point: Point = { x: 10, y: 20 };
```

# Union Types

```ts
type ID = number | string;

const userId: ID = 123;
const postId: ID = "abc";
```

# Type Assertion

```ts
let userInput: unknown;
let userName: string;

userInput = "Hello TypeScript!";
userName = userInput as string;

// OR

userName = <string>userInput;
```

# Generics

```ts
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>("Hello, generics!");
```

# Decorators

```ts
function Log(target: any, propertyName: string) {
  console.log("Property decorator called on:", propertyName);
}

class MyClass {
  @Log
  name: string = "John";
}
```

# Async/Await

```ts
function fetchData(): Promise<string> {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Data fetched!"), 2000);
  });
}

async function getData() {
  const data = await fetchData();
  console.log(data);
}
```

# Modules

```ts
// Exporting module
export interface MyInterface {
  //...
}

export const myVariable: string = "Hello";

// Importing module
import { MyInterface, myVariable } from "./myModule";
```

target: es2016
module: commonjs
strict: true
esModuleInterop: true
skipLibCheck: true
forceConsistentCasingInFileNames: true
