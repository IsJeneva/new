```
№1 Почему не создается объект класса?
class Figures {
  constructor(name) {
    this.name = name;
  }
}

class Rectangle extends Figures {
  constructor(name) {
    this.name = name;
    this.created = Date.now();
  }
}

let rectangle = new Rectangle ("Прямоугольник"); // Error: this is not defined
console.log(rectangle.name);

Решение: потому что конструктор дочернего класса должен вызывать super().

Правильный код:
class Figures {
  constructor(name) {
    this.name = name;
  }
}

class Rectangle extends Figures {
  constructor(name) {
    super(name);
    this.created = Date.now();
  }
}

let rectangle. = new Rectangle("Прямоугольник");
console.log(rectangle.name);

Решение: true


№2 Что будет выведено в консоль?
class Figures {}
let rectangle = new Figures();

console.log( rectangle instanceof Figures );

Решение: true


№3 Что будет выведено в консоль? Почему?
function Figures() {}
let rectangle = new Figures();

Figures.prototype = {};

console.log( rectangle instanceof Figures );
Решение: false, т.к. заменили прототив


№4 Реализуйте класс Worker (Работник), который будет иметь следующие свойства:
name (имя), surname (фамилия), rate (ставка за день работы), days (количество отработанных дней).
Также класс должен иметь метод getSalary(), который будет выводить зарплату работника.
Зарплата - это произведение (умножение) ставки rate на количество отработанных дней days.

Вот так должен работать класс:
var worker = new Worker('Иван', 'Иванов', 10, 31);

console.log(worker.getName()); //выведет 'Иван'
console.log(worker.getSurname()); //выведет 'Иванов'
console.log(worker.getRate()); //выведет 10
console.log(worker.getDays()); //выведет 31
console.log(worker.getSalary()); //выведет 310 - то есть 10\*31

Решение:
class WorkerTypeOne {
    name;
    surname;
    rate;
    days;
    constructor(name, surname, rate, days) {
        this.name = name;
        this.surname = surname;
        this.rate = rate;
        this.days = days;
    }
    getSalary(rate, days) {
        let salary = this.rate * this.days;
        return salary;
    }
}
let workeOne = new WorkerTypeOne('Иван', 'Иванов', 10, 31);
console.log(workeOne.name);
console.log(workeOne.surname);
console.log(workeOne.rate);
console.log(workeOne.days);
console.log(workeOne.getSalary());


№5 Модифицируйте класс WorkerTypeOne из предыдущей задачи следующим образом: сделайте все
его свойства приватными, а для их чтения сделайте методы-геттеры.

Класс теперь будет работать так:
var worker = new Worker('Иван', 'Иванов', 10, 31);

console.log(worker.getName()); //выведет 'Иван'
console.log(worker.getSurname()); //выведет 'Иванов'
console.log(worker.getRate()); //выведет 10
console.log(worker.getDays()); //выведет 31
console.log(worker.getSalary()); //выведет 310 - то есть 10\*31

Решение:
class WorkerTypeTwo {
    #name;
    #surname;
    #rate;
    #days;
    constructor(name, surname, rate, days) {
        this.#name = name;
        this.#surname = surname;
        this.#rate = rate;
        this.#days = days;
    }
    getName() {
        return this.#name;
    }
    getSurname() {
        return this.#surname;
    }
    getRate() {
        return this.#rate;
    }
    getDays() {
        return this.#days;
    }
    getSalary(rate, days) {
        let salary = this.#rate * this.#days;
        return salary;
    }
}
workeTwo = new WorkerTypeTwo('Иван', 'Иванов', 10, 31);
console.log(workeTwo.getName());
console.log(workeTwo.getSurname());
console.log(workeTwo.getRate());
console.log(workeTwo.getDays());
console.log(workeTwo.getSalary());
```
