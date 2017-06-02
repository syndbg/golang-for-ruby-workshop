# 3 - Main Kampf

It's a funny worldplay, don't judge me. :(

Anyway, everything in `Go` is really obsessed with the world `main`.

`main` is used heavily to organize your code and structure in your app/server better.

The points cover the minimum info in https://golang.org/doc/code.html#Workspaces 
with small changes due to my personal experience.

Ruby doesn't use (or enforce) `main` at all in code organization.

## main.go

Most of the servers/applications you'll see in the wide-web
always have a file named `main.go`.

`main.go` is used as a main starting point of a/an server/app.
**This, along with `package main` are important during compilation which will be covered later.**

For example if you want to start a/an server/app that accepts start-up parameters,
initializes a connection with the database and starts a HTTP server listening to a port of `N` - `main.go` is a good place to do that.

## func main

If you come from a Python background, you won't be surprised by the hello world with `func main`, like


```go
# ... some other statements ...
func main() {
	fmt.Println("Hello, 世界")
}
# END OF FILE
```

Note that in no way whatsover we call the `main` function. 
It's automagically called since it's named `main`.
