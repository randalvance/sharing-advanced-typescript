# Utility Types
---
## `Partial<Type>`
Constructs a type with all properties of `Type` set to optional.
Note:
I frequently use this to when creating a new object and I only want to specify some of the values of that object, and the rest will get default values.
---
<!-- .slide: data-background-iframe="https://www.typescriptlang.org/play?#code/JYOwLgpgTgZghgYwgAgArQM4HsTIN4BQyyMwUGYAcnALYQBcyFUoA5gNxHIA2cF1dRszadiAEziQA8jABCZMAAtGAEUkRRyOGLFQIGDELAsQHAgF8CBGAFcQCMMBzIEe9enI4AFDChYajB7YIACU+Fx6YDZQuITExKTkVLQMJH40AHSJ-CkANFzEvDmCaf4ZRcl0+fHIEtJyCsqlmXUQMvJQStXx2rr6hs0ZvXoG3ZaWQA" -->
vvv
```typescript
interface Person {
  firstName: string;
  lastName: string;
  dateOfBirth: Date;
  address: string;
}

function createPerson(overrides: Partial<Person>) {
  return {
    firstName: "John",
    lastName: "Commonfolk",
    dateOfBirth: new Date(),
    address: "Outerspace",
    ...overrides,
  }
}

const person = createPerson({
  firstName: "Randal",
});

console.log(person);
```