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
## `Readonly<T>`
<iframe class="editor" style="height: 600px" data-src="code-examples/utility-types/readonly.html"></iframe>
Note:
If this is done to an array, typescript will also disallow modifying the elements of the array and adding or removing items.