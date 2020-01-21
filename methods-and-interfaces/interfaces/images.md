# Images

[Package image](https://golang.org/pkg/image/#Image) defines the `Image` interface:

```text
package image

type Image interface {
    ColorModel() color.Model
    Bounds() Rectangle
    At(x, y int) color.Color
}
```

**Note**: the `Rectangle` return value of the `Bounds` method is actually an [`image.Rectangle`](https://golang.org/pkg/image/#Rectangle), as the declaration is inside package `image`.

\(See [the documentation](https://golang.org/pkg/image/#Image) for all the details.\)

The `color.Color` and `color.Model` types are also interfaces, but we'll ignore that by using the predefined implementations `color.RGBA` and `color.RGBAModel`. These interfaces and types are specified by the [image/color package](https://golang.org/pkg/image/color/)

```go
package main

import (
	"fmt"
	"image"
)

func main() {
	m := image.NewRGBA(image.Rect(0, 0, 100, 100))
	fmt.Println(m.Bounds())
	fmt.Println(m.At(0, 0).RGBA())
}

/*
(0,0)-(100,100)
0 0 0 0
*/
```

