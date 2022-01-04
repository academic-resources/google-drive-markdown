# OOP REVIEW


Object Oriented Programming
- computer programming model 
- organizes software design around data (or objects) rather than functions


What is an Object?
- data field that has unique attributes and behaviors
- self contained pieces of code


Three Pillars of OOP
1. encapsulation
2. inheritance
3. polymorphism



Encapsulation
- "enclose something in a capsule"
- the bundling of data and the methods that act on that data so that 
	access to that data is restricted from outside the bundle
- an object stores its state privately and only the object's methods
  have access to change it 
	- you dont change the encapsulated state directly
	- you call a method on the object which may update its state
	- code that uses thee methods dont have to worry about details



Inheritance
- data and methods defined on parent class are avaailable on objects created
  from classes that inherit from those parent classes
- prevents duplication of code  
- typically applied to classes




Polymorphism 
- ability to create a property, func, or object that has more than one realization
- ability to substitute classes that havee common functionality in sense of methods and data
- "if you can drive a car, you can drive any car"

```js

const rectangle = {
	width: 4,
	height: 6,
	area() {
		return this.width * this.height;
	}
}

const triangle = {
	base: 4,
	height: 2,
	area() {
		return this.base * this.height / 2;
	}
}


const square = {
  side: 1,
  area() {
    return this.side**2;
  }
}


// each object has an area method
// we can use this method regardless of object type

function cumulateShapes(shapes) {

	let totalArea = 0;
	shapes.forEach(shape => {
		totalArea += shape.area();
	})
	return totalArea;
}

```



Abstraction (fourth principle)
- display only essential information
- hide the details








# THE LAW OF DEMETER



Coupling
- the degree of interdependence betweeen two or more classes
- the fewer the connections, less chance for ripple effect
	- one small change causes other changes and so on
- changing one class should not require a change of another class
	- if it does, the class is too "coupled" or interdependent
- to reduce coupling, reduce num of clases a given class must know to operate



The Law Of Demeter
- a method of an object can only invoke methods or use props of the following
	- methods on object itself
	- any of objects pasaseed in as params to the method
	- an object created in the method
	- any values stored in instance vars of the object
	- any values stored in global vars
- guideline: dont use more than one dot (not counting one after "this")



BAD EXAMPLE
- airplane class is coupled to throttle class

```js

class Airplane {
  constructor() {
    this.engine = new PropEngine();
  }

  takeOff() {
    // this.engine is a value stored in an instance variable
    this.engine.getThrottle().open();
    // two dots^     and     ^
  }
}

class PropEngine {
  constructor() {
    this.throttle = new Throttle();
  }

  getThrottle() {
    return this.throttle;
  }
}

class Throttle {
  open() {
    return "VROOOOM"!;
  }
}



```


GOOD EXAMPLE

```js
class Airplane {
  constructor() {
    this.engine = new PropEngine();
  }

  takeOff() {
    this.engine.openThrottle();
  }
}

class PropEngine {
  constructor() {
    this.throttle = new Throttle();
  }

  openThrottle() {
    return this.throttle.open();
  }
}

class Throttle {
  open() {
    return "VROOOOM"!;
  }

```


When to ignore the Law of Demeter
- when working with objects that come from code you didnt create
- sometimes UIs 








# ES6 MODULES



Browser Support for ES6 Modules
- ES6 modules can only be used when file is specified as a `module`
- can use HTTP server to serve HTML file with <script type="module">
	- `python3 -m http.server`
- running local web server gives you access to browser support for ES6 syntax