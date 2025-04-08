---
layout: page
menubar: docs_menu
title: Time
subtitle: Native Functions
show_sidebar: false
toc: true
---

## Clock

Returns the current time in seconds since the since the Unix epoch.

### Declaration

```cpp
double clock();
```

### Parameters

None.

### Return Value

Returns a `double` representing the number of seconds (including fractional precision) since the Unix epoch (January 1st, 1970, 00:00:00 UTC).

### Example

```cpp
double start = clock();
sleep(0.5);
double end = clock();
print("Elapsed:", end - start);
```

Output:

```bash
$ Elapsed: 0.505
```

## Sleep

Pauses execution for a given number of seconds.

### Declaration

```cpp
void sleep(double seconds);
```

### Parameters

* `seconds`: A `double` value representing the number of seconds to sleep. Must be non-negative.

### Return Value

This function returns nothing. It has a return type of `void`.

### Example

```cpp
print(clock());
sleep(1.5);
print(clock());
```

Output:

```bash
$ 1744147162.493
1744147163.998
```