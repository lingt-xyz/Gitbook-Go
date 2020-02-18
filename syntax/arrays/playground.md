# Playground

## Initialization

```go
package main

import (
	"fmt"
)


func main() {
	ints1 := [3]int{1,2,3} // this is an array
	fmt.Printf("%v\n", ints1)
	
	ints2 := [...]int{1,2,3} // this is an array
	fmt.Printf("%v\n", ints2)
	
	ints3 := []int{1,2,3} // this is a slice
	fmt.Printf("%v\n", ints3)
	
	var ints4 [3]int
	fmt.Printf("%v\n", ints4)
}

// Expected results:
[1 2 3]
[1 2 3]
[1 2 3]
[0 0 0]
```

```go
package main

import (
	"fmt"
)


func main() {
	var matrix [2][2]int = [2][2]int{[2]int{1,0}, [2]int{0,1}}
	fmt.Println(matrix)
}

// [[1 0] [0 1]]
```

## Copy

```go
package main

import (
	"fmt"
)


func main() {
	a := [3]int{1,2,3}
	fmt.Printf("%v\n", a)
	
	b := a
	b[0] = 0
	fmt.Printf("%v\n", a)
	fmt.Printf("%v\n", b)
	
	c := &a
	c[0] = 0
	fmt.Printf("%v\n", a)
	fmt.Printf("%v\n", c)
}

//
[1 2 3]
[1 2 3]
[0 2 3]
[0 2 3]
&[0 2 3]
```

## Append

```go
package main

import (
	"fmt"
)


func main() {
	a := []int{1,2,3}
	fmt.Printf("%v\n", a)
	
	a = append(a, 4)
	fmt.Printf("%v\n", a)
	
	a = append(a, 5, 6)
	fmt.Printf("%v\n", a)
	
	a = append(a, []int{7, 9}...) // ... is spread out operator
	fmt.Printf("%v\n", a)
}

//
[1 2 3]
[1 2 3 4]
[1 2 3 4 5 6]
[1 2 3 4 5 6 7 9]
```

## Caution

```go
package main

import (
	"fmt"
)


func main() {
	a := []int{1, 2, 3333, 4, 5}
	fmt.Printf("%v\n", a)
	
	b := append(a[:2], a[3:]...)
	fmt.Printf("%v\n", b)
	fmt.Printf("%v\n", a)
}

//
[1 2 3333 4 5]
[1 2 4 5]
[1 2 4 5 5]
```

