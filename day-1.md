1. ***
   function sayHi() {
   console.log(name);
   console.log(age);
   var name = 'Lydia';
   let age = 21;
   }

sayHi();

    A: Lydia and undefined
    B: Lydia and ReferenceError
    C: ReferenceError and 21
    D: undefined and ReferenceError

D

2. ***
   for (var i = 0; i < 3; i++) {
   setTimeout(() => console.log(i), 1);
   }

for (let i = 0; i < 3; i++) {
setTimeout(() => console.log(i), 1);
}

    A: 0 1 2 and 0 1 2
    B: 0 1 2 and 3 3 3
    C: 3 3 3 and 0 1 2

C

3. ***
   const shape = {
   radius: 10,
   diameter() {
   return this.radius _ 2;
   },
   perimeter: () => 2 _ Math.PI \* this.radius,
   };

console.log(shape.diameter());
console.log(shape.perimeter());

    A: 20 and 62.83185307179586
    B: 20 and NaN
    C: 20 and 63
    D: NaN and 63

B

4.  ***

        +true;
        !'Lydia';

            A: 1 and false
            B: false and NaN
            C: false and false

A

5.  ***
    const bird = {
    size: 'small',
    };

const mouse = {
name: 'Mickey',
small: true,
};

    A: mouse.bird.size is not valid
    B: mouse[bird.size] is not valid
    C: mouse[bird["size"]] is not valid
    D: All of them are valid

C - Wrong A

In JavaScript, all object keys are strings (unless it's a Symbol). Even though we might not type them as strings, they are always converted into strings under the hood.

JavaScript interprets (or unboxes) statements. When we use bracket notation, it sees the first opening bracket [ and keeps going until it finds the closing bracket ]. Only then, it will evaluate the statement.

mouse[bird.size]: First it evaluates bird.size, which is "small". mouse["small"] returns true

However, with dot notation, this doesn't happen. mouse does not have a key called bird, which means that mouse.bird is undefined. Then, we ask for the size using dot notation: mouse.bird.size. Since mouse.bird is undefined, we're actually asking undefined.size. This isn't valid, and will throw an error similar to Cannot read property "size" of undefined.

6. ***
   let c = { greeting: 'Hey!' };
   let d;

d = c;
c.greeting = 'Hello';
console.log(d.greeting);

    A: Hello
    B: Hey!
    C: undefined
    D: ReferenceError
    E: TypeError

A

7. ***
   let a = 3;
   let b = new Number(3);
   let c = 3;

console.log(a == b);
console.log(a === b);
console.log(b === c);

    A: true false true
    B: false false true
    C: true false false
    D: false true true

C

new Number() is a built-in function constructor. Although it looks like a number, it's not really a number: it has a bunch of extra features and is an object.
When we use the == operator (Equality operator), it only checks whether it has the same value. They both have the value of 3, so it returns true.
However, when we use the === operator (Strict equality operator), both value and type should be the same. It's not: new Number() is not a number, it's an object. Both return false.

8. ***

class Chameleon {
static colorChange(newColor) {
this.newColor = newColor;
return this.newColor;
}

constructor({ newColor = 'green' } = {}) {
this.newColor = newColor;
}
}

const freddie = new Chameleon({ newColor: 'purple' });
console.log(freddie.colorChange('orange'));

    A: orange
    B: purple
    C: green
    D: TypeError

Answer: D

The colorChange function is static. Static methods are designed to live only on the constructor in which they are created, and cannot be passed down to any children or called upon class instances. Since freddie is an instance of class Chameleon, the function cannot be called upon it. A TypeError is thrown.

9. ***

let greeting;
greetign = {}; // Typo!
console.log(greetign);

    A: {}
    B: ReferenceError: greetign is not defined
    C: undefined

A

10. ***

function bark() {
console.log('Woof!');
}

bark.animal = 'dog';

    A: Nothing, this is totally fine!
    B: SyntaxError. You cannot add properties to a function this way.
    C: "Woof" gets logged.
    D: ReferenceError

A
