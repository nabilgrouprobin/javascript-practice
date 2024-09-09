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
```js
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

```js
cartQuantity = cartQuantity + 1
cartQuantity +=1
cantQuantity++
```
- other shortcuts
```
+=
-=
*=
/=
++
--
```
- naming variable
```js
camelCase = cartQuantity // special naming convention for js
PascalCase = CartQuantity
kabab-case = cart-quantity
snake_case = cart_quantity
```
- naming should not too short too long
- naming should be meningful and smart and mediumsize
- 3 ways to create variable in js
```js
let a; // better
var b; // good
const c; // best
```
- we can use 'typeof' with variable
- exercise of chapter 5
```html
//5a
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const name = 'Simon';
    </script>
  </body>
</html>
//5b
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const name = 'Simon';
      console.log(`My name is: ${name}`);
    </script>
  </body>
</html>
//5c
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const cost = 5 + 2 * 3 + 9;
    </script>
  </body>
</html>
//5d
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const cost = 5 + 2 * 3 + 9;
      console.log(`Cost of food: $${cost}`);
    </script>
  </body>
</html>
//5e
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const cost = 5 + 2 * 3 + 9;
      console.log(`Cost of food: $${cost}`);

      const tax = cost * 0.1;
    </script>
  </body>
</html>
//5f
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const cost = 5 + 2 * 3 + 9;
      console.log(`Cost of food: $${cost}`);

      const tax = cost * 0.1;
      console.log(`Tax (10%): $${tax}`);
    </script>
  </body>
</html>
//5g
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const cost = 5 + 2 * 3 + 9;
      console.log(`Cost of food: $${cost}`);

      const tax = cost * 0.1;
      console.log(`Tax (10%): $${tax}`);

      const totalCost = cost + tax;
      console.log(`Total cost: $${totalCost}`);
    </script>
  </body>
</html>
//5h
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
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

    <!-- vvv This code is new. vvv -->
    <button onclick="
      cartQuantity += 4;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+4</button>

    <button onclick="
      cartQuantity += 5;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+5</button>
    <!-- ^^^ This code is new. ^^^ -->

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
//5i
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
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
      cartQuantity += 4;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+4</button>

    <button onclick="
      cartQuantity += 5;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+5</button>

    <!-- vvv This code is new. vvv -->
    <button onclick="
      cartQuantity = cartQuantity - 1;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Remove from cart</button>
    <!-- ^^^ This code is new. ^^^ -->

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
//5j
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
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
      cartQuantity += 4;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+4</button>

    <button onclick="
      cartQuantity += 5;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+5</button>

    <button onclick="
      cartQuantity = cartQuantity - 1;
      console.log(`Cart quantity: ${cartQuantity}`);
      ">Remove from cart</button>

    <!-- vvv This code is new. vvv -->
    <button onclick="
      cartQuantity = cartQuantity - 2;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">-2</button>

    <button onclick="
      cartQuantity = cartQuantity - 3;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">-3</button>
    <!-- ^^^ This code is new. ^^^ -->

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
//5k
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
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
      cartQuantity += 4;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+4</button>

    <button onclick="
      cartQuantity += 5;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">+5</button>

    <!-- vvv This code was changed. vvv -->
    <button onclick="
      cartQuantity--;
      console.log(`Cart quantity: ${cartQuantity}`);
      ">Remove from cart</button>

    <button onclick="
      cartQuantity -= 2;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">-2</button>

    <button onclick="
      cartQuantity -= 3;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">-3</button>
    <!-- ^^^ This code was changed. ^^^ -->

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
//5l
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
//5m
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button>1</button>
    <button>2</button>
    <button>3</button>
    <button>+</button>
    <button>=</button>
  </body>
</html>
//5n
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button>1</button>
    <button>2</button>
    <button>3</button>
    <button>+</button>
    <button>=</button>
    <script>
      let calculation = '';
    </script>
  </body>
</html>
//5o
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button onclick="
      calculation += '1';
      console.log(calculation);
    ">1</button>
    
    <button>2</button>
    <button>3</button>
    <button>+</button>
    <button>=</button>
    <script>
      let calculation = '';
    </script>
  </body>
