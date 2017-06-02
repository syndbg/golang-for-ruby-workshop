# 6 - HTTP

We're going to skip a few steps and show a bit of HTTP servers.
We're going to go back on the normal trail of Golang learning later.


## HTTP hello world

```go
# hello_world_http.go
package main

import (
	"fmt"
	"io"
	"net/http"
)

func fizz(w http.ResponseWriter, r *http.Request) {
	io.WriteString(w, "fizz\n")
}

func buzz(w http.ResponseWriter, r *http.Request) {
	io.WriteString(w, "buzz\n")
}

func fizzbuzz(w http.ResponseWriter, r *http.Request) {
	io.WriteString(w, "fizzbuzz\n")
}

func main() {
	mux := http.NewServeMux()
	mux.HandleFunc("/fizz", fizz)
	mux.HandleFunc("/buzz", buzz)
	mux.HandleFunc("/fizzbuzz", fizzbuzz)
	fmt.Println("STARTING THE SERVER")
	http.ListenAndServe(":8080", mux)
}
```
