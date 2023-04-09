# Generics
---
## Generic Functions
<iframe class="editor" style="height: 600px" data-src="code-examples/generics/generic-functions.html"></iframe>
Note:
The type parameter can be infered based on the argument of the function.

vvv
For arrow functions, there is another syntax that uses angle bracket but it is no longer recommended as it conflicts when being used in JSX.

```typescript
const identity = <T>(input: T) => input;

identity(123); // Type: 123
```
---
## Generic Interfaces
<iframe class="editor" style="height: 600px" data-src="code-examples/generics/generic-interfaces.html"></iframe>
Note:
Show the inference of type parameters.
---
## Generic Types
<iframe class="editor" style="height: 600px" data-src="code-examples/generics/generic-type-alias.html"></iframe>
---
## Default Generic Types
<iframe class="editor" style="height: 600px" data-src="code-examples/generics/default-generic-type.html"></iframe>
---
## Constrained Generic Types
<iframe class="editor" style="height: 600px" data-src="code-examples/generics/constrained-generic-type.html"></iframe>