</html>
//5p
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button onclick="
      calculation += '1';
      console.log(calculation);
    ">1</button>
    
    <button onclick="
      calculation += '2';
      console.log(calculation);
    ">2</button>

    <button onclick="
      calculation += '3';
      console.log(calculation);
    ">3</button>

    <button onclick="
      calculation += ' + ';
      console.log(calculation);
    ">+</button>

    <button>=</button>
    
    <script>
      let calculation = '';
    </script>
  </body>
</html>
//5q
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button onclick="
      calculation += '1';
      console.log(calculation);
    ">1</button>

    <button onclick="
      calculation += '2';
      console.log(calculation);
    ">2</button>

    <button onclick="
      calculation += '3';
      console.log(calculation);
    ">3</button>

    <button onclick="
      calculation += ' + ';
      console.log(calculation);
    ">+</button>

    <button onclick="
      // Note: eval() takes a string and runs it as code.
      // Avoid using eval() in real world projects since
      // it can potentially be given harmful code to run.
      // Only use eval() for learning purposes.
      calculation = eval(calculation);
      console.log(calculation);
    ">=</button>

    <script>
      let calculation = '';
    </script>
  </body>
</html>
//5r
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <p>
      <button onclick="
        calculation += '1';
        console.log(calculation);
      ">1</button>

      <button onclick="
        calculation += '2';
        console.log(calculation);
      ">2</button>

      <button onclick="
        calculation += '3';
        console.log(calculation);
      ">3</button>

      <button onclick="
        calculation += ' + ';
        console.log(calculation);
      ">+</button>
    </p>

    <p>
      <button onclick="
        calculation += '4';
        console.log(calculation);
      ">4</button>

      <button onclick="
        calculation += '5';
        console.log(calculation);
      ">5</button>

      <button onclick="
        calculation += '6';
        console.log(calculation);
      ">6</button>

      <button onclick="
        calculation += ' - ';
        console.log(calculation);
      ">-</button>
    </p>

    <p>
      <button onclick="
        calculation += '7';
        console.log(calculation);
      ">7</button>

      <button onclick="
        calculation += '8';
        console.log(calculation);
      ">8</button>

      <button onclick="
        calculation += '9';
        console.log(calculation);
      ">9</button>

      <button onclick="
        calculation += ' * ';
        console.log(calculation);
      ">*</button>
    </p>

    <p>
      <button onclick="
        calculation += '0';
        console.log(calculation);
      ">0</button>

      <button onclick="
        calculation += '.';
        console.log(calculation);
      ">.</button>

      <button onclick="
        // Note: eval() takes a string and runs it as code.
        // Avoid using eval() in real world projects since
        // it can potentially be given harmful code to run.
        // Only use eval() for learning purposes.
        calculation = eval(calculation);
        console.log(calculation);
      ">=</button>

      <button onclick="
        calculation += ' / ';
        console.log(calculation);
      ">/</button>
    </p>

    <p>
      <button onclick="
        calculation = '';
        console.log(calculation);
      ">Clear</button>
    </p>

    <script>
      let calculation = '';
    </script>
  </body>
