# Constants

Constants are declared like variables, but with the `const`keyword.

Constants can be character, string, boolean, or numeric values.

{% hint style="warning" %}
Constants **cannot** be declared using the `:=` syntax.
{% endhint %}

```go
package main

import "fmt"

const Pi = 3.14

func main() {
	const World = "世界"
	fmt.Println("Hello", World)
	fmt.Println("Happy", Pi, "Day")

	const Truth = true
	fmt.Println("Go rules?", Truth)
}

// Expected results:
Hello 世界
Happy 3.14 Day
Go rules? true
```



