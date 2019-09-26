# A Short tutorial for Google Assistant Event. Node.js
I put here the most valuable information for Javascript, Node.js, MongoDb and Google Home. I collected some data and examples from different sources. You find a list all of them at the end of every section. :)

**Table of content**
- [Javascript code examples](#id-section1)
- [Node.js](#id-section2)
- [Google Assistant](#id-section3)

## Javascript Code examples <div id='id-section1'/>
Node.js is based on Javascript.
Most examples comes from: https://www.tutorialspoint.com/javascript/.

### JavaScript Variables
```javascript
const name = "Ali";
let money;
money = 2000.50;
```
### Variable Scope
```javascript
const myVar = 'global'; // Declare a global variable
function checkscope( ) {
  const myVar = 'local'; // Declare a local variable
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
const age = 15;

if ( age > 18 ) {
  console.log('Qualifies for driving');
} else {
  console.log('Does not qualify for driving');
}

```
### For Loop
```javascript
let count;
console.log('Starting Loop');

for (count = 0; count < 10; count++) {
  console.log('Current Count : ' + count );
  console.log('');
}

console.log('Loop stopped!');
```
### Declaring array
```javascript
const fruits = ['apple', 'orange', 'mango'];
fruits.length;
console.log('The lenght of this array is ', fruits.length);
console.log('This array: ' + fruits);

```
### Declaring function
```javascript
function sayHello(name) {
  cosole.log('Hello '+name);
}

sayHello('Tomasz');
```

```javascript
const sayHello = (name) =>
{
	cosole.log("Hello "+name);
}

sayHello(“Tomasz”)
```

### Declaring function as an arrow function
In our project we are using most the time arrow functions! As you see above arrow function is the same as the usual function in JS.

```javascript
const sayHello = (name) =>
{
	cosole.log("Hello "+name);
}

sayHello(“Tomasz”)

```

### Destructing

```javascript
const myJson =  {
  id: 34243,
  title: "myTitle",
  published: 1999
  genreIds: [9,33,3,32,44]  
};

const {title, id, published} = myJson;
console.log(title);
// "myTitle"
const [,second] = myJson.genreIds;
console.log(second);
// 33
```

### 







### Anonymous function

```javascript
const greetMe = function() {
  console.log('hi');
};

greetMe();
```

### Anonymous function as an arrow function
```javascript
const greetMe = () =>{
  console.log('hi');
};

greetMe();
```

### Objects
You can see an object as a such block of values

```javascript
const person = {
  firstName: 'Tomasz',
  lastName: 'Krajewski',
  greet: function() {
    console.log('Hello '+this.firstName + ' ' + this.lastName);
  },
};

person.greet();

console.log(person.firstName);
console.log(person['firstName']);

```
remember you can get your object value in the two ways:
```javascript
person.firstName
```
or
```javascript
person['firstName']
```



person['firstName']



### Node api

https://nodejs.org/api/index.html
```javascript
const util = require('util');
const greeting = util.format('Hello, %s', name);
util.log(greeting);

```

### Class example
```javascript
class Person {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }

  greet() {
    console.log('Hello '+ this.firstname);
  }
}
const user = new Person('Tommy', 'Boby');
console.log(user);
```



### Getters and Setters

```javascript
class Person {
  constructor(firstname, lastname) {
    this._firstname = firstname;
    this._lastname = lastname;
  }

  greet() {
    console.log('Hello '+ this.firstname);
  }
  get firstname() {
      console.log("Getting name")
      return this._firstname;
  }  
    
  set firstname(newName){
      this._firstname = newName;
  }
    
}
const user = new Person('Tommy', 'Boby');
console.log(user);
user.firstname = "Frank";
console.log(user.firstname);
```

### Inheritance

```javascript
class Teacher extends Person {
  constructor(teachingSkills) {
	// super needs to be called first
    super();
    this._teachingSkills = teachingSkills;
  }
  // this set will run first and once for Teacher  
  set firstname(newName){
    console.log('It runs for Teacher')  
    this._firstname = newName;
  }
    
}
const user = new Teacher('Tommy', 'Boby',5);
const user1 = new Person('Arne', 'Resing');
console.log(user);
user.firstname = "Frank";
console.log(user.firstname);
```



### Declaring Objects

```javascript
const o1 = new Object();
const o2 = {};
const user = {name: 'tom', surrname: 'Kraj'};
```

You can add easily attributes:
```javascript
const user = {name: 'tom', surrname: 'Kraj'};
user['favFruit'] = 'bannana';
console.log(user);

// result: { name: 'tom', surrname: 'Kraj', favFruit: 'bannana' }

console.log(Object.keys(user).length);

// result: 3
```

### How to declare arrays:
```javascript
let arr= new Array();
let arr2 = [];
```

### How to check array?
```javascript
const arr= new Array();
const arr2 = [];
console.log(Array.isArray(arr));

// true
```

### Add a new element to an array:
```javascript
const arr2 = [];
arr2.push('abc');
console.log(arr2);

// [ 'abc' ]
```

### Iteration
```javascript
const user = {name: 'tom', surname: 'moni'};

for (let key in user) {
  console.log(key);
}

// name
// surname
```

### "for" loop

```javascript
const myArray = ['ala', 'ma', 'kota'];
for (let i=0; i<myArray.length; i++ ) {
  console.log(myArray[i]);
}

// ala
// ma
// kota

```

### Easier "for" loop

```javascript
const myArray = ['ala', 'ma', 'kota'];
for (value of myArray ) {
  console.log(value);
}

// ala
// ma
// kota

```

### for each

```javascript
const myArray = ['ala', 'ma', 'kota'];
myArray.forEach((value, i) => {
    console.log('Value: '+value);
    console.log('Index'+i);
})

```

### Array.Of

```javascript
const myArray = Array.of(8, [44,3,2,2], {sport: 'value'})

```

### Array.fill

```javascript
const myArray = [1,2,3,4,5]
myArray.fill("a", -2)
// [1,2,3,'a','a']
```



### loop for objects

```javascript
const user = {name: 'tom', surrname: 'Kraj'};
for (let value in user ) {
  console.log(value);
}

```



### Primitives

string, number, boolean, null, undefined, symbol

We copy the values

BUT Objects are stored by references!!

```javascript
const user = {name: 'tom', surrname: 'Kraj'};

let newUser = user;

newUser.age = 19;

console.log(user);
//{name: 'tom', surrname: 'Kraj', age: 18};
console.log(newUser);
//{name: 'tom', surrname: 'Kraj', age: 18};
```



### Callbacks

callback is a function passed to some other function, which we assume will be invoked at some point. The function “call back” invoking the function you give it when it is done doing its work.

the function I invoked will invoke function I will give

```javascript
function printUpper(myString) {
  console.log(myString.toUpperCase());
}
function printNumber(myNumber) {
  console.log(myNumber);
}
function run(callback, input) {
    callback(input);
    
}

run(printUpper, 'Hellooooo')
```



another example:

```javascript
function greet(callback) {
  console.log('Hello');
  const data = {
    name: 'John',
  };
  callback(data);
}

greet(function(data) {
  console.log('the callback was invoked');
  console.log(data);
});
```
the function I invoked will invoke function I will give.

```

### Files

We can use synchronous convention:

​```javascript
const fs = require('fs');

// it reads binary data
const greet = fs.readFileSync(__dirname+ '/hej.txt', 'utf-8');

console.log(greet);
```
Do you see differences with asynchronous example? What will happens if you call greet variable? If you have checked both examples and you know why you got undefined in the second one you can read next pages ;)

```javascript
const fs = require('fs');

const greet = fs.readFile('hej.txt', 'UTF-8', function(err, data) {
  console.log(data);
});

console.log(greet);
//undefined WHYYYYYYYYYYYY???
// Repeat That
```

**Error-first callback**: Callbacks take an error object as their first parameter
null if no error, otherwise will contain an object defining the error. This is a standard so we know in what order to place our parameters for our callbacks.


### Asynchronous programming
If you didnt understand first example with file reading just relax and try to understand how asynchronous work.
let's take a look on php code which can be equivalent to any your well known language like java or python. Whatever ;)

setTimeout function is a function which has 2 arguments: a callback and a delay
setTimeout(callback, delay) = 2 argument

```javascript
setTimeout( () => {
  console.log('The last, or the first one?');
},
4000);

setTimeout( () => {
      console.log('Should I be the first??');
   },
   0);
console.log('or me?');
```

Before you execute code, ask yourself what you get from the console first?
Easy because it was still something in the event queue. Using method setTimeout you registred 2 callbacks:
1 with console.log "I have done my work" and the second "Should I be the first??"

hej.txt
```
Repeat That
```

```javascript
const fs = require('fs');

fs.readFile('hej.txt', {encoding: 'utf8'}, function(err, data ) {
  if (err) {
     console.log(err);
  }

  console.log(data);
  fs.appendFile('hej.txt', data, (err) => {
    if (err) {
      if (err) {
        console.log(err);
        return;
      }

      console.log('OK');
    }
  });
});
```
After that you should see:
hej.txt

```
Repeat That
Repeat That
```
another example:

```javascript
setTimeout(

    () =>
    console.log("Line 1, 0 timeout"), 0);

console.log("line 2");
setTimeout(

    () =>
    console.log("Line 3, 100 timeout"), 100);

for(let i = 0 i<1000; i++){
    if(i==1000) console.log("Done");
}
```



another example:



1. Lets prepare something like that to show how callback works. We get userObject

```javascript
var getUser = (id, callback) => {
	var user = {
		id: id,
		name: 'Tom'
		};
		callback(user);
	};

getUser(31, (userObject) => {
	console.log(userObject);
});
```
2. and now lets add a real world case that we need to wait 5 sec for our user...


```javascript
var getUser = (id, callback) => {
	var user = {
		id: id,
		name: 'Tom'
		};
		setTimeout(
		()=> {
		callback(user);
		}, 5000);


	};

getUser(31, (userObject) => {
	console.log(userObject);
});
```


## Promise

The promise as an abstraction which tries to cover asynchronous programming and make your life easier. Imagine that  It promises you that you get a "gift" but you don't know when it happens and if it whenever happens but at the end you will get an answer if your promise was kept or not.

There are 3 states of promises:

-   **Pending**, when the final value is not available yet. This is the only state that may transition to one of the other two states.
-   **Fulfilled**, when and if the final value becomes available. A _fulfillment value_ becomes permanently associated with the promise. This may be any value, including `undefined`.
-   **Rejected**, if an error prevented the final value from being determined. A _rejection reason_ becomes permanently associated with the promise. This may be any value, including `undefined`, though it is generally an error
First simple example

Promise is a constructor with 2 callbacks. Resolve and reject but you can cal them as you wish

```javascript
var somePromise = new Promise( (resolve, reject) => {
	resolve('Hey. It worked!');

});
```

```javascript
somePromise.then( (message) => {
	console.log('Success:' + message);
});
```

Lets take a look at the code:

```javascript
const promisedPresent = getPresent();
promisedPresent
  .then(present => console.log('A nice gift!!', present))
  .catch(error => console.log('Sorry, no gift for you :(', error))
```
Function getPresent will be executed only if promise will be done with resolve state. If not you will get an error from catch. What is interessting for us... you don't know when it happens. It can be in 1 sec or 5 minutes.

```javascript
function getPresent() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('After 5 seconds you got your gift, are you happy!');
    }, 5000); // 5 sekund
  });
}
```
Let see an other example.

Imagine you meet a girl who you really like. But you dont know if she likes you. You want to invite her to a cinema on Valentine's day but you need to get first if she likes you. You would never buy first ticket before you ask her out. Please check your code in the console.

You can treat setTimeout function like a time for thinking.

```javascript
const expectedAnswerfromMoni = 'Moni: I was waiting for that ages. Of course';
const expectedAnswerfromMoni2 = 'Moni: With pleasure my beloved';
const expectedAnswerKino = 'Kino lady: Yes we have 2 tickets for tonight movie: One Flew Over the Node.js Nest ';
const expectedKiss = 'Moni: Kiss Kiss Kiss. Only for you my hero!';


