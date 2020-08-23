# init

#### The init function <a id="init"></a>

Each source file can define its own niladic `init` function to set up whatever state is required. \(Actually each file can have multiple `init` functions.\) And finally means finally: `init` is called after all the variable declarations in the package have evaluated their initializers, and those are evaluated only after all the imported packages have been initialized.

Besides initializations that cannot be expressed as declarations, a common use of `init` functions is to verify or repair correctness of the program state before real execution begins.

```go
func init() {
    if user == "" {
        log.Fatal("$USER not set")
    }
    if home == "" {
        home = "/home/" + user
    }
    if gopath == "" {
        gopath = home + "/go"
    }
    // gopath may be overridden by --gopath flag on command line.
    flag.StringVar(&gopath, "gopath", gopath, "override default GOPATH")
}
```

![https://stackoverflow.com/questions/24790175/when-is-the-init-function-run](../.gitbook/assets/init.png)

