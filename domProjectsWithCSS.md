## chapter 10 DOM with CSS
- to change CSS with js
- '.classList' gives us control of the 'class' attribute
- 'classList' is an object
- to add a class 
```js
.classList.add('classNameThatWeWantToAdd');
// don't need '.' before classname within single quote
```
- to remove a class
```js
.classList.remove('classNameThatWeWantToRemove');
// don't need '.' before classname within single quote
```
- DOM projects
```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Projects</title>
    <style>
      body {
        font-family: Arial;
      }

      .subscribe-button {
        border: none;
        background-color: black;
        color: white;
        padding-top: 10px;
        padding-bottom: 10px;
        padding-left: 15px;
        padding-right: 15px;
        font-weight: bold;
        border-radius: 50px;
        cursor: pointer;
        margin-bottom: 30px;
      }

      .is-subscribed {
        background-color: rgb(240, 240, 240);
        color: black;
      }

      .cost-input {
        font-size: 15px;
        /*
        padding-top: 10px;
        padding-bottom: 10px;
        padding-left: 10px;
        padding-right: 10px;
        */
        padding: 10px;
      }

      .calculate-button {
        background-color: green;
        color: white;
        border: none;
        font-size: 15px;
        padding: 12px 15px;
        cursor: pointer;
      }
    </style>
  </head>
  <body>
    <p>YouTube Subscribe Button</p>
    <button onclick="
      subscribe();
    " class="js-subscribe-button subscribe-button">
      Subscribe
    </button>

    <p>Amazon Shipping Calculator</p>
    <input placeholder="Cost of order" class="js-cost-input cost-input" onkeydown="
      handleCostKeydown(event);
    ">
    <button onclick="
      calculateTotal();
    " class="calculate-button">Calculate</button>
    <p class="js-total-cost"></p>

    <script>
      String(25)
      console.log('25' - 5);
      console.log('25' + 5);

      window.document
      window.console.log('window');
      window.alert

      function handleCostKeydown(event) {
        if (event.key === 'Enter') {
          calculateTotal();
        }
      }

      function calculateTotal() {
        const inputElement = document.querySelector('.js-cost-input');
        let cost = Number(inputElement.value);

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
          buttonElement.classList.add('is-subscribed');
        } else {
          buttonElement.innerHTML = 'Subscribe';
          buttonElement.classList.remove('is-subscribed');
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
    <link rel="stylesheet" href="styles/10-rock-paper-scissors.css">
  </head>
  <body>
    <p class="title">Rock Paper Scissors</p>
    <button onclick="
      playGame('rock');
    " class="move-button">
      <img src="images/rock-emoji.png" class="move-icon">
    </button>

    <button onclick="
      playGame('paper');
    " class="move-button">
      <img src="images/paper-emoji.png" class="move-icon">
    </button>

    <button onclick="
      playGame('scissors');
    " class="move-button">
      <img src="images/scissors-emoji.png" class="move-icon">
    </button>

    <p class="js-result result"></p>
    <p class="js-moves"></p>
    <p class="js-score score"></p>

    <button onclick="
      score.wins = 0;
      score.losses = 0;
      score.ties = 0;
      localStorage.removeItem('score');
      updateScoreElement();
    " class="reset-score-button">Reset Score</button>

    <script src="scripts/10-rock-paper-scissors.js"></script>
  </body>
</html>

```
- CSS
```css
body {
  background-color: rgb(25, 25, 25);
  color: white;
  font-family: Arial;
}

.title {
  font-size: 30px;
  font-weight: bold;
}

.move-icon {
  height: 50px;
}

.move-button {
  background-color: transparent;
  border: 3px solid white;
  width: 120px;
  height: 120px;
  border-radius: 60px;
  margin-right: 10px;
  cursor: pointer;
}

.result {
  font-size: 25px;
  font-weight: bold;
  margin-top: 50px;
}

.score {
  margin-top: 60px;
}

.reset-score-button {
  background-color: white;
  border: none;
  font-size: 15px;
  padding: 8px 15px;
  cursor: pointer;
}
```
- javaScript
```js
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

  document.querySelector('.js-moves').innerHTML = `You
<img src="images/${playerMove}-emoji.png" class="move-icon">
<img src="images/${computerMove}-emoji.png" class="move-icon">
Computer`;
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
```
- Exercise
- 10a
```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .amazon-button {
        background-color: rgb(255, 216, 20);
        border: none;
        padding: 5px 40px;
        border-radius: 20px;
        cursor: pointer;
      }
    </style>
  </head>
  <body>
    <button class="amazon-button">
      Add to Cart
    </button>
  </body>
</html>
```
- 10b
```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .request-now-button {
        background-color: black;
        color: white;
        border: none;
        font-weight: bold;
        padding: 12px 20px;
        border-radius: 5px;
        cursor: pointer;
        margin-right: 20px;
      }

      .schedule-later-button {
        background-color: rgb(230, 230, 230);
        border: none;
        font-weight: bold;
        padding: 12px 20px;
        border-radius: 5px;
        cursor: pointer;
      }
    </style>
  </head>
  <body>
    <button class="request-now-button">
      Request now
    </button>
    <button class="schedule-later-button">
      Schedule for later
    </button>
  </body>
</html>
```
- 10c
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button class="js-button">Test</button>

    <script>
      // I used the variable name 'button' because
      // it's shorter, but feel free to use whatever
      // variable name you want.
      const button = document.querySelector('.js-button');
      console.log(button.classList.contains('js-button'));
    </script>
  </body>
