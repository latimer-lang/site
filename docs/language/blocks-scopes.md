---
layout: page
menubar: docs_menu
title: Blocks & Scopes
subtitle: Language Guide
show_sidebar: false
toc: true
---

Latimer uses **lexical (static) scoping** to define the visibility of variables. A **block** is any section of code enclosed in `{}` braces, and each block introduces a new scope.

## Block Scope

Variables declared inside a block are only accessible within that block.

```cpp
{
    int x = 42;
    print(x);  // OK
}
print(x);  // Error: x is not defined in this scope
```

Each set of braces creates a new scope. This includes function bodies, `if` statements, loops, and any standalone `{}` block.

## Variable Shadowing

Latimer does not allow variable shadowing. A variable may not be re-declared in the same or an inner scope if it shares the same name as a variable already in scope.

```cpp
int x = 1;
{
    int x = 2;  // Error: x is already declared in an outer scope
}
```

## Global Scope

Latimer does not have a special global environment. In many programming languages, global variables are accessible from anywhere in the program. In Latimer, this is not the case—all scopes behave the same, including the top-level scope.
