<h1 align="center">FILTER, MAP AND REDUCE</h1>

## Filter

This function calls another function, which is known as CALLBACK. The callback function that is called by the filter function contains a test, which applies it to each element of the array that calls the filter function. If its true, then this element is saved in another array.

*Exemples*

I need to find, in a list of names, the ones that begins with a especific letter, for exemplo, a 'C':

``` 

let names = ['Paula', 'Leandro', 'Caroline', 'Henrique', 'Camila', 'Marcelo', 'Andressa', 'José'];

let letter = 'C';

let selectNameWith = (elem) => elem.charAt(0) == letter

let selectedNames = names.filter(selectNameWith);

console.log(selectedNames);

```

Another exemple could be to find, in a list of students, the ones that has been approved:

```
let students = [
	{
		"name": "Paula Alves",
		"age": 38,
		"aproved": true,
	},
	{
		"name": "Leandro Ferri",
		"age": 25,
		"aproved": false,
	},
		{
		"name": "Caroline Vanazzi",
		"age": 26,
		"aproved": true,
	},	{
		"name": "Henrique Barbosa",
		"age": 12,
		"aproved": false,
	},	{
		"name": "Alice Eismann",
		"age": 1,
		"aproved": true,
	},
	]
	
let aproved = students.filter((elem) => elem.aproved);

console.log(aproved);

```

## Map 

As the function *filter*, this function uses a CALLBACK as well, and it manipulates the values of an array. It goes through each element of the array, applies the rule that has been defined on the callback function, and save this new value in another array. In another words, map doesn't change the original array. 

_Examples:_

```
let numbers = [1, 2, 3, 4, 5, 6]

let multiplicateEachNumber = numbers.map((item) => {
  return item * 2;
})

console.log(multiplicateEachNumber)
```

The script bellow does the same, but in another way:

```

let _multiplicateEachNumber = (item) => {
		return item * 2;
}
console.log(numbers.map(_multiplicateEachNumber));
```

Using MAP with objects is pretty much the same:			

```
	let guests = [
	  {
	    name: "paula alves",
	  }, 
	  {
	    name: "leandro",
	  }, 
	  {
	    name: "caroline",
	  }, 
	  {
	    name: "henrique",
	  }, 
	  ]

	let fixNames = guests.map((elem) => {
			return elem.name.charAt(0).toUpperCase() + elem.name.slice(1)
	})
	console.log(guests)
	console.log(fixNames)
```


## Reduce

As the others functions, the reduce function manipulate the elements of an array, but it also has an accumulator. This function is normally used to sum values of the elements in the array.

*Exemple:*
```
let values = [ 2, 4, 6, 3, 5, 8, 10]

let sum = values.reduce((total, item) => {
  return total + item
})
console.log(sum)
```

The function reduce can have 4 arguments: 
	- total: this is the accumulator. It can hold a initial value, and accumalate the operation at each time callback is called.
	- element: this is the actual element of the array.
	- index: this the index of the actual element.
	- array: the array that called the reduce function.

Now, an exemple that passes all the arguments:

```
let values = [4, 56, 12, 6, 8, 45]

let calculateAverage = values.reduce((total, item, index, array) => {
  total += item;
  if (index === array.length - 1) {
    return (total / array.length).toFixed(2);
  }
  return total
})
console.log(calculateAverage)
```

_This developer is powered by_ ☕ 
