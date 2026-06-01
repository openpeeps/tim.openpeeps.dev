---
title: "System Library"
description: "Documentation for the System Library in Tim Engine, which provides essential functions for interacting with the operating system and performing system-level tasks."
keywords: ["system library", "tim engine", "operating system", "system-level tasks", "documentation"]
---

## Introduction
The `std/system` library in Tim Engine provides the standard functions, built-in operators (like `+`, `-`, `*`) and also comparison operators (like `==`, `!=`, `<`, `>`) that are essential for performing various operations in your templates and scripts. This library is automatically imported into every template, so you can use its functions and operators without needing to import it explicitly.


<div class="alert alert-info rounded-4" role="alert">
  <div class="alert-content">The standard library feature is not available in the Source-to-Source (S2S) mode. <strong>You must stick to the built-in operators and functions provided by the target language when using S2S mode.</strong></div>
</div>


### OS operations
The `std/system` library provides a minimal set of functions for performing various OS operations, such as reading and writing files, sleeping for a specified duration

##### `writeFile`
```
fn writeFile*(path: string, content: string)
```
Write a file with the specified content

##### `readFile`
```
fn readFile*(path: string): string
```
Read a file and return its content as a string

##### `sleep`
```
fn sleep*(duration: int)
```
Sleep for a specified duration (in milliseconds)

### JSON parsing
The `std/system` library also includes functions for parsing JSON data, which can be useful for working with APIs or configuration files.

##### `parseJson`
```
fn parseJson*(content: string): json
```
Parse a JSON string and return it as a JSON object. This function takes a string containing JSON data, parses it, and returns the resulting JSON object.

##### `loadJson`
```
fn loadJson*(path: string): json
```
Load JSON data from a file and return it as a JSON object. This function reads the contents of the specified file, parses it as JSON, and returns the resulting JSON object.

##### `remoteJson`
```
fn remoteJson*(url: string): json
```
Load JSON data from a remote URL and return it as a JSON object. This function performs an HTTP GET request to the specified URL
and parses the response as JSON.