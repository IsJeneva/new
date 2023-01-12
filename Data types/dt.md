```
№1 Вывведите в консоль число 255 в двоичной и шестнадцатиричной системе счисления,используя метод для строкового представления числа.

Решение:  
let num = 255;

console.log( num.toString(16) );
console.log( num.toString(2) );


№2 Что будет выведено в консоль?
console.log( parseInt('300px') );
console.log( parseFloat('17.5em') );
console.log ( Math.floor(3.3) );
console.log ( Math.ceil(4.2) );
console.log ( Math.round(5.1) );
console.log ( Math.trunc(6.6) );
console.log ( Math.pow(2, 3) );
console.log ( Math.max(3, 5, -10, 0, 1) );
console.log ( Math.min(1, 2) );

Решение:300; 17.5; 3 3; 4 5; 5 5; 6 6; 7 8; 8 5; 9 1.


№3 Напишите функцию theFirst(str), возвращающую строку str с заглавным первым символом.

Решение:
function theFirst(str) {
  if (!str) return str;

  return str[0].toUpperCase() + str.slice(1);
}

console.log( theFirst("вася") ); // Вася


№4 Дан массив names, выведите в консоль последнее имя.
let names = ["Ann", "Kate", "Mary", "Eva"];

Решение:
let names = ["Ann", "Kate", "Mary", "Eva"];
console.log( names.at(-1) );


№5 Дан массив let products = ["Tomatoes", "Bread", "Water"];
Добавьте "Meat" в начало массива, выведите итоговый массив и вычислите его количество элементов

Решение:
let products = ["Tomatoes", "Bread", "Water"];

products.unshift("Meat");

console.log(products)
console.log( products.length );


№6 Дан массив let arr = ["Apple", "Orange", "Pear"];
Сделайте перебор элементов массива

Решение:  
let arr = ["Яблоко", "Апельсин", "Груша"];

for (let i = 0; i < arr.length; i++) {
  console.log( arr[i] );
}


№7 Дан массив arr, удалите все дублирующиеся значения
let arr = [1, 1, 2, 3, 3, 4, 5, 5]

Решение:
let arr = [1, 1, 2, 3, 3, 4, 5, 5]
let unique = arr.filter((v, i, a) => a.indexOf(v) === i);

console.log(unique);


№8 У вас есть массив объектов products, и в каждом из них есть products.name. Напишите код, который преобразует их в массив имён.
let tomatoes = { name: "tomatoes", price: 4 };
let cheese = { name: "cheese", price: 7 };
let bread = { name: "bread", price: 3 };

let products = [ tomatoes, cheese, bread ];

let titles = products.map(item => item.title);

console.log( titles);


№9 Напишите функцию getAverageAge для получения суммарного возраста users.Используйте метод reduce
let john = { name: "John", age: 27 };
let mary = { name: "Mary", age: 24 };
let harry = { name: "Harry", age: 25 };

Решение:
function getAverageAge(users) {
  return users.reduce((prev, user) => prev + user.age, 0) 
}

let john = { name: "John", age: 27 };
let mary = { name: "Mary", age: 26 };
let harry = { name: "Harry", age: 25 };

let arr = [ john, mary , harry ];

console.log( getAverageAge(arr) );


№10 Напишите функцию getWeekDay(date), показывающую день недели в коротком формате: «ПН», «ВТ», «СР», «ЧТ», «ПТ», «СБ», «ВС».

Решение:
function getWeekDay(date) {
  let days = ['ВС', 'ПН', 'ВТ', 'СР', 'ЧТ', 'ПТ', 'СБ'];

  return days[date.getDay()];
}

let date = new Date(2014, 1, 3); 
console.log( getWeekDay(date) ); 


№11 Преобразуйте product в JSON, затем прочитайте этот JSON в другую переменную.
let product = {
  title: "Orange",
  price: 5
};

Решение:
let product2 = JSON.parse(JSON.stringify(product));
```
