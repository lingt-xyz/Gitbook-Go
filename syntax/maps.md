# Maps

{% hint style="warning" %}
Maps are reference types
{% endhint %}

A map maps keys to values.

The zero value of a map is `nil`. A `nil` map has no keys, nor can keys be added.

The `make` function returns a map of the given type, initialized and ready for use.

```go
package main

import "fmt"

type Vertex struct {
	Lat, Long float64
}

var m map[string]Vertex	
// m is type of map, key is type of string, value is type of Vertex

func main() {
	m = make(map[string]Vertex)
	m["Bell Labs"] = Vertex{
		40.68433, -74.39967,
	}
	fmt.Println(m["Bell Labs"])
}


// {40.68433 -74.39967}
```

## Map literals

Map literals are like struct literals, but the keys are required.

```go
package main

import "fmt"

type Vertex struct {
	Lat, Long float64
}

var m = map[string]Vertex{
	"Bell Labs": Vertex{
		40.68433, -74.39967,
	},
	"Google": Vertex{
		37.42202, -122.08408,
	},
}

func main() {
	fmt.Println(m)
}


// map[Bell Labs:{40.68433 -74.39967} Google:{37.42202 -122.08408}]
```

If the top-level type is just a type name, you can omit it from the elements of the literal.

```go
var m = map[string]Vertex{
	"Bell Labs": {40.68433, -74.39967},
	"Google":    {37.42202, -122.08408},
}
```

## Mutating Maps

Insert or update an element in map `m`:

```text
m[key] = elem
```

Retrieve an element:

```text
elem = m[key]
```

Delete an element:

```go
delete(m, key)
```

Test that a key is present with a two-value assignment:

```go
elem, ok = m[key]

// If elem or ok have not yet been declared you could use a short declaration form
elem, ok := m[key]
```

If `key` is in `m`, `ok` is `true`. If not, `ok` is `false`.

