- DOM = Document Object Model
- another built in object is - 'document' object
- document object and webpage are linked together
- document object represents or models the webpage
- document object has properties and methods
- DOM combines HTML an javaScript together and it gives javaScript control the webpage
- if a HTML element is inside javaScript then the HTML element is converted into JS Object
- with DOM javaScript has full control of the webpage
- method = a function saved inside an object
- document.body = let us get the body element of html
- document.querySelector() = let us get any element from the page and put in inside javaScript as        javaScript Object
- document.querySelector('body') = document.body // same
- Every HTML element has a proprty called 'innerHTML'. that let us control the HTML inside the element
- document.querySelector() only gets the first element of html
- any class usning for CSS can also be used for javaScript
- HTML element inside javaScript is an object. object are values we can set object inside a varible
- we generally set the element variable ending with (--Element or --Elem)
- DOM combines JS and HTML together. it gives JS full control of the webpage
- innerHTML property counts extra spaces around text to solve this we need to use innerText
- innerText don't count extra spaces
- clicks, keydown => events
- onclick, onkeydown => event listeners = they check for events and run js
- eventlisteners
    - onclick          = click
    - onkeydown        = key press
    - onscroll         = scrolling
    - onmouseenter     = hovering mouse
     - onmouseleave    = stop hovering mouse
 - if a string only contains a number and we ( - , * , / ) then the string will be converted into         number automatically = type coercion --> not recommneded
 - window object is a built in object
 - document object represents the webpage
 - window object represents the browser
 - document object is inside the window object
 - console object is inside the window object
 - alert function is inside the window object
 - javaScript will automatically add window object in front of those object or function
