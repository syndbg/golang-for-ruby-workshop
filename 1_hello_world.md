# 1 - Hello World

Golang is an open source language by Google.
Its strong points are the simplicity to write highly scalable and reliable services.

## Installation

MacOS

```
brew install go
```

Ubuntu - check out https://github.com/golang/go/wiki/Ubuntu

## Hello world

Lets see 

```go
// hello_world.go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello, 世界")
}
```

Lets run `hello_world.go` by doing `go run hello_world.go`.

We're going to review the most used `go` sub-commands later.
For now `go run` will be good enough.

