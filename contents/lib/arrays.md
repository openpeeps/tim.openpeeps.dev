---
title: "Arrays"
description: "Learn about arrays in Tim Engine, including how to create, manipulate, and use arrays in your templates and scripts."
keywords: ["arrays", "tim engine", "creation", "storage", "manipulation", "documentation"]
---

Arrays in Tim Engine represents a collection of values that can be of any type, including other arrays or objects. The `std/arrays` library provides functions for creating and working with arrays in your templates and scripts.

## Creating arrays
You can create an array using the `[]` syntax. For example:
```
var fruits = ["apple", "banana", "cherry"]
```

## Accessing array elements
You can access individual elements of an array using their index, which starts at 0. For example:
```
echo fruits[0]  // Output: apple
echo fruits[1]  // Output: banana
```

## The Library
The `std/arrays` library provides various functions for manipulating arrays, such as adding, removing, and sorting elements. Here is the list of available functions in the `std/arrays` library:

##### `add`
```
function add*(arr: array, item: any): array
```
Add a new item to the end of an array.

##### `insert`
```
function insert*(arr: array, item: any, offset: int): array
```
Insert an item into an array at a specific index.

##### `delete`
```
function delete*(arr: array, index: int): array
```
Delete an item from an array at a specific index.

##### `join`
```
function join*(arr: array, separator: string): string
```
Join the elements of an array into a single string, separated by a specified separator.

##### `contains`
```
function contains*(arr: array, item: any): boolean
```
Check if an array contains a specific item.