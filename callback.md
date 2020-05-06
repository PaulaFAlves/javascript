<h1 align="center">CALLBACK</h1>

A CALLBACK is a function that will run after the function that calls it has finished. It a return function.
For example:

```
function loadScript(srcValue, callback) {
 	let script = document.createElement('script'); // an element is created, and it is saved on variable 'script'
 	script.src = srcValue; // the value in srcValue is passed to the property 'src' of the element 'script'
	document.head.append(script); // we append this new elemento to the 'head' of our HTML
 	script.onload = () => callback(script); // when the element is settled, the callback is called.
 	// if we dont put 'script.onload' it is going to work, but we want this to work ONLY IF THE ELEMENT IS LOADED ON THE HEAD OF THE HTML.
}

//the function is called passing the value of srcValue and the callback.
loadScript('https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js', script => {  
 	alert(`Cool, the script ${script.src} is loaded`);
});

// this is another way to write the same funtion:
loadScript('https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js', function(script) {
	alert(`Cool, the script ${script.src} is loaded`);
});

```


_This developer is powered by ☕ _