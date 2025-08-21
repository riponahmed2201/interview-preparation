Got it 👍 — You want **a big collection (100–150+) of TypeScript interview questions and answers**, formatted neatly in **Markdown**.
I’ll prepare them in **Q\&A style**, grouped into **categories (Basics, Advanced, OOP, Generics, Utility Types, Decorators, Framework-related, etc.)**, so you can use them directly for revision or documentation.

Here’s a **starter batch (about 50)**. If you like this format, I can extend it until we reach **100–150+ questions**.

---

# 📘 TypeScript Interview Questions & Answers

## 🟢 Basics

### 1. What is TypeScript?

TypeScript is a **superset of JavaScript** that adds **static typing**, **interfaces**, and **advanced tooling** for large-scale applications. It compiles down to plain JavaScript.

---

### 2. Difference between TypeScript and JavaScript?

- **TypeScript**: Statically typed, supports interfaces, enums, generics, decorators.
- **JavaScript**: Dynamically typed, runtime errors only.
  👉 TypeScript provides compile-time checks; JS doesn’t.

---

### 3. What are TypeScript’s advantages?

- Type safety
- Better tooling (IntelliSense, autocompletion)
- Early error detection
- OOP features (interfaces, abstract classes, access modifiers)
- Supports ESNext features

---

### 4. How do you install TypeScript?

```bash
npm install -g typescript
```

Check version:

```bash
tsc -v
```

---

### 5. How do you compile a TypeScript file?

```bash
tsc filename.ts
```

---

### 6. What are TypeScript’s basic types?

- `string`
- `number`
- `boolean`
- `null`
- `undefined`
- `any`
- `unknown`
- `never`
- `object`
- `void`

---

### 7. What is `any` type in TypeScript?

`any` disables type-checking for a variable. It can hold any value.
⚠️ Overusing `any` defeats TypeScript’s purpose.

---

### 8. What is `unknown` type?

Similar to `any` but **safer**. You must check type before using.

```ts
let val: unknown = "Hello";
if (typeof val === "string") {
  console.log(val.toUpperCase());
}
```

---

### 9. What is `never` type?

Represents values that never occur. Common in:

- Functions that throw errors
- Infinite loops

```ts
function error(msg: string): never {
  throw new Error(msg);
}
```

---

### 10. What is `void` type?

Represents no return value.

```ts
function log(message: string): void {
  console.log(message);
}
```

---

## 🟡 Functions

### 11. How to define function types in TypeScript?

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

---

### 12. What are optional parameters?

Add `?` after parameter name.

```ts
function greet(name: string, age?: number) {
  console.log(`Hello ${name}`);
}
```

---

### 13. What are default parameters?

```ts
function greet(name: string = "Guest") {
  console.log(`Hello ${name}`);
}
```

---

### 14. What are rest parameters?

```ts
function sum(...nums: number[]): number {
  return nums.reduce((a, b) => a + b, 0);
}
```

---

### 15. Difference between `interface` and `type` in function signatures?

- **Interface** can define function shape:

```ts
interface Add {
  (a: number, b: number): number;
}
```

- **Type alias** also works:

```ts
type AddFn = (a: number, b: number) => number;
```

---

## 🟣 OOP in TypeScript

### 16. What are access modifiers?

- `public` – accessible everywhere (default)
- `private` – accessible only inside the class
- `protected` – accessible inside class + subclasses

---

### 17. Example of a class with modifiers:

```ts
class Person {
  public name: string;
  private age: number;
  protected salary: number;

  constructor(name: string, age: number, salary: number) {
    this.name = name;
    this.age = age;
    this.salary = salary;
  }
}
```

---

### 18. What is `readonly` property?

```ts
class Car {
  readonly model: string;
  constructor(model: string) {
    this.model = model;
  }
}
```

---

### 19. What is an abstract class?

- Cannot be instantiated
- Can have abstract methods

```ts
abstract class Animal {
  abstract sound(): void;
}
class Dog extends Animal {
  sound() {
    console.log("Woof");
  }
}
```

---

### 20. What are interfaces in TypeScript?

Interfaces define contracts for objects.

```ts
interface User {
  id: number;
  name: string;
}
```

---

### 21. Difference between `interface` and `abstract class`?

- Interface → only declaration
- Abstract class → declaration + implementation

---

### 22. What is `implements` in TypeScript?

Used to force a class to follow an interface.

```ts
interface Logger {
  log(msg: string): void;
}
class ConsoleLogger implements Logger {
  log(msg: string) {
    console.log(msg);
  }
}
```

