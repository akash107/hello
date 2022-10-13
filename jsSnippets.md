Javascript Basics
Including JavaScript in an HTML Page
<script type="text/javascript">
//JS code goes here
</script>
Call an External JavaScript File
<script src="myscript.js"></script><code></code>
Including Comments
//
Single line comments
/* comment here */
Multi-line comments


Variables
var, const, let
var
The most common variable. Can be reassigned but only accessed within a function. Variables
defined with var move to the top when code is executed.
const
Cannot be reassigned and not accessible before they appear within the code.
let
Similar to const, however, let variable can be reassigned but not re-declared.
Data Types
var age = 23
Numbers
var x
Variables

var a = "init"
Text (strings)
var b = 1 + 2 + 3
Operations
var c = true
True or false statements
const PI = 3.14
Constant numbers
var name = {firstName:"John", lastName:”Doe"}
Objects
Objects
var person = {
firstName:"John",
lastName:"Doe",
age:20,
nationality:"German"
};


Arrays
var fruit = ["Banana", "Apple", "Pear"];
Array Methods
concat()
Join several arrays into one
indexOf()
Returns the first position at which a given element appears in an array
join()
Combine elements of an array into a single string and return the string
lastIndexOf()
Gives the last position at which a given element appears in an array

pop()
Removes the last element of an array
push()
Add a new element at the end
reverse()
Reverse the order of the elements in an array
shift()
Remove the first element of an array
slice()
Pulls a copy of a portion of an array into a new array of 4 24
sort()
Sorts elements alphabetically
splice()
Adds elements in a specified way and position
toString()
Converts elements to strings
unshift()
Adds a new element to the beginning
valueOf()
Returns the primitive value of the specified object


Operators
Basic Operators
+ Addition
- Subtraction
* Multiplication
/ Division
(..) Grouping operator
% Modulus (remainder)
++ Increment numbers
-- Decrement numbers

Comparison Operators
== Equal to
=== Equal value and equal type
!= Not equal
!== Not equal value or not equal type
> Greater than
< Less than
>= Greater than or equal to
<= Less than or equal to
? Ternary operator
Logical Operators
&& Logical and
|| Logical or
! Logical not
Bitwise Operators
& AND statement
| OR statement
~ NOT
^ XOR
<< Left shift
>> Right shift
>>> Zero fill right shift
