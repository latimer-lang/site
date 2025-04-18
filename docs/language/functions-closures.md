---
layout: page
menubar: docs_menu
title: Functions & Closures
subtitle: Language Guide
show_sidebar: false
toc: true
---

Latimer supports defining and calling functions by defining the function name, capture variables, and function arguments. Functions are first-class values and can be passed around like any other value.

## Function Declaration

Functions are declared using the following syntax:

```cpp
int add[](int a, int b) {
    return a + b;
}
```

This example declares a function named `add` that captures no closure variables (`[]`) and takes two parameters (`(int a, int b)`).

Functions must always specify:
- Captured variables: using `[]`
- Parameters: using `()`
- Return type: declared before the function name (e.g., `int`, `string`, `void`)

{% include notification.html message="
Function declarations and calls may not have more than **254** arguments.
" 
icon="fas fa-exclamation-triangle" %}

## Function Invocation

Functions are called using parentheses with arguments:

```cpp
print(add(3, 4));  // Outputs: 7
```

## Closures

To capture variables from an outer scope, list them explicitly inside square brackets:

```cpp
int count = 10;

void increment_count[count]() {
    count = count + 1;
}

increment_count();
print(count);  // Outputs: 11
```

Only variables listed in the closure brackets will be accessible inside the function. If you try to access or mutate any other outer-scope variable that is not listed, the compiler will error. 

{% include notification.html message="
Closures capture the value of variables at the time the function is declared.
```cpp
int x = 1;
void printX[x]() {
    print(x);
}

x = 2;
printX(); // Outputs: 1
```
" 
icon="fas fa-exclamation-triangle" %}

## Returning Functions

Functions are first-class values in Latimer. You can return a function from another function:

```cpp
void() make_printer[](string msg) {
    void printer[msg]() {
        print(msg);
    }
    return printer;
}

void() f = make_printer("hello");
f(); // Outputs: "hello"
```

In this example, the returned `printer` function captures the `msg` variable and retains it after `make_printer` has returned.

## Function Type Syntax

Function types are written as the return type followed by a list of argument types in parentheses.

For example, the add function has the type `int(int, int)`.
