---
layout: page
menubar: docs_menu
title: About
subtitle: Introduction
show_sidebar: false
toc: true
---

## What is Latimer?
Latimer (/ˈlæ.tɪ.mər/) is a statically-typed, interpreted programming language. It is designed to be easy to read, easy to write, and safe to use.

Latimer is under active development and is built from the ground up with simplicity, safety, and long-term usability in focus.

## Why Latimer?
(from the creator’s perspective)

Latimer was born from the desire to combine the speed and convenience of scripting languages with the safety and structure typically found in compiled languages.

One issue I’ve consistently encountered with scripting languages like Python and Bash is how easy it is to introduce bugs—especially in large scripts. The lack of strict structure often leads to subtle, hard-to-find errors.

A common example in Python is the **implicit variable declaration**. In Python, assignment always creates a variable in the current function’s scope, even if there is a variable with the same name declared outside of the function. This can lead to accidental shadowing. Worse, if a developer mistypes a variable name, Python silently creates a new one instead of warning them.

However, a user may intend to assign to an existing variable, but may have misspelled it. The interpreter doesn’t know that, so it goes ahead and silently creates some new variable and the variable the user wanted to assign to still has its old value. 

A simple example is:
```python
count = 10

def increment_count():
    coutn = count + 1  # typo: 'coutn' instead of 'count'

for _ in range(10):
    increment_count()
    # normally, we would expect this function to print 11, 12, 13, ...
    # in reality, it'll print 10, 10, 10, ...
    print(count)
```

Mistakes like this can be incredibly heinous to track down, especially in larger codebases.

Latimer avoids these problems by enforcing explicit syntax and eliminating ambiguous behavior. For example, variables must be declared before an assignment. 

```cpp
int count = 10;

void increment_count():
    coutn = count + 1;  // this would error because `coutn` is not declared

for (int i = 0; i < 10; i = i + 1) {
    increment_count();
    print(count);
}
```

These principles make Latimer predictable, readable, and maintainable—traits that are often missing from many scripting languages. It's designed for developers who want the flexibility of scripting but the discipline and safety of compiled languages.
