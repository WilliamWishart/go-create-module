# Notes

https://golang.org/doc/tutorial/create-module

## Could not import log

When adding the log package, VSCode reported an error.

> could not import log (no required module provides package "log")

Despite the reported error, the code did run as expected.

Running either `go mod init` or `go build` or `go mod tidy` didn't resolve the issue.

What did fix the problem was deleting the file `go.mod` and then running `go mod init` again. But this meant that `replace example.com/greetings => ../greetings` was missing from the `go.mod` file and had to be restored, followed by `go build`.
