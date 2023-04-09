# Working with Types
---
## Unions
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-001.html"></iframe>
Note:
1. Show the example of the union type. Create a variable using the union type and show that you can assign different values.
1. Show the example again of an infered union type.
---

## Unions (Part 2)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-002.html"></iframe>
---

## Unions (Part 3)
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/unions-003.html"></iframe>

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
## Type Guards

---
## Optional Properties
<iframe class="editor" style="height: 600px" data-src="code-examples/working-with-types/optional-properties.html"></iframe>
Note:
1. We use the `?` to make a property optional.
1. Using the `?` and indicating `| undefined` has different behavior. The latter needs to be explicitly assigned to undefined.

