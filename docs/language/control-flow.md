---
layout: page
menubar: docs_menu
title: Control Flow
subtitle: Language Guide
show_sidebar: false
toc: true
---

## Loops

Latimer supports two primary looping constructs: `for` and `while`.

### For

A `for` loop is typically used when the number of iterations is known ahead of time. It includes an initializer, a condition, and an increment expression—all written in the loop header.

```cpp
for (int i = 0; i < 5; i = i + 1) {
    print i;
}
// Prints: 0 1 2 3 4
```

The loop works as follows:
1. `int i = 0` initializes the loop variable.
2. `i < 5` is the condition; the loop continues as long as this is `true`.
3. `i = i + 1` runs after each iteration to update the loop variable.

All three components are optional. For example, you can declare `i` outside the loop:

```cpp
int i = 0;
for (; i < 3; i = i + 1) {
    print i;
}
```

### While

A while loop is used when the condition must be checked before every iteration, and the number of repetitions is not necessarily known in advance.

```cpp
int x = 1;
while (x < 100) {
    print x;
    x = x * 2;
}
// Prints: 1 2 4 8 16 32 64
```

The loop works as follows:
1. The condition `x < 100` is evaluated before each iteration.
2. If it’s `true`, the loop body runs.
3. If it’s `false`, the loop exits.

### Break

The `break` statement is used to exit the nearest enclosing loop immediately. Execution continues with the first statement after the loop.

```cpp
for (int i = 0; i < 10; i = i + 1) {
    if (i == 5) {
        break;
    }
    print i;
}
// Prints: 0 1 2 3 4
```

The loop terminates early when the condition inside the `if` statement is met. After `break` is executed, control moves to the first statement following the loop.

{% include notification.html message="
`break` must appear within a `for` or `while` loop. Using it in any other context errors.
" 
icon="fas fa-exclamation-triangle" %}

### Continue

The `continue` statement skips the rest of the current loop iteration and proceeds to the next one.

```cpp
for (int i = 0; i < 5; i = i + 1) {
    if (i == 2) {
        continue;
    }
    print i;
}
// Prints: 0 1 3 4
```

Here, when `i` is 2, the `print` statement is skipped, and the loop immediately proceeds to the next iteration.

{% include notification.html message="
`continue` must appear within a `for` or `while` loop. Using it in any other context errors.
" 
icon="fas fa-exclamation-triangle" %}

## Conditionals

Latimer supports conditional branching using `if`, `else if`, and `else` statements.

### If

An `if` statement takes an expression that evaluates to a boolean value. If the condition is `true`, the program executes the statement block inside the `if`.

```cpp
int temp_fahrenheit = 30;
if (temp_fahrenheit <= 32) {
    print "It's very cold. Consider wearing a scarf.";
}
// Prints "It's very cold. Consider wearing a scarf."
```

In the example above, the program checks whether the temperature is less than or equal to 32 degrees Fahrenheit (the freezing point of water). Since it is, the message is printed. Otherwise, execution continues after the closing brace of the `if` block.

The `if` statement can include an optional `else` clause to execute an alternative block when the condition is `false`.

```cpp
temp_fahrenheit = 40;
if (temp_fahrenheit <= 32) {
    print("It's very cold. Consider wearing a scarf.")
} else {
    print("It's not that cold. Wear a T-shirt.")
}
// Prints "It's not that cold. Wear a T-shirt."
```

In this case, because the temperature is 40, the `else` block is executed instead.

You can also chain multiple conditions using `else if`:

```cpp
temp_fahrenheit = 90;
if (temp_fahrenheit <= 32) {
    print("It's very cold. Consider wearing a scarf.")
} else if (temp_fahrenheit >= 86) {
    print("It's really warm. Don't forget to wear sunscreen.")
} else {
    print("It's not that cold. Wear a T-shirt.")
}
// Prints "It's really warm. Don't forget to wear sunscreen."
```

Here, the `else if` condition is triggered when the temperature is 90. The `else` clause serves as a fallback for values that don’t match any previous conditions.

The final `else` clause is optional and can be omitted if no fallback behavior is needed:

```cpp
temp_fahrenheit = 72;
if (temp_fahrenheit <= 32) {
    print("It's very cold. Consider wearing a scarf.")
} else if (temp_fahrenheit >= 86) {
    print("It's really warm. Don't forget to wear sunscreen.")
}
```

In this case, none of the conditions match, so the program continues without printing anything.
