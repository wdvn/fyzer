# fyzer
my lib in Jule


head/
├─ foo/
|  |- jule.mod
│  └─ foo.jule
├─ bar/
|  |- jule.mod
│  └─ bar.jule
├─ jule.mod
└─ main.jule

the foo.jule look like this:
```c++
use "std/fmt"
fn Foo(){
    fmt::Println("Foo")
}
```

the bar.jule look like this:
```c++
use "std/fmt"
use "heap/foo"   // way 1
//use "../foo"  // way 2
fn Bar(){
    fmt::Println("Bar")
}
```
I got the error when using the **Bar()** function in main:
```c++
use "head/bar"

fn main(){
    bar::Bar()
}
```
The error is:
error: import path must use the root name of the module
--> /home/mypc/projects/head/bar/bar.jule:2:5
2 | use "head/foo"
|     ^
| suggestion: module name of this package is: "bar"