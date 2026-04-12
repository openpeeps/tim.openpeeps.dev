---
title: "Variables"
description: "Definition and usage of variables in Tim Engine, including how to declare, assign, and use variables in your templates and scripts."
keywords: ["variables", "tim engine", "declaration", "assignment", "usage", "documentation"]
---

## Mutable variables
You can define mutable variables using the `var` keyword. In Tim, variables are case-insensitive, so `name`, `Name`, and `NAME` would refer to the same variable. For example:
```
var name: string          // variable 'name' of type string
$name = "Tim Engine"      // assigning a value to the variable 'name'
```

## Immutable variables
You can define immutable variables using the `const` keyword. A constant requires an initializer and cannot be reassigned after its initial value is set. For example:
```
const version = "1.0.0"   // constant 'version' with a string value
```

## Calling variables
Due to the design of Tim Engine, and how it processes HTML elements, you can call a variable by prefixing it with a `$` symbol. For example, to display the value of the `name` variable, you can use:
```
p: $name
```

## Variable scope
The life cycle of a variable in Tim Engine is determined by its scope. Both, constants and variables are scoped to the block in which they are defined. This means that a variable defined within a block (e.g., a loop or a conditional) will only be accessible within that block and its nested blocks. Once the block is exited, the variable will no longer be accessible. For example:
```
if (true) {
  var message = "Hello, World!"  // 'message' is defined within this block
  p: $message                    // 'message' can be accessed here
}
p: $message                      // not accessible here, will result in an error
```