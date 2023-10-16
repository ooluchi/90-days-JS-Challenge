## Complex Data Types

### Objects
>There are several uses for objects in JavaScript. The simplest method is to use it as a structure known as a record in computer science. A record is made up of many named fields. Each field is given a unique name (or key) and value. These fields are often referred to as properties in the context of JavaScript objects. You may store several values of various sorts in the same location by using records or, in our case, objects. The simplest and quickest method to build objects in JavaScript is by using the curly bracket literal.
e.g.
```js
let testObj = {};
console.log(typeof testObj); // -> object
The above object is empty. It does not have any defined fields, i.e., anykey–value pairs. The example below defines an object containing two fields with keys nr and str.


let testObj = {
nr: 600,
str: "text"
};
```

>We created objects using the same literal and properties that are key–value pairs. Commas separate the properties. A specific property (field) of an object can later be referred to with dot notation. This notation requires the name of the object (a literal or the name of a variable containing the object) to be followed by a dot, followed by the field name (key) again.

```js
console.log(testObj.nr); // -> 600
console.log(testObj.str); // -> text
```
We use objects to store multiple values in one place. These values are usually linked to each other for some reason.
If we gather info about users in a system, the info consists of the users’ first name, last name, age, and email address. 
The code this without using objects will be.

```js
let name1 = "Calvin";
let surname1 = "Hart";
let age1 = 66;
let email1 = "CalvinMHart@teleworm.us";
   
let name2 = "Mateus";
let surname2 = "Pinto";
let age2 = 21;
let email2 = "MateusPinto@dayrep.com";
```
>This looks okay but has some drawbacks. 
One, you’ll need to create unique names for each user’s last name, email address, and other data. What if we provided a more detailed description of each user? Or what if there were, say, 1,000 users instead of only two? In such a case, it would be, at the very least, annoying. We can organize it with objects to some degree. The second issue is that we need to know the precise number of people who will be described in the system even before we start coding. This would severely constrain real-world applications; thus, it would be preferable to be able to add them dynamically. With the help of objects, we can also make this better.
The improved code with objects:

```js
let user1 = {
    name: “Calvin”,
    surname: “Hart”,
    age: 66,
    email: “CalvinMHart@teleworm.us”
};
   
let user2 = {
    name: “Mateus”,
    surname: “Pinto”,
    age: 21,
    email: “MateusPinto@dayrep.com”
};
```
>The variables that hold information (in the form of objects) about certain users still need separate names. Still, this time, the attributes could have the same names. In addition to making the code cleaner and more uniform, this also makes it simpler to carry out operations on various users’ attributes.

>We can use a dot and a key name are used to access an object’s properties. The value connected to a certain key is accessible for both reading and editing. Furthermore, we can change the whole object by introducing a brand-new attribute that was not before there. Additionally, we accomplish this using dot notation; if the interpreter cannot locate the key we give when trying to alter the property, it will create it.

```js
console.log(user1.name); // -> Calvin
console.log(user2.name); // -> Mateus
   
console.log(user1.age); // -> 66
user1.age = 67;
console.log(user1.age); // -> 67
   
console.log(user2.phone); // -> undefined
user2.phone = "904-399-7557";
console.log(user2.phone); // -> 904-399-7557
```
We can remove fields from an existing one using the delete operator.
```js
console.log(user2.phone); // -> 904-399-7557
delete user2.phone;
console.log(user2.phone); // -> undefined
```
>There are many more ways to use things than only as data storage systems. It is a distinct subject primarily associated with object-oriented programming, a more sophisticated programming method. In this instance, objects will be simple structures made up of key-value pairs.