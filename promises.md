<h1 align="center">PROMISE</h1>

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


```
let p_resolve = Promise.resolve('it was resolved');
let p_reject = Promise.reject('not resolved');

p_resolve.then((result) => {
	console.log(result);
});

p_reject.catch((err) => {
	console.log(err);
});

// it was resolve
// not resolved

```


This developer is powered by  ☕ 