## Complex Data Types
### Array
>An array is a complex data type that can be used to hold a data collection, much like an object. The values that make up the saved data may be of any type, just like an object. In contrast to these structures, an array merely stores values, not the names (i.e., keys) that go along with them.

>The members of the array are ordered (although not necessarily sorted) and occupy consecutive, numbered locations inside it. As a result, we always know which element of the array we are referring to, even if we cannot identify it by name. An index or position refers to the number of fields in the array containing a certain value. Indexing begins at zero.

>Square brackets (an array literal) are the simplest method to generate arrays in JavaScript. Using this technique, you can build an array that is both empty and waiting to have items added to it later, as well as an array that already has some beginning components (comma-separated). When referencing a specific array element, we write the index of the element we are interested in within a square parenthesis following the name of the array variable.

Eg
```js
let days = [“Sun”, “Mon”, “Tue”, “Wed”, “Thu”, “Fri”, “Sat”];
console.log(days[0]); // -> Sun
console.log(days[2]); // -> Tue
console.log(days[5]); // -> Fri
   
days[0] = "Sunday";
console.log(days[0]); // -> Sunday
   
let emptyArray = [];
console.log(emptyArray[0]); // -> undefined
```
>From the example, we first declare and initiate the days array. The day has seven shortened days of the week names. Given that the array’s indexes (item positions) begin at 0, we first display three selected days of the week on the console before changing the element at index 0 to have the value “Sunday” instead. The last line of code declares an empty array and attempts to read an element that doesn’t exist from it.

>We can add a new element to an already-existing array by using s-bracket notation to change a position’s value. If anything is included in this index already doesn’t matter to the interpreter. Just a new value is introduced. 
```js
let animals = [];
console.log(animals[0]); // -> undefined
   
animals[0] = "dog";
animals[2] = "cat";
   
console.log(animals[0]); // -> dog
console.log(animals[1]); // -> undefined
console.log(animals[2]); // -> cat
```
>We define an empty animal array in the example. Then, we fill places 0 and 2 with “dog” and “cat” while keeping position 1 vacant. However, there are additional methods of adding new members to the array and removing existing ones, which we shall discuss in a minute.

>The same kind of data is often kept in a single array. However, JavaScript does not mandate this. As a result, it is simple to build an array with items of various kinds.


>The components of this layered array may be accessed by employing several square brackets, and we can also store arrays as elements of the array.
```js
let names = [[“Olivia”, “Emma”, “Mia”, “Sofia”], [“William”, “James”, “Daniel”]];
console.log(names[0]); // -> [“Olivia”, “Emma”, “Mia”, “Sofia”]
console.log(names[0][1]); // -> Emma
console.log(names[1][1]); // -> James
   
let femaleNames = names[0];
console.log(femaleNames[0]); // -> Olivia
console.log(femaleNames[2]); // -> Mia
```
>The example shows an array declaration with two more arrays as its components. While it’s needed in many other programming languages, the internal arrays need not all have the same length.

>The instanceof operator is a two-argument operator, which requires the tested variable (or literal) and object class to be specified.


#### Length
>The length property can be used to determine the array’s length (the number of items) and the empty spaces between its members.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
console.log(names.length); // -> 4
   
names[5] = "Amelia";
console.log(names.length); // -> 6
   
console.log(names); // -> [“Olivia”, “Emma”, “Mateo”, “Samuel”, undefined, “Amelia”]
console.log(names[3]); // -> Samuel
console.log(names[4]); // -> undefined
console.log(names[5]); // -> Amelia
```
#### IndexOf
>To find a specific value in the array, use the indexOf method. The index (position) of the value will be returned if the value is discovered (the element is in the array). If the element cannot be found, the function returns -1. The index of the first element in the array is returned if many elements are in the array with the same value.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
console.log(names.indexOf("Mateo")); // -> 2
console.log(names.indexOf("Victor")); // -> -1
```
#### Push
The push function adds the element supplied as its argument to the end of the array. The array’s length is extended by 1, and the new element—which has the biggest index of all elements—is placed on the right.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
console.log(names.length); // -> 4
names.push("Amelia");
console.log(names.length); // -> 5
console.log(names); // - > [“Olivia”, “Emma”, “Mateo”,
[“Samuel”, “Amelia”]
```
#### Unshift
The difference between the unshift method and push is that a new element is added to the beginning of the array. The new element is inserted into the newly formed vacant space at the beginning of the array after the array length is extended by one, and all previous items are relocated to the right. The new element has an index of 0.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
console.log(names.indexOf("Mateo")); // -> 2
console.log(names.indexOf("Victor")); // -> -1
```
#### Pop
The pop method gets rid of the last element from an array. After being executed, the biggest index element is returned and dropped from the initial array. Of course, this results in a reduction of 1 in the array’s length.
```js
let names= [“Olivia”, “Emma”, “Mateo”, “Samuel”];
console.log(names.length); // -> 4
   
let name = names.pop();
console.log(names.length); // -> 3
console.log(name); // -> Samuel
console.log(names); // -> [“Olivia”, “Emma”, “Mateo”]
```
#### Shift
In contrast to pop, the shift technique involves removing the element from the array’s index 0 at the beginning. It moves all other components to the left to fill up the vacant space when the method returns the deleted element. It cuts the original array length by 1.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
console.log(names.length); // -> 4
   
let name = names.shift();
console.log(names.length); // -> 3
console.log(name); // -> Olivia
console.log(names); // -> [“Emma”, “Mateo”, “Samuel”]
```
#### Reverse
The array items’ order is reversed with the reverse method. The first member of the original array will become the last, followed by the second element as the last but one.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
   
names.reverse();
console.log(names); // -> [“Samuel”, “Mateo”, “Emma”, “Olivia”]
```
#### Slice
You can build a new array using just a subset of the components in the old array by using the slice technique. The initial array is unaffected by using the technique. The method accepts either one or two inputs that are integer values.

>The basic combinations are:

- One argument larger than zero – all elements from the index given as an argument to the end of the array are copied;
- two arguments larger than zero – the element from the index specified as the first argument to the element specified as the second argument are copied;
- two arguments, first positive, second negative – all elements from the specified index to the end of the array are copied, except for the specified number of the last elements (e.g., argument -3 means that we do not copy the last three elements)
- one negative argument – the specified number of the last elements are copied to the end of the array (e.g., -2 means that you copy the last two elements).
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
   
let n1 = names.slice(2);
console.log(n1); // -> [“Mateo”, “Samuel”]
   
let n2 = names.slice(1,3);
console.log(n2); // -> [“Emma”, “Mateo”]
   
let n3 = names.slice(0, -1);
console.log(n3); // -> [“Olivia”, “Emma”, “Mateo”]
   
let n4 = names.slice(-1);
console.log(n4); // -> ["Samuel"]
   
console.log(names); // -> [“Olivia”, “Emma”, “Mateo”, “Samuel”]
```
#### Concat
The concat method adds items from the array provided as an argument to the original array elements to generate a new array. Both the initial array and the array supplied as an input remain unchanged by the method.
```js
let names = [“Olivia”, “Emma”, “Mateo”, “Samuel”];
let otherNames = [“William”, “Jane”];
let allNames = names.concat( otherNames);
   
console.log(names); // -> [“Olivia”, “Emma”, “Mateo”, “Samuel”]
console.log(otherNames); // -> [“William”, “Jane”]
console.log(allNames); // -> [“Olivia”, “Emma”, “Mateo”, “Samuel”, “William”, “Jane”]
```

