# Practices

* Use many, small interfaces
  * Single method interfaces are some of the most powerful and flexible
    * io.Writer, io.Reader, interface{}
* Don't export interfaces for types that will be consumed
* Do export interfaces for types that will be used by package
* Design functions and methods to receive interfaces whenever possible
  * concrete type for fields access
  * but interfaces for behaviours