</html>
```
- booleans and if statements
- there are only two boolean values - true  - false
- comaprision of numbers
- we don't surround this with quote like 'true'  or 'false'- if we did then it will become string
- true, false --> boolean
- 'true', 'false' --> string
- comparison operator --> >, <, >=, <=, ===, !==
- ( == ) and ( != ) compare only value
- ( === ) and ( !== ) compare both value and type
- in the order of operations comparison operators have the lower priority than math
  1. (...)
  2. \* /
  3. \+ -
  4. comparison operator
  5. logical operators
```js
console.log(3>5-5);
```       
- if statement
```js
if(boolean value or any command that results a boolean value){
command---->>
}
else{
command ----->
}
```
- if command line is one line then no need to use curly brackets
- we can add more branches between 'if' and 'else' named 'else if'
```js
if(age>=){
console.log('You can drive');
}
else if (age>=){
console.log('Almost there..!');
}
else if (age>=70){
console.log('You are overaged to drive');
}
else{
console.log(`You can't drive`);
}
```
- Math.random() generates a random number between 0 and 1 it generates '0<=number<1'
- logical operators = let us combine boolean values
```js
&&
||
!
```
- scope = scope means where a variable exists
- scope helps us to avoid naming conflicts
- when we reassign a variable we heave to set variable type to 'let'
- any variable we create inside the curly brackets will only exist inside the curly brackets
- 'var' doesn't really follow the rules of scope thats why we can't use 'var' in coding
- we can't redeclare block-scope variable but can reassign it even if ...................
- rock paper scissors
```js
<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
  </head>
  <body>
    <p>Rock Paper Scissors</p>
    <button onclick="
      const randomNumber = Math.random();

      let computerMove = '';

      if (randomNumber >= 0 && randomNumber < 1 / 3) {
        computerMove = 'rock';
      } else if (randomNumber >= 1 / 3 && randomNumber < 2 / 3) {
        computerMove = 'paper';
      } else if (randomNumber >= 2 / 3 && randomNumber < 1) {
        computerMove = 'scissors';
      }

      let result = '';

      if (computerMove === 'rock') {
        result = 'Tie.';
      } else if (computerMove === 'paper') {
        result = 'You lose.';
      } else if (computerMove === 'scissors') {
        result = 'You win.';
      }

      alert(`You picked rock. Computer picked ${computerMove}. ${result}`);
    ">Rock</button>

    <button onclick="
       randomNumber = Math.random();

       computerMove = '';

      if (randomNumber >= 0 && randomNumber < 1 / 3) {
        computerMove = 'rock';
      } else if (randomNumber >= 1 / 3 && randomNumber < 2 / 3) {
        computerMove = 'paper';
      } else if (randomNumber >= 2 / 3 && randomNumber < 1) {
        computerMove = 'scissors';
      }

      result = '';

      if (computerMove === 'rock') {
        result = 'You win.';
      } else if (computerMove === 'paper') {
        result = 'Tie.';
      } else if (computerMove === 'scissors') {
        result = 'You lose.';
      }

      alert(`You picked paper. Computer picked ${computerMove}. ${result}`);
    ">Paper</button>

    <button onclick="
      randomNumber = Math.random();

      computerMove = '';

      if (randomNumber >= 0 && randomNumber < 1 / 3) {
        computerMove = 'rock';
      } else if (randomNumber >= 1 / 3 && randomNumber < 2 / 3) {
        computerMove = 'paper';
      } else if (randomNumber >= 2 / 3 && randomNumber < 1) {
        computerMove = 'scissors';
      }

      result = '';

      if (computerMove === 'rock') {
        result = 'You lose.';
      } else if (computerMove === 'paper') {
        result = 'You win.';
      } else if (computerMove === 'scissors') {
        result = 'Tie.';
      }

      alert(`You picked scissors. Computer picked ${computerMove}. ${result}`);
    ">Scissors</button>

    <script>
      
    </script>
  </body>
</html>

```
- strategy for javaScript
   - figure out what steps we need
   - convert these steps into code
## More details about boolean and if statements
- Truthy and Falsy Values
- Truthy Values = the value just behave like 'true'
- Falsy Values = the value just behave like 'false'

- Falsy Values
  1. false
  2. 0
  3. NaN
  4. undefined
  5. null
  6. '' //empty value
```js
console.log(!0) //true
```
- NaN = Not a Number
```js
console.log('text'/5) //NaN
```
- undefined = doesn't have a value
```js
let variable1;
console.log(variable1);
```
- for 'const' we must assign a value or undefined
```js
const variable1 = undefined;
```
- null //later
```js
//later
```
- shortcuts for if-statements
   - Ternary operators '?:'
   - Guard oprators '&&'
   - Default operators '||'
- we can set variable for ternary operators
```js
const result = 0 ? 'truthy' : 'falsy';
console.log(result);
```
- short circuit evaluation for && operators and || operators
```
false && value2 // && operator stops early and doesn't even need to runn the code right side value2
```
or
```js
false && console.log('hello')
true && console.log('hello')
const message = 5>3 && 'hello'
const message = 0 && 'hello'
```
- Default operators
```js
const currency = 'EUR' || 'USD';
const currency = undefined || 'USD';
console.log(currency)
```
- homework chapter 6
- 6a
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const hour = 9;

      if (hour >= 6 && hour <= 12) {
        console.log('Good morning!');
      } else if (hour >= 13 && hour <= 17) {
        console.log('Good afternoon!');
      } else {
        console.log('Good night!');
      }
    </script>
  </body>
</html>
```
- 6b
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      // Try changing this variable to
      // display different messages.
      const hour = 15;

      if (hour >= 6 && hour <= 12) {
        console.log('Good morning!');
      } else if (hour >= 13 && hour <= 17) {
        console.log('Good afternoon!');
      } else {
        console.log('Good night!');
      }
    </script>
  </body>
