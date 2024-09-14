## advamced function

- advanced function
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Advanced Functions</title>
  </head>
  <body>
    <button onclick="" class="js-button">Click</button>

    <script>
      /*
      const buttonElement = document.querySelector('.js-button');

      const eventListener = () => {
        console.log('click');
      };
      buttonElement.addEventListener('click', eventListener);

      buttonElement.removeEventListener('click', eventListener);

      buttonElement.addEventListener('click', () => {
        console.log('click2');
      });
      */

      /*
      greeting();
      function greeting() {
        console.log('hello');
      }
      greeting();

      const num = 2;
      const function1 = function() {
        console.log('hello2');
      };

      console.log(function1);
      console.log(typeof function1);
      function1();

      const object1 = {
        num: 2,
        fun: function() {
          console.log('hello3');
        }
      };
      object1.fun();

      function display(param) {
        console.log(param);
      }
      display(2);

      function run(param) {
        param();
      }
      run(function() {
        console.log('hello4');
      });
      */

      /*
      setTimeout(function() {
        console.log('timeout');
        console.log('timeout2');
      }, 3000);

      console.log('next line');

      setInterval(function() {
        console.log('interval');
      }, 3000);

      console.log('next line 2');
      */

      /*
      [
        'make dinner',
        'wash dishes',
        'watch youtube'
      ].forEach((value, index) => {
        if (value === 'wash dishes') {
          return;
        }

        console.log(index);
        console.log(value);
      });

      const regularFunction = function(param, param2) {
        console.log('hello');
        return 5;
      };

      const arrowFunction = (param, param2) => {
        console.log('hello');
        return 5;
      };
      arrowFunction();

      const oneParam = param => {
        console.log(param + 1);
      };
      oneParam(2);

      const oneLine = () => 2 + 3;
      console.log(oneLine());

      const object2 = {
        method: () => {

        },
        method() {

        }
      };
      */

      console.log([1, -3, 5].filter((value, index) => {
        /*
        if (value >= 0) {
          return true;
        } else {
          return false;
        }
        */
        return value >= 0;
      }));

      console.log([1, 1, 3].map((value, index) => {
        return value * 2;
      }));

      console.log([1, 1, 3].map(value => value * 2));
    </script>
  </body>
</html>

```
- rock paper scissors html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
    <link rel="stylesheet" href="styles/12-rock-paper-scissors.css">
  </head>
  <body>
    <p class="title">Rock Paper Scissors</p>
    <button class="move-button js-rock-button">
      <img src="images/rock-emoji.png" class="move-icon">
    </button>

    <button class="move-button js-paper-button">
      <img src="images/paper-emoji.png" class="move-icon">
    </button>

    <button class="move-button js-scissors-button">
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
    " class="reset-score-button js-reset-score-button">Reset Score</button>

    <button class="auto-play-button" onclick="
      autoPlay();
    ">Auto Play</button>
    
    <script src="scripts/12-rock-paper-scissors.js"></script>
  </body>
</html>

```
- rock paper scissors css
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