const yourAsynchronousTask = (expectedAnswer, reactionTime) => {
  return new Promise((resolve, reject) => {
    setTimeout((err) => {
      if (err) {
        reject(expectedAnswer);
      }
      resolve(expectedAnswer);
    }, reactionTime); // 5 sekund
  });
};

console.log('You: Hey Moni, do you want to go out with me?');

yourAsynchronousTask(expectedAnswerfromMoni, 4000).then((result) => {
  console.log(result);
  console.log('You: Do you want to go with me to cinema tonight?');
  return yourAsynchronousTask(expectedAnswerfromMoni2, 6000).then((result) => {
    console.log(result);
    console.log('You: I wasnt sure you want to go but I can call cinema right now');
    return yourAsynchronousTask(expectedAnswerKino, 10000).then((result) => {
      console.log(result);
      console.log('You: Hey Moni, should I get something from you?');
      return yourAsynchronousTask(expectedKiss, 1000).then((result) => {
        console.log(result);
      });
    });
  });
}).catch((error)=>{
  console.log(error);
});

console.log('But in the same time I can do other things!!!');
console.log('I take a look at her eyes');
console.log('Smile to her and so on');
```
But you can think... what happens when Moni say anytime no for your question! Our code wont execute after first "no" and you will get error message.

An another simple example:

In this time you can treat setTimeout function like any asynchronous call like calling database or any API

```javascript
const asyncAdd = (a, b) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (typeof a ==='number' && typeof b ==='number') {
        resolve(a+b);
      } else {
        reject('you can sum number and string!!');
      }
    }, 3000);
  });
};