</html>
```
- 6c
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const hour = 9;
      const name = 'Simon';

      if (hour >= 6 && hour <= 12) {
        console.log(`Good morning ${name}!`);
      } else if (hour >= 13 && hour <= 17) {
        console.log(`Good afternoon ${name}!`);
      } else {
        console.log(`Good night ${name}!`);
      }
    </script>
  </body>
</html>
```
- 6d
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const age = 5;

      if (age <= 6 || age >= 65) {
        console.log('Discount');
      } else {
        console.log('No discount');
      }
    </script>
  </body>
</html>
```
- 6e
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const age = 5;
      const isHoliday = true;

      // && has a higher priority than || so for
      // this to work correctly, we need to add
      // brackets () around the || check to make
      // sure that it gets done first.
      if ((age <= 6 || age >= 65) && !isHoliday) {
        console.log('Discount');
      } else {
        console.log('No discount');
      }
    </script>
  </body>
</html>
```
- 6f
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const randomNumber = Math.random();
    </script>
  </body>
</html>
```
- 6g
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const randomNumber = Math.random();

      if (randomNumber < 0.5) {
        console.log('heads');
      } else {
        console.log('tails');
      }
    </script>
  </body>
</html>
```
- 6h
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const randomNumber = Math.random();
      let result;

      if (randomNumber < 0.5) {
        result = 'heads';
      } else {
        result = 'tails';
      }
    </script>
  </body>
</html>
```
- 6i
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const randomNumber = Math.random();
      let result;

      if (randomNumber < 0.5) {
        result = 'heads';
      } else {
        result = 'tails';
      }

      const guess = 'heads';

      if (guess === result) {
        console.log('You win!');
      } else {
        console.log('You lose!');
      }
    </script>
  </body>
</html>
```
- 6j
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const randomNumber = Math.random();
      const result = randomNumber < 0.5 ? 'heads' : 'tails';

      const guess = 'heads';
      console.log(guess === result ? 'You win!' : 'You lose!');
    </script>
  </body>
