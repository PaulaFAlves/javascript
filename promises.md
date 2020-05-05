## PROMISE

It's an object that can create a value in the future, and its function is to improve an asynchronous code. This value can be a success (resolve, if everything goes well) or not (reject, if something goes wrong). This returns represents the state os the promisse. 

_Example:_

```
let p = new Promise((resolve, reject) => {
	let x = 'the promise is done!';
	resolve(x);
})

console.log(10);

p.then((x) => {
	console.log(x)
})

console.log(20);
// 10
// 20
// 5

```




<!-- 
representa a conclusao de uma funcao assincrona, seja como sucesso ou com falha.
funciona como callback ( callback = acao que vai ser executada assim que outra for concuida).
callback -> funcao assincrona
promise -> outra maneira de ver o callback
async/await -> retorna uma promise -->