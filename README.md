 # javaScript
## javaScript Basics

- HTML creates the content
- CSS changes the apearance
- JS makes it interactive

- to create pop up
```js
alert('hello');
```
or
```js
alert('Good Job');
```
- javaScript provides mathematics calculation on console

```js
2+2
```
or
```js
10-3
```
- to remove everything on page and show sms / to modify the webpage

```js
document.body.innerHTML = 'hello';
```
- syntax = rules that we have to follow in a programming language.

- homework 1
```js
alert('Good morning!');
alert('Abdur Rouf Robin');
10+5
20-5
2+2-5
document.body.innerHTML = 'Good morning!';
document.body.innerHTML ='Robin';
10+8+20
100-20-50+200
document.body.innerHTML = '';

```

## Numbers

- order of operations
  - BODMAS
  - we can't calculate % . we have to calculate manually 1% = 1/10
      - (..)
      - *, /
      - +, -
- 0.1 + 0.2 = 0.3000000000000004 // computer can't floating number properly
- to avoid this problem ---->> transform into integer (for dollar transform into cents) (to taka          transform into poisa)
- to round
    ```js
    Math.round(2.2)
    Math.round(2.3)
    Math.round((2095 + 799)*0.1)/100
    ```
### How to use Google
- mdn web docs javaScript
- chatgpt
- devdocs
-  homework of chapter 2
```js
//2a
1*10+3*8+1*5
//2b
(1*10+3*8+1*5)*3
//2c
(1850+750*2)/100
//2d
Math.round((1850+7.50*2)*0.1)/100
//2e
Math.round((1850+7.50*2)*0.2)/100
//2f
(2095+799+1899)/100
//2g
(2095+799+1899+499)/100
//2h
Math.round((2095+799+1899+499)*0.1)/100
//2i
(2095+799+1899+499)/100 + Math.round((2095+799+1899+499)*0.1)/100
//2j
Math.floor(2.8)
//2k
Math.ceil(2.2)
//2l
(25*9)/5+32
//2m
(86-32)*5/9
//2n
((-5)*9/5)+32
```
## String
- string = text
- syntax = '...'
- we can add string like
```js
'some' + 'text' //sometext
'some' + 'more' + 'text' //somemoretext
// this is called concatenation = combine strings together
```
- we can see the type of any value
```js
typeof 3 //number
typeof 'hello' //string
```
- we can add number and string

```js
'hello' + 3 //hello3
//this is called type coercion or automatic type conversion
```
- practice
```js
'$' + 20.95 +7.99 //shows error
'$20.95' + 7.99 //shows error
'$' + ((2095+799)/100) //right
'$Items (' + (1 + 1) + '): $'+ (2095+799)/100
alert('$Items (' + (1 + 1) + '): $'+ (2095+799)/100);
```
- 3 ways to create string
  - single quote = '....' // better
  - double quotes = "...." // when we want to use single quote in string like I'm
     - escape character = \\'
     - escape character = \\"
     - escape character = \\n //new line character
  - backtick = template string =\`....\`
    - interpolation = insert value directly into string
    ```js
    `Items(${1+1}): $${(2095+799)/100}`
    ```
    - multi-line strings = strings are in multiple line
   
    ```js
    `some
    text`
    //'some\ntext'
    ```
 - exercise of chapter 3
```js
//3a
'My name is:'
//3b
'Robin'
//3c
'My name is:' + 'Robin'
//3d
'Total cost: $' + (5+3)
//3e
`Total cost: $${5 + 3}`
//3f
alert(`Total cost: $${5 + 3}`)
//3g
'Total cost: $' + (599+295)/100
//3h
`Total cost: $${(599+295)/100}`
//3i
alert(`Total cost: $${(599+295)/100}`)
//3j
`Total cost:$${(599+295)/100}
Thank you, come again!`
//3k
`Items (${2+2}):                 $${(2*2095 + 2*799)/100}`
//3l
`Shipping & handling:        $${(499+499)/100}`
//3m
`Total before tax:       $${(2*2095 + 2*799)/100 + (499+499)/100}`
//3n
`Estimated tax(10%):                   $${Math.round(((2*2095 + 2*799) + (499+499))*0.1)/100}`
//3o
`Order total:   $${(2*2095 + 2*799)/100 + (499+499)/100+Math.round(((2*2095 + 2*799) + (499+499))*0.1)/100}`
```
## Html Css Javascript together
- install a code editor ( VS Code )
- HTML = Hyper Text MarkUp Language
- nesting = element inside an element
- multiple spaces are combined into 1 space
- newline also count as converted space
- webpage is a single page of website
- CSS = Cascading Style Sheets
- Attribute changes the behavior of an element
- onclick = whenever we click the element
- first script tag then onclick js
- // used in js for single line comments
- /*  */ used in js for multiline comments
- \<!-- --> used in HTML for comments
- /**/ used in css
- exercise of chapter 4
```js
//4a
<button>Click</button>
//4b
<button>Simon</button>
<button>chocolate</button>
//4c
<p>Hello, world!</p>
//4d
<p>Hello, world!</p>
<p>Today I went to the grocery store to buy some eggs and vegetables.</p>
//4e
<style>
  .add-to-cart-button {
    background-color: yellow;
  }

  .buy-now-button {
    background-color: orange;
  }
