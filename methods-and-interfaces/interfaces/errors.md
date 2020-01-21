# Errors

Go programs express error state with `error` values.

The `error` type is a built-in interface similar to `fmt.Stringer`:

```text
type error interface {
    Error() string
}
```

\(As with `fmt.Stringer`, the `fmt` package looks for the `error` interface when printing values.\)

Functions often return an `error` value, and calling code should handle errors by testing whether the error equals `nil`.

```text
i, err := strconv.Atoi("42")
if err != nil {
    fmt.Printf("couldn't convert number: %v\n", err)
    return
}
fmt.Println("Converted integer:", i)
```

A nil `error` denotes success; a non-nil `error` denotes failure.

```go
package main

import (
	"fmt"
	"time"
)

type MyError struct {
	When time.Time
	What string
}

func (e *MyError) Error() string {
	return fmt.Sprintf("at %v, %s",
		e.When, e.What)
}

func run() error {
	return &MyError{
		time.Now(),
		"it didn't work",
	}
}

func main() {
	if err := run(); err != nil {
		fmt.Println(err)
	}
}


// at 2009-11-10 23:00:00 +0000 UTC m=+0.000000001, it didn't work
```

## Infinite loop

```go
type ErrNegativeSqrt float64

func (e ErrNegativeSqrt) Error() string {
	return fmt.Sprintf("cannot Sqrt negative number: %v", float64(e))
	// infinite loop if:
	//return fmt.Sprintf("cannot Sqrt negative number: %v", float64(e))
}
```

Because the implementation of fmt package, `error` type was checked before `Stringer`.

{% embed url="https://github.com/golang/go/blob/2ed57a8cd86cec36b8370fb16d450e5a29a9375f/src/pkg/fmt/print.go\#L639" %}

