```
№1 Напишите программу на JavaScript для удаления свойства rollno из следующего объекта.
Выведите в консоль результат до и после удаления свойств.
Sample object:
var student = {
  name : "David Rayy",
  sclass : "VI",
  rollno : 12 
};

Решение:
var student = {
  name : "David Rayy",
  sclass : "VI",
  rollno : 12 
};
console.log(student);
delete student.rollno;
console.log(student);


№2 У нас есть объект, в котором хранятся данные о возрасте сотрудников нашей команды.
Посчитайте суммарный возраст сотрудников и выведете его в консоль
let salaries = {
  John: 25,
  Ann: 21,
  Pete: 22
};

Решение:
let salaries = {
  John: 25,
  Ann: 21,
  Pete: 22
};

let sum = 0;
for (let key in salaries) {
  sum += salaries[key];
}

console.log(sum);


№3 Каким будет результ сравнения двух объектов?
let a = {};
let b = {};

console.log( a == b );

Решение: false

№4 Что будет выведено в консоль?
const smallCupWithEar = {
  volume: 300,
  hasEar: true
};

const largeCup = { volume: 500 };

const myIdealCup = Object.assign(smallCupWithEar, largeCup);

console.log(myIdealCup);

Решение: {
  volume: 500,
  hasEar: true
}


№5 Функция makeUser возвращает объект.
Каким будет результат при обращении к свойству объекта ref? Почему?
function makeUser() {
  return {
    name: "John",
    ref: this
  };
}

let user = makeUser();

console.log( user.ref.name );

Решение: Error: Cannot read property 'name' of undefined
Здесь значение this внутри makeUser() равно undefined, потому что оно вызывается как функция,
а не через «точечный» синтаксис как метод. 


№6 Что будет выведено в консоль?
let user = {}; // пользователь без адреса
console.log( user?.address?.street );

Решение: undefined (без ошибки)

№7 Что будет выведено в консоль?
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 == id2);

Решение: false
```
