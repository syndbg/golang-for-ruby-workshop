# 5 - Functions

Took us a while to get here, but step on solid foundations.

## How to define them

```go
# hello_world_function.go
package main

func helloWorld() {
	fmt.Println("Hello World")
}

func main() {
	helloWorld()
}
```

## How to define parameters

```go
package main

func say(message string) {
	fmt.Println(message)
}

func main() {
	say("Hello world")
}
```

## How to accept variadic number of parameter (a.k.a varargs)

```go
package main

func say(messages... []string) {
	fmt.Println(messages)
}

func main() {
	say("Hello", "World")
}
```

## How to return from functions
