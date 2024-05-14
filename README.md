# projectinfo

[![Go Report Card](https://goreportcard.com/badge/github.com/xyproto/projectinfo)](https://goreportcard.com/report/github.com/xyproto/projectinfo) [![GoDoc](https://godoc.org/github.com/xyproto/projectinfo?status.svg)](https://godoc.org/github.com/xyproto/projectinfo) [![License](https://img.shields.io/badge/license-BSD-green.svg?style=flat)](https://raw.githubusercontent.com/xyproto/projectinfo/main/LICENSE)

Given a directory of source code, try to find the name of the project.

Example usage:

```go
package main

import (
    "fmt"
    "os"

    "github.com/xyproto/projectinfo"
)

func main() {
    // Check for command line arguments
    if len(os.Args) < 2 {
        fmt.Println("Usage: projectname [directory]")
        os.Exit(1)
    }

    // The first argument should be the directory to scan
    dir := os.Args[1]

    // Use the ReadProjectName function from the projectinfo package
    name, err := projectinfo.ReadProjectName(dir)
    if err != nil {
        fmt.Printf("Failed to read project name: %v\n", err)
        os.Exit(1)
    }

    // Output the found project name
    fmt.Printf("Project name: %s\n", name)
}
```

## General info

* Version: 1.1.0
* License: BSD-3