asyncAdd(5, 10).then((res) => {
  console.log(res);
  return asyncAdd(res, 10).then((newResult) => {
    console.log(newResult);
    return asyncAdd(newResult, '2').then((nextResult) => {
      console.log;
    });
  });
}).catch((error) => {
  console.log(error);
});
```

As you saw in the last example you can can join so many promises as you want.

But you can chain so many then as you wish:

```javascript
getPresent()
  .then(present => returnToTheShop(present))
  .then(returnedMoney => buyNewiPhone(returnedMoney))
  .then(iPhone => iPhone.openTypeOfWeb());
```

To manage promises you can use an external module:
https://github.com/axios/axios



## Async

requires at least node 7.6

if you write "async" before function you just telling that this function depends on other asynchronous function. 

## Generators 

   you can compare generators to analog camera. If you take a picture the next is prepared

```javascript
function* aGenerator(){
  console.log('I ran once')
  yield 1; // Pause here and wait 
  console.log('I ran once')  
}
const gen = aGenerator();
gen.next();
gen.next();
gen.next(); 
```

##  ES7

1.   Exponentiation:

```javascript
const x = 3*3*3;
const x3 = 3**3;
```

2. Includes: returns true or false

```javascript
const arr = [0,2,3,4,555]
console.log(arr.includes(2))
```



### Error handling

if you get use to syntax try catch… you need to forget it for NodeJS. Pattern in Node.js
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

Sources:
https://www.tutorialspoint.com/javascript/


## Node.js <div id='id-section2'/>

Source: https://www.tutorialspoint.com/nodejs/

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

but you can do something like this too!
```javascript
var squer= (number) => number*number;
squer(10); // => 100
```


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

If you want to use variables as a module you can just declare it in your variable in a JS script file:

```javascript
const helpers = require('./greet');