</html>
```
- 6k
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Show Quantity</button>

    <button onclick="
      if (cartQuantity + 1 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity++;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">Add to Cart</button>

    <button onclick="
      if (cartQuantity + 2 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity += 2;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+2</button>

    <button onclick="
      if (cartQuantity + 3 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity = cartQuantity + 3;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+3</button>

    <button onclick="
      if (cartQuantity + 4 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity += 4;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+4</button>

    <button onclick="
      if (cartQuantity + 5 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity += 5;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+5</button>

    <button onclick="
      cartQuantity--;
      console.log(`Cart quantity: ${cartQuantity}`);
      ">Remove from cart</button>

    <button onclick="
      cartQuantity -= 2;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">-2</button>

    <button onclick="
      cartQuantity -= 3;
      console.log(`Cart quantity: ${cartQuantity}`);
    ">-3</button>

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
- 6l
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Show Quantity</button>

    <button onclick="
      if (cartQuantity + 1 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity++;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">Add to Cart</button>

    <button onclick="
      if (cartQuantity + 2 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity += 2;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+2</button>

    <button onclick="
      if (cartQuantity + 3 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity = cartQuantity + 3;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+3</button>

    <button onclick="
      if (cartQuantity + 4 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity += 4;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+4</button>

    <button onclick="
      if (cartQuantity + 5 > 10) {
        alert('The cart is full');
      } else {
        cartQuantity += 5;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">+5</button>

    <!-- vvv This code was changed. vvv -->
    <button onclick="
      if (cartQuantity - 1 < 0) {
        alert('Not enough items in the cart');
      } else {
        cartQuantity--;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">Remove from cart</button>

    <button onclick="
      if (cartQuantity - 2 < 0) {
        alert('Not enough items in the cart');
      } else {
        cartQuantity -= 2;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">-2</button>

    <button onclick="
      if (cartQuantity - 3 < 0) {
        alert('Not enough items in the cart');
      } else {
        cartQuantity -= 3;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    ">-3</button>
    <!-- ^^^ This code was changed. ^^^ -->

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
## chapter 7 functions

- function lets us reuse code
- make our code easier to update
- following the code line by line = tracing the code

- function basics
- best practice to use camel case
- in function name we use verb or action to start like pickComputerMove(){}
- any variable created between curly bracket only exist between curly brackets like const computerMove
- solution 1. use global variable
           2. use return statement
- we prefer using return statement rather than using global variable because ' scope help us to prevent naming conflicts'
- keep thing inside a scope if we can --> best practice
- return statemnet = let us get a value out of a function also the value of the function when it is     called but we need to save the return value into another variable then console.log it
- we can return 1. a value 2. a variable 3. a calculation 4. a function also
- return; = returns the value 'undefined'
- when we use return it ends the function immediately
- we need to  call the function in where we want to use funtion
- return = gets a value out of a function
- parameter = puts a value into a function
- parameter works same as a variable
- parameter name = camelCase
- argument = when we passing a value while calling the function. it is an actual value
- parameter = it acts as a placeholder for the data
- if we don't give any argument to parameter it will be undefined automatically
- and any caluculation with undefined number results NaN = Not a Number
- to fix this we set a default value in parameter initializing 
- inside a function we can call another function

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Functions</title>
  </head>
  <body>
    <script>
      /*
      function function1() {
        console.log('hello');
        console.log(2 + 2);
      }

      function1();
      function1();
      */

      function calculateTax(cost, taxPercent = 0.1) {
        console.log(cost * taxPercent);
      }

      calculateTax(2000, 0.2);
      calculateTax(5000);
    </script>
  </body>
</html>

```
- rock paper scissors game
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
  </head>
  <body>
    <p>Rock Paper Scissors</p>
    <button onclick="
      playGame('rock');
    ">Rock</button>

    <button onclick="
      playGame('paper');
    ">Paper</button>

    <button onclick="
      playGame('scissors');
    ">Scissors</button>

    <script>
      function playGame(playerMove) {
        const computerMove = pickComputerMove();

        let result = '';

        if (playerMove === 'scissors') {
          if (computerMove === 'rock') {
            result = 'You lose.';
          } else if (computerMove === 'paper') {
            result = 'You win.';
          } else if (computerMove === 'scissors') {
            result = 'Tie.';
          }

        } else if (playerMove === 'paper') {
          if (computerMove === 'rock') {
            result = 'You win.';
          } else if (computerMove === 'paper') {
            result = 'Tie.';
          } else if (computerMove === 'scissors') {
            result = 'You lose.';
          }
          
        } else if (playerMove === 'rock') {
          if (computerMove === 'rock') {
            result = 'Tie.';
          } else if (computerMove === 'paper') {
            result = 'You lose.';
          } else if (computerMove === 'scissors') {
            result = 'You win.';
          }
        }

        alert(`You picked ${playerMove}. Computer picked ${computerMove}. ${result}`);
      }

      function pickComputerMove() {
        const randomNumber = Math.random();

        let computerMove = '';

        if (randomNumber >= 0 && randomNumber < 1 / 3) {
          computerMove = 'rock';
        } else if (randomNumber >= 1 / 3 && randomNumber < 2 / 3) {
          computerMove = 'paper';
        } else if (randomNumber >= 2 / 3 && randomNumber < 1) {
          computerMove = 'scissors';
        }

        return computerMove;
      }
    </script>
  </body>
</html>

```
- exercise
- 7a
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function greet() {
        console.log('Hello!');
      }
      greet();
      greet();
    </script>
  </body>
</html>
```
- 7b
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function greet(name) {
        console.log(`Hello ${name}!`);
      }
      greet('Simon');
      greet('Alice');
    </script>
  </body>
</html>
```
- 7c
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function greet(name) {
        if (!name) {
          console.log('Hi there!');
        } else {
          console.log(`Hello ${name}!`);
        }
      }
      greet('Simon');
      greet('Alice');
      greet();
    </script>
  </body>
</html>
```
- 7d
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function convertToFahrenheit(celsius) {
        return (celsius * 9 / 5) + 32;
      }
      console.log(convertToFahrenheit(25));
    </script>
  </body>
