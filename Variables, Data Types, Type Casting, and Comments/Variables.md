
# Variables 

## Naming Variables
> Variables are just like containers we use to store information. Each container comes with its own name. 

>We are free to choose any name for variables used in JavaScript. Still, the names we give variables should correlate with the variable content. Even if it does not, JavaScript does not particularly verify the relationship between the variable name and variable content. Still, it is good practice to give relatable names. Also, it makes it easy for you and others to understand the code.

>Like many programming languages, you must declare a variable before use. Variable declaration happens when you reserve the variable name. When we declare a variable, we are telling the program that at a later point in the execution, we'll refer to our container by this name to either get or save a value to it.

>Variable names in JavaScript can have any combination of lowercase and uppercase letters, numerals, underscore characters, and dollar signs, but they cannot begin with a digit. 

>The JavaScript interpreter treats names like test, Test, or TEST differently because it also differentiates between lowercase and upper-case letters in variable names.


>There are words that by default you should not use as variables names in JS. These words are:

|     |     |    |    |
| --- | --- | ---| ---|
| abstract | arguments | await | boolean | 
| break | byte | case | catch |
| char | class | const | continue|
| debugger | default | delete | do |
| double | else | enum | eval|
| export | extends | false | final |
| finally | float | for | function |
| goto | implements | if | import |
| in | instanceof | int | interface |
| let |	long |	native	| new |
| null	| package	| private | protected |
| public | return |short |static |
| super | switch | synchronized	| this |
| throw | throws | transient | true |
| try | typeof | var | void |
| volatile | while |with |yield |

***



## Declaring Variables
>Asides from reserving a name for a variable when delivering a variable, we reserve memory space. In JavaScript, we should not be concerned about what happens in the memory. 

>Since they are “variables,” the values kept in the variable will often be able to be changed while the program is running. Presently, we refer to them as constants instead of variables. We use the terms var or let for variables and const for constants in the declarations. 
e.g.
```js
var height;
console.log(height); // -> undefined
console.log(weight); // -> Uncaught ReferenceError: weight is not defined
```

>From the example above, we declared the variable. In the second line, the result will be undefined because we have not assigned any value to the variable height. In the third kine, we tried to see the contents of the weight variable. 

>The result will be ReferenceError because we did declare the variable. The variable in question is undefined because the JavaScript interpreter, which runs our program, has notified us that it is unaware of a variable by that name.

> We can use var or let. We can use them the same way, but they are not entirely the same.

>The term “var” originates from the original syntax of JavaScript, although “let” was added considerably later. Therefore, older programs tend to use var more often.

>“Let” stops us from declaring another variable with the same name (an error is raised). If you re-declare a variable using var, you might get execution errors. You may get away with it with simple code. However, the opposite is the case for complex programs.

>No matter whether let or var was used in the preceding declaration, the interpreter checks to see whether the variable has previously been defined.

## Initializing variables
>Initialization comes after variable declaration. A variable’s initialization involves giving it a name and a specific value. It is assigned using the operator =.

>A variable may be assigned a particular value, the contents of another variable, or, for instance, the output of a function.

>Initialization can be carried out either concurrently with the declaration or independently as a command. The initial value must be entered into it before attempting to read, edit, or display the variable.

>We can combine initialization, e.g.
```js
let height = 180;
let anotherHeight = height;
console.log(height); // -> 180
console.log(anotherHeight); // -> 180
```

>We can declare and initialize separately, e.g. 

```js
let weight;
weight = 70;
console.log(weight); // -> 70
```

>Note: When a variable name is specified in console.log, the interpreter detects it and shows the value of the variable. The same name will be considered as plain text and presented as such if you enclose it in quotation marks.


## Changing variable values
We can change the variable name in JavaScript to overwrite the former one.
E.g 
```js
let steps = 100;
console.log(steps); // -> 100
steps = 120; // -> 120
console.log(steps);
steps = steps + 200;
console.log(steps); // -> 320
```

