```
№1 Что будет выведено в консоль?
function callSomeFunc(){console.log("Функция callSomeFunc");}
try{
    callSomeFunc();
    console.log("Конец блока try");
}
catch(error){
    console.log("Возникла ошибка!");
}
 
console.log("Остальные инструкции");

Решение: Функция callSomeFunc; Конец блока try; Остальные инструкции


№2 Что будет выведено в консоль?
try{
    callSomeFunc();
    console.log("Конец блока try");
}
catch{
    console.log("Произошла ошибка");
}
finally{
    console.log("Блок finally")
}
 
console.log("Остальные инструкции");

Решение: Произошла ошибка; Блок finally; Остальные инструкции


№3 Создайте класс FormatError, который наследует от встроенного класса SyntaxError.
Класс должен поддерживать свойства message, name и stack.
let err = new FormatError("ошибка форматирования");

console.log( err.message ); // ошибка форматирования
console.log( err.name ); // FormatError
console.log( err.stack ); // stack

console.log( err instanceof FormatError ); // true
console.log( err instanceof SyntaxError ); // true (потому что наследует от SyntaxError)

Решение:
class FormatError extends SyntaxError {
  constructor(message) {
    super(message);
    this.name = "FormatError";
  }
}

let err = new FormatError("ошибка форматирования");

console.log( err.message ); // ошибка форматирования
console.log( err.name ); // FormatError
console.log( err.stack ); // stack

console.log( err instanceof SyntaxError ); // true
```
