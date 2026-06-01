---
title: "User Scripts"
description: "Inject custom scripts into the Tim scripting environment"
keywords: ["custom library", "ffi", "foreign function interface", "library creation"]
---

## Overview
The User Scripts feature allows you to inject custom Nim code into the Tim scripting environment, enabling you

## User scripts
Expose custom Nim functions to the scripting environment, allowing you to create your own libraries and utilities that can be used within your application's scripting system.

This is particularly useful for creating reusable code snippets, utility functions, or even integrating third-party libraries into your application. For example:

```nim
# initialize Tim engine like you normally would
var timEngine*: TimEngine = newTim(...)

# Now, you can add custom functions to the scripting environment
timEngine.userScript.addProc("hello", @[paramDef("name", ttyString)], ttyStrings,
  proc (args: StackView, argc: int): value.Value =
    return initValue("Hello, " & args[0].stringVal[] & "!")
)
```

Calling this from a `.timl` script would look like this:

```
echo hello("Tim") // Output: Hello, Tim!
```
