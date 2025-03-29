---
description: This page provides useful snippets that could be used in the codebase.
---

# Useful Snippets

## Memory allocation

````
```go
package main

import (
	"fmt"
	"runtime"
)

func printAlloc() {
	var m runtime.MemStats
	runtime.ReadMemStats(&m)
	fmt.Printf("%d MB\n", m.Alloc/1024/1024)
}

func main() {
	printAlloc()
}
```
````



