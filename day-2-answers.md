11. C Wrong
12. A
13. C Wrong
14. A Wrong
15. C
16. C
17. C Wrong
18. C
19. B Wrong
20. C

Answers

11. Answer: A

In JavaScript, functions are objects, and therefore, the method getFullName gets added to the constructor function object itself. For that reason, we can call Person.getFullName(), but member.getFullName throws a TypeError.

If you want a method to be available to all object instances, you have to add it to the prototype property:

Person.prototype.getFullName = function() {
return `${this.firstName} ${this.lastName}`;
};

12. Answer: A

For sarah, we didn't use the new keyword. When using new, this refers to the new empty object we create. However, if you don't add new, this refers to the global object!

We said that this.firstName equals "Sarah" and this.lastName equals "Smith". What we actually did, is defining global.firstName = 'Sarah' and global.lastName = 'Smith'. sarah itself is left undefined, since we don't return a value from the Person function.

13. Answer: D

During the capturing phase, the event goes through the ancestor elements down to the target element. It then reaches the target element, and bubbling begins.

14. Answer: B

All objects have prototypes, except for the base object. The base object is the object created by the user, or an object that is created using the new keyword. The base object has access to some methods and properties, such as .toString. This is the reason why you can use built-in JavaScript methods! All of such methods are available on the prototype. Although JavaScript can't find it directly on your object, it goes down the prototype chain and finds it there, which makes it accessible for you.

15. Answer: C

JavaScript is a dynamically typed language: we don't specify what types certain variables are. Values can automatically be converted into another type without you knowing, which is called implicit type coercion. Coercion is converting from one type into another.

In this example, JavaScript converts the number 1 into a string, in order for the function to make sense and return a value. During the addition of a numeric type (1) and a string type ('2'), the number is treated as a string. We can concatenate strings like "Hello" + "World", so what's happening here is "1" + "2" which returns "12".

16. Answer: C

The postfix unary operator ++:

    Returns the value (this returns 0)
    Increments the value (number is now 1)

The prefix unary operator ++:

    Increments the value (number is now 2)
    Returns the value (this returns 2)

This returns 0 2 2.

17. Answer: B

If you use tagged template literals, the value of the first argument is always an array of the string values. The remaining arguments get the values of the passed expressions!

18. Answer: C

When testing equality, primitives are compared by their value, while objects are compared by their reference. JavaScript checks if the objects have a reference to the same location in memory.

The two objects that we are comparing don't have that: the object we passed as a parameter refers to a different location in memory than the object we used in order to check equality.

This is why both { age: 18 } === { age: 18 } and { age: 18 } == { age: 18 } return false.

19. Answer: C

The rest parameter (...args) lets us "collect" all remaining arguments into an array. An array is an object, so typeof args returns "object"

20. Answer: C

With "use strict", you can make sure that you don't accidentally declare global variables. We never declared the variable age, and since we use "use strict", it will throw a reference error. If we didn't use "use strict", it would have worked, since the property age would have gotten added to the global object.
