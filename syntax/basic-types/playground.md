# Playground

## string

```go
package main

import (
	"fmt"
)

func main() {
	s := "this is a string"
	fmt.Printf("%v, %T", s[0], s[0])
	fmt.Printf("%v, %T", string(s[0]), s[0])
}

// Expected results:
116, uint8
t, uint8
```

## rune

```go
package main

import (
	"fmt"
)

func main() {
	var r rune = 'a'
	fmt.Printf("%v, %T\n", r, r)
}

// Expected results:
97, int32
```

