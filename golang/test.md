# Test

## Introduction

This page shows how to run go test based on simple example.

**Main file**

```go
// main.go
package main

import (
	"fmt"
	"io"
)

func copySourceToDest(source io.Reader, dest io.Writer) error {
	b, err := io.ReadAll(source)
	if err != nil {
		return err
	}
	_, err = dest.Write(b)
	return err
}
 
func main() {
	fmt.Println("Test")
}

```

**Test file**

```go
// main_test.go
package main

import (
	"bytes"
	"strings"
	"testing"
)

func TestCopySourceToDest(t *testing.T) {
	const input = "foo"
	source := strings.NewReader(input)
	dest := bytes.NewBuffer(make([]byte, 0))

	err := copySourceToDest(source, dest)
	if err != nil {
		t.FailNow()
	}

	got := dest.String()
	if got != input {
		t.Errorf("expected: %s, got: %s", input, got)
	}
}

```

### How to run tests

#### 1. Run test

```sh
$ go test
# Output:
PASS
ok      ch02    0.269s
```

#### 2. Run test, more verbose

```sh
$ go test -v
# Output:
=== RUN   TestCopySourceToDest
--- PASS: TestCopySourceToDest (0.00s)
PASS
ok      ch02    0.257s
```

#### 3. Run test by suppling the test files as argiments

```sh
$ go test main.go main_test.go
# Output
ok      command-line-arguments  0.257s
```

#### 4. Run test by specifying test

```sh
$ go test -run TestCopySourceToDest
# Output
PASS
ok      ch02    0.247s
```

#### 5. Run a test coverage

```sh
go test -cover
# Output
PASS
coverage: 66.7% of statements
ok      ch02    0.253s
```

#### 6. Run test by providing a package name

```sh
$ go test person
# Output
ok  	person	0.004s
```

#### 7. Run a test on all packages in a directory

```sh
$ go test ./...
```