</html>
```
- 7e
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function convertToCelsius(fahrenheit) {
        return (fahrenheit - 32) * 5 / 9;
      }
      console.log(convertToCelsius(86));
    </script>
  </body>
</html>
```
- 7f
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function convertToFahrenheit(celsius) {
        return (celsius * 9 / 5) + 32;
      }

      function convertToCelsius(fahrenheit) {
        return (fahrenheit - 32) * 5 / 9;
      }

      function convertTemperature(degrees, unit) {
        if (unit === 'C') {
          const result = convertToFahrenheit(degrees);
          return `${result}F`;
        } else if (unit === 'F') {
          const result = convertToCelsius(degrees);
          return `${result}C`;
        }
      }

      console.log(convertTemperature(25, 'C'));
      console.log(convertTemperature(86, 'F'));
    </script>
  </body>
</html>
```
- 7g
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function convertLength(length, from, to) {
        if (from === 'km' && to === 'miles') {
          return `${length / 1.6} miles`;
        } else if (from === 'miles' && to === 'km') {
          return `${length * 1.6} km`;

        // You can also do if (from === 'km' && to === 'km) { ... }
        // if (from === to) is a trick you can use to save some code.
        } else if (from === to) {
          return `${length} ${to}`;
        }
      }

      console.log(convertLength(50, 'miles', 'km'));
      console.log(convertLength(32, 'km', 'miles'));
      console.log(convertLength(50, 'km', 'km'));
    </script>
  </body>
</html>

```
- 7h
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function convertLength(length, from, to) {
        if (from === 'km' && to === 'miles') {
          return `${length / 1.6} ${to}`;

        } else if (from === 'km' && to === 'ft') {
          return `${length * 3281} ${to}`;
          
        } else if (from === 'miles' && to === 'km') {
          return `${length * 1.6} ${to}`;

        } else if (from === 'miles' && to === 'ft') {
          return `${length * 5280} ${to}`;

        } else if (from === 'ft' && to === 'km') {
          return `${length / 3281} ${to}`;

        } else if (from === 'ft' && to === 'miles') {
          return `${length / 5280} ${to}`;

        // You can also do if (from === 'km' && to === 'km) { ... }
        // if (from === to) is a trick you can use to save some code.
        } else if (from === to) {
          return `${length} ${to}`;
        }
      }

      console.log(convertLength(50, 'miles', 'km'));
      console.log(convertLength(32, 'km', 'miles'));
      console.log(convertLength(50, 'km', 'km'));

      console.log(convertLength(5, 'miles', 'km'));
      console.log(convertLength(5, 'miles', 'ft'));
      console.log(convertLength(5, 'km', 'ft'));
    </script>
  </body>
</html>