</html>
```
- 10d
```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      /* The word "toggle" means turn on/off. */
      .toggle-button {
        background-color: rgb(230, 230, 230);
        border: none;
        padding: 10px 15px;
        border-radius: 5px;
        margin-right: 10px;
        font-size: 15px;
        cursor: pointer;
      }

      .is-toggled {
        background-color: black;
        color: white;
      }
    </style>
  </head>
  <body>
    <button class="toggle-button js-button" onclick="
      const button = document.querySelector('.js-button');
      if (!button.classList.contains('is-toggled')) {
        button.classList.add('is-toggled');
      } else {
        button.classList.remove('is-toggled');
      }
    ">Gaming</button>
  </body>
</html>
```
- 10e
```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      /* The word "toggle" means turn on/off. */
      .toggle-button {
        background-color: rgb(230, 230, 230);
        border: none;
        padding: 10px 15px;
        border-radius: 5px;
        margin-right: 10px;
        font-size: 15px;
        cursor: pointer;
      }

      .is-toggled {
        background-color: black;
        color: white;
      }
    </style>
  </head>
  <body>
    <button class="toggle-button js-button" onclick="
      let button = document.querySelector('.js-button');
      if (!button.classList.contains('is-toggled')) {
        button.classList.add('is-toggled');
      } else {
        button.classList.remove('is-toggled');
      }
    ">Gaming</button>

    <button class="toggle-button js-button-2" onclick="
       button = document.querySelector('.js-button-2');
      if (!button.classList.contains('is-toggled')) {
        button.classList.add('is-toggled');
      } else {
        button.classList.remove('is-toggled');
      }
    ">Music</button>

    <button class="toggle-button js-button-3" onclick="
       button = document.querySelector('.js-button-3');
      if (!button.classList.contains('is-toggled')) {
        button.classList.add('is-toggled');
      } else {
        button.classList.remove('is-toggled');
      }
    ">Tech</button>
  </body>
</html>
```
- 10f html
```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="10f.css">
  </head>
  <body>
    <button class="toggle-button js-button" onclick="
      toggleButton('.js-button');
    ">Gaming</button>

    <button class="toggle-button js-button-2" onclick="
      toggleButton('.js-button-2');
    ">Music</button>

    <button class="toggle-button js-button-3" onclick="
      toggleButton('.js-button-3');
    ">Tech</button>

    <script src="10f.js"></script>
  </body>
</html>
```
- 10f CSS
```css
.toggle-button {
  background-color: rgb(230, 230, 230);
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  margin-right: 10px;
  font-size: 15px;
  cursor: pointer;
}

.is-toggled {
  background-color: black;
  color: white;
}
```
- 10f js
```js
// The word "toggle" means turn on/off.
function toggleButton(selector) {
  const button = document.querySelector(selector);
  if (!button.classList.contains('is-toggled')) {
    button.classList.add('is-toggled');
  } else {
    button.classList.remove('is-toggled');
  }
}
```
- 10g
```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="10g.css">
  </head>
  <body>
    <button class="toggle-button js-button" onclick="
      toggleButton('.js-button');
    ">Gaming</button>

    <button class="toggle-button js-button-2" onclick="
      toggleButton('.js-button-2');
    ">Music</button>

    <button class="toggle-button js-button-3" onclick="
      toggleButton('.js-button-3');
    ">Tech</button>

    <script src="10g.js"></script>
  </body>
</html>
```
- 10g CSS
```css
.toggle-button {
  background-color: rgb(230, 230, 230);
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  margin-right: 10px;
  font-size: 15px;
  cursor: pointer;
}

.is-toggled {
  background-color: black;
  color: white;
}
```
- 10g js
```js
// The word "toggle" means turn on/off.
function toggleButton(selector) {
  const button = document.querySelector(selector);
  if (!button.classList.contains('is-toggled')) {

    // Before turning this button ON, check if there's
    // already a button that's turned ON and turn it OFF.
    turnOffPreviousButton();

    button.classList.add('is-toggled');
  } else {
    button.classList.remove('is-toggled');
  }
}

