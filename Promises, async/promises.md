```
№1 Что будет выведено в консоль?
console.log('start');

const promise1 = new Promise((resolve, reject) => {
  console.log(1)
  resolve(2)
  console.log(3)
})

promise1.then(res => {
  console.log(res)
})

console.log('end');

Решение: start , 1 , 3 , end и 2 .


№2 Что будет выведено в консоль?
console.log('start')

const fn = () => (new Promise((resolve, reject) => {
  console.log(1);
  resolve('success')
}))

console.log('middle')

fn().then(res => {
  console.log(res)
})

console.log('end');
Решение: start , middle, 1 , end и success.


№3 Что будет выведено в консоль и почему?
Promise.all([
  new Promise((resolve, reject) => setTimeout(() => resolve(1), 1000)),
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Ошибка!")), 2000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(3), 3000))
]).catch(alert);

Решение: через 2с будет выведено: Error: Ошибка! Т.к. Promise.all ожидает выполнения всех промисов,
но в случае ошибки, она становится результатом


№4 Что будет выведено в консоль и почему?
Promise.race([
  new Promise((resolve, reject) => setTimeout(() => resolve(1), 1000)),
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Ошибка!")), 2000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(3), 3000))
]).then(console.log);

Решение: 1, быстрее всех выполнился первый промис, он и дал результат.
После этого остальные промисы игнорируются.


№5 Что будет выведено в консоль и почему?
console.log('start')

setTimeout(() => {
  console.log('setTimeout')
})

Promise.resolve().then(() => {
  console.log('resolve')
})

console.log('end');

Решение: start , end , resolve и setTimeout


№6 Перепишите, используя async/await вместо .then/catch:
function loadJson(url) {
  return fetch(url)
    .then(response => {
      if (response.status == 200) {
        return response.json();
      } else {
        throw new Error(response.status);
      }
    })
}

loadJson('no-such-user.json') 
  .catch(console.log); 

Решение:
async function loadJson(url) { 
  let response = await fetch(url); 

  if (response.status == 200) {
    let json = await response.json(); 
    return json;
  }

  throw new Error(response.status);
}

loadJson('no-such-user.json')
  .catch(console.log); 
```
