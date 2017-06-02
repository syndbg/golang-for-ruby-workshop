# 4 - Variables

Variables can be defined in numerous ways in Go, for good or bad.

## Defining variables explicitly with `var`

```
// hello_world_variables.go
package main

import (
	"fmt"
)

func main() {
    // We can define them at once
    // `var hello, world string`,
    // but for readability and consistency, use the long form, 
    // you won't be smarter if you use the shorter one.
    var hello string
    var world string
    
    hello = "Hello" 
    world = "世界"
    
	fmt.Print(hello)
	fmt.Print(", ")
	fmt.Print(world)
    fmt.Println()
}
```

As you can see you use `var [name] [type]`.

## The basic types

* Boolean - `bool`
* String - `string`
* Integer - `int  int8  int16  int32  int64 uint uint8 uint16 uint32 uint64 uintptr`
* Float - `float32 float64`
* Complex - `complex64 complex128`
* Byte - `byte // alias for uint8`
* Runes (Unicode code point, this is specific in use) - `rune // alias for int32`


## Defining variables with an initializer

Of course defining variables explicitly and then initializing them to something else is a bit more writing than necessary.

You can shorten it like

```
// hello_world_variable_initializers.go
package main

import (
	"fmt"
)

func main() {
    hello := "Hello" 
    world := "世界"
    
	fmt.Print(hello)
	fmt.Print(", ")
	fmt.Print(world)
    fmt.Println()
}
```

As you can see the format previously was `var [name] [type]`.
Now you can just do `[name] := [value]`.

Never forget that you write **:**. It's **:=** vs **=**.

When using an initializer Golang will infer the type of variable from the value.

Equivalent Ruby code

```ruby
hello = "Hello"
```

## Constants?

How to define constants

```go
// hello_world_variable_constants.go
package main

import (
	"fmt"
)

func main() {
    const hello = "Hello" 
    const world = "世界" 
	fmt.Print(hello)
	fmt.Print(", ")
	fmt.Print(world)
    fmt.Println()
}
```

Constants **can only be defined** like `const [name] = [value]`. 
You explicitly use `const` but don't have to define the type.
And also note you're using **=** and not **:=**.


Redefining constants is not possible at all in Golang.

```
// hello_world_variable_constants_redefine.go
package main

import (
	"fmt"
)

func main() {
    const hello = "Hello" 
    const world = "世界" 
	fmt.Print(hello)
	fmt.Print(", ")
	fmt.Print(world)
    fmt.Println()
    // NOTE: Compilation error.
    // `cannot assign to world`.
    world = "World"
}
```

Ruby **has no real constants**. The equivalent Ruby code


```
HELLO = "Hello"
# NOTE: We can't use UTF-8.
WORLD = "World"
puts "#{HELLO}, #{WORLD}"

# NOTE: Absolutely no problem to do so.
# Only thing you'll see is a warning that doesn't prohibit you at all.
# `warning: already initialized constant WORLD. warning: previous definition of WORLD was here`
WORLD = "Earth"
puts "#{HELLO}, #{WORLD}"
```

## Static and dynamic typing 

Now that we know how to define variables, lets put emphasis on the typing.

Golang is a static-typed language but does not require you to be explicit (*cough Java, cough*).

Okay what's static typing in the first place? Show, don't tell

In 1 image: https://static.squarespace.com/static/50b76babe4b05c3cd8bab78a/50b7714be4b0192bc2226c59/50b7714ce4b0192bc2226c64/1180560080000/?format=original

In few lines of code:

```ruby
# In this Ruby example
# we're assigning `foo` to bar.
# the type of `foo` is dependent on the 
foo = 'bar'
puts foo.class
# String
foo = 5
puts foo.class
# Integer
# Okay, so we can change the variable `foo`
# to any type we like. Meaning that.... the variable `foo` can have a dynamic type.
```

Lets try the same act of dynamic typing in Go

```go
# static_dynamic_typing.go
package main

func main() {
  foo := "bar"
  # It's: string
  # NOTE: Code below results into 
  # ` cannot use 5 (type int) as type string in assignment`
  foo = 5
}
```

It's important to note that in static-typed language you define the type of the variable that holds the value.
While in dynamic-typed language you define a variable that holds a specific type depending on the value's type.
