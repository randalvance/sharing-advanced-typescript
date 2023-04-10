# Utility Types
---
## `Partial<T>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/partial.html"></iframe>
Note:
The Partial utility type maps every property of another type to be optional.

I commonly when creating some object with defeault values and then you can pass overrides to those default value.
---
## `Required<T>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/required.html"></iframe>
---
## `NonNullable<T>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/non-nullable.html"></iframe>
---
## `Readonly<T>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/readonly.html"></iframe>
Note:
If this is done to an array, typescript will also disallow modifying the elements of the array and adding or removing items.
---
## `Record<K, T>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/record.html"></iframe>
---
## `Omit<T, K>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/omit.html"></iframe>
---
## `Pick<T, K>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/pick.html"></iframe>
---
## `Extract<T, U>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/extract.html"></iframe>
Note:
Constructs a type by extracting from `T` all union members that are assignable to `U`.
---
## `Exclude<U, E>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/exclude.html"></iframe>
Note:
Constructs a type by excluding from `U` all union members that are assignable to `E`.
---
## More Union Types
1. [Union Types](https://www.typescriptlang.org/docs/handbook/utility-types.html) - List of all built-in utility types.
1. [ts-essentials](https://github.com/ts-essentials/ts-essentials) - A library of essential TypeScript types and utilities.