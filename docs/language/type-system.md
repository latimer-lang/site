---
layout: page
menubar: docs_menu
title: Type System
subtitle: Language Guide
show_sidebar: false
toc: true
---

Latimer is a **statically typed language**, meaning all expressions and statements are checked for type correctness before being interpreted. This helps catch errors early, enforce clarity, and improve runtime reliability.

## Primitive Types

Latimer provides the following built-in types:

- `int`: a 64-bit signed integer
- `double`: a 64-bit double-precision floating-point number (IEEE 754)
- `char`: a single character
- `string`: a sequence of characters
- `bool`: a boolean value (`true` or `false`)

Each of these types has a strict and non-overlapping definition. There is **no implicit type coercion** between these types.

## Type Annotations

Variables and functions must be declared with explicit type annotations.

```cpp
int age = 30;
string name = "Latimer";

int add[](int a, int b) {
    return a + b;
}
```

Latimer currently does not support type inference—types must always be provided to avoid ambiguity and ensure full static checking.

## Type Checking

All assignments and function calls are type-checked at compile time. A value of one type cannot be assigned to a variable of a different type, and a function must be called with arguments matching its signature.

```cpp
int x = 10;
x = "hello";  // Error: cannot assign string to int
```

There are no implicit casts between types. If conversions are to be supported in future versions, they will require explicit functions.

## Type Equality

Types are **nominal** in Latimer, meaning two types are equal if and only if they are explicitly declared to be the same. This applies to both primitive and function types.

## Nullability

Latimer has a built-in `null` value. Any variable may be assigned `null`, regardless of its type. Conceptually, `null` is treated as a universal subtype, meaning it is allowed wherever a value of any type is expected.
