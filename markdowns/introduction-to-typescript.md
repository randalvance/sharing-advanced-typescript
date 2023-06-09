# Typescript Refresher
---
## What is Typescript?
1. Typescript is a programming language developed by Microsoft. <!-- .element: class="fragment" data-fragment-index="0" -->
1. It is composed of: <!-- .element: class="fragment" data-fragment-index="1" -->
    1. Programming Language <!-- .element: class="fragment" data-fragment-index="2" -->
    1. Type Checker <!-- .element: class="fragment" data-fragment-index="3" -->
    1. Compiler <!-- .element: class="fragment" data-fragment-index="4" -->
    1. Language Service <!-- .element: class="fragment" data-fragment-index="5" -->
Note:
1. Programming Language - It is the language itself.
1. Type Checker - A tool that checks the types of your code and reports errors.
1. Compiler - A tool that compiles your code into JavaScript.
1. Language Service - A background service that provides language features such as autocomplete, go to definition, find all references, etc. It is used by editors and IDEs to provide these features.
---
<!-- .slide: data-background="white" -->
<iframe class="editor" data-src="code-examples/intro/intro.html"></iframe>
Note:
Show that nobody knows what the parameter of the function's members are and therefore, will be prone to runtime errors.

---
## Advantages of Typescript
1. Typescript is a superset of JavaScript. <!-- .element: class="fragment" data-fragment-index="0" -->
1. Type checking at compile time. <!-- .element: class="fragment" data-fragment-index="1" -->
1. IDE support <!-- .element: class="fragment" data-fragment-index="2" -->
1. Improved code maintainability. <!-- .element: class="fragment" data-fragment-index="3" -->
Note:
1. Typescript is a superset of JavaScript. This means that all valid JavaScript code is also valid Typescript code. In the previous slide, we started with just a valid Javascript and we converted it to Typescript by adding types to the parameters of the function's members.
1. Type checking at compile time. This means that the compiler will check the types of your code and report errors even before running your code.
1. IDE support. Your IDE can provide code auto-completion, error highlighting, find all references, and refactoring tools. This allows to find compile time errors much earlier. It also allows to refactor your code with confidence and to navigate your codebase much easier.
1. Improve code maintainability. Because it is easier to find references to a certain symbol, it can check if it is still being used and if not, you can safetely remove it. Any refactorings like renaming variables and functions will cause compile time errors if you missed a reference.
---
## Disadvantages of Typescript
1. More setup needed. <!-- .element: class="fragment" data-fragment-index="0" -->
1. An extra compilation step. <!-- .element: class="fragment" data-fragment-index="1" -->
1. Not practical to use for simple projects. <!-- .element: class="fragment" data-fragment-index="2" -->
Note:
1. More setup needed. You need to install the Typescript compiler and configure your IDE to use it. Although it has been simplified through the years.
---
## Setup Typescript
1. Install Node JS
1. Install Typescript
   ```bash
   npm install -g typescript
   ```
1. Initialize typescript inside a new directory, or an existing javascript project.
    ```bash
    tsc --init
    ```
1. Create an `src` directory and place your typescript code over there.
1. Run this to compile your typescript code into javascript.
    ```bash
    tsc --watch
    ```
---
## tsconfig
1. When you initialize a typescript project, a `tsconfig.json` file is created.
1. This file contains the configuration for the typescript compiler, and which files to include for type checking.
1. You can find all possible configs in this [link](https://www.typescriptlang.org/tsconfig).
    ```json
    {
      "include": ["src/**/*", "tests/**/*"],
      "compilerOptions": {
        "noImplicitAny": true,
        "strictNullChecks": true
      }
    }
    ```
---
## Basic Types
1. `number`
1. `string`
1. `boolean`
1. `null`
1. `undefined`
1. `bigint`
1. `symbol`
1. `any`
1. `unknown`
1. `never`
---
## Type Inference
Typescript can infer the type of a variable from its value.
<iframe class="editor" style="height: 300px" data-src="code-examples/intro/type-inference.html"></iframe>

---
## Object Types
<iframe class="editor" style="height: 600px" data-src="code-examples/intro/object-types.html"></iframe>
Note:
Show the inferred type of the object.

Show that only members of the object are in autocomplete.

Show that accessing members not in the object causes an error.

Create a type for the object named `User` and annotate the user object.
1. Show it first using a type.
1. Show it using an interface.

---
## Array Types
<iframe class="editor" style="height: 600px" data-src="code-examples/intro/array-types.html"></iframe>

Note:
Show type inference.

Show annotating the array type.
---
## Function Types
<iframe class="editor" style="height: 600px" data-src="code-examples/intro/function-types.html"></iframe>
Note:
Show type inference.

Show annotating the function type.

Show adding the function type in a `type`.
vvv
```typescript
type StringTransformer = (input: string) => string;

const transformString: StringTransformer => string = (input) => {
  return input + ' transformed';
};
```

---
## Tuple Types
<iframe class="editor" style="height: 600px" data-src="code-examples/intro/tuple-types.html"></iframe>
Note:
Tuples are fixed type array and each element can have a different type.

They are commonly used as return values of a function so you can destructure it. Example is the return value of `useState` hook in react.

---
## Type vs Interface
1. Use an interface when:
    1. Define a new type or shape of an object.
    1. Inherit from another interface.
    1. Have a class implement an interface.
    1. Declaration merging
1. Use a type alias when:
    1. Define a union type, tuple type, intersection type, function type
    1. When you derived a type from another type (type mapping)
Note:
Declaration merging will be demonstrated later.