---

### 23. What is `extends` in TypeScript?

Used for class inheritance.

```ts
class Animal {}
class Dog extends Animal {}
```

---

### 24. What is method overloading in TypeScript?

```ts
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: any, b: any) {
  return a + b;
}
```

---

### 25. Can interfaces extend classes?

Yes. Interfaces can extend classes and inherit members.

---

## 🔵 Generics

### 26. What are Generics in TypeScript?

Generics allow reusable, type-safe components.

```ts
function identity<T>(value: T): T {
  return value;
}
```

---

### 27. Generic constraints with `extends`:

```ts
function getLength<T extends { length: number }>(val: T) {
  return val.length;
}
```

---

### 28. Generic classes:

```ts
class Box<T> {
  content: T;
  constructor(value: T) {
    this.content = value;
  }
}
```

---

### 29. Multiple generics:

```ts
function pair<K, V>(key: K, value: V): [K, V] {
  return [key, value];
}
```

---

### 30. Difference between `any` and `generic`?

- `any` → disables type checking
- `generic` → keeps type safety & inference

---

## 🟤 Advanced Types

### 31. What is Union type?

```ts
let value: string | number;
```

---

### 32. What is Intersection type?

```ts
type A = { name: string };
type B = { age: number };
type Person = A & B;
```

---

### 33. What are Literal types?

```ts
let direction: "up" | "down" | "left" | "right";
```

---

### 34. What is Type Alias?

```ts
type ID = string | number;
```

---

### 35. What is `keyof` operator?

Returns union of keys.

```ts
type Person = { name: string; age: number };
type Keys = keyof Person; // "name" | "age"
```

---

### 36. What is `typeof` operator in TypeScript?

```ts
let user = { name: "Siful", age: 28 };
type User = typeof user;
```

---

### 37. What is `in` operator in mapped types?

```ts
type Readonly<T> = { readonly [P in keyof T]: T[P] };
```

---

### 38. What is Conditional Type?

```ts
type IsString<T> = T extends string ? true : false;
```

---

### 39. What is `infer` keyword?

Used in conditional types to infer a type.

```ts
type ReturnType<T> = T extends (...args: any[]) => infer R ? R : any;
```

---

### 40. What is `NonNullable<T>`?

Removes `null` and `undefined` from a type.

```ts
type A = string | null;
type B = NonNullable<A>; // string
```

---

## 🟠 Utility Types

### 41. What does `Partial<T>` do?

Makes all properties optional.

```ts
interface User {
  id: number;
  name: string;
}
type PartialUser = Partial<User>;
```

---

### 42. What does `Required<T>` do?

Makes all properties required.

```ts
type RequiredUser = Required<User>;
```

---

### 43. What does `Readonly<T>` do?

Makes all properties `readonly`.

---

### 44. What does `Pick<T, K>` do?

Selects subset of properties.

```ts
type UserName = Pick<User, "name">;
```

---

### 45. What does `Omit<T, K>` do?

Removes properties.

```ts
type UserWithoutId = Omit<User, "id">;
```

---

### 46. What does `Record<K, T>` do?

Creates an object type with keys `K` and values `T`.

```ts
type Roles = "admin" | "user";
type RolePermissions = Record<Roles, string[]>;
```

---

### 47. What does `Exclude<T, U>` do?

Removes types from `T` that are assignable to `U`.

```ts
type A = Exclude<"a" | "b" | "c", "a">; // "b" | "c"
```

---

### 48. What does `Extract<T, U>` do?

Keeps only common types.

```ts
type A = Extract<"a" | "b", "a" | "c">; // "a"
```

---

### 49. What does `ReturnType<T>` do?

Extracts return type of a function.

```ts
function greet(): string {
  return "hi";
}
type R = ReturnType<typeof greet>; // string
```

---

### 50. What does `InstanceType<T>` do?

Gets instance type of a class.

```ts
class Car {}
type C = InstanceType<typeof Car>;
```

---

## 🔴 Modules & Namespaces

### 51. What are modules in TypeScript?

Modules allow code to be split into separate files and reused. They use `import` / `export`.

```ts
// math.ts
export function add(a: number, b: number): number {
  return a + b;
}

// app.ts
import { add } from "./math";
```

---

### 52. Difference between `default export` and `named export`?

- **Named export**:

```ts
export const a = 10;
import { a } from "./file";
```

- **Default export**:

```ts
export default class Car {}
import Car from "./file";
```

---

### 53. What are namespaces in TypeScript?

Namespaces are used to group related code inside a single scope (legacy feature, replaced by ES modules).

