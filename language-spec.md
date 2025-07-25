# Veny Language Specification (v0.5.1)

## Overview

Veny is a statically typed, object-oriented programming language designed for clarity, brevity, and efficient compilation to Java. It draws inspiration from languages like Kotlin, Python, and Go, while staying grounded in strong static typing.

---

## Syntax and Structure

### 1. **Packages and Files**

* Each file must declare a package:

```veny
package myapp.utils
```

### 2. **Class Declaration**

```veny
class Greeter {
    val name: Text = "Alice"

    greet(): void {
        Console.print("Hello, " + name)
    }
}
```

* `val` denotes an immutable field.
* `var` denotes a mutable field.

### 3. **Method Declarations**

* Methods are defined within classes.
* Syntax:

```veny
add(x: Int, y: Int): Int {
    return x + y
}
```

### 4. **Entry Point**

```veny
class App {
    entry(args: [Text]): void {
        Console.print("Welcome to Veny")
    }
}
```

* The `entry` method is the program's starting point.
* `args` is a list of text arguments passed from the CLI.

---

## Types

* **Built-in Types**: `Int`, `Float`, `Bool`, `Text`, `Void`
* **Array Types**: `[Int]`, `[Float]`, etc.
* **Type Inference**: Allowed (not implemented at the moment) where context is enough:

```veny
val name = "Veny"  // type inferred as Text
```

---

## Statements and Expressions

* Variable declarations:

```veny
val radius: Float = 5.0
var active: Bool = true
```

* Conditionals:

```veny
if active {
    Console.print("Running")
} else {
    Console.print("Stopped")
}
```

* Loops:

```veny
while active {
    Console.print("Looping")
    break
}
```
```veny
for i in 1..10 {
    Console.print(i)
}
```

---

## Arrays

* Declared with `[Type]` syntax:

```veny
val numbers: [Int] = [1, 2, 3, 4]
```

* Array literals support type inference:

```veny
val names = ["Alice", "Bob"]  // Inferred as [Text]
```

---

## Standard Library (WIP)

Initial functions include:

```veny
Console.print(message: Text): void
```

Future expansions will include `Math`, `Array` and other utilities.

---

## Concurrency (Future Work)

* Planned support for fibers:

```veny
Fiber.run {
    // lightweight task
}
```

---

## Tooling

* **Compiler**: Generates Java code.
* **Execution**: Built and run using GraalVM for native executables.

---

## Project Structure

* Compiler: `veny-compiler`
* CLI: `veny-cli`
* Stdlib: `veny-stdlib` (Java project, imported in generated code)

---

## Version

* `v0.5.1`
* Entry point updated to `entry(args: [Text])`

---
Veny is developed by Stoyan Petkov and contributors.

© 2025 The Veny Language Project. Licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

