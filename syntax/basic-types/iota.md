# iota

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

