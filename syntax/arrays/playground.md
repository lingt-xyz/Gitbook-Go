# Playground

```go
package main

import (
	"fmt"
)


func main() {
	ints1 := [3]int{1,2,3}
	fmt.Printf("%v\n", ints1)
	
	ints2 := [...]int{1,2,3}
	fmt.Printf("%v\n", ints2)
	
	var ints3 [3]int
	fmt.Printf("%v\n", ints3)
}

// Expected results:
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