>JavaScript Variables are untyped/weakly and dynamically typed. 

>This means that JavaScript has no will over the kind of data we give variables. In JavaScript, the two primary kinds in JavaScript are numbers and character strings.


## Constants
>We can use const to declare variables. Const indicate constants. Constants are also used to hold specific values, but they cannot be changed after initialization values have been placed into them. This indicates that the declaration and initialization of this kind of container occur concurrently.

>A constant eliminates the chance of unintentionally modifying a value that is kept in it. Paths to resources, tokens, and other pieces of information that don’t change during the course of the script are typical instances of constants.

>However, constants may also be used in areas where the information acquired or computed will remain unchanged, such as sub-results in computations. In addition to avoiding accidental value changes, using a const enables the JavaScript engine to optimize the code, which might impact performance.




## Scope
The scope of a variable depends on where it is declared. A program block is one of the fundamental components that affects the range of variables.

### Program blocks
We can put a program’s code in blocks. Usually, the blocks are connected to conditional statements, loops, or functions. Through the simple selection of a particular set of instructions, we can also divide a block of a program that is unconnected to anything particular.

E.g.
```js

let count;
console.log(count); // -> undefined
{
    count = 1;
    console.log(count); // -> 1
}
count = count + 1;
console.log(count); // -> 2
```

>We first declare the variable.
After that, we open a block where we initialize the variable and show its value. After the block, we add 1 to the value that is saved in the variable and re-display it. The interpreter will run the program as if it hadn’t seen the block in this situation, running through the instructions before, during, and after the block. This is only an example of employing brackets; there is no practical logic for creating a block without, say, conditional instructions.

>Nested program blocks allow us to build one block inside of another.

```JS

let count;
console.log(count); // -> undefined
{
    count = 1;
    {
    console.log(count); // -> 1
    }
}
count = count + 1;
console.log(count); // -> 2
```

>The block’s internal code has been shifted to the right. It is referred to as an indentation. Although it makes no difference to a JavaScript interpreter, doing so makes the code easier to comprehend by making it clear to readers—including you—which sections of the code are within and which are outside the block. Although indentations are often added in the proper locations by code editors by default, it is a good practice to keep this in mind and manually format the code if necessary.

### let and const
>Any variable or constant that is declared outside of code blocks using let or const will be considered global. This means that their names will be shown throughout the program, including outside of blocks, inside of blocks, in functions, and elsewhere. We shall have access to their values and be able to refer to them by their names wherever we are.

>Declaring something within a block using let or const establishes a local constant or variable. Only the block in which it was defined and, optionally, any blocks that are nested inside of that block will be able to see it.



## A brief word about functions
>Sometimes, we can use a certain code that we need to carry out a particular task multiple times. However, it makes our program’s size inevitably expand. Second, every location where we utilized this piece of code would need to be changed if we wanted to update it, for example, to fix a defect.

>This issue has a straightforward solution: a function. Like a variable, a function is just a distinct section of code that you may name. Simply use that name to refer to it when utilizing it elsewhere (we say that we call the function).
E.g 
```js
function testFunction() {
    console.log("Hello");
    console.log("World");
}
```

>The function keyword comes first in the definition, then the function name that we came up with. You can see parentheses behind the function name, which may or may not include arguments that were supplied to the function. The program block, which houses the function’s instructions, is then opened. The instructions of a function are not carried out when it is defined. The function must be called separately by name in order to be used.

E.g.:
```js
console.log("Let’s begin:"); // -> let's begin:
console.log("Hello"); // -> Hello
console.log("World"); // -> World
console.log("and again:"); // -> and again:
console.log("Hello"); // -> Hello
console.log("World"); // -> World
console.log("and once more:"); // -> and once more:
console.log("Hello"); // -> Hello
console.log("World"); // -> World
```
It will print out:

Let’s begin:
Hello
World
and again:
Hello
World
and once more:
Hello
World
