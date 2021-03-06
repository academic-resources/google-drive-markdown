//----------------------------------------------------------
//****\*\*\*\*****\*\*\*\*****\*\*\*\*****\*\*\*****\*\*\*\*****\*\*\*\*****\*\*\*\*****
//---------------------------------------------------------

**for (key in object)**

const object = { a: 1, b: 2, c: 3 };

for (const property in object) {
console.log(`${property}: ${object[property]}`);
}

// expected output:
// "a: 1"
// "b: 2"
// "c: 3"

Syntax
for (variable in object){
statement
}
variable
A different property name is assigned to variable on each iteration.
object
Object whose non-Symbol enumerable properties are iterated over.
Description

A for...in loop only iterates over enumerable, non-Symbol properties. Objects created from built–in constructors like Array and Object have inherited non–enumerable properties from Object.prototype and String.prototype, such as String's indexOf() method or Object's toString() method. The loop will iterate over all enumerable properties of the object itself and those the object inherits from its prototype chain (properties of nearer prototypes take precedence over those of prototypes further away from the object in its prototype chain).

Deleted, added, or modified properties
A for...in loop iterates over the properties of an object in an arbitrary order (see the delete operator for more on why one cannot depend on the seeming orderliness of iteration, at least in a cross-browser setting).

If a property is modified in one iteration and then visited at a later time, its value in the loop is its value at that later time. A property that is deleted before it has been visited will not be visited later. Properties added to the object over which iteration is occurring may either be visited or omitted from iteration.

In general, it is best not to add, modify, or remove properties from the object during iteration, other than the property currently being visited. There is no guarantee whether an added property will be visited, whether a modified property (other than the current one) will be visited before or after it is modified, or whether a deleted property will be visited before it is deleted.

Array iteration and for...in
Note: for...in should not be used to iterate over an Array where the index order is important.

Array indexes are just enumerable properties with integer names and are otherwise identical to general object properties. There is no guarantee that for...in will return the indexes in any particular order. The for...in loop statement will return all enumerable properties, including those with non–integer names and those that are inherited.

Because the order of iteration is implementation-dependent, iterating over an array may not visit elements in a consistent order. Therefore, it is better to use a for loop with a numeric index (or Array.prototype.forEach() or the for...of loop) when iterating over arrays where the order of access is important.

Iterating over own properties only
If you only want to consider properties attached to the object itself, and not its prototypes, use getOwnPropertyNames() or perform a hasOwnProperty() check (propertyIsEnumerable() can also be used). Alternatively, if you know there won't be any outside code interference, you can extend built-in prototypes with a check method.

Why Use for...in?
Given that for...in is built for iterating object properties, not recommended for use with arrays, and options like Array.prototype.forEach() and for...of exist, what might be the use of for...in at all?

It may be most practically used for debugging purposes, being an easy way to check the properties of an object (by outputting to the console or otherwise). Although arrays are often more practical for storing data, in situations where a key-value pair is preferred for working with data (with properties acting as the "key"), there may be instances where you want to check if any of those keys hold a particular value.

Examples
Using for...in
The for...in loop below iterates over all of the object's enumerable, non-Symbol properties and logs a string of the property names and their values.

var obj = {a: 1, b: 2, c: 3};

for (const prop in obj) {
console.log(`obj.${prop} = ${obj[prop]}`);
}

// Output:
// "obj.a = 1"
// "obj.b = 2"
// "obj.c = 3"
Iterating own properties
The following function illustrates the use of hasOwnProperty(): the inherited properties are not displayed.

var triangle = {a: 1, b: 2, c: 3};

function ColoredTriangle() {
this.color = 'red';
}

ColoredTriangle.prototype = triangle;

var obj = new ColoredTriangle();

for (const prop in obj) {
if (obj.hasOwnProperty(prop)) {
console.log(`obj.${prop} = ${obj[prop]}`);
}
}

// Output:
// "obj.color = red"

//--------------------END of for (let key in Obj)------

//------------Object.entries
Syntax
Object.entries(obj)
Parameters
obj
The object whose own enumerable string-keyed property [key, value] pairs are to be returned.
Return value
An array of the given object's own enumerable string-keyed property [key, value] pairs.

Description
Object.entries() returns an array whose elements are arrays corresponding to the enumerable string-keyed property [key, value] pairs found directly upon object. The ordering of the properties is the same as that given by looping over the property values of the object manually.

Examples
const obj = { foo: 'bar', baz: 42 };
console.log(Object.entries(obj)); // [ ['foo', 'bar'], ['baz', 42] ]

// array like object
const obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.entries(obj)); // [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ]

// array like object with random key ordering
const anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.entries(anObj)); // [ ['2', 'b'], ['7', 'c'], ['100', 'a'] ]

// getFoo is property which isn't enumerable
const myObj = Object.create({}, { getFoo: { value() { return this.foo; } } });
myObj.foo = 'bar';
console.log(Object.entries(myObj)); // [ ['foo', 'bar'] ]

// non-object argument will be coerced to an object
console.log(Object.entries('foo')); // [ ['0', 'f'], ['1', 'o'], ['2', 'o'] ]

// returns an empty array for any primitive type, since primitives have no own properties
console.log(Object.entries(100)); // [ ]

// iterate through key-value gracefully
const obj = { a: 5, b: 7, c: 9 };
for (const [key, value] of Object.entries(obj)) {
console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
}

// Or, using array extras
Object.entries(obj).forEach(([key, value]) => {
console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
});
Converting an Object to a Map
The new Map() constructor accepts an iterable of entries. With Object.entries, you can easily convert from Object to Map:

const obj = { foo: 'bar', baz: 42 };
const map = new Map(Object.entries(obj));
console.log(map); // Map { foo: "bar", baz: 42 }
Iterating through an Object
Using Array Destructuring, you can iterate through objects easily.

const obj = { foo: 'bar', baz: 42 };
Object.entries(obj).forEach(([key, value]) => console.log(`${key}: ${value}`)); // "foo: bar"