function turnOffPreviousButton() {
  const previousButton = document.querySelector('.is-toggled');
  if (previousButton) {
    previousButton.classList.remove('is-toggled');
  }
}
```
- 10h
```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Projects</title>
    <style>
      body {
        font-family: Arial;
      }

      .cost-input {
        font-size: 15px;
        padding: 10px;
      }

      .calculate-button {
        background-color: green;
        color: white;
        border: none;
        font-size: 15px;
        padding: 12px 15px;
        cursor: pointer;
      }

      /* Give the error message a red color. */
      .error-message {
        color: red;
      }
    </style>
  </head>
  <body>
    <p>Amazon Shipping Calculator</p>
    <input placeholder="Cost of order" class="js-cost-input cost-input" onkeydown="
      handleCostKeydown(event);
    ">
    <button onclick="
      calculateTotal();
    " class="calculate-button">Calculate</button>
    <p class="js-total-cost"></p>

    <!-- Create an element to display the error message. -->
    <p class="js-error-message error-message"></p>

    <script>
      function handleCostKeydown(event) {
        if (event.key === 'Enter') {
          calculateTotal();
        }
      }

      function calculateTotal() {
        const inputElement = document.querySelector('.js-cost-input');
        let cost = Number(inputElement.value);

        // First, reset all previous messages.
        document.querySelector('.js-total-cost')
          .innerHTML = '';
        document.querySelector('.js-error-message')
          .innerHTML = '';

        if (cost < 0) {
          document.querySelector('.js-error-message')
            .innerHTML = 'Error: cost cannot be less than $0';
          // If we display an error, we can use return to
          // end this function immediately. This is called
          // an "early return" and it makes the code cleaner
          // because it reduces nesting / indents.
          return;
        }

        if (cost < 40) {
          cost = cost + 10;
        }

        document.querySelector('.js-total-cost')
          .innerHTML = `$${cost}`;
      }
    </script>
  </body>
</html>

```
- 10i
```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      body {
        font-family: Arial;
        background-color: rgb(0, 0, 0);
      }

      .calculation {
        color: white;
        font-size: 45px;
        margin-top: 15px;
        margin-bottom: 5px;
      }

      .calculator-button {
        height: 60px;
        width: 60px;
        border-radius: 60px;
        border: none;
        font-size: 26px;
        cursor: pointer;
        margin-right: 5px;
      }

      .gray-button {
        background-color: rgb(51, 51, 51);
        color: white;
      }

      .orange-button {
        background-color: rgb(254, 160, 10);
        color: white;
      }

      .clear-button {
        font-size: 17px;
      }
    </style>
  </head>
  <body>
    <!-- Create an element to display the calculation. -->
    <p class="js-calculation calculation"></p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('1');
      ">1</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('2');
      ">2</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('3');
      ">3</button>

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' + ');
      ">+</button>
    </p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('4');
      ">4</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('5');
      ">5</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('6');
      ">6</button>

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' - ');
      ">-</button>
    </p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('7');
      ">7</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('8');
      ">8</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('9');
      ">9</button>

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' * ');
      ">*</button>
    </p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('0');
      ">0</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('.');
      ">.</button>

      <button class="calculator-button gray-button" onclick="
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

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' / ');
      ">/</button>
    </p>

    <p>
      <button class="calculator-button gray-button clear-button" onclick="
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
- 10j
```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="10j.css">
  </head>
  <body>
    <!-- Create an element to display the calculation. -->
    <p class="js-calculation calculation"></p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('1');
      ">1</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('2');
      ">2</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('3');
      ">3</button>

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' + ');
      ">+</button>
    </p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('4');
      ">4</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('5');
      ">5</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('6');
      ">6</button>

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' - ');
      ">-</button>
    </p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('7');
      ">7</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('8');
      ">8</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('9');
      ">9</button>

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' * ');
      ">*</button>
    </p>

    <p>
      <button class="calculator-button gray-button" onclick="
        updateCalculation('0');
      ">0</button>

      <button class="calculator-button gray-button" onclick="
        updateCalculation('.');
      ">.</button>

      <button class="calculator-button gray-button" onclick="
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

      <button class="calculator-button orange-button" onclick="
        updateCalculation(' / ');
      ">/</button>
    </p>

    <p>
      <button class="calculator-button gray-button clear-button" onclick="
        calculation = '';

        // Display the calculation on the page
        // instead of console.log
        displayCalculation();

        localStorage.setItem('calculation', calculation);
      ">Clear</button>
    </p>

    <script src="10j.js"></script>
  </body>
</html>

```
- 10j CSS
```css
body {
  font-family: Arial;
  background-color: rgb(0, 0, 0);
}

.calculation {
  color: white;
  font-size: 45px;
  margin-top: 15px;
  margin-bottom: 5px;
}

.calculator-button {
  height: 60px;
  width: 60px;
  border-radius: 60px;
  border: none;
  font-size: 26px;
  cursor: pointer;
  margin-right: 5px;
}

.gray-button {
  background-color: rgb(51, 51, 51);
  color: white;
}

.orange-button {
  background-color: rgb(254, 160, 10);
  color: white;
}

.clear-button {
  font-size: 17px;
}
```
- 10j js
```js
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
```