.reset-score-button,
.auto-play-button {
  background-color: white;
  border: none;
  font-size: 15px;
  padding: 8px 15px;
  cursor: pointer;
}
```

- rock paper scissors js
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

let isAutoPlaying = false;
let intervalId;

//const autoPlay = () => {

//};
function autoPlay() {
  if (!isAutoPlaying) {
    intervalId = setInterval(() => {
      const playerMove = pickComputerMove();
      playGame(playerMove);
    }, 1000);
    isAutoPlaying = true;

  } else {
    clearInterval(intervalId);
    isAutoPlaying = false;
  }
}

document.querySelector('.js-rock-button')
  .addEventListener('click', () => {
    playGame('rock');
  });

document.querySelector('.js-paper-button')
  .addEventListener('click', () => {
    playGame('paper');
  });

document.querySelector('.js-scissors-button')
  .addEventListener('click', () => {
    playGame('scissors');
  });

document.body.addEventListener('keydown', (event) => {
  if (event.key === 'r') {
    playGame('rock');
  } else if (event.key === 'p') {
    playGame('paper');
  } else if (event.key === 's') {
    playGame('scissors');
  }
});

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

- todo list html

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Todo List</title>
    <link rel="stylesheet" href="styles/12-todo-list.css">
  </head>
  <body>
    <p>Todo List</p>

    <div class="todo-input-grid">
      <input placeholder="Todo name"
        class="js-name-input name-input">
      <input type="date"
        class="js-due-date-input due-date-input">
      <button class="add-todo-button js-add-todo-button">Add</button>
    </div>

    <div class="js-todo-list todo-grid"></div>

    <script src="scripts/12-todo-list.js"></script>
  </body>
</html>

```
- todo list css
```css
body {
  font-family: Arial;
}

.todo-grid,
.todo-input-grid {
  display: grid;
  grid-template-columns: 200px 150px 100px;
  column-gap: 10px;
  row-gap: 10px;
  align-items: center;
}

.todo-input-grid {
  margin-bottom: 10px;
  align-items: stretch;
}

.name-input,
.due-date-input {
  font-size: 15px;
  padding: 6px;
}

.add-todo-button {
  background-color: green;
  color: white;
  border: none;
  font-size: 15px;
  cursor: pointer;
}

.delete-todo-button {
  background-color: darkred;
  color: white;
  border: none;
  font-size: 15px;
  cursor: pointer;
  padding-top: 10px;
  padding-bottom: 10px;
}
```
- todo list js
```js
const todoList = [{
  name: 'make dinner',
  dueDate: '2022-12-22'
}, {
  name: 'wash dishes',
  dueDate: '2022-12-22'
}];

renderTodoList();

function renderTodoList() {
  let todoListHTML = '';

  todoList.forEach((todoObject, index) => {
    const { name, dueDate } = todoObject;
    const html = `
      <div>${name}</div>
      <div>${dueDate}</div>
      <button class="delete-todo-button js-delete-todo-button">Delete</button> 
    `;
    todoListHTML += html;
  });

  document.querySelector('.js-todo-list')
    .innerHTML = todoListHTML;

  document.querySelectorAll('.js-delete-todo-button')
    .forEach((deleteButton, index) => {
      deleteButton.addEventListener('click', () => {
        todoList.splice(index, 1);
        renderTodoList();
      });
    });
}

document.querySelector('.js-add-todo-button')
  .addEventListener('click', () => {
    addTodo();
  });

function addTodo() {
  const inputElement = document.querySelector('.js-name-input');
  const name = inputElement.value;

  const dateInputElement = document.querySelector('.js-due-date-input');
  const dueDate = dateInputElement.value;

  todoList.push({
    //name: name,
    //dueDate: dueDate,
    name,
    dueDate
  });

  inputElement.value = '';

  renderTodoList();
}
```
- exercise
- 12a
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const add = function() {
        console.log(2 + 3);
      };

      add();
      add();
    </script>
  </body>
</html>
```
- 12b
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const add = function() {
        console.log(2 + 3);
      };

      add();
      add();

      function runTwice(fun) {
        fun();
        fun();
      }

      runTwice(function() {
        console.log('12b');
      });
      
      runTwice(add);
    </script>
  </body>
</html>
```
- 12c
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button class="js-button" onclick="
      updateButton();
    ">Start</button>

    <script>
      // Grouping the JavaScript code into a function
      // is optional, but it is a bit cleaner.
      function updateButton() {
        const button = document.querySelector('.js-button');

        setTimeout(function() {
          button.innerHTML = 'Finished!';
        }, 1000);
      }
    </script>
  </body>