- DOM
```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM</title>
  </head>
  <body>
    <button>hello</button>
    <button class="js-button">Second button</button>

    <script>
      // documnet.body.innerHTML = 'hello'; // this code removes everything on the page with 'hello'
      // here document --> object then body --> property of document and also an object
      innerHTML = property of body
      // document.title = 'Good job!'; // change the title of the page
      document.querySelector('anyElementName, .anyClassName, #anyIdName') /* get the first element           class or id */
      
      document.querySelector('button')    
      console.log(document.querySelector('button'))
      console.log(document.querySelector('button').innerHTML);
      document.querySelector('button')
        .innerHTML = 'Changed';

      
      document.querySelector('.js-button');
      console.log(document.querySelector('.js-button'));
      const buttonElement = document.querySelector('.js-button');
      console.log(buttonElement);
      
      /*
      console.log(document.title); // to console the title of webpage
      document.title = 'Changed'; // to change the title of webpage

      console.log(document.body); // to console all the code including body element
      console.log(typeof document.body); // object // HTML elemet inside JS = object

      console.log(document.body.innerHTML); // it gives all the html inside the body element without         body element
      document.body.innerHTML = 'changed'; // change innet html with text
      // change inner html with new html code
      document.body.innerHTML = '<button>Good job!</button>'; // change the inner HTML of body element
      */
      
      /*
      document.body.innerHTML = 'hello';
      document.title = 'Good job!';
      */
    </script>
  </body>
</html>
```
- DOM Project
```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Projects</title>
  </head>
  <body>
    <p>YouTube Subscribe Button</p>
    <button onclick="
      subscribe();
    " class="js-subscribe-button">
      Subscribe
    </button>

    <p>Amazon Shipping Calculator</p>
    // <input>    this is called a void element
    // placeholder is an attribute
    <input placeholder="Cost of order" class="js-cost-input" onkeydown="
      handleCostKeydown(event);
    ">
    <button onclick="
      calculateTotal();
    ">Calculate</button>
    <p class="js-total-cost"></p>

    <script>
      String(25) // it will convert the number into string
      console.log('25' - 5); //20
      console.log('25' + 5); // 255

      
      window.document
      window.console.log('window');
      window.alert

      function handleCostKeydown(event) {
        // console.log('typring')
        // console.log(event) //object
        // console.log(event.key)
        if (event.key === 'Enter') {
          calculateTotal();
        }
      }

      function calculateTotal() {
        const inputElement = document.querySelector('.js-cost-input');
        inputElement.value // this is how we get the value from an input element but as string
        let cost = Number(inputElement.value);
        // Number() is a built in funciton

        if (cost < 40) {
          cost = cost + 10;
        }

        document.querySelector('.js-total-cost')
          .innerHTML = `$${cost}`;
      }

      function subscribe() {
        const buttonElement = document.querySelector('.js-subscribe-button');

        if (buttonElement.innerText === 'Subscribe') {
          buttonElement.innerHTML = 'Subscribed';
        } else {
          buttonElement.innerHTML = 'Subscribe';
        }
      }
      
    </script>
  </body>
</html>

```
- rock paper scissors
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

    <p class="js-result"></p>
    <p class="js-moves"></p>
    <p class="js-score"></p>

    <button onclick="
      score.wins = 0;
      score.losses = 0;
      score.ties = 0;
      localStorage.removeItem('score');
      updateScoreElement();
    ">Reset Score</button>

    <script>
      let score = JSON.parse(localStorage.getItem('score')) || {
        wins: 0,
        losses: 0,
        ties: 0
      };

      updateScoreElement();

      /*
      if (!score) {
        score = {
          wins: 0,
          losses: 0,
          ties: 0
        };
      }
      */

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

        if (result === 'You win.') {
          score.wins += 1;
        } else if (result === 'You lose.') {
          score.losses += 1;
        } else if (result === 'Tie.') {
          score.ties += 1;
        }

        localStorage.setItem('score', JSON.stringify(score));

        updateScoreElement();

        document.querySelector('.js-result').innerHTML = result;

        document.querySelector('.js-moves').innerHTML = `You ${playerMove} - ${computerMove} Computer`;
      }

      function updateScoreElement() {
        document.querySelector('.js-score')
          .innerHTML = `Wins: ${score.wins}, Losses: ${score.losses}, Ties: ${score.ties}`;
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
- Exercise of chapter 9
- 9a
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button>9a</button>

    <script>
      console.log(document.querySelector('button'));
    </script>
  </body>
</html>
```
- 9b
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button>9a</button>
    
    <!-- Feel free to use a different class name. -->
    <button class="js-button">9b</button>

    <script>
      console.log(document.querySelector('button'));
      
      document.querySelector('.js-button')
        .innerHTML = '9b done!';
    </script>
  </body>
</html>
```
- 9c
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button onclick="
      document.querySelector('.js-choice')
        .innerHTML = 'You chose: heads';
    ">heads</button>

    <button onclick="
      document.querySelector('.js-choice')
        .innerHTML = 'You chose: tails';
    ">tails</button>

    <p class="js-choice"></p>
  </body>
</html>
```
- 9d
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <input placeholder="Name" class="js-name-input">

    <button onclick="
      const inputElement = document.querySelector('.js-name-input');
      document.querySelector('.js-message')
        .innerHTML = `Your name is: ${inputElement.value}`;
    ">Submit</button>

    <p class="js-message"></p>
  </body>
</html>
```
- 9e
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <input placeholder="Name" class="js-name-input"
      onkeydown="
        if (event.key === 'Enter') {
          // Optional: instead of duplicating this code,
          // you could also put it in a function.
          const inputElement = document.querySelector('.js-name-input');
          document.querySelector('.js-message')
            .innerHTML = `Your name is: ${inputElement.value}`;
        }
      ">

    <button onclick="
      const inputElement = document.querySelector('.js-name-input');
      document.querySelector('.js-message')
        .innerHTML = `Your name is: ${inputElement.value}`;
    ">Submit</button>

    <p class="js-message"></p>
  </body>
</html>
```
- 9f
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <input placeholder="Name" class="js-name-input"
      onkeydown="
        if (event.key === 'Enter') {
          displayMessage();
        }
      ">

    <button onclick="
      displayMessage();
    ">Submit</button>

    <p class="js-message"></p>

    <script>
      function displayMessage() {
        const inputElement = document.querySelector('.js-name-input');
        document.querySelector('.js-message')
          .innerHTML = `Your name is: ${inputElement.value}`;
      }
    </script>
  </body>
</html>
```
- 9g
```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Projects</title>
  </head>
  <body>
    <!-- Answer is at the bottom. -->
    <p>Amazon Shipping Calculator</p>
    <input placeholder="Cost of order" class="js-cost-input" onkeydown="
      handleCostKeydown(event);
    ">
    <button onclick="
      calculateTotal();
    ">Calculate</button>
    <p class="js-total-cost"></p>

    <script>
      function handleCostKeydown(event) {
        if (event.key === 'Enter') {
          calculateTotal();
        }
      }

      /*
       * Issue = the calculation is inaccurate.
       * Fix = calculate the number in cents and then
       *       convert back to dollars at the end.
       */
      function calculateTotal() {
        const inputElement = document.querySelector('.js-cost-input');

        // Convert the numbers to cents by * 100.
        let cost = Number(inputElement.value) * 100;

        if (cost < 4000) {
          cost = cost + 1000;
        }

        // Convert back to dollars at the end.
        document.querySelector('.js-total-cost')
          .innerHTML = `$${cost / 100}`;
      }
    </script>
  </body>
</html>
```
- 9h
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <input placeholder="Type something" class="js-input"
      onkeyup="
        const inputElement = document.querySelector('.js-input');
        document.querySelector('.js-message')
          .innerHTML = inputElement.value;
      ">

    <p class="js-message"></p>
  </body>
</html>
```
- 9i
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Cart Quantity</title>
  </head>
  <body>
    <button onclick="
      // Display the cart quantity on the page
      // instead of in the console.
      displayCartQuantity();
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

      // Display the cart quantity after updating.
      displayCartQuantity();
    ">Reset Cart</button>

    <!-- Create an element to display the cart quantity. -->
    <p class="js-cart-quantity"></p>

    <script>
      let cartQuantity = 0;

      // Display the cart quantity when the page loads.
      displayCartQuantity();

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

        // Display the cart quantity after updating.
        displayCartQuantity();
      }

      function displayCartQuantity() {
        document.querySelector('.js-cart-quantity')
          .innerHTML = `Cart quantity: ${cartQuantity}`;
      }
    </script>
  </body>
</html>

```
- 9j
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <!-- Create an element to display the calculation. -->
    <p class="js-calculation"></p>

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

        // Display the calculation on the page
        // instead of console.log
        displayCalculation();

        localStorage.setItem('calculation', calculation);
      ">=</button>

      <button onclick="
        updateCalculation(' / ');
      ">/</button>
    </p>

    <p>
      <button onclick="
        calculation = '';

        // Display the calculation on the page
        // instead of console.log
        displayCalculation();

        localStorage.setItem('calculation', calculation);
      ">Clear</button>
    </p>

    <script>
      let calculation = localStorage.getItem('calculation') || '';

      // Display the calculation when the page first loads.
      displayCalculation();

      function updateCalculation(value) {
        calculation += value;

        // Display the calculation on the page
        // instead of console.log
        displayCalculation();

        localStorage.setItem('calculation', calculation);
      }

      function displayCalculation() {
        document.querySelector('.js-calculation')
          .innerHTML = calculation;
      }
    </script>
  </body>
</html>

```
