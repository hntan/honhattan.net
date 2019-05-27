---
title: "Day Three - Learning Go"
date: 2019-05-27T20:09:41+07:00
draft: true
---

This is the day three of 30-Day Challenges in learning new technoloy everyday.

The title for today is Learning [Go][go-homepage]. To be honest I tried to write some line of codes in Go before but my understanding about the language is discreted. So I hope after this day, I will achieve my studing goal in a more systematic way!


## A brief history about Go.

Go is statically typed, complied programming language designed at Google by Robert Griesemer (V8 engine, Java Hotspt VM), Rob Pike (Unix Team, UTF-8) and Ken Tompson (Unix).

It's similar to C but memory safety, garbage collection, structral typing, and CSP-type concurrency.


> Did the C++ committee really believe that what was wrong with C++ was that it didn't have enough features?
>
> -- Rob Pike --

> Robert: Starting point: C, fix some obvious flaws, remove crud, add a few missing features.

> Rob: name: 'go'. you can invent reasons for this name but it has nice properties. it's short, easy to type. tools: goc, gol, goa. if there's an interactive debugger/interpreter it could just be called 'go'. the suffix is .go.

> Robert Empty interfaces: interface {}. These are implemented by all interfaces, and thus this could take the place of void*.

And the end of course it came out quite different from either C or C++.

First, I want to confess that I'm borrowing some slides a [Infoq's representation][infoq-go] about Go. I'm appologied for not asking permission for using them.

## Go characteristics

* Simple, there are only 25 keywords
* Fast, it runs like C
* Natively compiled
* Statical typeed
* Open source
* Garbage collected
* CSP Concurrency
* Fast compile times


## Installing Go

[Download the archive][download-link] and extract it to your prefered location.

For me, the location is: `$HOME/Workspace/tools/go`

Export go classpath.
`export PATH=$PATH:$HOME/Workspace/tools/go/bin`

You also need to create your workspace directory before getting started. To understand more Go workspace, please visit [Go workspace][go-workspace].  
If you don't set the workspace path. The default path is `$HOME/go`.  
For me, my workspace is `$HOME/Workspace/go`.


## Getting started

### Hello world
Now we will write our first hello program. Open your terminal and type `vim main.go`.

_Note that our main.go file is located at `~/Workspace/go/github.com/hntan/hello/main.go`_

{{< highlight go>}}
package main

import "fmt"

func main() {
        fmt.Println("Hello World!")
}

{{< / highlight >}}

Run `go build` common to build the hello program. A executable file will be generated beside the main.go.

{{< highlight bash >}}
tan@tan-pc:~/Workspace/go/src/github.com/hntan/hello$ ll
total 1968
drwxr-xr-x 2 tan tan    4096 May 27 22:44 ./
drwxr-xr-x 3 tan tan    4096 May 27 22:43 ../
-rwxr-xr-x 1 tan tan 2001583 May 27 22:44 hello*
-rw-r--r-- 1 tan tan      73 May 27 22:23 main.go
{{< / highlight >}}

Execute it.

{{< highlight bash >}}
tan@tan-pc:~/Workspace/go/src/github.com/hntan/hello$ ./hello 
Hello World!
{{< / highlight >}}

#### Import other packages to our main.go

{{< highlight go >}}
package main

import (
        "fmt"

        "github.com/golang/example/stringutil"
)

func main() {
        str := "Hello World!"
        rStr := stringutil.Reverse(str)

        fmt.Println(rStr)
}

{{< / highlight >}}

Build and execute it.

{{< highlight bash >}}
tan@tan-pc:~/Workspace/go/src/github.com/hntan/hello$ ./hello
!dlroW olleH
{{< / highlight >}}


### Arrays and slices


### Interfaces


### Pointers


### Go channels and concurrency





[go-homepage]: https://golang.org/
[infoq-go]: https://www.infoq.com/presentations/go-lang-design/
[download-link]: https://golang.org/dl/
[go-workspace]: https://golang.org/doc/code.html