# Data Types and Type Conversions
>Types of data according to their properties include numeric data and text data. 

>Numbers include integer numbers and real numbers.
JavaScript data types are primitive (or simple) and complex (or composite). 

>Primitive JS data types include numbers and strings of characters. They lack complexity. A single value will be kept in a variable if you put data of a primitive type into it. This value will be atomic, meaning that its components cannot be separated from it.

>Complex JS data types include arrays and objects. A complex type of data, like an array, will have a large number of primitive (not complex) type elements.

>Literals are a technique for highlighting certain values (data) in the computer code. Many programming languages, including JavaScript, use literals.

## The typeof operator
>An operator is a symbol or term that designates a certain action to be performed on the specified parameters. E.g., the + sign is a two-argument operator that denotes summing; it is unary as it accepts one argument.

>The typeof operator has the following possible return values:


“undefined”, “object”, “boolean”, “number”, “bigint”, “string”, “symbol”, “function”


## Primitive data types
- They are Boolean, Number, BigInt, String, Symbol, and undefined.

### Boolean
- Takes one of two values: true or false. 
- It is mostly used as a conditional expression when determining which portion of the code should be run or how many times something should be repeated.
- Boolean is used as a “flag” that indicates anything that may be either present or missing, enabled or disabled, etc. Boolean variables should have descriptive names, just like any other kind of variable. Although it’s not required, it’s common to see boolean flag names prefixed with “is” to indicate that they are intended to be checked for true/false values.

```js
let isDataValid = true;
let isStringTooLong = false;
let isGameOver = false;
continueLoop = true;
   
console.log(false); // -> false
console.log(typeof false); // -> boolean
console.log(isDataValid); // -> true
console.log(typeof isDataValid); // -> boolean
```
- On boolean values, we may conduct logical operations without conversion (i.e., changing to a different type), including those that you might be familiar with from mathematics, including NOT, AND, and OR (represented by the symbols! &&, and ||, respectively).


### Number

- Real numbers, including fractions and integers. The way this sort of data is kept in memory makes the values sometimes approximate, including but not limited to extremely large quantities and certain fractions. The integer values should be restricted in JavaScript to the range from -(253 - 1) to (253 - 1) in order to guarantee the accuracy of computations.
- You can perform arithmetic operations, like addition, subtraction, multiplication, and division with numbers.

```js
const year = 1991;
let delayInSeconds = 0.00016;
let area = (16 * 3.14);
let halfArea = area / 2;
 
console.log(year); // -> 1991;
console.log(typeof year); // -> number;
```
- Numbers can be decimals. They could be in hexadecimal (0x…), octal (0o...), or binary (0b...) form. They can be in exponential form, so, for example, instead of 9000, we can write 9e3, and instead of 0.00123, we can write 123e-5. 

```js
let a = 10; // decimal - default
let b = 0x10; // hexadecimal
let c = 0o10; // octal
let d = 0b10; // binary
   
console.log(a); // -> 10
console.log(b); // -> 16
console.log(c); // -> 8
console.log(d); // -> 2
   
let x = 9e3;
let y = 123e-5;
console.log(x); // -> 9000
console.log(y); // -> 0.00123
```
Also, we can use Infinity, -Infinity, and NaN (not a number). NaN indicates that some arithmetic operation (or mathematical function) could not be completed because the input is either not a number or cannot be turned into a number.

```js
let a = 1 / 0;
let b = -Infinity;
   
console.log(a); // -> Infinity
console.log(b); // -> -Infinity
console.log(typeof a); // -> number
console.log(typeof b); // -> number
   
let s = "it's definitely not a number";
let n = s * 10;
console.log(n); // -> NaN
console.log(typeof n); // -> number
```

