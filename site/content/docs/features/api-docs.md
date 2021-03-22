+++
title = "API Documentation"
template = "doc-page.html"
weight = 1
description = "hdoc's autogenerated documentation creates beautiful websites with all of the information your users need."
+++

# API Documentation

hdoc's main feature is the generating API documentation.
hdoc will go through your codebase, scan for symbols and documentation attached to them, and then use this information to construct a website.

hdoc collects information on four categories of symbols:
- Functions and methods
- Classes, structs, and unions
- Enums
- Namespaces

If you'd like to see what hdoc is capable of first-hand, take a look at [the demo](https://demo.hdoc.io).

## Supported Commands

hdoc supports a small subset of [Doxygen's commands](https://www.doxygen.nl/manual/commands.html).
hdoc supports both the `@` and `\` conventions for commands, meaning you can use `@brief` or `\brief` interchangeably.

For functions and methods:
- `@brief`
- `@param`
- `@returns`

For classes, structs, and unions:
- `@brief`
- Comments attached to member variables (i.e. `///<`)

For enums:
- `@brief`
- Comments attached to enumeration values (i.e. `///<`)

## Additional Documentation

hdoc will also include other documentation attached to a declaration assuming it's using a supported comment syntax.
For example, the function declaration below will parse the `@brief`, `@param`, and `@returns` commands.
It will also extract the comment about n-dimentional imaginary matrix transforms and attach it to the page for this function.

```cpp
/// @brief Applies Foo's algorithm on x
///
/// This is a n-dimensional imaginary matrix transform that is
/// that makes our flux capacitor work.
///
/// @param x the distilled essense of the matrix Z
/// @returns The hypercombobulated entangled version of x
int foobar(int x) { return x + 1; }
```