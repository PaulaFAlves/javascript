<h1 align="center">CALLBACK</h1>

<<body font-size="10px">
	


A CALLBACK is a function that will run after the function that calls it has finished. It a return function.
For example:

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
5. if we dont put 'script.onload' it is going to work, but we want this to work ONLY IF THE ELEMENT IS LOADED ON THE HEAD OF THE HTML.

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



_This developer is powered by_ ☕ 
</body>