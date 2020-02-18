# Playground

## bit operation

```go
package main

import (
	"fmt"
)

func main() {
	a := 10 // 1010
	b := 3	// 0011
	fmt.Println(a & b)	// 0010
	fmt.Println(a | b)	// 1011
	fmt.Println(a ^ b)	// 1001
	fmt.Println(a &^ b)	// 0100
	
	c := 8	// 0100
	fmt.Println(c << 2)	// 010000	// 2^3 * 2^2
	fmt.Println(c >> 2)	// 01			// 2^3 / 2^2
}

// Expected results:
2
11
9
8
32
2
```

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

