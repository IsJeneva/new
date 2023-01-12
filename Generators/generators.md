```
№1 Что будет выведено в консоль?
function* generator(i) {
  yield i;
  yield i*2;
}

const gen = generator(10);

console.log(gen.next().value);
console.log(gen.next().value);

Решение: 10; 20.


№2 Что будет выведено в консоль?
function* yieldAndReturn() {
  yield "Y";
  return "R";
  yield "unreachable";
}

var gen = yieldAndReturn()
console.log(gen.next());
console.log(gen.next());
console.log(gen.next());

Решение: { value: "Y", done: false }; { value: "R", done: true }; { value: undefined, done: true }


№3 Что будет выведено в консоль?
async function* generateSequence(start, end) {

  for (let i = start; i <= end; i++) {

    // ура, можно использовать await!
    await new Promise(resolve => setTimeout(resolve, 1000));

    yield i;
  }

}

(async () => {

  let generator = generateSequence(1, 5);
  for await (let value of generator) {
   console.log(value); // 1, потом 2, потом 3, потом 4, потом 5
  }

})();
Решение: 1, 2, 3, 4, 5 каждую секунду


№4 Создайте функцию-генератор random(seed), которая получает seed и создаёт генератор с указанной формулой.
Формула: next = previous * 16807 % 2147483647

let generator = random(1);

console.log(generator.next().value); // 16807
console.log(generator.next().value); // 282475249
console.log(generator.next().value); // 1622650073

Решение:
function* pseudoRandom(seed) {
  let value = seed;

  while(true) {
    value = value * 16807 % 2147483647
    yield value;
  }

};

let generator = pseudoRandom(1);

console.log(generator.next().value); 
console.log(generator.next().value); 
console.log(generator.next().value);
```
