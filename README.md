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
