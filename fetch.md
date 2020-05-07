<h1 align="center">FETCH</h1>


## WHAT IS PROMISE?


Is an API that returns a promise; thus, we can use _.then, .catch and async/wait with it_.</br>
We can use fetch() to get data from an API, for example, a list of all the citys in Rio Grande do Sul State.</br>
This information is in the following API, in this URL: [https://servicodados.ibge.gov.br/api/v1/localidades/estados/43/municipios](https://servicodados.ibge.gov.br/api/v1/localidades/estados/43/municipios)
So, let's use fetch to catch this data:

```

fetch('https://servicodados.ibge.gov.br/api/v1/localidades/estados/43/municipios')
.then(res => res.json())
.then(res => {
	let dados = res;
		console.log(dados)
	})

````
what happened here? We called the fetch API and passed it the URL from which we wanted the data from. As we haven't passed any other parameter other than te URL, it assumes that the method is 'GET'. Then, a response is sended to us as an object, but we needed it to be a json format, so we have to transform it into that. So, we called json(). Now, you got another promise, and you have to decide you want to do with that. In the example above, we wanted to use the data afterwards, so we saved it content on a variable, called dados, and console.log it.



## For example:


_This developer is powered by ☕ _