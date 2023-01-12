```
№1 Что будет выведено в консоль?
let animal = {
  running: null
};
let tiger = {
  __proto__: animal,
  running: true
};

console.log( tiger.running ); // ? (1)

delete tiger.running;

console.log( tiger.running ); // ? (2)

delete animal.running;

console.log( tiger.running );

Решение: true; null; undefined.


№2 Присвойте следующим объектам ссылки __proto__:
let head = {
  glasses: 1
};

let table = {
  pen: 3
};

let bed = {
  sheet: 1,
  pillow: 2
};

let pockets = {
  money: 2000
};


Решение:
let head = {
  glasses: 1
};

let table = {
  pen: 3,
  __proto__: head
};

let bed = {
  sheet: 1,
  pillow: 2,
  __proto__: table
};

let pockets = {
  money: 2000,
  __proto__: bed
};


console.log( pockets.pen ); // 3
console.log( bed.glasses ); // 1
console.log( table.money ); // undefined


№3 Какие действия выполняются в данной задаче?
let animal = {
  eats: true
};

let = Object.create(animal); (1)

console.log(bear.eats);

console.log(Object.getPrototypeOf(bear) === animal); (2)

Object.setPrototypeOf(bear, {}); (3)

Решение:
(1): создаётся новый объект с прототипом animal;
(2): получаем прототип объекта bear;
(3): заменяем прототип объекта bear на {}


№4 Что будет выведено в консоль?
Animal.prototype.toString = function() {
  return 'This is ' + this.species + ' ' + this.name;
};

cat.toString = function() {
  return this.species + ' ' + this.name;
};

const cat = new Animal('Wizard', 'Cat', 'Meow');
const dog = new Animal('Pancho', 'Dog', 'Woof');

console.log(cat.toString());  
console.log(dog.toString());

Решение: Cat Wizard; This is Dog Pancho;
```
