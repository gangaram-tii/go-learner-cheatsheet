# Go learners Cheatsheet


## My first Go program:

```go
package main
import ("fmt")

func main() {
  fmt.Println("Hello World!")
}
```
In Go, every program is encapsulated within a package, typically initiated with the package keyword. In the context of the main package, an import statement such as import ("fmt") allows access to functionalities from external packages like fmt. Between lines of code, blank lines serve to enhance readability, as Go disregards whitespace. The main function, declared with func main() {}, serves as the entry point of execution, containing the code to be run within its curly braces {}. Within this function, fmt.Println() is employed to print text, in this case, "Hello World!", utilizing the println function from the fmt package.

In Go, statements are separated by ending a line or by a semicolon ";". The left curly bracket { cannot come at the start of a line.

Go follows C++ style comments.

 ## Variables:

 
- **int** - stores integers (whole numbers), such as 123 or -123
- **float32** - stores floating point numbers, with decimals, such as 19.99 or -19.99
- **string** - stores text, such as "Hello World". String values are surrounded by double quotes
- **bool** - stores values with two states: true or false

### Declaration:
#### Use 'var' keyword:

```go
var variablename type = value
```
Example:

```go
var a string
var b int
var c bool
```
#### Using `:=` sign:
The type of the variable is inferred from the value.

```go
i_m_int := 2 //Compiler infers type as integer, var keyword is not used
var i_am_str = "Hello" //Compiler infers type as string, var keyword is used
```
These declarations are also OK:

```go
var a, b, c, d int = 1, 3, 5, 7
var d, e = 6, "Hello"
f, g := 7, "World!"
var (
     h int
     i int = 1
     j string = "hello"
   )
```

A variable name:
- must start with a letter or an underscore character (_)
- cannot start with a digit
- can only contain alpha-numeric characters and underscores (a-z, A-Z, 0-9, and _ )
- is case-sensitive (age, Age and AGE are three different variables).
- cannot contain spaces
- cannot be any Go keywords
    
Also:
- There is no limit on the length of the variable name



 var  |	:=
 --- | ---
Can be used inside and outside of functions |	Can only be used inside functions
Variable declaration and value assignment can be done separately | Variable declaration and value assignment cannot be done separately (must be done in the same line)

### Constant:
Not possible to change the value.
Example:

```go
const I_M_CONST_INT int = 1
const I_M_ANOTHER_CONST_INT = 1
//Can be grouped in a block for readability
const (
  A int = 1
  B = 3.14
  C = "Hi!"
)
```

### Printing on output console

Part of `fmt` package:

- Println() 
- Print()
- Printf()

`Println()` function is similar to `Print()` with the difference that a whitespace is added between the arguments, and a newline is added at the end.

The `Printf()` function first formats its argument based on the given format specifier and then prints them.

- `%v`: is used to print the value of the arguments
- `%T`: is used to print the type of the arguments

### More on Integers:
Type | Size 
--- | --- 
int/uint  | Depends on platform (32 bits in 32 bit systems and 64 bit in 64 bit systems)
int8/uint8 | 8 bits/1 byte
int16/uint16 | 16 bits/2 byte
int32/uint32 | 32 bits/4 byte
int64/uint64 | 64 bits/8 byte

Formatting:
- `%d`: Base 10 integer.
- `%4d`: Pad with spaces (width 4, right justified)
- `%-4d`: Pad with spaces (width 4, left justified)
- `%04d`:	Pad with zeroes (width 4
- `%x`: Hexadecimal representation, with lower-case letters for a-f.
- `%X`: Hexadecimal representation, with upper-case letters for A-F.
- `%#x`: Hexadecimal representation, with leading 0x
- `%b`: Binary representation.
- `%t`: Value of the boolean operator in true or false format (same as using %v)
  
### More on Floats:
Follows the IEEE 754 standard:

Type | Size 
--- | ---
float32 |	32 bits, Single precision,(s=1,e=8,m=23)
float64 |	64 bits, Double precision, (s=1,e=11,m52)

Formatting:
- `%f`: Decimal floating-point.
- `%e, %E`: Scientific notation, with 'e' or 'E' replacing the decimal point.
- `%.2f`: Default width, precision 2
- `%6.2f`: Width 6, precision 2
- `%g`:	Exponent as needed, only necessary digits

### Strings:
Formatting:
- `%s`: The default format for strings.
- `%q`: Prints the value as a double-quoted string
- `%8s`: Prints the value as plain string (width 8, right justified)
- `%-8s`: Prints the value as plain string (width 8, left justified)
- `%x`: Prints the value as hex dump of byte values
- `% x`: Prints the value as hex dump with spaces

### Pointers:
- `%p`: Pointer representation.

## Arrays:
Indexing: starts with 0

```go
var array_name = [length]datatype{values} // here length is defined
var array_name = [...]datatype{values} // here length is inferred
array_name := [length]datatype{values} // here length is defined
array_name := [...]datatype{values} // here length is inferred 
```

Example:

```go
var arr1 = [3]int{1,2,3}
arr2 := [5]int{4,5,6,7,8}
var arr3 = [...]int{1,2,3}
arr4 := [...]int{4,5,6,7,8}
var cars = [4]string{"Volvo", "BMW", "Ford", "Mazda"}
/* ATTENTION */
arr5 := [5]int{1:10,2:40} // Initializes only value at index 1 and 2
x := len(arr5) // Length of array
```

## Slices
Slices are similar to arrays, but are more powerful and flexible. Unlike arrays, the length of a slice can grow and shrink.

- **Length (len)**: It represents the number of elements contained in the slice. It can be obtained using the built-in len() function.

- **Capacity (cap)**: It represents the maximum number of elements that the slice can hold without allocating more memory. It can be obtained using the built-in cap() function.
    
Syntax:

```go
slice_name := []datatype{values}
myslice := []int{}
```

Example1:

```go
package main

import "fmt"

func main() {
    // Creating a slice with length 3 and capacity 5
    slice := make([]int, 3, 5)

    // Creating a slice from an Array
    arr1 := [6]int{10, 11, 12, 13, 14,15}
    slice1 := arr1[2:4]

    fmt.Println("Length of slice:", len(slice))     // Output: Length of slice: 3
    fmt.Println("Capacity of slice:", cap(slice))   // Output: Capacity of slice: 5
}
```

In this example, len(slice) returns 3 because the slice has 3 elements, and cap(slice) returns 5 because the slice has a capacity of 5.

Example2:
```go
package main
import ("fmt")

func main() {
  arr1 := [6]int{10, 11, 12, 13, 14,15}
  myslice := arr1[2:4]

  fmt.Printf("myslice = %v\n", myslice)
  fmt.Printf("length = %d\n", len(myslice))
  fmt.Printf("capacity = %d\n", cap(myslice))

  myslice2 := []int{10, 11, 12, 13, 14}
  fmt.Printf("length = %d\n", len(myslice2))
  fmt.Printf("capacity = %d\n", cap(myslice2))
}
```

In the example above myslice is a slice with length 2. It is made from arr1 which is an array with length 6.

The slice starts from the third element of the array which has value 12 (remember that array indexes start at 0. That means that [0] is the first element, [1] is the second element, etc.). The slice can grow to the end of the array. This means that the capacity of the slice is 4.

If myslice started from element 0, the slice capacity would be 6.

In Go, when you create a slice using a composite literal, the capacity of the slice is set to the same value as its length. myslice2 has length and capacity 5.


In Go, a slice doesn't have a fixed capacity; it can dynamically grow as elements are added to it. However, you can specify a capacity when creating a slice using the make function. The capacity specifies the size of the underlying array that the slice can expand into before it needs to allocate more memory. Here's an example:

```go
slice := make([]int, 0, 10) // Creates a slice with length 0 and capacity 10
```

In this example, the slice has a length of 0 (no elements) and a capacity of 10. As you append elements to the slice, it can grow up to the specified capacity before it needs to reallocate memory. If you exceed the capacity, Go automatically doubles the capacity to accommodate more elements efficiently.

### Slice Operations:
By example:

```go
mySlice := []int{10,20,30}
/* Change Value */
mySlice[2] = 50
/* Append 60,70,80 to the slice */
mySlice = append(mySlice, 60, 70, 80)

/* Append a slice */
mySlice2 := []int{11,21,31}
/* Here we use the ... syntax to unpack the elements of slice2 into the append() function call */
mySlice3 = append(mySlice, mySlice2...)

```
