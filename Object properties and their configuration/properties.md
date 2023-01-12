```
№1 Используя флаг writable, сделайте свойство user.name доступным только для чтения.
let user = {
  name: "John"
};

Решение:
let user = {
  name: "John"
};

Object.defineProperty(user, "name", {
  writable: false
});


№2 Что будет выведено в консоль?
const user = {};

Object.defineProperties(user, {
  name: {
    value: "Olga",
    enumerable: true
  },
  age: {
    value: 25,
    configurable: true,
    enumerable: true,
    writable: true
  }
});

console.log(user);

Решение: { name: "Olga", age: 25 }


№3 Что будет выведено в консоль?
let myCar = {
  brand: "Opel",
  year: 2014,
  set age(value) {
    this.year = 2020 - value;
  },
  get allInfo() {
    return `Car: ${this.brand}, year: ${this.year}`;
  }
};

myCar.age = 2010; 
console.log(myCar.allInfo);

Решение: Car: Opel, year: 10 (вызов геттера)


№4 Что будет выведено в консоль?
// Исходный объект
let myCar = {
  brand: "Opel",
  year: 0
};

Object.defineProperty(myCar, "age", {
  set: function(value) {
    this.year = 2020 - value;
  },
  get: function() {
    return `Car: ${this.brand}, year: ${this.year}`;
  }
});

myCar.age = 2010;
console.log(myCar.age); 
console.log(myCar); 

Решение: Car: Opel, year: 10; { brand: "Opel", year: 10, … }
```

