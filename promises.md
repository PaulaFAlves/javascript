<h1 align="center">PROMISE</h1>


## WHAT IS PROMISE?


It's an object that can create a value in the future, and its function is to improve an asynchronous code.</br>
Promises has two arguments, **resolve** and **reject**, and they are both callback functions, in other words, functions that will run after another(in this case, the promise).
The result of the promisse will call resolve if it was successfull, or reject if an error occurred.</br> 

So:
	- resolve(value) -> value is the successfull return of the promise
	- reject(error) -> error is an error object

The promise has internal properties:

	- STATE  -> pending, fulfilled or rejected
	- RESULT -> undefined, "value" or "error"

Like this:

		* New promise = 
					STATE:  pending
					RESULT: undefined
					* if result(value) =
						STATE:  fulfilled
						RESULT: value
					* if reject(error) = 
						STATE:  rejected
						RESULT: error

## For example:

```
let promise = new Promise(function(resolve, reject) {
		resolve(123)
	});
	promise.then(
		result => console.log(result))
```
or:

```
	let promise = new Promise(function(resolve, reject) {
		reject(new Error('Error'))
	});
	promise.then(
		reject => console.log(reject))

```


_This developer is powered by ☕ _
