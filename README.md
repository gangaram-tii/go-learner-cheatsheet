# Go learners Cheatsheet


## My first Go program:

```
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

```
var variablename type = value
```
Example:

```
var a string
var b int
var c bool
```
#### Using `:=` sign:
The type of the variable is inferred from the value.

```
i_m_int := 2 //Compiler infers type as integer, var keyword is not used
var i_am_str = "Hello" //Compiler infers type as string, var keyword is used
```
These declarations are also OK:

```
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

```
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
- `%d`: Base 10 integer.
- `%b`: Binary representation.
- `%x`: Hexadecimal representation, with lower-case letters for a-f.
- `%X`: Hexadecimal representation, with upper-case letters for A-F.
- `%f`: Decimal floating-point.
- `%e, %E`: Scientific notation, with 'e' or 'E' replacing the decimal point.
- `%s`: The default format for strings.
- `%p`: Pointer representation.