### BigInt
- We can write integers of almost any length with the BigInt. The Number type is sufficient for practically all common mathematical operations, but sometimes, we need a type that can accommodate considerably larger numbers.
- BigInts and Numbers can both be used for mathematical tasks. However, there is a distinction when dividing. The division result will always be rounded to the closest whole number since the BigInt is an integer type.
- Numbers with the...n suffix are considered BigInt literals.
```js
let big = 1234567890000000000000n;
let big2 = 1n;
   
console.log(big); // -> 1234567890000000000000n
console.log(typeof big); // -> bigint
   
console.log(big2); // -> 1n
console.log(7n / 4n); // -> 1n
```
- You cannot add a BigInt and a Number to each other (this will generate an error).

```js
let big3 = 1000n + 20;
// -> Uncaught TypeError: Cannot mix BigInt and other types, use explicit conversions
```

### String
- A string type is a string of characters that make up a piece of text. Concatenation, substring extraction, and string length checks are often performed on texts. Since HTML and a significant portion of Internet content are both text, strings are widely utilized in programming and much more so in web development.
- Among the most typical applications for text in web development are:
    - links and paths to resources;
    - tokens;
    - checking user-filled forms and input;
    - dynamic content generation

- Adding quotation marks (single or double) to a text indicates a string. The beginning and end quote characters must match up.

```js
let country = "Malawi";
let continent = 'Africa';
   
console.log(country); // -> Malawi
console.log(typeof country); // -> string
console.log(continent); // -> Africa
console.log(typeof continent); // -> string
```

> Single quotes placed within a string that has been marked with double quotes will be interpreted as regular characters. This will also function in the reverse circumstance (i.e., inserting double quotes between the single quotes).

```js
let message1 = “The man ‘Mars’ made a sale.”;
let message2 = ‘Ola “Wedger” intends to pass close to Mauritius.’;
   
console.log(message1); // -> The man ‘Mars’ made a sale.
console.log(message2); // -> Ola “Wedger” intends to pass close to Mauritius.’.
```


>We shall treat a backslash and a quote mark as ordinary characters in our string rather than as literal constructions. For a backslash to be regarded as an ordinary character (and not a control character), the escape character (i.e., a backslash) must appear before the backslash itself.

```js
let message1 = 'The vessel \'Mars\' called at the port.';
let message2 = "Cyclone \"Cilida\" to pass close to Mauritius.";
   
console.log(message1); // -> The vessel ‘Mars’ called at the port.
console.log(message2); // -> Cyclone “Cilida” to pass close to Mauritius.
   
let path = "C:\\Windows";
console.log(path); // -> C:\Windows
```
> You cannot do arithmetic operations on String-type values, such as subtraction, multiplication, or division. It usually ends in an error. More precisely, the NaN value will be returned as a result of the action.


>The exception is the addition operation, which is not seen as an arithmetic operation but rather as an attempt to blend two input strings into a single new string.
```js
let path = "C:\\" + "Windows";
console.log(path); // -> C:\Windows
   
let test = "100" + "10";
console.log(test); // -> 10010
console.log(typeof test); // -> string

let country = "Malawi";
let continent = "Africa";
   
let sentence = ` ${country} is located in ${continent}.`;
console.log(sentence); // -> Malawi is located in Africa.
```
> String-type data may be used for a variety of productive tasks. Unfortunately, they need the introduction of two new ideas: autoboxing and methods (and, indirectly, objects). 
An object’s method is a particular kind of function. Complex data types, known as objects, are made up of several values (stored in properties) and methods. 


### Undefined
The value of the undefined type is undefined. If no value is set to a variable following a declaration, it has the default value. Any variable may also be given the value undefined. However, this is generally not recommended since null is a better option for indicating that a variable doesn’t have any meaningful values.

### Symbol
It’s a new primitive type that was added to JavaScript in 2015. It doesn’t have any literal value and can only be created using a special constructor function. Symbols are a form of identifier that are guaranteed to be unique.


### Null
> The null value is used to indicate that the variable does not contain anything, and most often, it is a variable that is intended to contain values of complex types.












