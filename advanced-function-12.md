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
- 
```
```
