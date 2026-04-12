---
title: "Objects"
description: "Details about objects in Tim Engine, including how to create and manipulate objects in your templates and scripts."
keywords: ["objects", "tim engine", "creation", "manipulation", "documentation"]
---

Objects in Tim Engine are a fundamental data structure that allows you to store
and manipulate data in a structured way. The `std/objects` library provides functions for creating and working with objects in your templates and scripts.


## Creating Objects
You can create an object using the curly braces `{}` syntax, just like in many other programming languages (e.g., JavaScript). For example:
```
var person = {
  name: "Alice",
  age: 30,
  isStudent: false
}
```

In this example, we create an object `person` with three properties: `name`, `age`, and `isStudent`. Each property has a corresponding value


### Accessing Object Properties
You can access the properties of an object using dot notation. For example:
```
p: $person.name       // outputs "Alice"
p: $person.age        // outputs 30
p: $person.isStudent  // outputs false
```

### Modifying Object Properties
When the object is mutable (defined with `var`), you can modify its properties by assigning new values to them. For example:
```
$person.name = "Bob"          // change name to "Bob"
$person.age = 25              // change age to 25
$person.isStudent = true      // change isStudent to true
```

### Nested Objects
Objects can also contain other objects as properties, allowing you to create complex data structures. For example:
```
var company = {
  name: "Tech Corp",
  employees: {
    alice: {
      age: 30,
      position: "Developer"
    },
    bob: {
      age: 25,
      position: "Designer"
    }
  }
}
```

### Nested Arrays
Objects can also contain arrays as properties, which can be useful for storing lists of data. For example:
```
var team = {
  name: "Development Team",
  members: [
    { name: "Alice", role: "Developer" },
    { name: "Bob", role: "Designer" },
    { name: "Charlie", role: "Project Manager" }
  ]
}
```

<div class="alert alert-info rounded-4" role="alert">
  <div class="alert-content">For more infos about arrays, check the <a href="/lib/arrays">Arrays library documentation</a>, where you can find all the functions and utilities for working with arrays in Tim Engine.</div>
</div>


### Iterating Over Object Properties
You can iterate over the properties of an object using a `for` loop. For example:
```
for $key, $value in $person {
  echo $key & ": " & $value
}
```