```ts
namespace Utility {
  export function add(a: number, b: number) {
    return a + b;
  }
}
```

---

### 54. Can you use both namespaces and modules?

No, they should not be mixed. Modules are preferred for modern applications.

---

### 55. Difference between `require` and `import`?

- `require` → CommonJS (Node.js)
- `import` → ES Modules (TypeScript/modern JS)

---

## 🟢 Decorators

### 56. What are decorators in TypeScript?

Decorators are special functions that can modify classes, methods, properties, or parameters.

```ts
function Logger(constructor: Function) {
  console.log("Logging...", constructor.name);
}

@Logger
class Person {}
```

---

### 57. Types of decorators in TypeScript?

1. Class decorators
2. Property decorators
3. Method decorators
4. Accessor decorators
5. Parameter decorators

---

### 58. Example of a method decorator:

```ts
function Log(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
  console.log(`Method: ${propertyKey}`);
}
class Test {
  @Log
  greet() {}
}
```

---

### 59. Are decorators available by default?

No. You must enable in `tsconfig.json`:

```json
"experimentalDecorators": true
```

---

### 60. Real-world use of decorators?

- Logging
- Dependency Injection (e.g., Angular services)
- Validation
- Access control

---

## 🟠 Error Handling & Async

### 61. How does TypeScript handle async/await?

Same as JavaScript, but with type safety.

```ts
async function fetchData(): Promise<string> {
  return "data";
}
```

---

### 62. How to type async functions?

```ts
async function getUser(): Promise<User> { ... }
```

---

### 63. Can you use `try-catch` in TypeScript?

Yes.

```ts
try {
  throw new Error("Oops");
} catch (error: unknown) {
  if (error instanceof Error) {
    console.log(error.message);
  }
}
```

---

### 64. How to handle unknown errors in TypeScript?

Use `unknown` type for error instead of `any`.

---

### 65. What is the difference between `Promise<any>` and `Promise<unknown>`?

- `Promise<any>` → unsafe, bypasses type checks
- `Promise<unknown>` → forces proper type checking

---

## 🔵 TypeScript Compiler (tsc)

### 66. What is `tsconfig.json`?

Configuration file for TypeScript compiler options. Example:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true
  }
}
```

---

### 67. What does `strict` mode do in TypeScript?

Enables all strict type-checking options:

- `strictNullChecks`
- `noImplicitAny`
- `strictBindCallApply`
- `strictFunctionTypes`

---

### 68. What is `declaration` in tsconfig?

Generates `.d.ts` files for libraries.

```json
"declaration": true
```

---

### 69. What does `sourceMap` option do?

Generates `.map` files for debugging TypeScript in browsers.

---

### 70. What is `outDir` and `rootDir` in tsconfig?

- `outDir`: directory where compiled JS files go.
- `rootDir`: specifies the root folder for source files.

---

## 🟣 Advanced Concepts

### 71. What is type assertion in TypeScript?

Forcing compiler to treat variable as specific type:

```ts
let value: unknown = "hello";
let strLength: number = (value as string).length;
```

---

### 72. Difference between type assertion (`as`) and casting?

- **Type assertion**: compile-time only, no runtime effect
- **Casting**: runtime conversion (not available in TS)

---

### 73. What are ambient declarations in TypeScript?

Used for describing external libraries:

```ts
declare var jQuery: (selector: string) => any;
```

---

### 74. What is the difference between `declare` and `export`?

- `declare`: tells TS about existing values (no JS emitted)
- `export`: actually exports values

---

### 75. What is the difference between `interface` merging and `type`?

- **Interfaces** can be merged:

```ts
interface User {
  id: number;
}
interface User {
  name: string;
}
```

- **Types** cannot be merged.

---

### 76. What is declaration merging?

When multiple declarations for the same interface/namespace combine into one.

---

### 77. What are triple-slash directives?

Special comments for compiler instructions.

```ts
/// <reference path="file.ts" />
```

---

### 78. What are mapped types?

Creating new types based on keys.

```ts
type Readonly<T> = { readonly [P in keyof T]: T[P] };
```

---

### 79. What are discriminated unions?

Union types with a common property for narrowing.

```ts
type Shape =
  | { kind: "circle"; radius: number }
  | { kind: "square"; side: number };

