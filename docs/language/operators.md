---
layout: page
menubar: docs_menu
title: Operators
subtitle: Language Guide
show_sidebar: false
toc: true
---

Latimer supports a variety of operators for arithmetic, logic, assignment, comparisons, and more. This page provides an overview of all supported operators, grouped by category.

## Arithmetic

Arithmetic operators perform basic mathematical operations:

| Operator | Description      | Example       |
|----------|------------------|---------------|
| `+`      | Addition          | `a + b`       |
| `-`      | Subtraction       | `a - b`       |
| `*`      | Multiplication    | `a * b`       |
| `/`      | Division          | `a / b`       |
| `%`      | Modulo (remainder)| `a % b`       |

These operators work on numeric types like `int` and `double`.

## Logical

Logical operators evaluate boolean expressions:

| Operator | Description       | Example              |
|----------|-------------------|----------------------|
| `&&`     | Logical AND        | `a && b`             |
| `||`     | Logical OR         | `a || b`             |
| `!`      | Logical NOT (unary)| `!a`                 |

Operands must be boolean values (`true` or `false`). Logical operators **does not** perform a short-circuit evaluation.

## Comparison

Comparison operators compare values and return a boolean result:

| Operator | Description         | Example       |
|----------|---------------------|---------------|
| `==`     | Equal to             | `a == b`      |
| `!=`     | Not equal to         | `a != b`      |
| `<`      | Less than            | `a < b`       |
| `<=`     | Less than or equal   | `a <= b`      |
| `>`      | Greater than         | `a > b`       |
| `>=`     | Greater than or equal| `a >= b`      |

Operands must be of compatible types (e.g., comparing `int` to `int` or `string` to `string`).

## Assignment

Assignment in Latimer is done using the `=` operator.

```cpp
int a;
a = 10;
int b = a = 5; // b is 5, a is also 5
```

Assignments are expressions that return the assigned value.

```cpp
string name;

if ((name = read_name()) != "") {
    print("Hello, " + name + "!");
} else {
    print("No name provided.");
}
```

Note: The left-hand side of an assignment must be an existing variable identifier.

## Bitwise

Bitwise operators operate on the binary representation of integer values:

| Operator | Description        | Example       |
|----------|--------------------|---------------|
| `&`      | Bitwise AND         | `a & b`       |
| `|`      | Bitwise OR          | `a | b`       |
| `^`      | Bitwise XOR         | `a ^ b`       |
| `~`      | Bitwise NOT (unary) | `~a`          |
| `<<`     | Left shift          | `a << 2`      |
| `>>`     | Right shift         | `a >> 1`      |

These are only valid on `int` values.

## Ternary

The ternary operator allows for concise conditional expressions. It follows the format:

```cpp
condition ? value_if_true : value_if_false;
```

The condition must evaluate to a boolean value. If the condition is `true`, the expression evaluates to `value_if_true`; otherwise, it evaluates to `value_if_false`.

For example,

```cpp
int score = 85;
string result = score >= 60 ? "Pass" : "Fail";
print(result);
// Prints: "Pass"
```

is equivalent to

```cpp
string result;
if (score >= 60) {
    result = "Pass";
} else {
    result = "Fail";
}
```

## Precedence & Associativity

The following table shows Latimer’s operator precedence, from highest to lowest. Operators on the same line have equal precedence and are evaluated left to right, unless noted.

| Precedence | Operators                          | Associativity     |
|------------|------------------------------------|-------------------|
| 1          | `()`                               | — (grouping)      |
| 2          | `!`, `~`, `-` (unary)              | Right-to-left     |
| 3          | `*`, `/`, `%`                      | Left-to-right     |
| 4          | `+`, `-`                           | Left-to-right     |
| 5          | `<<`, `>>`                         | Left-to-right     |
| 6          | `<`, `<=`, `>`, `>=`               | Left-to-right     |
| 7          | `==`, `!=`                         | Left-to-right     |
| 8          | `|`, `&`, `^`                      | Left-to-right     |
| 9          | `||`, `&&`                         | Left-to-right     |
| 10         | `? :` (ternary)                    | Right-to-left     |
| 11         | `=` (assignment)                   | Right-to-left     |

Use parentheses to override default precedence and clarify complex expressions.
