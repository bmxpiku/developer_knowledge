### 1. STRING TEMPLATE
   concatenating string using +, can now be done using`

OLDER VERSION:
```javascript
var message = "The user "+ user.firstName + "" + user.lastName +
" cannot be "+ action + "because "+ validationError;
```

NEWER VERSION:
```javascript
var message = `The user ${user.firstName} ${user.lastName} cannot be
${action} because ${validationError}`;
```

NOTE:
The hard line-break between be and ${action} is because backtick strings are also “multiline literals.” This means that whitespace is preserved within the string, so the message above would appear on two lines. It would break after “be,” then display two spaces (because the code indents two spaces) before continuing.

### 2. VARIABLE DECLARATION
var declared variables could be reassigned, so we now have let keyword that don’t allow that. Rest all is same.

```javascript
var msg = "Howdy";
var msg = "Hello there"; // acceptable, just reassigns
```
On the other hand:
```javascript
let message = `This is your message.`;
let message = `This is another message.`; // ERROR! can't redeclare the earlier declared variable message
```
### 3. CONST KEYWORD
Same as final in java and const in C/C++
```javascript
const message = `This is your message.`;
message = `This is your second message.`; // ERROR! can't reassign a const variable
```
### 4. BLOCK SCOPE
var declared variables were not blocked scope but function scoped.let and const declared variabled will be scoped in the block they are declared.

### 5. DESTRUCTURING ASSIGNMENT
It breaks an array into its elements, keeping the original array unchanges. This process assignes the variables with items in the corresponding positions.

EXAMPLE:
```javascript
let names = [“Ted”, “Jenni”, “Athen”];
let [ted, jenni, athen] = names;
console.log(ted, jenni, athen); // prints “Ted Jenni Athen”
//SIMILAR TO THE FOLLOWING:
var ted = names[0];
var jenni = names[1];
var athen = names[2];
```
### 6. DESTRUCTURING IN OBJECTS
EXAMPLES:

```javascript
var url = "http://www.newardassociates.com/#/speaking";
var parsedURL = /^(w+)://([^/]+)/(.*)$/.exec(url);
var [protocol, fullhost, fullpath] = parsedURL;
console.log(protocol); // “http”
let point = { x:2, y: 5 };
let {x, y} = point;
console.log(x, y); // prints 2, 5
let point = { x:2, y: 5 };
let {y, x} = point;
console.log(x, y); // prints 2, 5
let {y: pty, x: ptx} = point;
console.log(ptx, pty); // prints 2, 5
```
left-hand side indicating the name to match, and the right-hand side indicating the actual declared variable name:
```javascript
let rect = { lowerLeft: { x:0, y:0 }, upperRight: { x:3, y:4} };
let { lowerLeft: { x:llx, y: lly }, upperRight: { x:urx, y:ury } }
= rect;
console.log(llx, lly, urx, ury); // prints “0 0 3 4
```
### 7. DESTRUCTURING OBJECT PRAMETERS IN A METHOD CALL
```javascript
   let person = {
       firstName: "Ted",
       lastName: "Neward",
       age: 45,
       favoriteLanguages: ["ECMAScript", "Java", "C#", "Scala", "F#"]
   }
   function displayDetails({firstName, age}) {
      console.log(`${firstName} is ${age} years old`);
   }
   displayDetails(person);