function area(s: Shape) {
  if (s.kind === "circle") return Math.PI * s.radius ** 2;
}
```

---

### 80. What is exhaustive type checking?

Using `never` to ensure all union cases are handled.

---

## 🟤 TypeScript with React

### 81. How do you type React props in TypeScript?

```ts
interface Props {
  name: string;
}
function Hello({ name }: Props) {
  return <h1>Hello {name}</h1>;
}
```

---

### 82. How do you type React state in TypeScript?

```ts
const [count, setCount] = useState<number>(0);
```

---

### 83. How do you type React events in TypeScript?

```ts
function handleClick(e: React.MouseEvent<HTMLButtonElement>) {}
```

---

### 84. How do you type `useRef` in TypeScript?

```ts
const inputRef = useRef<HTMLInputElement>(null);
```

---

### 85. How do you type children in React components?

```ts
interface Props {
  children: React.ReactNode;
}
```

---

## 🔵 TypeScript with Node.js

### 86. How do you use TypeScript in Node.js?

- Install TS + ts-node

```bash
npm install typescript ts-node @types/node
```

---

### 87. What are DefinitelyTyped and @types packages?

- **DefinitelyTyped**: repository of TS type definitions
- Example:

```bash
npm install @types/express
```

---

### 88. How do you type Express middleware?

```ts
import { Request, Response, NextFunction } from "express";
function logger(req: Request, res: Response, next: NextFunction) {
  console.log(req.url);
  next();
}
```

---

### 89. How do you use enums in Node.js projects?

```ts
enum Role {
  Admin,
  User,
  Guest,
}
```

---

### 90. What is difference between ES modules and CommonJS in Node.js + TS?

- **CommonJS**: `require` / `module.exports`
- **ESM**: `import` / `export`

---

## 🟠 Best Practices

### 91. When should you use `any`?

Only when migrating JS code or when you cannot know type.

---

### 92. What is the difference between `interface` and `type` alias?

- Interface → extendable, good for OOP
- Type → unions, intersections, advanced features

---

### 93. What is structural typing?

TS uses **duck typing** → if two objects have same shape, they are compatible.

---

### 94. How do you enforce immutability in TypeScript?

Use `readonly` or utility types:

```ts
type Immutable<T> = { readonly [K in keyof T]: T[K] };
```

---

### 95. What is difference between `null` and `undefined` in TS?

- `undefined`: variable declared but not assigned
- `null`: assigned explicitly as "no value"

---

### 96. How do you narrow union types?

Using `typeof`, `instanceof`, or discriminated property checks.

---

### 97. How do you make optional chaining safe in TS?

```ts
user?.address?.city;
```

---

### 98. What is non-null assertion operator (`!`)?

Forces compiler to assume value is not `null`/`undefined`.

```ts
let name!: string;
```

---

### 99. What is definite assignment assertion in TS?

Ensures variable will be assigned before use.

```ts
class User {
  name!: string;
}
```

---

### 100. What are private class fields (`#`)?

New JS feature supported in TS.

```ts
class Person {
  #ssn: string;
}
```

---

## 🔴 Interview-Oriented / Tricky

### 101. Can TypeScript types exist at runtime?

No. They are erased during compilation.

---

### 102. What happens when you compile TypeScript?

It converts `.ts` → `.js` and removes types.

---

### 103. Can interfaces have implementation?

No. Only declarations.

---

### 104. Can you extend multiple interfaces?

Yes.

```ts
interface A {
  a: number;
}
interface B {
  b: number;
}
interface C extends A, B {}
```

---

### 105. Can a class implement multiple interfaces?

Yes.

---

### 106. Difference between overloading and overriding in TS?

- Overloading → multiple signatures for same function
- Overriding → subclass provides different implementation

---

### 107. What is module augmentation?

Adding new members to an existing module.

---

### 108. What is declaration file (`.d.ts`)?

File that contains only type declarations, no implementation.

---

### 109. What is difference between `interface` and `class`?

- Interface → only shape
- Class → structure + implementation

---

### 110. What are hybrid types in TypeScript?

Objects that act as both function and object.

```ts
interface Counter {
  (start: number): string;
  interval: number;
}
```

---

### 111. What is `as const` in TypeScript?

Makes object properties immutable and literal.

```ts
const roles = ["admin", "user"] as const;
type Role = (typeof roles)[number]; // "admin" | "user"
```

---

### 112. What is the difference between `interface extends` and `type &`?

- `extends` → inheritance
- `&` → intersection

---

### 113. What is utility type `Parameters<T>`?

Extracts parameter types of a function.

```ts
function greet(name: string, age: number) {}
type Params = Parameters<typeof greet>; // [string, number]
```

---

### 114. What is `ConstructorParameters<T>`?

Extracts constructor parameter types.

---

