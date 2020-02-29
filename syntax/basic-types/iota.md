# iota

Go's `iota` identifier is used in `const` declarations to simplify definitions of incrementing numbers.

{% embed url="https://github.com/golang/go/wiki/Iota" %}

## Counter

```go
package main

import (
	"fmt"
)

const (
	a = iota
	b = iota
	c = iota
)

const (
	r = iota
	s = iota
	t = iota
)

func main() {
	fmt.Println(a)
	fmt.Println(b)
	fmt.Println(c)
	fmt.Println(r)
	fmt.Println(s)
	fmt.Println(t)
}

// Expected results:
0
1
2
0
1
2
```

## Simplified Counter

```go
package main

import (
	"fmt"
)

const (
	a = iota
	b
	c
)

func main() {
	fmt.Println(a)
	fmt.Println(b)
	fmt.Println(c)
}

// Expected results:
0
1
2
```

## Counter from 1

```go
package main

import (
	"fmt"
)

const (
	_ = iota
	a
	b
	c
)

func main() {
	fmt.Println(a)
	fmt.Println(b)
	fmt.Println(c)
}

// Expected results:
1
2
3
```

## Counter from an offset

```go
package main

import (
	"fmt"
)

const (
	_ = iota + 10
	a
	b
	c
)

func main() {
	fmt.Println(a)
	fmt.Println(b)
	fmt.Println(c)
}

// Expected results:
11
12
13
```

## Application

### File Size

```go
package main

import (
	"fmt"
)

const (
	_ = iota
	KB = 1 << (10 * iota)
	MB
	GB
	TB
)

func main() {
	fileSize := 2000000000.
	fmt.Printf("%.2fGB", fileSize/GB)
}

// 1.86GB
```

### Permission

```go
package main

import (
	"fmt"
)

const (
	X = 1 << iota
	W
	R
)

func main() {
	var permission byte = X | W | R
	fmt.Printf("%b\n", permission)
	fmt.Printf("Is readable? %v", R & permission == R)
}


// Expected results:
111
Is readable? true
```