</html>
```
- 12d
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button class="js-button" onclick="
      updateButton();
    ">Start</button>

    <script>
      function updateButton() {
        const button = document.querySelector('.js-button');
        
        button.innerHTML = 'Loading...';
        setTimeout(function() {
          button.innerHTML = 'Finished!';
        }, 1000);
      }
    </script>
  </body>
</html>
```
- 12e
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button class="js-button" onclick="
      displayMessage();
    ">Add to cart</button>
    
    <p class="js-message"></p>

    <script>
      function displayMessage() {
        const messageElement = document.querySelector('.js-message');
        messageElement.innerHTML = 'Added';

        setTimeout(function() {
          messageElement.innerHTML = '';
        }, 2000);
      }
    </script>
  </body>
</html>
```
- 12f
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <button class="js-button" onclick="
      displayMessage();
    ">Add to cart</button>
    
    <p class="js-message"></p>

    <script>
      let timeoutId;

      function displayMessage() {
        const messageElement = document.querySelector('.js-message');
        messageElement.innerHTML = 'Added';

        // First, cancel the previous timeout so that
        // it doesn't remove the message too quickly.
        clearTimeout(timeoutId);

        timeoutId = setTimeout(function() {
          messageElement.innerHTML = '';
        }, 2000);
      }
    </script>
  </body>
</html>
```
- 12g
```html
<!DOCTYPE html>
<html>
  <head>
    <title>App</title>
  </head>
  <body>
    <script>
      setInterval(function() {
        if (document.title === 'App') {
          document.title = '(2) New messages';
        } else {
          document.title = 'App';
        }
      }, 1000);
    </script>
  </body>
</html>
```
- 12h
```html
<!DOCTYPE html>
<html>
  <head>
    <title>App</title>
  </head>
  <body>
    <button onclick="
      messages++;
    ">Add</button>

    <button onclick="
      messages--;
    ">Remove</button>

    <script>
      let messages = 2;

      setInterval(function() {
        if (document.title === 'App') {
          document.title = `(${messages}) New messages`;
        } else {
          document.title = 'App';
        }
      }, 1000);
    </script>
  </body>
</html>
```
- 12i
```html
<!DOCTYPE html>
<html>
  <head>
    <title>App</title>
  </head>
  <body>
    <!--
      Note: This is just a sample solution. Other
      solutions are possible so don't worry if
      your solution looks different.
    -->
    <button onclick="
      messages++;
      displayNotification();
    ">Add</button>

    <button onclick="
      if (messages > 0) {
        messages--;

        // If there are no new messages, stop displaying
        // the notification in the tab.
        if (messages === 0) {
          stopNotification();
        }
      }
    ">Remove</button>

    <script>
      let messages = 2;

      // Save the intervalId in case we need to cancel it.
      let intervalId;

      // We'll use this variable to keep track of whether
      // or not we're displaying the notification.
      let isDisplayingNotification;

      // Start displaying the notification in the tab
      // when the page first loads.
      displayNotification();

      function displayNotification() {
        // If we're already displaying the notification,
        // stop this function because we don't want to
        // create 2 intervals at the same time.
        if (isDisplayingNotification) {
          return;
        }

        isDisplayingNotification = true;

        intervalId = setInterval(function() {
          if (document.title === 'App') {
            document.title = `(${messages}) New messages`;
          } else {
            document.title = 'App';
          }
        }, 1000);
      }

      function stopNotification() {
        isDisplayingNotification = false;

        clearInterval(intervalId);
        document.title = 'App';
      }
    </script>
  </body>
</html>
```
- 12j
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const multiply = (a, b) => {
        return a * b;
      };

      console.log(multiply(2, 3));
      console.log(multiply(7, 10));
    </script>
  </body>
</html>
```
- 12k
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const multiply = (a, b) => a * b;

      console.log(multiply(2, 3));
      console.log(multiply(7, 10));
    </script>
  </body>
</html>
```
- 12l
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function countPositive(nums) {
        let positiveNumbers = 0;

        // When there is only 1 parameter,
        // the brackets are optional. So
        // we can also write: num => { ... }
        nums.forEach((num) => {
          if (num > 0) {
            positiveNumbers++;
          }
        });

        return positiveNumbers;
      }

      console.log(countPositive([1, -3, 5]));
      console.log(countPositive([-2, 3, -5, 7, 10]));
    </script>
  </body>
