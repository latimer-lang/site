---
layout: page
menubar: docs_menu
title: Getting Started
subtitle: Introduction
show_sidebar: false
toc: true
---

## Installation
{% include notification.html 
message="Latimer is currently in active development and the binary is not yet ready for release. Please check back on it soon!
"%}

To get started with Latimer, you need to use the `latimer` command line binary to run your code. You can download these from a [recent release](https://github.com/latimer-lang/latimer/releases/).

## Creating a "Hello World"
To write your first Latimer script, create a new file with the `.lat` extension. For this example, we’ll create a file called `hello_world.lat`.

Latimer does not require a `main()` function to execute a program. Instead, it executes all statements in the global scope.

```cpp
void hello_world() {
    print("Hello World!");
}

hello_world();
```


## Running the "Hello World"
To run the script, use the `latimer` binary. Assuming the binary is in the same directory as `hello_world.lat`, run the program with:

```bash
$ ./latimer hello_world.lat
Hello World!
```

## Next Steps
Congratulations on writing your first Latimer program! If you want to explore more, consider checking out:
- Explore [rest of the documentation](https://www.latimer-lang.org/docs/language/syntax-overview/) for a deeper look at Latimer’s features and internals.
- Check out the [Latimer GitHub repository](https://github.com/latimer-lang/latimer) to browse the source code or contribute via pull request.

## Getting Help
If you’re stuck or have questions, there are a few ways to get support:
- Browse or post in [GitHub Discussions](https://github.com/latimer-lang/latimer/discussions) — Ask for help, share ideas, or show off what you're building.
- Open an issue on [GitHub Issues](https://github.com/latimer-lang/latimer/issues) — If you think you’ve found a bug or something’s not working as expected.
- Read the full documentation — You might find what you’re looking for in the language guide or native functions docs.

Latimer is being built in the open, so don’t hesitate to reach out or contribute!
