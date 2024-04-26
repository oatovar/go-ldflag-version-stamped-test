# Test Project

This is a small program used to test [Trivy's](https://github.com/aquasecurity/trivy)
ability to detect versions set in a binary via `go build -ldflags='<FLAGS>'`.

## Building the test binary

1. Run `go build -ldflags='-X main.version=1.0.0' -o bin/test.elf .`
2. Verify that `go version -m bin/test.elf | grep -F 'main.version=1.0.0'` outputs

    ```text
    build	-ldflags="-X main.version=1.0.0"
    ```

3. Modify any Go build variables as needed to test edge cases e.g. `$GOOS`, `$GOARCH`, etc.

## LICENSE

MIT
