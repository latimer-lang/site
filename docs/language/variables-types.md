---
layout: page
menubar: docs_menu
title: Variables & Types
subtitle: Language Guide
show_sidebar: false
toc: true
---

## Primitive Types

Latimer supports the following primitive types:

- `int`: a 64-bit signed integer
- `double`: a 64-bit double-precision floating-point number (IEEE 754)
- `char`: a single character
- `string`: a sequence of characters
- `bool`: a boolean value (`true` or `false`)

## Other Types

Latimer also includes the `void` type, which is used for functions that do not return a value. In addition, developers can define custom struct types and function types.

```cpp
void return_nothing() {
    return;
}

struct Person {
    string name;
    int age;
};

Person bob;
```

## Variable Declarations

Variables are declared by specifying the type followed by the variable name:

```cpp
int x;
```

You can also initialize a variable at the time of declaration using the `=` operator:

```cpp
int x = 1;
```

By default, declared variables are uninitialized. Attempting to access a variable before assigning a value will result in an error:

```cpp
int x;
print(x); // Error: 'x' is uninitialized
```

## Values

Latimer supports the following kinds of runtime values:

- string literals: text values enclosed in quotes (e.g. `"Hello"`)
- character literals: individual characters enclosed in apostrophes (e.g. `'A'`, `'B'`)
- integer literals: integer numbers (e.g. `123`)
- floating-point literals: decimal numbers represented using `double` precision (e.g. `123.45`)
- `null`: represents the absence of a value
- boolean literals (e.g. `true` or `false`)
- functions: a callable block of code that may take parameters and return a value; functions are first-class values and can be passed around or stored in variables
- struct: : a user-defined composite objects composed of named fields; struct instances are value types and can be passed into functions

{% include notification.html message="
In Latimer, floating-point numbers need digits before and after the dot. For example, `0.123` is valid, but `.123` is not. Likewise, use `123.0` instead of `123`.
" 
icon="fas fa-exclamation-triangle" %}

Latimer does not perform any implicit type casts for variables or return values. For example, the following code results in a type error:

```cpp
bool one() {
    return 1;
}
```

In many C-style languages, this would be valid—where the integer `1` is implicitly cast to a boolean `true`. However, in Latimer, this is a type error: the function is declared to return a `bool`, but instead returns an `int`.

Latimer enforces strict type matching to prevent unintended behavior and improve code clarity.
