## Chapter 3 Notes
---
### *Summary*
This chapter is about I/O (input and output)

### *Notes*
---
Stream: a sequence of characters from the source to the destination
Input stream: chars. from an input(keyboard) --> computer
Output stream: chars. from computer --> output device(monitor)


#### Headers
iostream: header that takes care of input and output data
* istream: input
* ostream: output

cin: common input
cout: common output

To use a header use \#include
Ex: `#include <iostream>`

char: one character
int: integer
double: a pretty long floating point number


#### Functions
Function (subprogram): set of instructions
When a function is run it runs a task
`main` is executed when a program is ran
To run a function other than `main` you must call it
like `MyFunction();` this calls
```
MyFunction() {
	code...
}
```

Libraries contain lots of organized collections of predefined functions


### Some predefined functions
**File Reading**
`get()`: function stores the next character(including whitespace) into memory
`putback()`: Places previous character extracted by the get function from an input stream back to that stream
`peek()`: Returns next character from the input stream *Does not remove it from the stream*

dot notation gets members from a class
Ex: `cin.get()`

You cannot declare or set different types of data into wrong types
like you can't put **int** into a **double** variable

showpoint forces output to show decimal point
Ex:
`cout << showpoint;`
`cout << fixed << showpoint;`

`cout << setw(5) << x << endl;`: *must have iomanip header*

**Justifications**
`ostreamVar << left`
disable left by using unsetf
`ostreamVar.unsetf(ios::left)`
`ostreamVar << right;`

reads until end of line
`getline(istreamVar, strVar);`