## Plain Old JS Object Lesson Learning Objectives (W2D2) - Learning Objectives

1. Label variables as either Primitive vs. Reference
   There are 5 primitive data types:
   Boolean, Null, Undefined, Number, String
   1 Reference Type:
   Object (arrays are a kind of object)
2. Identify when to use . vs [] when accessing values of an object:

```js
//Using [](bracket) notation

let person = {};

person['firstName'] = 'Jesse';
console.log(person);
person['firstName'] = 'Steven';

console.log(person);

//Using . (dot) notation

let person = {};

person.name = 'Brian';
console.log(person);
person.name = 'Steven';
console.log(person);
```

3. Use the obj[key] !== undefined pattern to check if a given variable that contains a key exists in an object

# Checking for Undefinied with bracket notation

```js
let person = {};
person.name = 'Paul';
person.age = 25;
console.log(person);
console.log(person['name'] === 'Paul');
console.log(person['age'] === 25);
console.log(person['occupation'] === undefined);
console.log(person['occupation'] !== undefined);
```

4. Utilize Object.keys and Object.values in a function

```js
//Object.keys

let cars = { make: 'honda', model: 'civic' };
console.log(Object.keys(cars));

//Object.values

let cars = { make: 'honda', model: 'civic' };
console.log(Object.values(cars));
```

5. Iterate through an object using a for in loop

```js
let obj = { game: 'call of duty', console: 'PC duh?' };

for (let keys in obj) {
	let values = obj[keys];
	console.log('Here are the key value pairs!', keys, '-', values);
}
```

6. Define a function that utilizes ...rest syntax to accept an arbitrary number of arguments

```js
let acceptEverything = function (...everything) {
	console.log(everything);
};

acceptEverything('thing1', 'thing2', 'thing3');
```

7. Use ...spread syntax for Object literals and Array literals

```js
let arrayOfNums = [0, 1, 2, 3, 4];

let moreNums = [...arrayOfNums, 5, 6, 7, 8, 9];

console.log(moreNums);

let hubby = { firstName: 'John', lastName: 'Doe' };
let wifey = { firsName: 'Jane', lastName: 'Doe' };

let couple = { ...hubby, ...wifey };
//Something interesting happens here
console.log(couple);

let person1 = { name: 'Jack', faveColor: 'red' };
let person2 = { name: 'Paul', faveColor: 'blue' };
let people = { ...person1, ...person2 };
console.log(people);
```

8. Destructure an array to reference specific elements

```js
let nums = [1, 2];

let [num1, num2] = nums;

console.log('num1 variable', num1, ' num2 variable', num2);
```

9. Destructure an object to reference specific values

```js
let person = {
	name: 'Kelly',
	getFaveColor: function () {
		return 'blue';
	},
	friends: {
		name: 'Ryan',
	},
};

let {
	friends: { name },
} = person;

console.log('name', person.name);
console.log('favorite color', person.getFaveColor());
console.log(name);
```

10. Write a function that accepts a array as an argument and returns an object representing the count of each character in the array

```js
let myCounter = function (array) {
	let myObj = {};
	let count = 1;
	array.forEach(function (char) {
		if (myObj[char] === undefined) {
			myObj[char] = count;
		} else {
			myObj[char]++;
		}
	});
	return myObj;
};

console.log(myCounter(['a', 'a', 'n', 'c']));
```
## Pair Programming Lesson Learning Objectives
1.	Differentiate between the "Driver" and "Navigator" roles in a pair programming session.
2.	Describe at least three benefits of effective pair programming.
3.	Demonstrate empathetic communication and be able to explain the meaning of "You are not your code".
4.	Identify negative interactions during a pair programming session.
5.	Identify the exact steps of a/A's pair programming process.
6.	Describe the importance of pair programming competency while interviewing for jobs.