</style>

<button class="add-to-cart-button">Add to cart</button>
<button class="buy-now-button">Buy now</button>
//4f
<!DOCTYPE html>
<html>
  <head>
    <style>
      .add-to-cart-button {
        background-color: yellow;
      }
    
      .buy-now-button {
        background-color: orange;
      }
    </style>
  </head>
  <body>
    <button class="add-to-cart-button">Add to cart</button>
    <button class="buy-now-button">Buy now</button>
  </body>
</html>
//4g
<!DOCTYPE html>
<html>
  <head>
    <title>Buttons</title>
    <style>
      .add-to-cart-button {
        background-color: yellow;
      }
    
      .buy-now-button {
        background-color: orange;
      }
    </style>
  </head>
  <body>
    <button class="add-to-cart-button">Add to cart</button>
    <button class="buy-now-button">Buy now</button>
  </body>
</html>
//4h
<!DOCTYPE html>
<html>
  <head>
    <title>Buttons</title>
    <style>
      .add-to-cart-button {
        background-color: yellow;
      }
    
      .buy-now-button {
        background-color: orange;
      }
    </style>
  </head>
  <body>
    <button class="add-to-cart-button">Add to cart</button>
    <button class="buy-now-button">Buy now</button>

    <script>
      console.log('Welcome!');
    </script>
  </body>
</html>
//4i
<!DOCTYPE html>
<html>
  <head>
    <style>
      .add-to-cart-button {
        background-color: yellow;
      }
    
      .buy-now-button {
        background-color: orange;
      }
    </style>
  </head>
  <body>
    <p>Adults Plain Cotton T-shirt</p>
    <p>Price: $7.99</p>
    <button class="add-to-cart-button">Add to cart</button>
    <button class="buy-now-button">Buy now</button>
  </body>
</html>
//4j
<!DOCTYPE html>
<html>
  <head>
    <style>
      .add-to-cart-button {
        background-color: yellow;
      }
    
      .buy-now-button {
        background-color: orange;
      }
    </style>
  </head>
  <body>
    <p>Adults Plain Cotton T-shirt</p>
    <p>Price: $7.99</p>

    <!-- I added some extra spaces to make the code
    easier to read. -->
    <button class="add-to-cart-button" onclick="
      alert('Added');
    ">Add to cart</button>

    <button class="buy-now-button" onclick="
      console.log('Loading...');
      alert('Purchased');
    ">Buy now</button>
  </body>
</html>
```
## chapter 5 variables
- variable = a container
```
let variable1 = 3
let calculation = 2 + 2
let result = calculation + 2
let message = 'hello!'
variable1 = variable1 + 1
```
- variable name restriction
   - can't use special word
   - can't use special characters except $ and _
   - can't start with a number
   - ; means end of an instruction
   - semicolon insertion = insert semicolon in last automatically
   - assiging a value to a variable and reassigning a value to the variable
   - cart project
 ```html
  <!DOCTYPE html>
\<html>
  \<head>
    \<title>Cart Quantity</title>
  \</head>
  <body>
    \<button onclick="
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Show Quantity</button>

    <button onclick="
      cartQuantity++;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Add to Cart</button>

    <button onclick="
      cartQuantity += 2;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+2</button>

    <button onclick="
      cartQuantity = cartQuantity + 3;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+3</button>

    <button onclick="
      cartQuantity = 0;
      console.log('Cart was reset.');
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Reset Cart</button>

    <script>
      let cartQuantity = 0;
    </script>
   </body>
   </html>
```
- all these line do the same thing

```
cartQuantity = cartQuantity + 1
cartQuantity +=1
cantQuantity++
```