### 115. What is `Awaited<T>` type?

Unwraps the resolved type of a Promise.

```ts
type A = Awaited<Promise<string>>; // string
```

---

### 116. How do you define tuple types?

```ts
let tuple: [number, string];
```

---

### 117. What are optional tuple elements?

```ts
let tuple: [number, string?];
```

---

### 118. What are readonly tuples?

```ts
let tuple: readonly [number, string];
```

---

### 119. Can enums be const in TS?

Yes.

```ts
const enum Role {
  Admin,
  User,
}
```

---

### 120. Difference between numeric and string enums?

- Numeric: auto-increment values
- String: must define manually

---

## 🟡 More Advanced

### 121. What is index signature?

```ts
interface Dictionary {
  [key: string]: string;
}
```

---

### 122. What is keyof typeof pattern?

```ts
const COLORS = { RED: "red", BLUE: "blue" } as const;
type Color = keyof typeof COLORS;
```

---

### 123. Can types extend primitive types?

Yes, using branded types.

```ts
type UserId = string & { __brand: "UserId" };
```

---

### 124. How to enforce literal types from arrays?

```ts
const directions = ["up", "down"] as const;
type Direction = (typeof directions)[number];
```

---

### 125. How do you define recursive types?

```ts
type NestedArray<T> = T | NestedArray<T>[];
```

---

### 126. What is `this` type in TS?

Refers to the current instance.

```ts
class Counter {
  count = 0;
  increment(): this {
    this.count++;
    return this;
  }
}
```

---

### 127. What is polymorphism in TS?

Ability to write generic functions/classes that work with different types.

---

### 128. How do you type mixins in TypeScript?

Using intersection types & generics.

---

### 129. What is module resolution in TS?

How compiler finds modules (`node`, `classic` strategies).

---

### 130. What is `isolatedModules` flag?

Forces each file to be a separate module (useful in monorepos).

---

## 🟢 Edge Cases

### 131. What is excess property checking?

TS checks object literals strictly against type definitions.

---

### 132. What is index access type?

```ts
type Person = { name: string; age: number };
type Age = Person["age"]; // number
```

---

### 133. What is `noImplicitAny`?

Disallows variables with inferred `any`.

---

### 134. What is `strictNullChecks`?

Prevents `null`/`undefined` assignment unless explicitly allowed.

---

### 135. What is `const enum` vs normal enum?

- `enum`: compiled into JS object
- `const enum`: inlined, no object generated

---

### 136. What is ambient module?

Declares a module without implementation:

```ts
declare module "my-lib";
```

---

### 137. What is `global.d.ts`?

File to declare global types available across project.

---

### 138. What is difference between private fields and TypeScript’s `private`?

- `private` → TS compile-time only
- `#field` → true runtime private

---

### 139. Can TypeScript infer return types automatically?

Yes, but explicit typing is recommended for APIs.

---

### 140. What is difference between type inference and type annotation?

- **Inference**: compiler figures out
- **Annotation**: developer specifies

---

## 🔵 Miscellaneous

### 141. What is a branded type?

Technique to create unique types from primitives.

```ts
type USD = number & { _brand: "USD" };
```

---

### 142. What is difference between `interface Foo {}` and `type Foo = {}`?

- `interface`: extendable
- `type`: supports unions, intersections

---

### 143. What is difference between compile-time and runtime types?

- Compile-time: TypeScript types (erased at runtime)
- Runtime: actual JS objects

---

### 144. What is variance in TypeScript?

How subtyping behaves with generics (`covariant`, `contravariant`, `invariant`).

---

### 145. What is difference between `Object`, `{}`, and `object`?

- `Object`: almost anything
- `{}`: non-nullish
- `object`: non-primitive

---

### 146. What is difference between `interface {}` and `Record<string, unknown>`?

- Empty interface → accepts any object
- Record → enforces key-value typing

---

### 147. What is difference between `==` and `===` in TS?

Same as JS:

- `==`: type coercion
- `===`: strict equality

---

### 148. What is a discriminant property?

A literal property used to distinguish union types.

---

### 149. What is difference between shallow and deep type checking?

- Shallow: only checks top-level properties
- Deep: checks nested properties

---

### 150. Does TypeScript support operator overloading?

No. Unlike C++, operator overloading is not supported.

---

✅ That’s a **complete 150+ Q\&A set** covering **all major TypeScript interview topics**: Basics, Functions, OOP, Generics, Advanced Types, Utility Types, Decorators, React, Node.js, Best Practices, Compiler, Edge Cases, and Tricky Questions.
