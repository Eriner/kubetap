# FAQ

## Errors build kubetap

### Go toolchain not new enough

Kubetap requires Go version 1.14 or later.

You can check the current Go version by running:

```sh
$ go version
go version go1.14.2 darwin/amd64
```

## Errors running kubetap

### Why can't I run the tap command after installing from source?

If you get an error like this:

```sh
$ kubectl tap --help
Error: unknown command "tap" for "kubectl"

Did you mean this?
  top
  cp
```

And if you can't execute the standalone binary in a shell, as in:

```sh
kubectl-tap
```

...then it is likely that your `${GOPATH}/bin` directory is not in
your `${PATH}`. Try adding the following line to your `.bashrc` or
`.zshrc`:

```sh
export PATH="${GOPATH}/bin:${PATH}"
```

### The Mac OS Binary doesn't run

Mac binaries require notarization. It is recommended to use Homebrew to install
Kubetap on Mac, or to build from source.