```
- 7i
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function convertLength(length, from, to) {
        // I like to put invalid checks at the top since it's a bit
        // easier to see. Also, if something is invalid, we can skip
        // the rest of the function.
        if (from !== 'km' && from !== 'miles' && from !== 'ft') {
          return `Invalid unit: ${from}`;
        } else if (to !== 'km' && to !== 'miles' && to !== 'ft') {
          return `Invalid unit: ${to}`;
        }
        
        if (from === 'km' && to === 'miles') {
          return `${length / 1.6} ${to}`;

        } else if (from === 'km' && to === 'ft') {
          return `${length * 3281} ${to}`;
          
        } else if (from === 'miles' && to === 'km') {
          return `${length * 1.6} ${to}`;

        } else if (from === 'miles' && to === 'ft') {
          return `${length * 5280} ${to}`;

        } else if (from === 'ft' && to === 'km') {
          return `${length / 3281} ${to}`;

        } else if (from === 'ft' && to === 'miles') {
          return `${length / 5280} ${to}`;

        // You can also do if (from === 'km' && to === 'km) { ... }
        // if (from === to) is a trick you can use to save some code.
        } else if (from === to) {
          return `${length} ${to}`;
        }
      }

      console.log(convertLength(50, 'miles', 'km'));
      console.log(convertLength(32, 'km', 'miles'));
      console.log(convertLength(50, 'km', 'km'));

      console.log(convertLength(5, 'miles', 'km'));
      console.log(convertLength(5, 'miles', 'ft'));
      console.log(convertLength(5, 'km', 'ft'));

      console.log(convertLength(5, 'lbs', 'lbs'));
    </script>
  </body>
</html>

```
- 7j
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <p>
      <button onclick="
        updateCalculation('1');
      ">1</button>

      <button onclick="
        updateCalculation('2');
      ">2</button>

      <button onclick="
        updateCalculation('3');
      ">3</button>

      <button onclick="
        updateCalculation(' + ');
      ">+</button>
    </p>

    <p>
      <button onclick="
        updateCalculation('4');
      ">4</button>

      <button onclick="
        updateCalculation('5');
      ">5</button>

      <button onclick="
        updateCalculation('6');
      ">6</button>

      <button onclick="
        updateCalculation(' - ');
      ">-</button>
    </p>

    <p>
      <button onclick="
        updateCalculation('7');
      ">7</button>

      <button onclick="
        updateCalculation('8');
      ">8</button>

      <button onclick="
        updateCalculation('9');
      ">9</button>

      <button onclick="
        updateCalculation(' * ');
      ">*</button>
    </p>

    <p>
      <button onclick="
        updateCalculation('0');
      ">0</button>

      <button onclick="
        updateCalculation('.');
      ">.</button>

      <button onclick="
        // Note: eval() takes a string and runs it as code.
        // Avoid using eval() in real world projects since
        // it can potentially be given harmful code to run.
        // Only use eval() for learning purposes.
        calculation = eval(calculation);
        console.log(calculation);
      ">=</button>

      <button onclick="
        updateCalculation(' / ');
      ">/</button>
    </p>

    <p>
      <button onclick="
        calculation = '';
        console.log(calculation);
      ">Clear</button>
    </p>

    <script>
      let calculation = '';

      function updateCalculation(value) {
        calculation += value;
        console.log(calculation);
      }
    </script>
  </body>
</html>

```
- 7k
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Show Quantity</button>

    <button onclick="
      updateCartQuantity(1);
    ">Add to Cart</button>

    <button onclick="
      updateCartQuantity(2);
    ">+2</button>

    <button onclick="
      updateCartQuantity(3);
    ">+3</button>

    <button onclick="
      updateCartQuantity(4);
    ">+4</button>

    <button onclick="
      updateCartQuantity(5);
    ">+5</button>

    <button onclick="
      updateCartQuantity(-1);
    ">Remove from cart</button>

    <button onclick="
      updateCartQuantity(-2);
    ">-2</button>

    <button onclick="
      updateCartQuantity(-3);
    ">-3</button>

    <button onclick="
      cartQuantity = 0;
      console.log('Cart was reset.');
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Reset Cart</button>

    <script>
      let cartQuantity = 0;

      function updateCartQuantity(change) {
        if (cartQuantity + change > 10) {
          alert('The cart is full');

        } else if (cartQuantity + change < 0) {
          alert('Not enough items in the cart');

        } else {
          cartQuantity += change;
          console.log(`Cart quantity: ${cartQuantity}`);
        }
      }
    </script>
  </body>
</html>

```
- 7l
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Show Quantity</button>

    <button onclick="
      updateCartQuantity(1);
    ">Add to Cart</button>

    <button onclick="
      updateCartQuantity(2);
    ">+2</button>

    <button onclick="
      updateCartQuantity(3);
    ">+3</button>

    <button onclick="
      updateCartQuantity(4);
    ">+4</button>

    <button onclick="
      updateCartQuantity(5);
    ">+5</button>

    <button onclick="
      updateCartQuantity(-1);
    ">Remove from cart</button>

    <button onclick="
      updateCartQuantity(-2);
    ">-2</button>

    <button onclick="
      updateCartQuantity(-3);
    ">-3</button>

    <button onclick="
      cartQuantity = 0;
      console.log('Cart was reset.');
      console.log(`Cart quantity: ${cartQuantity}`);
    ">Reset Cart</button>

    <script>
      let cartQuantity = 0;

      function updateCartQuantity(change) {
        if (cartQuantity + change > 10) {
          alert('The cart is full');
          return;
        }

        if (cartQuantity + change < 0) {
          alert('Not enough items in the cart');
          return;
        }

        cartQuantity += change;
        console.log(`Cart quantity: ${cartQuantity}`);
      }
    </script>
  </body>
</html>

```








