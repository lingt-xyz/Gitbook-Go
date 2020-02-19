# WaitGroup

```go
package main

import (
	"fmt"
	"strconv"
	"sync"
)

var wg = sync.WaitGroup{}

func main() {
	for i:=0; i<5; i++ {
		wg.Add(1)
		go sayHello(i)
	}
	wg.Wait()
	fmt.Println("Done")
	
}

func sayHello(i int) {
	fmt.Println("Hello" + strconv.Itoa(i));
	wg.Done()
}

//
Hello4
Hello0
Hello1
Hello2
Hello3
Done
```

