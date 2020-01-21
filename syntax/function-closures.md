# Function closures

Go functions may be closures. A closure is a function value that references variables from outside its body. The function may access and assign to the referenced variables; in this sense the function is "bound" to the variables.

{% hint style="info" %}
[A closure is a persistent scope which holds on to local variables even after the code execution has moved out of that block.](https://stackoverflow.com/questions/36636/what-is-a-closure)
{% endhint %}

For example, the `adder` function returns a closure. Each closure is bound to its own `sum` variable.

```go
package main

import "fmt"

func adder() func(int) int {
	sum := 0
	return func(x int) int {
		sum += x
		return sum
	}
}

func main() {
	pos, neg := adder(), adder()
	for i := 0; i < 10; i++ {
		fmt.Println(
			pos(i),
			neg(-2*i),
		)
	}
}

/*
0 0
1 -2
3 -6
6 -12
10 -20
15 -30
21 -42
28 -56
36 -72
45 -90
*/
```

