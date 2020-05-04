# CALL, APPLY AND BIND

_CALL and APPLY are methods that can change the value of "this"._

## Apply

example: using math.max

## Call

We want to catalog a list of products. Some properties of the product doesn't change, like the category, and others are different for each product.
We a function Product to buid products, and it has the properties than will be changed:

```
function Product(name, price){
	this.name = name;
	this.price = price;
}
```

As we want to be more specific, and divide this product into categories. To do that, we build another function, which name will the the type of that product. For exemple, we have food, clothes and cleaning products.

```
function Food(name, price){
	Product.call(this, name, price);
	this.cathegory = 'food';
}
function Clothes(name, price){
	Product.call(this, name, price);
	this.cathegory = 'clothes';
}
function Cleaning(name, price){
	Product.call(this, name, price);
	this.cathegory = 'cleaning';
}
let pizza = Food('Pizza', 5);
console.log(pizza); // Object { name: "Pizza", price: 5, cathegory: "food" }
let alvejante = new Cleaning('Alvejante', 2);
console.log(alvejante); // Object { name: "Pizza", price: 5, cathegory: "food" }
let calca = new Clothes('calca', 10);
console.log(calca); // Object { name: "calca", price: 10, cathegory: "clothes" }
```