</html>
```
- 12m
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function addNum(array, num) {
        // When there is only 1 parameter,
        // the brackets are optional. So we
        // can also write: value => value + num
        return array.map((value) => value + num);
      }

      console.log(addNum([1, 2, 3], 2));
      console.log(addNum([-2, -1, 0, 99], 2));
    </script>
  </body>
</html>
```
- 12n
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function removeEgg(foods) {
        // If food is 'egg', the inner function returns false
        //   and the food is not included in the result.
        // Otherwise, the inner function returns true
        //   and the food is included in the result. 
        return foods.filter((food) => food !== 'egg');
      }

      console.log(removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']));
    </script>
  </body>
</html>
```
- 12o
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function removeEgg(foods) {
        let eggsRemoved = 0;

        return foods.filter((food) => {
          // If the food is 'egg', we should return false
          // but only if we haven't removed 2 eggs already.
          if (food === 'egg' && eggsRemoved < 2) {
            eggsRemoved++;
            return false;
          }

          return true;
        });
      }

      console.log(removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']));
    </script>
  </body>
</html>
```
- 12p
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <!--
      This is the updated code for exercise 12c
      just as an example. Feel free, to update
      12d - 12i as well for more practice.
    -->
    <button class="js-button" onclick="
      updateButton();
    ">Start</button>

    <script>
      function updateButton() {
        const button = document.querySelector('.js-button');

        // The function below was changed
        // to an arrow function.
        setTimeout(() => {
          button.innerHTML = 'Finished!';
        }, 1000);
      }
    </script>
  </body>
</html>
```
- 12q
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <!--
      This is the updated code for exercise 12c
      just as an example. Feel free, to update
      12d - 12i as well for more practice.
    -->
    <button class="js-button">Start</button>

    <script>
      document.querySelector('.js-button')
        .addEventListener('click', () => {
          const button = document.querySelector('.js-button');

          // The function below was changed
          // to an arrow function.
          setTimeout(() => {
            button.innerHTML = 'Finished!';
          }, 1000);
        });
    </script>
  </body>
</html>
```
- 12r html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
    <link rel="stylesheet" href="12r.css">
  </head>
  <body>
    <p class="title">Rock Paper Scissors</p>
    <button class="move-button js-rock-button">
      <img src="images/rock-emoji.png" class="move-icon">
    </button>

    <button class="move-button js-paper-button">
      <img src="images/paper-emoji.png" class="move-icon">
    </button>

    <button class="move-button js-scissors-button">
      <img src="images/scissors-emoji.png" class="move-icon">
    </button>

    <p class="js-result result"></p>
    <p class="js-moves"></p>
    <p class="js-score score"></p>

    <!-- Solution for exercise 12v. -->
    <button class="reset-score-button js-reset-score-button">
      Reset Score
    </button>

    <!-- Solution for exercise 12s. -->
    <button class="auto-play-button js-auto-play-button">
      Auto Play
    </button>

    <!-- Solution for exercise 12x. -->
    <p class="js-reset-confirmation"></p>
    
    <script src="12r.js"></script>
  </body>
</html>

```
- 12r css
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

.reset-score-button,
.auto-play-button,
/* Solution for exercise 12x. */
.reset-confirm-button {
  background-color: white;
  border: none;
  font-size: 15px;
  padding: 8px 15px;
  cursor: pointer;
}

/* Solution for exercise 12x. */
.reset-confirm-button {
  margin-left: 10px;
}
```
- 12r js
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

let isAutoPlaying = false;
let intervalId;

//const autoPlay = () => {

//};
function autoPlay() {
  if (!isAutoPlaying) {
    intervalId = setInterval(() => {
      const playerMove = pickComputerMove();
      playGame(playerMove);
    }, 1000);
    isAutoPlaying = true;
    
    // Solution for 12t.
    document.querySelector('.js-auto-play-button')
      .innerHTML = 'Stop Playing';

  } else {
    clearInterval(intervalId);
    isAutoPlaying = false;

    // Solution for 12t.
    document.querySelector('.js-auto-play-button')
      .innerHTML = 'Auto Play';
  }
}

// Solution for exercise 12s.
document.querySelector('.js-auto-play-button')
  .addEventListener('click', () => {
    autoPlay();
  });

document.querySelector('.js-rock-button')
  .addEventListener('click', () => {
    playGame('rock');
  });

document.querySelector('.js-paper-button')
  .addEventListener('click', () => {
    playGame('paper');
  });

document.querySelector('.js-scissors-button')
  .addEventListener('click', () => {
    playGame('scissors');
  });

  document.body.addEventListener('keydown', (event) => {
    if (event.key === 'r') {
      playGame('rock');
    } else if (event.key === 'p') {
      playGame('paper');
    } else if (event.key === 's') {
      playGame('scissors');
    
    // Solution for 12u.
    } else if (event.key === 'a') {
      autoPlay();
    
    // Solution for 12w.
    } else if (event.key === 'Backspace') {
      // Solution for 12w.
      // resetScore();

      // Solution for 12x.
      showResetConfirmation();
    }
  });

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

// Solution for 12v.
function resetScore() {
  score.wins = 0;
  score.losses = 0;
  score.ties = 0;
  localStorage.removeItem('score');
  updateScoreElement();
}

// Solution for 12v.
document.querySelector('.js-reset-score-button')
  .addEventListener('click', () => {
    // Solution for 12v.
    // resetScore();

    // Solution for 12x.
    showResetConfirmation();
  });

// Solution for 12x.
function showResetConfirmation() {
  document.querySelector('.js-reset-confirmation')
    .innerHTML = `
      Are you sure you want to reset the score?
      <button class="js-reset-confirm-yes reset-confirm-button">
        Yes
      </button>
      <button class="js-reset-confirm-no reset-confirm-button">
        No
      </button>
    `;
  
  document.querySelector('.js-reset-confirm-yes')
    .addEventListener('click', () => {
      resetScore();
      hideResetConfirmation();
    });
  
  document.querySelector('.js-reset-confirm-no')
    .addEventListener('click', () => {
      hideResetConfirmation();
    });
}

function hideResetConfirmation() {
  document.querySelector('.js-reset-confirmation')
    .innerHTML = '';
}
```
- 12s html
```html
<!--
  Remove onclick="" from the Auto Play button.
  And add class="js-auto-play-button" so we can
  select it in JavaScript and use .addEventListener()
  See 12r.html for the full code.
-->
<button class="auto-play-button js-auto-play-button">
  Auto Play
</button>
```
- 12s css
```
```
- 12s js
```js
/*
  Get the auto play button using the DOM and
  use .addEventListener()
  See 12r.js for the full code.
*/
document.querySelector('.js-auto-play-button')
  .addEventListener('click', () => {
    autoPlay();
  });
```
- 12t js
```js
// See 12r.js for the full code.
function autoPlay() {
  if (!isAutoPlaying) {
    intervalId = setInterval(() => {
      const playerMove = pickComputerMove();
      playGame(playerMove);
    }, 1000);
    isAutoPlaying = true;
    
    // When the game is auto playing, change
    // the text in the button to 'Stop Playing'.
    document.querySelector('.js-auto-play-button')
      .innerHTML = 'Stop Playing';

  } else {
    clearInterval(intervalId);
    isAutoPlaying = false;

    // When the game is not playing, change
    // the text back to 'Auto Play'.
    document.querySelector('.js-auto-play-button')
      .innerHTML = 'Auto Play';
  }
}
```
- 12u js
```js
// See 12r.js for the full code.
document.body.addEventListener('keydown', (event) => {
  if (event.key === 'r') {
    playGame('rock');
  } else if (event.key === 'p') {
    playGame('paper');
  } else if (event.key === 's') {
    playGame('scissors');
  
  // Add an if-statement condition to
  // check if 'a' was pressed.
  } else if (event.key === 'a') {
    autoPlay();
  }
});
```
- 12v html
```html
<!--
  Remove onclick="" from the Reset Score button
  and use .addEventListener instead.
  See 12r.html for the full code.
-->
<button class="reset-score-button js-reset-score-button">
  Reset Score
</button>
```
- 12v js
```js
// Create a new resetScore function so
// we can reuse this code.
// See 12r.js for the full code.
function resetScore() {
  score.wins = 0;
  score.losses = 0;
  score.ties = 0;
  localStorage.removeItem('score');
  updateScoreElement();
}

// Add an event listener for the reset score
// button using .addEventListener
document.querySelector('.js-reset-score-button')
  .addEventListener('click', () => {
    resetScore();
  });
```
- 12w js
```js
// See 12r.js for the full code.
document.body.addEventListener('keydown', (event) => {
  if (event.key === 'r') {
    playGame('rock');
  } else if (event.key === 'p') {
    playGame('paper');
  } else if (event.key === 's') {
    playGame('scissors');
  } else if (event.key === 'a') {
    autoPlay();
  
  // Add an if-statement condition to
  // check if 'Backspace' was pressed.
  } else if (event.key === 'Backspace') {
    resetScore();
  }
});
```
- 12x html
```html
<!--
  Add an element for displaying the
  confirmation message.
  See 12r.html for the full code.
-->
<p class="js-reset-confirmation"></p>
```
- 12x css
```css
/* See 12r.css for the full code. */
.reset-score-button,
.auto-play-button,
/*
  Reuse the style for the reset-score-button
  by using a comma in the selector.
*/
.reset-confirm-button {
  background-color: white;
  border: none;
  font-size: 15px;
  padding: 8px 15px;
  cursor: pointer;
}

/*
  Add extra margin to the confirm buttons.
  In CSS, we can add multiple sets of styles
  to the same class. Styles written later
  will override styles written before.
*/
.reset-confirm-button {
  margin-left: 10px;
}
```
- 12x js
```js
// Below are 3 parts that need to be
// changed in the JavaScript code for
// this exercise.
// See 12r.js for the full code.
document.body.addEventListener('keydown', (event) => {
  if (event.key === 'r') {
    playGame('rock');
  } else if (event.key === 'p') {
    playGame('paper');
  } else if (event.key === 's') {
    playGame('scissors');
  } else if (event.key === 'a') {
    autoPlay();

  } else if (event.key === 'Backspace') {
    // Update 'Backspace' to show the
    // confirmation message instead of
    // resetting the score immediately.
    showResetConfirmation();
  }
});

document.querySelector('.js-reset-score-button')
  .addEventListener('click', () => {
    // Update the click event listener to
    // show the confirmation message instead
    // of restting the score immediately.
    showResetConfirmation();
  });

// Function for showing the confirmation message.
function showResetConfirmation() {
  document.querySelector('.js-reset-confirmation')
    .innerHTML = `
      Are you sure you want to reset the score?
      <button class="js-reset-confirm-yes reset-confirm-button">
        Yes
      </button>
      <button class="js-reset-confirm-no reset-confirm-button">
        No
      </button>
    `;
  
  // You could use onclick="..." in the HTML above,
  // but it's recommended to use .addEventListener()
  document.querySelector('.js-reset-confirm-yes')
    .addEventListener('click', () => {
      resetScore();
      hideResetConfirmation();
    });
  
  document.querySelector('.js-reset-confirm-no')
    .addEventListener('click', () => {
      hideResetConfirmation();
    });
}

// A helper function (it helps us reuse the
// code for hiding the confirmation message).
function hideResetConfirmation() {
  document.querySelector('.js-reset-confirmation')
    .innerHTML = '';
}
```