console.log(helpers.greet);
console.log(helpers.otherGreet);

```
Exports module
```javascript
const greet = 'Hello from me!';
const otherGreet = 'Hello from other side';
module.exports = {greet, otherGreet};
```

## Blocking Code vs non blocking code example


The most weird thing with nodejs is to understand non blocking code. Please compare 2 examples:

Create a text file named hej.txt with the following content :

**hej.txt**
```javascript
This is an example from Tutorials Point is giving self learning content
to teach the world in simple and easy way!!!!!
```
Create a js file named blockingCode.js with the following code −
```javascript
const fs = require('fs');

const data = fs.readFileSync('hej.txt');

console.log(data.toString());
console.log('Program Ended');
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
const fs = require('fs');

fs.readFile('hej.txt', function(err, data) {
  if (err) return console.error(err);
  console.log(data.toString());
});
console.log('Program Ended');
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

## DEBUGGER

This solution is only for remote code like in

```
node inspect-brk [filename.js]
```
Open for example WebStorm or any JS IDE supporting debug mode and connect to the debugger

In Webstorm click in the buttom toolbar Run-->Edit Configurations
Please choose from templates: "Attach to Node.js/Chrome"
In the host add ip address of your docker-machine. In my case **localhost** or any ip address where your app is hosted

![enter image description here](https://lh3.googleusercontent.com/tHxcCnHN6wc4Qg7FM-WqsBrnUpqaXrEpYsRyWY2_eBYy3N3OulflFn_eTtg_ikTJHSbdrFal3Ij7sr84XyTCXsed59h8yDthnsG5olrGG4t78vrcINhxuGEBs9p_62vWZlMstMaEAwh6oo8UEj60UAueE-Z3AJ427lJKXaNhYXVDIDn-XRa0svnhyeqoSfqvOZqZiJGmNVaKQ9JIWvAZsJvCyy2gwWAabP-7BvYCxu5oW4vCn9e6tFlCPxY8qPUhAU7LeJJH4d4wZ1T8kWpvf_G6lkOhheXjMgdaammQYd3PgcUtpCE8XbxaMq45rhknXX8Z-f-XgmKkoSjbTors2BhAq7vWWY2_Nwlwks18Mfvn2nyEUe1cTHqEnoUj3oQCJTeuMH9cPzpwyE67GGM0Pl1QZpnlIZv__HWMPa9O00rwITVflVUr09DcECKaNARjNW8OVM8SMoe9A-QBn49YTUObZ_MSPu1BX_xRpW9GdJ-BzqztrbaMQR9hAMbGxGP6B_n6iD0TWC92QkjeV0zqkVFBX4YKzoOWQxSV15agUYKPCFM2KpG_rJ1YtnWPCNOMR0PjJUzzdz44bdu0vh_60N78ZP1OV6j8BkXymOrdBvtTxv_X7uKtrtpJF1VgcbZzzPE9ahnGTlYRvtUAgJNw0zfNSkoxcvddE8MolHNTYk7b1Hq0BDk2G4bQvfOgPFhm_oGIEavzkz7uGR3hlA=w1346-h841-no)
and click apply and **+** button in the left button corner

![enter image description here](https://lh3.googleusercontent.com/Bss0hviB3jsPljLWRodBulNb3aOZE0X3SXwf1-Bf5K7VgeQOCh1xwi3yVPmp3_IMKrDIKZgu27_zH3orh3Vlwn-QexQFPzlcamP-zihZpuleaKa-MFy4Or0285VnWtkc1M_9Xj9Xbg6AJY4gnA1vEHPAi8HobQT8X2l13P796INCRhjd7hqNs442qsgJKXwjkLCX1Y04__FRHOE3ywH26rdg8u3-KVefsfAQgE5hcDRWsq5sq-TLM7nSaz0-AsK9_3uNiyHlT_mIsGMSYcqVEO1usyIAhUJe79DEPGHjUM0ONqorHKzaw9L1oXMDgxCkoLVKxnGAj_Ccu-X6mxRxj8cU0ExTHoBQtD5yZ2lVWP-N4R4RuUeLJ_Wo4ZPg0AxU3zP_A5PXHIUqTBptF1d199URQOV7ps68KbeiRhvUffWLwyzcaId--yLsDXn9ID1ZEUSSHiH8W8ztxZlMKx1ENjTTcIKPED8j911t_o-vEiiycjjIU_nq6bkHywFy3oUqjcsb98Hw2LwEIBo7Hb2HyXAwNQbhgXlpzIvcC_6qbogGVr3gxUSf8itbZPP5wffnGJ9T8huAZw-MdVbIPhd_c6A47wft9uu_RCn_Ya1Anrd99fEfkgUH6LLbpfDiDYdEYX31F6j2W5oEGCptzva-0DO24S2YIvwNrsoGa62yy8LfNd5gZ0ebDZMxZ-nrFW1doFTQoyLLprb2mrFtNw=w1145-h299-no)

Now if you click Run-->You can run your defined debug process

You can add your first breakpoint clicking to a choosen line and start conversation from DialogFlow.
You can see your debugged code in the WebStorm console.

![enter image description here](https://lh3.googleusercontent.com/_RGQbo9Hw3Bk53SgNFH1lZLYbi5eK8TVmbhsf9Le6bQZmJ7AYCCOFPsHgzvzyFWcxLlghsqm0tmvEp2aiakwebuLx-SEW0onBDdr9w96--Fdd5C9Ja-Qx3tu1eLd6REIFdm7robfx2PLEa4jOyyttmlfxyPMx30D2h5EAAt4APUu0rYMKcHMIxNz171Wrqy4iMcoPpSMV-8PuqEwklViBkVZvi0xrsDyyxnFQlghBYqwfyg7go57TwIPTfbxnPYJDJxivy_XHOu-x2HPl1OwgS0kIBPVF0e8HSflw28PqKxVl3YbFdhe3gp8OOdWfE-HQaul8CaJjH77dJ8eliucTBHJIqnyLHuAjemqcG_JTLNAJeKlLng4OuJLRZIPTJbK2h0BYWeOWk7mAnlqSoi-cTcWrODVmReRUAqmNYM8Lk-3zJSDtYi1gHOXaWRTzyV99y0Pfb4ZSsJ9nvAke4evQc94cIaUpdswWCj6BvAi_U0IpEzMbtgw24fvIh72k4nA_4HM_cYAfheXgzjCEJTk9eLYwRA0TwvcuUBCWLGV8J_0pzNN0yMmL_1S3ToTTPKKfMH82nNS-IHD9b92tWXnDpVcrj4R7CNs2Jq4mAk_MTZtQ8wxeDhbjj6woFj0fQI_TYFfn_t79JJA-3d9ulqyM9WjHmYIrXWgNb5oKuKuzKLSqNOOnXi64PU4YQsuvfoXBu_04c2eOriqP7bsCA=w1771-h679-no)


Sources:
https://www.tutorialspoint.com/nodejs/

<div id='id-section3'/>
## Google Assistant tutorial

We are using solution which is based on node.js express app.  The reason? we can start and test our app locally very fast.

Please visit our github repository to follow all code explanations:
https://github.com/falent/googleHomeAssistantExpressNodeJS

### Creating start.js file
firstly we create file start.js

This is a normal express app. It starts a server which is waiting for any call to port 5000. For us important is method express().use which we add 2 parametrs bodyParser.json() and app. BodyParser.json ensure us that every call from outside will be parsed to Json object. The second "app" parametr tells to use google solution (based on DialogFlow) to treat any call from outside.

```JavaScript
'use strict';
const app = require('./app');

const express = require('express');
const bodyParser = require('body-parser');

const port = process.env.PORT || 5000;
express().use(bodyParser.json(), app).listen(port);
```

We imported app object. What is that?

### Creating app.js file

Our code uses the Actions on Google Node.js client library to respond to the HTTP requests that the Assistant sends first to Express app and than to our webhook:

```JavaScript
const {dialogflow} = require('actions-on-google');
```
The library allows you to create a DialogflowApp object, which acts as a wrapper for the Dialogflow API.

```JavaScript
const app = dialogflow({debug: false});
```
We need to add a function which will be triggered by the name of intent. In this case we add function app.intent with 2 parametrs. 'welcomeIntent' is a name of our intent and 'conv' is a sent object from google assistant
```JavaScript
app.intent('welcomeIntent', (conv) => {
    conv.ask('Hi, What is your name?');
});
```
For people who ever programmed node.js webapp with express.
Please compare the example above with express app example:
```JavaScript
app.get('/welcomePage', (req, res) => {
    res.send('Hi, What is your name?');
});
```
If you had any expirience with express app you can treat conv parametr as res parametr in dialogFlow app.

If you print to the console the conv object you can see a long JSON request:

```JSON
{
  "responses": [],
  "expectUserResponse": true,
  "digested": false,
  "noInputs": [],
  "speechBiasing": [],
  "_responded": false,
  "request": {
    "isInSandbox": true,
    "surface": {
      "capabilities": [
        {
          "name": "actions.capability.AUDIO_OUTPUT"
        },
        {
          "name": "actions.capability.MEDIA_RESPONSE_AUDIO"
        },
        {
          "name": "actions.capability.WEB_BROWSER"
        },
        {
          "name": "actions.capability.SCREEN_OUTPUT"
        }
      ]
    },
    "requestType": "SIMULATOR",
    "inputs": [
      {
        "rawInputs": [
          {
            "query": "Talk to my company celero LTD",
            "inputType": "KEYBOARD"
          }
        ],
        "intent": "actions.intent.MAIN"
      }
    ],
    "user": {
      "userStorage": "{\"data\":{}}",
      "lastSeen": "2018-12-09T16:31:52Z",
      "locale": "en-US",
      "userId": "ABwppHGscAZl8ESw0TOWpQy3BbypDvPomBN7Bjlz0lm3ICUVdnsON6KwbFXST_fw2Z-hAR-f-u5o"
    },
    "conversation": {
      "conversationId": "ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX",
      "type": "NEW"
    },
    "availableSurfaces": [
      {
        "capabilities": [
          {
            "name": "actions.capability.AUDIO_OUTPUT"
          },
          {
            "name": "actions.capability.WEB_BROWSER"
          },
          {
            "name": "actions.capability.SCREEN_OUTPUT"
          }
        ]
      }
    ]
  },
  "headers": {
    "accept": "text/plain, */*",
    "content-type": "application/json; charset=UTF-8",
    "accept-charset": "big5, big5-hkscs, cesu-8, euc-jp, euc-kr, gb18030, gb2312, gbk, ibm-thai, ibm00858, ibm01140, ibm01141, ibm01142, ibm01143, ibm01144, ibm01145, ibm01146, ibm01147, ibm01148, ibm01149, ibm037, ibm1026, ibm1047, ibm273, ibm277, ibm278, ibm280, ibm284, ibm285, ibm290, ibm297, ibm420, ibm424, ibm437, ibm500, ibm775, ibm850, ibm852, ibm855, ibm857, ibm860, ibm861, ibm862, ibm863, ibm864, ibm865, ibm866, ibm868, ibm869, ibm870, ibm871, ibm918, iso-2022-cn, iso-2022-jp, iso-2022-jp-2, iso-2022-kr, iso-8859-1, iso-8859-13, iso-8859-15, iso-8859-2, iso-8859-3, iso-8859-4, iso-8859-5, iso-8859-6, iso-8859-7, iso-8859-8, iso-8859-9, jis_x0201, jis_x0212-1990, koi8-r, koi8-u, shift_jis, tis-620, us-ascii, utf-16, utf-16be, utf-16le, utf-32, utf-32be, utf-32le, utf-8, windows-1250, windows-1251, windows-1252, windows-1253, windows-1254, windows-1255, windows-1256, windows-1257, windows-1258, windows-31j, x-big5-hkscs-2001, x-big5-solaris, x-compound_text, x-euc-jp-linux, x-euc-tw, x-eucjp-open, x-ibm1006, x-ibm1025, x-ibm1046, x-ibm1097, x-ibm1098, x-ibm1112, x-ibm1122, x-ibm1123, x-ibm1124, x-ibm1166, x-ibm1364, x-ibm1381, x-ibm1383, x-ibm300, x-ibm33722, x-ibm737, x-ibm833, x-ibm834, x-ibm856, x-ibm874, x-ibm875, x-ibm921, x-ibm922, x-ibm930, x-ibm933, x-ibm935, x-ibm937, x-ibm939, x-ibm942, x-ibm942c, x-ibm943, x-ibm943c, x-ibm948, x-ibm949, x-ibm949c, x-ibm950, x-ibm964, x-ibm970, x-iscii91, x-iso-2022-cn-cns, x-iso-2022-cn-gb, x-iso-8859-11, x-jis0208, x-jisautodetect, x-johab, x-macarabic, x-maccentraleurope, x-maccroatian, x-maccyrillic, x-macdingbat, x-macgreek, x-machebrew, x-maciceland, x-macroman, x-macromania, x-macsymbol, x-macthai, x-macturkish, x-macukraine, x-ms932_0213, x-ms950-hkscs, x-ms950-hkscs-xp, x-mswin-936, x-pck, x-sjis_0213, x-utf-16le-bom, x-utf-32be-bom, x-utf-32le-bom, x-windows-50220, x-windows-50221, x-windows-874, x-windows-949, x-windows-950, x-windows-iso2022jp",
    "content-length": "3040",
    "host": "e5731f27.ngrok.io",
    "user-agent": "Apache-HttpClient/4.5.6 (Java/1.8.0_181)",
    "accept-encoding": "gzip,deflate",
    "x-forwarded-proto": "https",
    "x-forwarded-for": "35.238.119.89"
  },
  "_init": {},
  "sandbox": true,
  "input": {
    "raw": "Talk to my company celero LTD",
    "type": "KEYBOARD"
  },
  "surface": {
    "capabilities": {
      "list": [
        {
          "name": "actions.capability.AUDIO_OUTPUT"
        },
        {
          "name": "actions.capability.MEDIA_RESPONSE_AUDIO"
        },
        {
          "name": "actions.capability.WEB_BROWSER"
        },
        {
          "name": "actions.capability.SCREEN_OUTPUT"
        }
      ]
    }
  },
  "available": {
    "surfaces": {
      "list": [
        {
          "capabilities": {
            "list": [
              {
                "name": "actions.capability.AUDIO_OUTPUT"
              },
              {
                "name": "actions.capability.WEB_BROWSER"
              },
              {
                "name": "actions.capability.SCREEN_OUTPUT"
              }
            ]
          }
        }
      ],
      "capabilities": {
        "surfaces": [
          {
            "capabilities": {
              "list": [
                {
                  "name": "actions.capability.AUDIO_OUTPUT"
                },
                {
                  "name": "actions.capability.WEB_BROWSER"
                },
                {
                  "name": "actions.capability.SCREEN_OUTPUT"
                }
              ]
            }
          }
        ]
      }
    }
  },
  "user": {
    "raw": {
      "userStorage": "{\"data\":{}}",
      "lastSeen": "2018-12-09T16:31:52Z",
      "locale": "en-US",
      "userId": "ABwppHGscAZl8ESw0TOWpQy3BbypDvPomBN7Bjlz0lm3ICUVdnsON6KwbFXST_fw2Z-hAR-f-u5o"
    },
    "storage": {},
    "_id": "ABwppHGscAZl8ESw0TOWpQy3BbypDvPomBN7Bjlz0lm3ICUVdnsON6KwbFXST_fw2Z-hAR-f-u5o",
    "locale": "en-US",
    "permissions": [],
    "last": {
      "seen": "2018-12-09T16:31:52.000Z"
    },
    "name": {},
    "entitlements": [],
    "access": {},
    "profile": {}
  },
  "arguments": {
    "parsed": {
      "input": {},
      "list": []
    },
    "status": {
      "input": {},
      "list": []
    },
    "raw": {
      "list": [],
      "input": {}
    }
  },
  "device": {},
  "id": "ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX",
  "type": "NEW",
  "screen": true,
  "body": {
    "responseId": "4814d39d-076e-47cc-a164-ed2868e7797d",
    "queryResult": {
      "queryText": "GOOGLE_ASSISTANT_WELCOME",
      "parameters": {},
      "allRequiredParamsPresent": true,
      "fulfillmentMessages": [
        {
          "text": {
            "text": [
              ""
            ]
          }
        }
      ],
      "outputContexts": [
        {
          "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/google_assistant_welcome"
        },
        {
          "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_screen_output"
        },
        {
          "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_audio_output"
        },
        {
          "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/google_assistant_input_type_keyboard"
        },
        {
          "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_web_browser"
        },
        {
          "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_media_response_audio"
        }
      ],
      "intent": {
        "name": "projects/fir-5c548/agent/intents/00693871-1f4c-484e-b658-a54b86e7df92",
        "displayName": "welcomeIntent"
      },
      "intentDetectionConfidence": 1,
      "languageCode": "en-us"
    },
    "originalDetectIntentRequest": {
      "source": "google",
      "version": "2",
      "payload": {
        "isInSandbox": true,
        "surface": {
          "capabilities": [
            {
              "name": "actions.capability.AUDIO_OUTPUT"
            },
            {
              "name": "actions.capability.MEDIA_RESPONSE_AUDIO"
            },
            {
              "name": "actions.capability.WEB_BROWSER"
            },
            {
              "name": "actions.capability.SCREEN_OUTPUT"
            }
          ]
        },
        "requestType": "SIMULATOR",
        "inputs": [
          {
            "rawInputs": [
              {
                "query": "Talk to my company celero LTD",
                "inputType": "KEYBOARD"
              }
            ],
            "intent": "actions.intent.MAIN"
          }
        ],
        "user": {
          "userStorage": "{\"data\":{}}",
          "lastSeen": "2018-12-09T16:31:52Z",
          "locale": "en-US",
          "userId": "ABwppHGscAZl8ESw0TOWpQy3BbypDvPomBN7Bjlz0lm3ICUVdnsON6KwbFXST_fw2Z-hAR-f-u5o"
        },
        "conversation": {
          "conversationId": "ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX",
          "type": "NEW"
        },
        "availableSurfaces": [
          {
            "capabilities": [
              {
                "name": "actions.capability.AUDIO_OUTPUT"
              },
              {
                "name": "actions.capability.WEB_BROWSER"
              },
              {
                "name": "actions.capability.SCREEN_OUTPUT"
              }
            ]
          }
        ]
      }
    },
    "session": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX"
  },
  "version": 2,
  "action": "",
  "intent": "welcomeIntent",
  "parameters": {},
  "contexts": {
    "_session": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX",
    "input": {
      "google_assistant_welcome": {
        "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/google_assistant_welcome"
      },
      "actions_capability_screen_output": {
        "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_screen_output"
      },
      "actions_capability_audio_output": {
        "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_audio_output"
      },
      "google_assistant_input_type_keyboard": {
        "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/google_assistant_input_type_keyboard"
      },
      "actions_capability_web_browser": {
        "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_web_browser"
      },
      "actions_capability_media_response_audio": {
        "name": "projects/fir-5c548/agent/sessions/ABwppHGmrysp8kg2DTPeaa8wLUOyZfEZWnYVMMBlECUfjewwxFRMxm-Q7ON1BsNW417QlzFlghEX/contexts/actions_capability_media_response_audio"
      }
    },
    "output": {}
  },
  "incoming": {
    "parsed": [
      ""
    ]
  },
  "query": "GOOGLE_ASSISTANT_WELCOME",
  "data": {}
}
```

Your whole simple app look like below.

```JavaScript
const {dialogflow} = require('actions-on-google');
const app = dialogflow({debug: false});

app.intent('welcomeIntent', (conv) => {
    conv.ask('Hi, What is your name?');
});

module.exports = app;

```

Of course we could define n app.intent functions in one app.js file but it is better to add app.intent functions to each separate file. For that purpose we need to register our intents functions

Lets defined first a getNameIntent. We will expect that a user tell us a name and Google Assistant (GA) will say hello with this name.
We need to define a path where we put our intent and create that file.

```JavaScript
const welcomeIntent = require('./intents/welcomeIntent.js')
```
In the app.js file we need to create a for loop which is responding for register all intents because we want to have all defined intents in the separate files.

In a function addIntents we define n parameters (... args)
```JavaScript

/** Adds Intent-name & callback key value pairs to app */
function addIntents(...args) {
  for (let i = 0; i < args.length; i++) {
    for (const key in args[i]) {
      if (args[i].hasOwnProperty(key)) {
        app.intent(key, args[i][key]);
      }
    }
  }
}
```
It checks if that function is defined in a propter style like 'nameOfIntent': function (conv). It checks if function which is object has own property. If yes register intent in the way: app.intetnt('nameOfIntent', function(conv) it is ok but in our code we try to use an arrow functions. Please keep in mind those 2 examples are equivalent:
```JavaScript
module.exports = {
  'welcomeIntent': function(conv) {
    conv.ask('Hi, what is your name?');
  },
};
```
and arrowFunction:
```JavaScript
module.exports = {
  'welcomeIntent': (conv) => {
    conv.ask('Hi, what is your name?');
  },
};
```
We can respond to user with conv.ask method.  In that case GA will wait for an answer when it says "Hi, what is your name".

In the end we need to register this function to our intents in our app.js file.

```JavaScript
addIntents(
    welcomeIntent
);
```
In that case our welcomeIntent was exported to the separated file. You can be sure now that your code would be easier to maintain.

Imagine you want to add a new Intent, a nameIntent that you get a user name. You need to create a new variable and add it to addIntents functions.

In the nameIntent.js file
```JavaScript
module.exports = {
  'nameIntent': (conv, parameter) => {
    const myName = conv.parameter['given-name'];
    conv.close('Hi '+myName);
  },
};
```

In the 'nameIntent' the callback receives two important arguments:

-   A [`Dialogflow Conv`](https://actions-on-google.github.io/actions-on-google-nodejs/classes/dialogflow.dialogflowconversation.html) object. This is a client library abstraction of the state of the dialog, and includes properties which represent values of the incoming request to our webhook, such as the current active Dialogflow contexts, the surface capabilities of the user device, etc.
-   A Dialogflow [`Parameters`](https://actions-on-google.github.io/actions-on-google-nodejs/interfaces/dialogflow.parameters.html) object. This is a JavaScript Object representation of the parameter values collected in the related intent. If you configured your entity in Dialogflow in the nameIntent your GA should say Hi, [name] and close conversation.




## How to add responses to your conversations

As mentioned you can add responses in 2 ways to your user.
 a) In this case Google Assistant waits for your next reaction
```javascript
    conv.ask(
        'Google Asistant waits for you next question/statment'
    );
```
b) Google Assistant closes conversation and your action too.

```javascript
    conv.close(
        'Im closing your action and I dont want to talk with you any more now!'
    );
```

Of course we could add some more interactions with our user. Imagine we would like to deliver some clickable link or images to your user phone..


## Responses in a different way

We would like to put some ssml tags (some instruction for google assistant that it follows reading our text).

First we need to import some more features from DialogFlow library:
``` javascript

const {
  dialogflow,
  SimpleResponse,
  BasicCard,
  Suggestions

} = require('actions-on-google');
```

You can provide that user can see on its smartphone some other things.

``` javascript

app.intent('welcomeIntent', (conv) => {

    conv.ask(new SimpleResponse({
        text: 'Hello in my company app. My user will see that in its phone',
        speech: '<speak> Hello <break time="3s"/> in my app </speak>',
    }));

    conv.ask(new BasicCard({
        title: 'This is my wonderfull company app',
        image: new Image({
            url: 'http://www.thebluediamondgallery.com/handwriting/images/example.jpg',
            alt: 'Really?',
        }),
        buttons: new Button({
            title: 'My company channel',
            url: 'https://www.youtube.com/user/OPITZCONSULTING',
        }),
    }));
});
```
Output:

![enter image description here](https://lh3.googleusercontent.com/AHXGBELsEDQUPOETvfC_6lBjpVqQfZamJu0Z58-tOfPyhVaUv3gSEs8KRoCb5_zG6PLup1akhHQZ)

  ### Sessions variable

You can save some session values in conv object
`conv.data.userName `

```JavaScript
module.exports = {
  'nameIntent': (conv, parameter) => {
    const myName = conv.parameter['given-name'];
    conv.data.userName = myName;
    conv.close(`Hi ${myName}`);
  },
};
```
this attribute will be stored as a session variable. You can get access to it any time you want in other intents.



### Interesting examples in JS

How to execute ?
`a(2)(3) `

```JavaScript
function a(x){
    console.log(x);
    return function(y){
        console.log(x+y);
    }
}
```

`b(2).run `

```JavaScript
function b(x){
    console.log(x);
    return {run: 'Hallloooo'}
}
```

