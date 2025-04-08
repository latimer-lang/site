---
layout: page
menubar: docs_menu
title: Overview
subtitle: Language Guide
show_sidebar: false
toc: true
---

## Overview
Latimer’s syntax is designed to be familiar to users coming from C-style languages like C++ or Java, while removing ambiguity and enforcing clarity through explicit semantics. This page provides a quick overview of the language’s structure and conventions.

## File Extension
Latimer scripts are plain text files with a .lat extension. While the compiler does not enforce any extensions on files, it is a good convention to do so! All top-level statements are executed in order, and there's no required main() entry point.

```cpp
// hello_world.lat
print("Hello World!");
```

## Statements & Semicolons
Statements are terminated by semicolons (;). Omitting them is not allowed. This allows the start and end of statements to be easily-distinguishable and multiple statements to exist in one line.

```cpp
print(1); print(2); // Prints 1 and 2, respectively
```

## Comments
Use `//` for single-line comments. 

```cpp
// This is a single-line comment
```

Use `/* ... */` for multi-line comments.

```cpp
/* 
This is a multi-line comment.
It spans multiple lines.
*/

print/* this is allowed and prints 1 */(1);
```
Multi-line comments can appear anywhere whitespace is allowed, including inline—such as between a function name and its argument list.

All comments are ignored during compilation.

## Whitespaces
Any form of whitespaces (`" "`, `\t`, `\r`) are ignored by the lexer.

```cpp
print        (     1); // This works and prints 1
```

## Naming Conventions
Latimer follows a consistent naming convention based on `snake_case` for most identifiers, including variables, functions, and types.

The exception is **struct names**, which begin with a capital letter and use **CamelCase**. This distinction helps visually separate struct types from regular identifiers when reading code at a glance.
