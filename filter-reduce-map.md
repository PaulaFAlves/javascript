# Filter, map and reduce

## Filter

Função que chama outra função, conhecida como CALLBACK. O callback irá conter uma regra de negócio, ou seja, vai aplicar um filtro em cada elemento do array que estamos analisando e retornar somente aquilo que aquilo atende a condição. Neste caso, o elemento é salvo dentro de um novo array.

*Exemplos*

Quero buscar, dentro de uma lista de nomes, somente aqueles que começam com uma letra em específico, por exemplo, com a letra 'C':

``` 

let names = ['Paula', 'Leandro', 'Caroline', 'Henrique', 'Camila', 'Marcelo', 'Andressa', 'José'];

let letter = 'C';

let selectNameWith = function(elem) {
	return elem.charAt(0) == letter
}

let selectedNames = names.filter(selectNameWith);

console.log(selectedNames);

```

Outro exemplo de aplicação da função filter seria em uma lista de alunos, buscar somente aqueles que foram aprovados:

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
	
let aproved = students.filter(function(elem) {
	return elem.aproved
	})

console.log(aproved);

```