```
### 8. DEFAULT PARAMETER
Now we can provide the default values of the function variables just like C/C++
```javascript
let sayHello = function(message = "Hello world!") {
  console.log(message);
}
sayHello(); // prints "Hello world!"
sayHello("Howdy!"); // prints "Howdy!"
```
### 9. REST PARAMETERS TO A FUNCTION: PASSING A LIST OF ARGUMENTS
Historically, you might have done this by accessing the built-in argumentsparameter that is silently constructed and passed to every function call:

IF THE VALUES PASSED IN THE EXISTING FUNCTION EXCEEDED THE DEFINED THEN THEY WERE ADDED TO THE arguments.

Those were accessed through:
```javascript
var args = Array.prototype.slice.call(arguments, <function-name>.length);
```
IN ES6 WE NOW HAVE JAVA STYLE SYNTAX TO CAPTURE A LIST OF VALUES
EXAMPLE:
```javascript
function greet(firstName, …args) {
console.log("Hello",firstName);
args.forEach(function(arg) { console.log(arg); });
}
greet("Ted");
greet("Ted", "Hope", "you", "like", "this!");
```
### 10. SPREAD PARAMETERS: OPPOSITE TO REST PARAMETERS
This destructurs an array into individual parts and simplest use case is to concatanate arrays.
```javascript
let arr1 = [0, 1, 2];
let arr2 = [...arr1, 3, 4, 5];
console.log(arr2); // prints 0,1,2,3,4,5
//IMPORTANT USECASE:
function printPerson(first, last, age) {
console.log(first, last, age);
}
let args = ["Ted", "Neward", 45];
printPerson(...args);
```
### 11. ARROW OPERATOR FOR THE FUNCTION
The keyword of function can now be droped using => fat arrow operator.

EXAMPLE:
```javascript
function(arg1, arg2){//something here}
The above can now be written as:
(arg1, arg2) => {//something here}
```
NOTE:
Also note that if the body of the arrow function is a single expression yielding a value, no explicit return is required. Instead, that single expression is implicitly returned to the arrow function’s caller. If, however, the body is more than one statement or expression, the curly brackets are mandatory, and any returned value must be sent back to the caller via the usual return syntax.

### 12. TO ITERATE OVER THE ARRAY
```javascript    
let arr = ["janishar", "ali", "anwar"]
let displayArr = function(arr) {
    for (let x in arr) {
        console.log(x);
    }
};
```
### 13. this scope 
IF `this` IS REFERENCED FROM THE GLOBAL SCOPE THEN IT REFERS TO THE GLOBAL VARIABLES, FUNCTIONS, AND OBJECTS.
    `this` REFERS TO THE PARENT OBJECT ON WHICH THE FUNCTION IS CALLED.

EXAMPLE:
```javascript
let displayThis = function() {
    for (let m in this) {
    console.log(m);
  }
};
displayThis(); // this == global object
let bob = {
    firstName: "Bob",
    lastName: "Robertson",
    displayMe: displayThis
};
bob.displayMe(); // this == bob
```

### 14. IN NODE JS `require(‘events’)` IS A PUB-SUB MODULE
```javascript    
let EventEmitter = require('events');
let ee = new EventEmitter();
ee.on('event', function() {
    console.log("function event fired", this);
});
ee.emit('event');
```
NOTE:
If you register a legacy function with the EventEmitter, the this captured will be the one determined at runtime. But if you register an arrow function with the EventEmitter, this will be bound at the time the arrow function is defined:

### 15. GENERATOR FUNCTION: SIMILAR TO STREAMS IN REACTIVE PROGRAMMING
    Infinte stream is implemented using GENERATOR in ES6.

EXAMPLE:
```javascript
function* getName() {
    yield “Ted”;
    yield “Charlotte”;
    yield “Michael”;
    yield “Matthew”;
}
let names = getName();
console.log(names.next().value);
console.log(names.next().value);
console.log(names.next().value);
console.log(names.next().value);
console.log(names.next().value);
```
The function will print each name in order. When it runs out of names it will print undefined.

### 16. FOR-OF KEYWORD
    The for-of keyword is similar to for-in.

There’s a subtle difference between for-of and for-in, but for the most part you can use for-of as a drop-in replacement for the older syntax. It just adds the ability to use generators implicitly

### 17. JAVASCRIPT OBJECT BASED ENVIRONMENT
    Javascript it not a class based but and object based environment. In an object based environment, there is no classes, each object is cloned from other existing objects. When an object is cloned, it retains an emplicit reference back to its prototype.

### 18. DEFINING A CLASS
```javascript    
class Person{}
let p = new Person();
```
### 19. CONSTRUCTOR OF A CLASS
```javascript
class Person{
    constructor(firstName, lastName, age){
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }
}
let ted = new Person("Ted", "Neward", 45);
console.log(ted);
```
### 20. GETTER AND SETTER
```javascript
class Person {
    constructor(firstName, lastName, age) {
        console.log(arguments);
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }
    get firstName() { return this._firstName; }
    set firstName(value) { this._firstName = value; }
    get lastName() { return this._lastName; }
    set lastName(value) { this._lastName = value; }
    get age() { return this._age; }
    set age(value) { this._age = value; }
}
```
NOTE:

this._<field_name> referes to the <field_name> variable added through the constructor.

### 21. PROTOTYPE CHAIN
Since its earliest days, JavaScript has maintained a prototype chain from one object to another. You might assume that prototype chaining is similar to inheritance in Java or C++/C#, but there’s only one real similarity between the two techniques: When JavaScript needs to resolve a symbol that isn’t already directly on the object, it looks along the prototype chain for a possible match.

### 22. INHERITENCE
```javascript
class Author extends Person{
    constructor(firstName, lastName, age, subject){
        super(firstName, lastName, age);
        this.subject = subject;
    }
    get subject() { return this._subject; }
    set subject(value) { this._subject = value; }
    writeArticle() {
        console.log(
        this.firstName,
        "just wrote an article on",
        this.subject
        );
    }
}
let mark = new Author("Mark", "Richards", 55, "Architecture");
mark.writeArticle();
```
### 23. STATIC OR SINGLETON
    static field:

ECMAScript 6 makes no explicit provision for static properties or fields but we can create on indirectly.
```javascript
class Person{
constructor(firstName, lastName, age){
console.log(arguments);
// Just introduce a new field on Person itself
// if it doesn’t already exist; otherwise, just
// reference the one that’s there
if (typeof(Person.population === 'undefined'))
Person.population = 0;

        Person.population++;

        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }
//...as before
}
static function:
```
To define a static method you’d use the static keyword in the class declaration for defining a function:
```javascript
class Person{
//...as before
    static haveBaby() {
    return Person.population++;
    }
}
```
### 24. MODULE: IMPORT AND EXPORT :

It is not supported in nodejs as of 19th May 2017

EXPORT:

If you have a file that you want to treat as a module 
— let’s call it output — you’ll simply export the symbols you want to be able to use elsewhere, like so:

Listing 1. Exporting an output function

// output.js
```javascript
export function output() {
console.log("OUT: ", arguments);
}
```
IMPORT:
```javascript
import { out } from 'output.js';
out("I'm using output!");
```
In order to use the module, you have to know all the names you wish to import. (Though some might consider this a benefit, because it ensures that no symbols will be imported without the importer’s knowledge.) If you want to grab all the exported names from a module, you can use the wildcard (*) import syntax, but then you need to define a module name where you want to scope them:

WILD CARD IMPORT
```javascript
import * as Output from 'output';// you can also drop .js
Output.out("I'm using output!");
```
### 25. SYMBOL
Symbol is a type. An instance of Symbol is a unique name that cannot be duplicated anywhere else. It is used to hold a value in secure way. Symbol’s primary function is to help programmers avoid name clashes across libraries. It’s a little awkward to grasp at first, but try thinking of Symbol as a unique hash based on the string name it’s fed.

### 26. COLLECTION:
Array, Map and Set

MAP: A Map is a set of name/value pairs.

It contains methods get() and set(), it finds and sets key/value pairs, respectively
clear() will empty the collection entirely
keys() returns an iterable collection of the keys in the Map
values() does the same for the values
Also, like Array, Map includes functional-language-inspired methods like forEach(), which operate on the Map itself.

EXAMPLE:
```javascript
let m = new Map();
m.set('key1', 'value1');
m.set('key2', 'value2');
m.forEach((key, value, map) => {
    console.log(key,'=',value,' from ', map);
})
console.log(m.keys());
console.log(m.values());
```
SET:

Set, more like a traditional object collection, in that objects can simply be added to the collection. But Set will examine each object in turn to ensure that it is not a duplicate of a value already present within the collection.

EXAMPLE:
```javascript
let s = new Set();
s.add("Ted");
s.add("Jenni");
s.add("Athen");
s.add("Ted"); // duplicate!
console.log(s.size); // 3
```
### 27. WEAKREFERENCE
WeakMaps and WeakSets, which are Maps and Sets that hold their values through weak references, rather than the traditional strong reference.

### 28. PROMISE
Promise in now inbuilt in the ES6. (We will cover promise in a separate article.)

### 29. PROXIES
Proxy let to change behavior to an existing object before its accessed.
```javascript
const target = {
    message1: "hello",
    message2: "everyone"
};

const handler2 = {
    get: function(target, prop, receiver) {
      return "world";
    }
};

const proxy2 = new Proxy(target, handler2);
console.log(proxy2.message1); // world
console.log(proxy2.message2); // world
```
