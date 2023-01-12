```
№1 Используя рекурсию, Напишите функцию sumTo(n), которая вычисляет сумму чисел 1 + 2 + ... + n.

Решение:
function sumTo(n) {
  if (n == 1) return 1;
  return n + sumTo(n - 1);
}


console.log( sumTo(100) );


№2 Что будет выведено в консоль?
function showName(firstName, lastName, ...titles) {

  console.log( titles[0] );
  console.log( titles[1] );
  console.log( titles.length );
}
showName("Французский", "деятель", "Наполеон", "Бонапарт");

Решение: Наполеон Бонапарт 2


№3 Даны два массива. Испотльзуя оператор расширения соедините их в один массив и выведите итоговый
let arr = [1, 5, 8];
let arr2 = [8, 9, 15];

let arr3 = [0, ...arr, 2, ...arr2];
console.log (arr3);

Решение: 0, 1, 5, 8, 2, 7, 9, 15


№4 Что будет выведено в консоль?
function Counter() {
  let count = 0;

  this.up = function() {
    return ++count;
  };

  this.down = function() {
    return --count;
  };
}

let counter = new Counter();

console.log( counter.up() );
console.log( counter.up() );
console.log( counter.down() );

Решение: 1, 2, 1


№5 Что будет выведено в консоль?
function do_something() {
  console.log(bar); 
  var bar = 111;
  console.log(bar);
}

Решение: undefined, 111


№6 Что будет выведено в консоль?
const math = {
  factit: function factorial(n) {
  console.log(n)
  if (n <= 1) {
    return 1;
    }
  return n * factorial(n - 1);
  }
};

math.factit(3) //3;2;1;


№7 Используя setInterval, напишите функцию outputNumbers(from, to), которая будет выводить число каждую секунду,
Начиная с from и заканчивая to.

Решение:
function outputNumbers(from, to) {
  let current = from;

  let timerId = setInterval(function() {
    console.log(current);
    if (current == to) {
      clearInterval(timerId);
    }
    current++;
  }, 1000);
}

outputNumbers(1, 10);


№8 Что будет выведено в консоль?
var obj = { x: 15 };
    var x = 10;

function fun() {
    console.log(this.x);  
    console.log(this);    
}
 
fun();          
fun.call(obj); 

Решение: 10 (this ссылается на глобальный объект Window); 15 (15 – это значение свойства x внутри объекта obj).


№9 Что будет выведено в консоль?
var person = {
    firstName:"John",
    lastName: "Konor",
    fullName: function() {
        return this.firstName + " " + this.lastName;
    }
}
var user = {
    firstName:"Max",
    lastName: "White",
}

console.log(person.fullName.call(user));

Решение: "Max White"


№10 Что будет выведено в консоль?
    function f() {
        console.log(this.titile);
    }

f = f.bind( {titile: "Table"} ).bind( {titile: "Сhair"} ).bind( {titile: "Сabinet"} );

        f();

Решение: Table
```
