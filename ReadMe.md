# A Short tutorial for Google Assistant Event. Node.js 
I put here the most valuable information for Javascript, Node.js, MongoDb and Google Home. I collected some data and examples from different sources. You find a list all of them at the end of every section. :) 

**Table of content** 
- [Javascript code examples](#id-section1) 
- [Node.js](#id-section2) 
- [Google Assistant](#id-section3) 

## Javascript Code examples <div id='id-section1'/> 
Node.js is based on Javascript. 
Examples come from: https://www.tutorialspoint.com/javascript/ 
### JavaScript Variables
```javascript
var name = "Ali";
var money;
money = 2000.50;
```
### Variable Scope
```javascript
var myVar = "global"; // Declare a global variable
function checkscope( ) {
	var myVar = "local";  // Declare a local variable
             console.log(myVar);
}
```
### Operator and Description

+ +(Addition) 
	+ Adds two operands Ex: A + B will give 30 

+  -(Subtraction) 
	+ Subtracts the second operand from the first Ex: A - B will give -10 

+ *(Multiplication)
	+  Multiply both operands Ex: A * B will give 200 

+ / (Division)
	+  Divide the numerator by the denominator Ex: B / A will give 2 

+ % (Modulus) Outputs the remainder of an integer division Ex: B % A will give 0 

+ ++ (Increment)
	+  Increases an integer value by one Ex: A++ will give 11 

+ -- (Decrement)
	+  Decreases an integer value by one Ex: A-- will give 9

### Logical Operators
 + && (Logical AND)
	+  If both the operands are non-zero, then the condition becomes true. Ex: (A && B) is true.

 + || (Logical OR) 
	+ If any of the two operands are non-zero, then the condition becomes true. Ex: (A || B) is true. 

 + ! (Logical NOT)
	+  Reverses the logical state of its operand. If a condition is true, then the Logical NOT operator will make it 

 + false. Ex: ! (A && B)
	 +  is false. Assignment Operators

### Operator and Description
+ = (Simple Assignment )
	+ Assigns values from the right side operand to the left side operand
	Ex: C = A + B will assign the value of A + B into C

+ += (Add and Assignment)
	+ It adds the right operand to the left operand and assigns the result to the left operand.
	Ex: C += A is equivalent to C = C + A

+ −= (Subtract and Assignment)
	+ It subtracts the right operand from the left operand and assigns the result to the left operand.
	Ex: C -= A is equivalent to C = C - A

+ *= (Multiply and Assignment)
	+ It multiplies the right operand with the left operand and assigns the result to the left operand.
	Ex: C *= A is equivalent to C = C * A

+ /= (Divide and Assignment)
	+ It divides the left operand with the right operand and assigns the result to the left operand.
	Ex: C /= A is equivalent to C = C / A

+ %= (Modules and Assignment)
	+ It takes modulus using two operands and assigns the result to the left operand.
	Ex: C %= A is equivalent to C = C % A

### if...else statement
```javascript
var age = 15;

if( age > 18 ){
   console.log("Qualifies for driving");
}
else{
   console.log("Does not qualify for driving");
}

```
### For Loop
```javascript
var count;
console.log ("Starting Loop");

for(count = 0; count < 10; count++){
   console.log ("Current Count : " + count );
   console.log ("");
}

console.log ("Loop stopped!");
```
### Declaring array
```javascript
var fruits = [ "apple", "orange", "mango" ];
fruits.length; 

```
### Declaring function
```javascript
function sayHello(name)
{
	cosole.log("Hello "+name);
}

sayHello(“Tomasz”)

```
### Anonymous function

```javascript
var greetMe = function(){
	console.log(“hi”);
}

greetMe();
```

### Objects
You can see an object as a such block of values

```javascript
var person = {
	firstName: "Tomasz",
	lastName: "Krajewski",
	greet:	function(){
		console.log('Hello '+this.firstName + " " + this.lastName);
	}
};

person.greet();

console.log(person.firstName);
console.log(person['firstName'];

```
remember you can get your object value in the two ways:
```javascript
person.firstName
```
or
```javascript
person[‘firstName’]
```

### Node api 
https://nodejs.org/api/index.html
```javascript
var util = require(‘util’)
var greeting = util.format(‘Hello, %s’, name);
util.log(greeting)

```

### Class example
```javascript
‘use strict’

class Person {
	constructor(firstname, lastname){
		this.firstname = firstname;
		this.lastname = lastname;
}

greet(){
console.log(‘Hello ’+ this.firstname)
}

}
```
### Callbacks

callback is a function passed to some other function, which we assume will be invoked at some point. The function “call back” invoking the function you give it when it is done doing its work.

```javascript
function greet(callback) {
	console.log(‘Hello’);
	callback();
}
```
if Im done with my greet function I invoke callback function

take a look at an example:

```javascript
function greet(callback) {
	console.log(‘Hello’);
	var data = {
		name: ‘John’
	};
	callback(data);
}

greet(function(data){
	console.log(‘the callback was invoked’);
	console.log(data);
});
```
the function I invoked will invoke function I will give.

#### Callbacks alternative syntax

```javascript
fs.readFile('names.txt', function (err, content){
	console.log(content);
});

// We will get the same output
var callback = function (err, content){
	console.log(content);
};
fs.readFile('names.txt', callback);
});
 
```

### Files 

We can use synchronous convention: 

```javascript
var fs = require(‘fs’);

//it reads binary data
var greet = fs.readFileSync(__dirname+ ‘/greet.txt’, ‘utf-8’);

console.log(greet);
```
Do you see differences with asynchronous example? What will happens if you call greet variable? You checked both examples and you know why you got undefined in the second one you can read next pages ;)

```javascript
var fs = require('fs');

//it reads binary data
var greet = fs.readFile('greet.txt','UTF-8', function(err, data){
        console.log(data);
});

console.log(greet);

```

Error-first callback: Callbacks take an error object as their first parameter
null if no error, otherwise will contain an object defining the error. This is a standard so we know in what order to place our parameters for our callbacks.

### Asynchronous programming
If you ddnt understand first example with file reading just relax and try to understand how asynchronous work.
let's take a look on php code which can be equivalent to any your language like java or python. Whatever

```php
//find my file and give me a handler so I can start operations
$file = fopen(‘test.txt’, ‘r’);
//just see it like a buffer ;)
$contents = fread($file, 100000);
echo $contents;
fclose($file)
```

It spends a lot of time doing nothing executing all instructions step by step

How could something works in Nodejs?

```javascript
var fs = require(‘fs’);

var file;
var buf = new Buffer(100000);

fs.open(‘test.txt’, ‘r’, (err, handle) => {

	file = handle;

});

fs.read(file, buf, 0, 100000, null, (err, length) =>{
	console.log(buf.toString())
fs.close(file, {} => {});
});

```

Let see another example:
```javascript
setTimeout( () => {
	console.log(“I have done my work);
}, 4000);
console.log(“Im waiting that everything will finish”);
```

Before you execute code, ask yourself what you get from the console first?
Easy because it was still something in the event queue


```javascript
var fs = require(‘fs’)

var file;

var buf = new Buffer(100000);

fs.open(‘test.txt’, ‘r’, (err, handle)=> {
	fs.read(handle, buf, 0, 100000, null, (err, length) => {
		console.log(buf.toString(‘utf8’, 0, length));
		fs.close(handle, () => {});
	});
});
```

In that we emulate code from listing …

1 it takes all parametrs and check everything
2. It push this function to event stack
	fs.read(handle, buf, 0, 100000, null, (err, length) => {
		console.log(buf.toString(‘utf8’, 0, length));
		fs.close(handle, () => {});
	});

## Promise

The promise as an abstracrion which tries to cover asynchronous programming and make your life easier. Imagine that  It promises you that you get a "gift" but you don't know when it happens and if it whenever happens but at the end you will get an answer if your promise was keept or not.

there are 3 states of promises:

-   **Pending**, when the final value is not available yet. This is the only state that may transition to one of the other two states.
-   **Fulfilled**, when and if the final value becomes available. A _fulfillment value_ becomes permanently associated with the promise. This may be any value, including `undefined`.
-   **Rejected**, if an error prevented the final value from being determined. A _rejection reason_ becomes permanently associated with the promise. This may be any value, including `undefined`, though it is generally an error

Lets take a look at the code:

```javascript
const promisedPresent = getPresent();
promisedPresent
  .then(present => console.log('A nice gift!!', present))
  .catch(error => console.log('Sorry, no gift for you :(', error))
```
Function get will be executed only if promise will be fullfilment. If not you will get an error from catch. What is interessting for us... you don't know when it happens. It can be in 1 sec or 5 minutes. 

```javascript
function getPresent() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('After 5 seconds you got your gift, are you happy!');
    }, 5000); // 5 sekund
  });
}
```

You can join more promises:
```javascript
getPresent()
  .then(present => returnToTheShop(present))
  .then(returnedMoney => buyNewiPhone(returnedMoney))
  .then(iPhone => iPhone.openTypeOfWeb());
```



### Declaring Objects
```javascript
var o1 = new Object();
var o2 = {}
var user = {name: “tom”, password:”Kraj”}
```

You can add easily attributes:
```javascript
user[“fruit”] = “bananna”
```

```javascript
Object.keys(user).length
```
### How to declare arrays:
```javascript
var arr= new Array();
var arr2 = [];
```

### How to check array?
```javascript
Array.isArray(ar);
```

### Add a new element to an array:
```javascript
arr.push("abc")
```

### Iteration 
```javascript
var user = {name: “tom”, surname:”krajewski”};
for (key in user){
	console.log(key);
}
```

### Easier "for" loop 
```javascript
var myArray = [“ala”,”ma”,”kota”];
for (value of myArray ){
	console.log(value);
}
```
### Error handling
if you get use to syntax try catch… you need to forget it for NodeJS
```
do_something (par1, par2, par3, (error, result) =>{
	
	if (error){
	SOMETHING BAD HAPPEND HERE!
	}
		
	else{
	do your stuff
	}

});
```


Pattern how to solve problem with this:


```javascript

var fs = require(‘fs’);

function FileObject() {
	this.filename = “”;

this.file_exists = function (callback) {
	console.log(this.filename, ‘r’, function (err, handle) {
	if (err) {
		console.log(“Can’t open” + this.filename);
		callback(err);
		return;
	}

	fs.close(handle);
	callback(nulll, true);
});
}
}

var fo = new FileObject();

fo.filename = “some not existed file”;

fo.file_exists(err, exists) => {
	if (err) {
		console.log(“error opening file “ + JSON.stringify(err));
		return;
	}
});

```

why we get undefined?!

```javascript

var fs = require(‘fs’);

function FileObject() {
	this.filename = “”;

this.file_exists = function (callback) {
var self = this;
	console.log(self.filename, ‘r’, function (err, handle) {
	if (err) {
		console.log(“Can’t open” + self.filename);
		callback(err);
		return;
	}

	fs.close(handle);
	callback(nulll, true);
});
}
}

var fo = new FileObject();

fo.filename = “some not exited name”;

fo.file_exists(err, exists) => {
	if (err) {
		console.log(“error opening file “ + JSON.stringify(err));
		return;
	}
});

```
OR… with error functions

```javascript

var fs = require(‘fs’);

function FileObject() {
	this.filename = “”;

this.file_exists = function (callback) {
	console.log(this.filename, ‘r’, (err, handle)  => {
	if (err) {
		console.log(“Can’t open” + this.filename);
		callback(err);
		return;
	}

	fs.close(handle);
	callback(nulll, true);
});
}
}

var fo = new FileObject();

fo.filename = “some not exited name”;

fo.file_exists(err, exists) => {
	if (err) {
		console.log(“error opening file “ + JSON.stringify(err));
		return;
	}
});

```
Sources: 
https://www.tutorialspoint.com/javascript/
https://www.tutorialspoint.com/nodejs/ 

## Node.js <div id='id-section2'/> 

Node.js is a very powerful JavaScript-based framework/plattform built on Google Chrome's JavaScript V8 Engine. It is used to develop I/O intensive web applications like video streaming sites, single-page applications, and other web applications. Node.js is open source, completely free, and used by thousands of developers around the world. 

## Features of Node.js
Following are some of the important features that make Node.js the first choice of software architects.
- Asynchronous and Event Driven − All APIs of Node.js library are asynchronous, that is, non-blocking. It essentially means a Node.js based server never waits for an API to return data. The server moves to the next API after calling it and a notification mechanism of Events of Node.js helps the server to get a response from the previous API call.

- Very Fast − Being built on Google Chrome's V8 JavaScript Engine, Node.js library is very fast in code execution.
- Single Threaded but Highly Scalable − Node.js uses a single threaded model with event looping. Event mechanism helps the server to respond in a non-blocking way and makes the server highly scalable as opposed to traditional servers which create limited threads to handle requests. Node.js uses a single threaded program and the same program can provide service to a much larger number of requests than traditional servers like Apache HTTP Server.
- No Buffering − Node.js applications never buffer any data. These applications simply output the data in chunks.
Why Node.js is so fast because it uses machine code which is low level code that your computer can run directly without needing an interpreter. 

## Environment:
If you use my VM nodejs is already installed. If you decided to use your own PC, please download latest version of Node.js https://nodejs.org/en/download/ 

## First Steps

### Hello world
Create a js file named hello.js on your machine having the following code.

```bash
$ echo console.log("Hello World")  > main.js
```
Now execute main.js file using Node.js interpreter to see the result:
```bash
$ node main.js
```

If everything is fine with your installation, this should produce the following result:
```
Hello, World!
```
### Create a project
Create a new directory

```bash
$ mkdir myFirstNodeProject
$ cd MyFirstNodeProject
```

With npm init you create a new node.js project with package.json that defines all properties of the project. It walks you through the properties and asks you one by one how to specify them. You can choose the default settings by clicking enter.

```bash
$ npm init 
```
![npm init](https://lh3.googleusercontent.com/-tSviVQvQQvG9Dzb2LtAajfo0p7R2AxIztmRKUr3KSJN1haKM7rBPUYhu08URltlahXfNVPViOw)



### package.json
package.json is present in the root directory of any Node application/module and is used to define the properties of a package. Let's open package.json of my template skill:

```json

{
  "name": "My-template",
  "version": "0.0.1",
  "description": "Quickstart template for a NodeJS Application, you can easily deploy it in heroku",
  "engines": {
    "node": "6.9.4"
  },
  "main": "dist/app/index.js",
  "scripts": {
    "start": "node dist/app/index.js",
    "heroku-deploy": "git checkout atomic-development && git add ./ && git commit -m \"development increment\" && git push heroku atomic-development:master --force && heroku logs --tail",
    "serve": "node dist/app/index.js"
  },
  "repository": {
    "type": "git",
    "url": "t"
  },
  "keywords": [
    "nodejs"
  ],
  "author": "Tomasz Krajewski",
  "contributors": [
    {
      "name": "Tomasz Krajewski",
      "email": "Tomasz.Krajewski@opitz-consulting.com"
    }
  ],
  "license": "MIT",
  "devDependencies": {
	"alexa-verifier": "^0.3.6"

  },
  "dependencies": {
    "alexa-sdk": "^1.0.10",
    "aws-lambda-mock-context": "^3.1.1",
    "body-parser": "^1.17.2",
    "botkit": "^0.5.4",
    "express": "^4.15.3",
    "request": "^2.81.0",
    "mongoose": "^4.10.5",
    "mongodb": "^2.2.26",
    "ip": "1.1.5",
    "local-ipv4-address": "0.0.2"

  }
}

```
Thanks package.json you are able to install all node.js modules. For example if you like to add the dependency request to do API calls, you need only to use the following command and the request module will be added to your project. Parametr --save will ensure that your module will be added to package.json
```bash
$ npm install request --save
```
![enter image description here](https://lh3.googleusercontent.com/riwdB6g1lWULXXQu6GaK7FaCk6r8JvySAkqQrJnHSGsmq6gliSaXeXJ9TvLCa0PH-TJNMKD3qYQ)
All required modules from package.json will be saved to your project directory. The file package.json now contains the dependency request.
![enter image description here](https://lh3.googleusercontent.com/O7KM53-AhCm6GAiie9DS-VRKObytbWwGOJTuRdNp8AOtFP-YN2bbRJ8y-KZxfUWsFyIt-nHlfOs)


## Arrow function
An arrow function is defined using a pair of parentheses that contains the list of parameters (param1, param2, ..., paramN), followed by a fat arrow => and a pair of curly braces {...} that delimits the body statements.
When the arrow function has only one parameter, the pair of parenthesis can be omitted. When it contains a single statement, the curly braces can be omitted too.

The following example shows the arrow function basic usage:
```javascript
var absValue = (number) => {  
  if (number < 0) {
    return -number;
  }
  return number;
}
absValue(-10); // => 10  
absValue(5);   // => 5  
```

absValue is an arrow function that calculates the absolute value of a number.
The function declared using a fat arrow has the following properties:
The arrow function does not create its own execution context, but takes it lexically (contrary to function expression or function declaration, which create own this depending on invocation)
The arrow function is anonymous: name is an empty string (contrary to function declaration which have a name)
arguments object is not available in the arrow function (contrary to other declaration types that provide arguments object)


## Module
lets take a look at an example:

apps.js
```javascript
const fs = require('fs');
const os = require('os');
var user = os.userInfo();
const notes = require('./notes.js');

fs.appendFile('greetings.txt', 'Hello '+user);

```
notes.js
```javascript
console.log(module);

```

output:

```javascript
Module {
  id: 'C:\\aprivat\\Node Tutorial\\notes.js',
  exports: {},
  parent:
   Module {
 	id: '.',
 	exports: {},
 	parent: null,
 	filename: 'C:\\aprivat\\Node Tutorial\\app.js',
 	loaded: false,
 	children: [ [Circular] ],
 	paths:
  	[ 'C:\\aprivat\\Node Tutorial\\node_modules',
    	'C:\\aprivat\\node_modules',
    	'C:\\node_modules' ] },
  filename: 'C:\\aprivat\\Node Tutorial\\notes.js',
  loaded: false,
  children: [],
  paths:
   [ 'C:\\aprivat\\Node Tutorial\\node_modules',
 	'C:\\aprivat\\node_modules',
 	'C:\\node_modules' ] }
```

So let's use this exports object
apps.js
```javascript
const fs = require('fs');
const os = require('os');
var user = os.userInfo();
const notes = require('./notes.js');
console.log(notes.myNote);
fs.appendFile('greetings.txt', 'Hello '+user);
```
notes.js
```javascript
module.exports.myNote = “Hello”;

```

**Excercise 1**:
What did you see in the output?


The real goal is exports functions that we can use in app.js
Lets change notes.js
notes.js
```javascript
module.exports.myNote = () => {
 return "my note";
}
```

and app.js
```javascript
const fs = require('fs');
const os = require('os');
var user = os.userInfo();
const notes = require('./notes.js');
notes.myNote();
fs.appendFile('greetings.txt', 'Hello '+user);
```

If you want to use variables as a module you cab just declare it in your variable in a JS script file:

```javascript
var greet = require(‘./greet);
```
Exports module
```javascript
var greet = “Hello from me!”
module.exports = greet;
```






## Blocking Code vs non blocking code example


The most weird thing with nodejs is to understand non blocking code. Please compare 2 examples:

Create a text file named input.txt with the following content :

```javascript
This is an example from Tutorials Point is giving self learning content
to teach the world in simple and easy way!!!!!
```
Create a js file named blockingCode.js with the following code −
```javascript
var fs = require("fs");

var data = fs.readFileSync('input.txt');

console.log(data.toString());
console.log("Program Ended");
```

Now run the main.js to see the result −
```
$ node main.js
```
Verify the Output.

It was a blocking code example.

## Non-Blocking Code Example
Create nonBlockingCode.js
```javascript
var fs = require("fs");

fs.readFile('input.txt', function (err, data) {
   if (err) return console.error(err);
   console.log(data.toString());
});
console.log("Program Ended");
```
Now run the nonBlockingCode.js to see the result −

```
$ node nonBlockingCode.js
```

These two examples explain the concept of blocking and non-blocking calls.
The first example shows that the program blocks until it reads the file and then only it proceeds to end the program.
The second example shows that the program does not wait for file reading and proceeds to print "Program Ended" and at the same time, the program without blocking continues reading the file.
Thus, a blocking program executes very much in sequence. From the programming point of view, it is easier to implement the logic but non-blocking programs do not execute in sequence. In case a program needs to use any data to be processed, it should be kept within the same block to make it sequential execution.


character encoding: how characters are stored in binary. The numbers (or code points) are converted and stored in binary.

## Buffer
//take this string and convert it to binary data
```javascript
var buf = new Buffer(‘Hello’, ‘utf8’);
console.log(buf);
console.log(buf.toString());

//adding data
buf.write(“wor”);
```

## DEBUGGER
node debug [filename.js]

Functions:
set breakpoint([line_number])
help all functions

or debugger in Atom 



Sources:
https://www.tutorialspoint.com/nodejs/ 


## Google Assistant tutorial <div id='id-section1'/> 



`conv.user.storage` object instead for storing the user's name between conversations. If the user previously granted your Action permission to access their name, it will appear in the greeting message.
**Key term:**

-   **No-input event:** Special event that Actions on Google sends to Dialogflow whenever a user doesn't provide input after a developer-defined number of reprompts. In Actions on Google, this is represented by the `actions.intent.NO_INPUT` intent. If you are using Dialogflow, this is represented as an `actions_intent_NO_INPUT` event.

