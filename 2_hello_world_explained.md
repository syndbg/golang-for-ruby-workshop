# 2 - Hello world explained

## What's a package and why it's always present?

Every Go file has to have the `package` defined.
`main` is used as a good default package.
Think of `package`(s) as modules.

*You don't have to import files* from the same module.

## How can I import packages from the STD or anywhere else?

1. You can use single line `import` statement like

```go
import "fmt"
```

2. Or you can import multiple modules at once (or just one) like

```go
import (
  "fmt"
  "log"
)
```

I **highly recommend always using the 2nd approach**. 
It's more consistent and you'll always easily add a second module without the need to change between the 1st and 2nd approaches.


**However note that imported modules must always be in use**.

The following `import` statement is invalid if the `log` module is not used.

```go
import (
  "fmt"
  "log"
)
```

Therefore you can either remove the `log` module or comment it like

```go
import (
  "fmt"
  // "log"
)
```
