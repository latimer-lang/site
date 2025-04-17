---
layout: page
menubar: docs_menu
title: File I/O
subtitle: Native Functions
show_sidebar: false
toc: true
---

## Print

Outputs a single value to standard output, followed by a newline.

### Declaration
```cpp
void print(int | double | string | bool | char | null value);
```

### Parameters
* `value`: `int` \| `double` \| `string` \| `bool` \| `char` \| `null`

### Return Value

This function returns nothing. It has a return type of void.

### Example

```cpp
print("Hello, world!");
print(42);
print(true);
```

Output:
```bash
$ Hello, world!
42
true
```
