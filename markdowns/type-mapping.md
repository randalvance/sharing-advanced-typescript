# Type Mapping
Note:
We will discuss Typescript's capabilities to extract types from other types, or transform it into another type.
---
## The `keyof` Operator
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/keyof-operator.html"></iframe>
---
## The `typeof` Operator
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/typeof-operator.html"></iframe>
---
## Indexed Access Types
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/indexed-access-types.html"></iframe>
Note:
You can also map from an object, but you need to combine `typeof`.
---
## Indexed Access Types (Arrays)
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/indexed-access-types-arrays.html"></iframe>
Note:
It doesn't matter how big the index is.

If an array is mixed, it will be a union of all elements, regardless of the index you pass.

For tuples, index will be respected and you will get the type of the element at that index.
---
## Mapped Types
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/mapped-types.html"></iframe>
Note:
Here's a contrived example where we want to map every property of a type in a new type and change the type of each of those properties from `string` to `number`.
vvv
## Mapped Types (Making Props Optional)
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/mapped-types-optional.html"></iframe>
Note:
There is an equivalent utility type called `Partial` that does the same thing.
vvv
## Mapped Types (Making Props Required)
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/mapped-types-required.html"></iframe>
Note:
There is an equivalent utility type called `Required` that does the same thing.
vvv
## Mapped Types (With Generics)
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/mapped-types-generics.html"></iframe>
---
## Conditional Types
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/conditional-types-001.html"></iframe>
Note:
This example shows a basic usage using the `infer` keyword.
vvv
## Conditional Types
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/conditional-types-002.html"></iframe>
Note:
Here's another more practical example.
---
## Template Literal Keys
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/template-literal-keys.html"></iframe>
Note:
We can use the template literal keys to map to a new prop name.

It works on union of string keys, which is why we need to use `keyof`.

Use the `Capitalize` utility type to capitalize the first letter of the prop name.
vvv
## Template Literal Keys
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/template-literal-keys-renaming.html"></iframe>
Note:
We can use the `as` keyword to rename each property.
---
## Template Literal Types
<iframe class="editor" style="height: 600px" data-src="code-examples/type-mappings/template-literal-types.html"></iframe>
---
## Inferred Types
Extract Array Item Type
<iframe class="editor" style="height: 500px" data-src="code-examples/type-mappings/inferred-types-array-item.html"></iframe>
vvv
## Inferred Types
Get Parameter and Return Type of Function
<iframe class="editor" style="height: 500px" data-src="code-examples/type-mappings/inferred-types-function-return.html"></iframe>
Note:
There are also built-in utility types called `ReturnType` and `Parameters` that do the same thing.