<h1 align="center">CALLBACK</h1>
<body font-size="8px">


## What is a CALLBACK?
	

A **CALLBACK** is a function that will run after the function that calls it has finished. It a return function.


## For example:

```
function loadScript(srcValue, callback) {
 	let script = document.createElement('script'); 
 	script.src = srcValue; 
	document.head.append(script); 
 	script.onload = () => callback(script);
}
```

Let me explain: 

1. an element is created, and it is saved on variable 'script'
2. he value in srcValue is passed to the property 'src' of the element 'script'
3. we append this new elemento to the 'head' of our HTML
4. when the element is settled, the callback is called.
5. if we dont put 'script.onload' it is going to work, but we want this to work **ONLY IF THE ELEMENT IS LOADED ON THE HEAD OF THE HTML.**

```
loadScript('https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js', script => {  
 	alert(`Cool, the script ${script.src} is loaded`);
});
```

The function is called passing the value of srcValue and the callback.

This is another way to write the same funtion:

```

loadScript('https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js', function(script) {
	alert(`Cool, the script ${script.src} is loaded`);
});

```

We can handling error on callback function as well. </br>
Let's see how it works:

```
function loadScript(srcValue, callback) {
 	let script = document.createElement('script'); 
 	script.src = srcValue; 
	document.head.append(script); 
 	script.onload = () => callback(null, script); 
 	script.onerror = () => callback(new Error(`Script error for ${srcValue}`))
}
```

Now, callback has 2 arguments: the first one is an error, and the second one is the script that has been builded on the function.</br>
If everything is right, 'onload' is called, calling callback, and passing through an error and the script as arguments.</br>
If something is wrong, 'onerror' is called, calling callback, and passing through only an error.

```
loadScript('https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js', (error, script) => {  
	if (error) {
		alert(error)
	} else {
		alert(`Cool, the script ${script.src} is loaded`);
	}
});
```

## More examples:



_This developer is powered by_ ☕ 
</body>