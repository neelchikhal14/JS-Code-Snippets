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

4.  ***

    +true;
    !'Lydia';

        A: 1 and false
        B: false and NaN
        C: false and false

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

9. ***

let greeting;
greetign = {}; // Typo!
console.log(greetign);

    A: {}
    B: ReferenceError: greetign is not defined
    C: undefined

10. ***

function bark() {
console.log('Woof!');
}

bark.animal = 'dog';

    A: Nothing, this is totally fine!
    B: SyntaxError. You cannot add properties to a function this way.
    C: "Woof" gets logged.
    D: ReferenceError
