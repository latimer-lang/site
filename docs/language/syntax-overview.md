---
layout: page
menubar: docs_menu
title: Syntax Overview
subtitle: Language Guide
show_sidebar: false
toc: true
---

## Overview
Latimer’s syntax is designed to be familiar to users coming from C-style languages like C++ or Java, while removing ambiguity and enforcing clarity through explicit semantics. This page provides a quick overview of the language’s structure and conventions.

## File Structure
Latimer scripts are plain text files with a .lat extension. While the compiler does not enforce any extensions on files, it is a good convention to do so! All top-level statements are executed in order, and there's no required main() entry point.

```cpp
// hello_world.lat
print "Hello World!";
```

## Statements & Semicolons
Statements are terminated by semicolons (;). Omitting them is not allowed. This allows the start and end of statements to be easily-distinguishable and multiple statements to exist in one line.

```cpp
print 1; print 2; // Prints 1 and 2, respectively
```

## Comments
Use // for single-line comments comments. 

```cpp
// This is a single-line comment
```

Multi-line comments are to come in the future and will have a /* ... */ syntax.

```cpp
/* 
This is a multi-line comment
*/

print /* this will be allowed and will print 1 */ 1;
```

## Whitespaces
Any form of whitespaces (`" "`, `\t`, `\r`) are ignored by the lexer.

```cpp
print              1; // This works and prints 1
```

## Naming Conventions
Latimer follows a consistent naming convention based on `snake_case` for most identifiers, including variables, functions, and types.

The exception is **struct names**, which begin with a capital letter and use **CamelCase**. This distinction helps visually separate struct types from regular identifiers when reading code at a glance.
