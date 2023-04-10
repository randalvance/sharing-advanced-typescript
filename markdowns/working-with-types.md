# Working with Types
---
## Unions
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-001.html"></iframe>
Note:
1. Show the example of the union type. Create a variable using the union type and show that you can assign different values.
1. Show the example again of an infered union type.
vvv

## Unions (Part 2)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-002.html"></iframe>

Note:
Doing a union of objects.
vvv

## Unions (Part 3)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-003.html"></iframe>

Note:
A union where both types have a property but different type.

---
## Unions (Arrays)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-arrays.html"></iframe>

---
## Optional Properties
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/optional-properties.html"></iframe>
Note:
1. We use the `?` to make a property optional.
1. Using the `?` and indicating `| undefined` has different behavior. The latter needs to be explicitly assigned to undefined.

---
## Intersections
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/intersections.html"></iframe>
Note:
Show what happens when you intersect string and number. It will have a type of `never`.

---
## Strict Null Checks
```json
{
  "compilerOptions": {
    "strictNullChecks": true
  }
}
```

#### With Strict Null Checks
<iframe class="editor" style="height: 150px" data-src="code-examples/working-with-types/strictNullChecks.html"></iframe>

#### Without Strict Null Checks
<iframe class="editor" style="height: 150px" data-src="code-examples/working-with-types/strictNullChecksOff.html"></iframe>
Note:
With the `tsconfig` compiler option called `strictNullCheck`, you can ask Typescript to be strict about assigning nulls or undefined on primitive types.

---
### Prefer `strictNullChecks`
<iframe class="editor" style="height: 600px" data-src="https://www.typescriptlang.org/play?strictNullChecks=false#code/GYVwdgxgLglg9mABAEzgZTgWwKZQBYxgDmAFAM5bZpQBOhRAXImbfQJSIDeAUIohAgoAbbADohcUhRzU6xcdmL42Abm4Bfbt1QYc+eiTAghQ1UA"></iframe>
Note:
1. Show that with `strictNullChecks` off, a null exception will occur during runtime.
1. Modify the tsconfig setting to enable `strictNullChecks`. Now there will be an error immediately reported.
1. Update the signature to allow passing null or undefined.
1. There will be an error that the parameter is possibly undefined.

---
## Literal Types
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/literal-types-001.html"></iframe>
Note:
Literal types uses the actual literals as the types themselves. You can assign only that literal to the variable.

1. Add `| no` to the annotation.
1. Show that the auto-complete suggests both yes and no.
1. Show that it is case sensitive.
1. A good way to do enumeration. Although there is a separate enum feature in typescript.
---
## Type Narrowing (with `typeof`)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/type-narrowing-001.html"></iframe>

Note:
Typescript can narrow down the type of a given variable based on it's scope.

The `typeof` operator returns the type of a given object as a string.

The first if block detects that the variable is a string while the else block narrows it down to just an int cause there's no more block after it.

What happens if you put an extra else block, the type will be `never`.

---
## Type Narrowing (with conditions)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/type-narrowing-001.html"></iframe>

---
## Discriminated Unions
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/discriminated-unions.html"></iframe>

Note:
1. Discriminated union is a type of union where each member has a common property that can be used to narrow down the type (called a discriminant).
1. Demonstrate using `switch` statement.

---
## Type Predicates
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/type-predicates.html"></iframe>
vvv
```typescript
function isNumberOrString(value: string | number) : value is string {
    return typeof value === 'string';
}

function doSomething(value: string | number) {
    if (isNumberOrString(value)) {
        console.log(value);
    } else {
        console.log(value);
    }
}

```
Note:
You can define special functions with custom logic to narrow down the type of a variable.

These are called type predicates.

The following example uses calls a function that accepts a parameter of type `string | number` and returns a boolean.
Because it simply returns a boolean, typescript has no idea what the type of the variable is after the function returned.

---
## Type Assertions
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/type-assertions.html"></iframe>
Note:
There are cases where you want to convert another type to a specific type. You can use the `as` keyword to do so.
For example, the return value of `JSON.parse` is of type `any`. We can convert it to an interface so that we can have type-safety.

You can only convert to another type if it is a subtype of the original type. With the exception of any and unknown which are considered top-level types. You can convert those to any type.

Show an example of converting a string to a number. You can bypass that by adding `as unknown` or `as any`.

---
## The `any` Type
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/any-type.html"></iframe>

Note:
It is considered a top-level type. Any value can be assigned to it.

It is the default type if you did not specified a type annotation and it cannot be infered from the value assigned to it.

It will essentially turn-off typescript's type checking.

---
## The `unknown` Type
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/any-type.html"></iframe>

Note:
If you don't know a type, you can use the `unknown` type. It is also a top-level type.

You can also assign any value to `unknown`. But it is safer because you cannot access any member without first explicitly asserting the type.

Another way you can access a member of an `unknown` if you use `typeof` or `instanceof`.

