### Conversions
> Having one kind of value while needing another type of value is a rather typical occurrence. The most straightforward instance is when a number has to be added to some text. In JavaScript, conversions may be applied manually or automatically in certain circumstances by using methods like String() and Number(). 


> This code demonstrates the conversion of different data types (string, number, boolean, bigint, undefined, and null) to strings using the String() constructor or template literals. It also shows how the type and value change after the conversion.

Example:

- String Conversion for a Text (str):

```js
let str = "text";
let strStr = String(str);
console.log(`${typeof str} : ${str}`);       //  ->  string : text
console.log(`${typeof strStr} : ${strStr}`); //  ->  string : text
```
Here, a variable str is assigned the value “text.” It is then explicitly converted to a string using String(str). The console.log statements display the type and value before and after the conversion.

- String Conversion for a Number (nr):

```js
let nr = 42;
let strNr = String(nr);
console.log(`${typeof nr} : ${nr}`);         //  ->  number : 42
console.log(`${typeof strNr} : ${strNr}`);   //  ->  string : 42
```

> Similarly, a number (42) is converted to a string, and the type and value are displayed before and after the conversion.

- String Conversion for a Boolean (bl):

```js
let bl = true;
let strBl = String(bl);
console.log(`${typeof bl} : ${bl}`);          //  ->  boolean : true
console.log(`${typeof strBl} : ${strBl}`);   //  ->  string : true
```
> A boolean (true) is converted to a string, and the type and value are displayed before and after the conversion.

- String Conversion for a BigInt (bnr):

```js
let bnr = 123n;
let strBnr = String(bnr);
console.log(`${typeof bnr} : ${bnr}`);        //  ->  bigint : 123
console.log(`${typeof strBnr} : ${strBnr}`); //  ->  string : 123
```
> A BigInt (123n) is converted to a string, and the type and value are displayed before and after the conversion.

- String Conversion for Undefined (un):

```js
let un = undefined;
let strUn = String(un);
console.log(`${typeof un} : ${un}`);          //  ->  undefined : undefined
console.log(`${typeof strUn} : ${strUn}`);   //  ->  string : undefined
An undefined variable is converted to a string, and the type and value are displayed before and after the conversion.
```
- String Conversion for Null (n):

```js
let n = null;
let strN = String(n);
console.log(`${typeof n} : ${n}`);           //  ->  object : null
console.log(`${typeof strN} : ${strN}`);    //  ->  string : null
```
> A null value is converted to a string, and the type and value are displayed before and after the conversion.

> String() constructor or template literals can be used to convert various data types to strings in JavaScript. The resulting string value may not always precisely represent the original type, as seen in the case of null being displayed as an “object.”




### Conversion to Number
Not as evident as conversion to a string is conversion to a number. For strings that represent real numbers, such as “14,” “-72.134,” or strings that represent numbers in scientific notation, such as “2e3, or unusual number values, such as “NaN” or “Infinity,” it functions as intended.
But hexadecimal, octal, and binary integers can also be found in the text. They each need to come before 0x, 0o, or 0b. Any string that cannot be changed into a special value is returned as NaN (not a number). A BigInt can also be converted to a Number, but it’s important to keep in mind that it can contain considerably larger values than a Number, meaning that huge values may be partially truncated or become inaccurate. Many computer languages transform the Boolean values true and false to 1 and 0, respectively. Undefined values will try to be converted to NaN, whereas null values will attempt to be converted to 0.
```js
console.log(Number(42)); // -> 42
   
console.log(Number("11")); // -> 11
console.log(Number("0x11")); // -> 17
console.log(Number("0o11")); // -> 9
console.log(Number("0b11")); // -> 3
console.log(Number("12e3")); // -> 12000
console.log(Number("Infinity"));// -> Infinity
console.log(Number("text")); // -> NaN
   
console.log(Number(14n)); // -> 14
   
console.log(Number(true)); // -> 1
console.log(Number(false)); // -> 0
   
console.log(Number(undefined)); // -> NaN
   
console.log(Number(null));// -> 0
```
### Conversion to Boolean
Boolean conversions adhere to straightforward principles as there are only two possible values: true or false. You will get the value false for:
0,
NaN,
empty string,
undefined,
null
Any other value will result in true being returned.
```js
console.log(Boolean(true)); // -> true
console.log(Boolean(42)); // -> true
console.log(Boolean(0)); // -> false
console.log(Boolean(NaN)); // -> false
   ```
### Conversion to BigInt
We need a Number or String that represents a number as the value to be converted in order for conversions to a BigInt to be successful. Values for conversion can be in hexadecimal, octal, binary, or the conventional decimal form. This is true for both cases in which we provide the Number and String literals (or variables storing data of both kinds) as arguments. Exponential notation is another option, but it is limited to Number arguments. When a given value cannot be converted to a BigInt, conversion to a BigInt will raise an error and terminate the application.
```js
console.log(BigInt(11)); // -> 11n
console.log(BigInt(0x11)); // -> 17n
console.log(BigInt(11e2)); // -> 1100n
console.log(BigInt(true)); // -> 1n
console.log(BigInt("11")); // -> 11n
console.log(BigInt("0x11")); // -> 17n
console.log(BigInt(null)); // -> Uncaught TypeError: Cannot convert null to a BigInt
console.log(BigInt(undefined)); // -> Uncaught TypeError: Cannot convert undefined to a BigInt
console.log(BigInt(NaN)); // -> Uncaught RangeError: The number NaN cannot be converted to a BigInt because it is
```