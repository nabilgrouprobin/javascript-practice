## Arrays and Loops

- arrays and loops
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Arrays and Loops</title>
  </head>
  <body>
    <script>
      /*
      const myArray = [
        10, 
        20, 
        30
      ];
      console.log(myArray);

      console.log(myArray[1]);
      myArray[0] = 99;
      console.log(myArray);

      [1, 'hello', true, { name: 'socks' }, [1, 2]]

      console.log(typeof [1, 2]);
      console.log(Array.isArray([1, 2]));

      console.log(myArray.length);
      
      myArray.push(100);
      console.log(myArray);

      myArray.splice(0, 1);
      console.log(myArray);
      */

      /*
      let i = 1;

      while (i <= 5) {
        console.log(i);
        i++;
      }

      for (let i = 1; i <= 5; i++) {
        console.log(i);
      }

      let randomNumber = 0;

      while (randomNumber < 0.5) {
        randomNumber = Math.random();
      }

      console.log(randomNumber);
      */

      /*
      const todoList = [
        'make dinner',
        'wash dishes',
        'watch youtube'
      ];

      for (let i = 0; i < todoList.length; i++) {
        const value = todoList[index];
        console.log(value);
      }
      */

      /*
      const nums = [1, 1, 3];
      let total = 0;

      for (let i = 0; i < nums.length; i++) {
        const num = nums[i];
        total += num;
      }
      console.log(total);

      const numsDoubled = [];

      for (let i = 0; i < nums.length; i++) {
        const num = nums[i];
        numsDoubled.push(num * 2);
      }
      console.log(numsDoubled);
      */

      const array1 = [1, 2, 3];
      const array2 = array1.slice();
      array2.push(4);
      console.log(array1);
      console.log(array2);

      const [firstValue, secondValue] = [1, 2, 3];

      for (let i = 1; i <= 10; i++) {
        if (i % 3 === 0) {
          continue;
        }
        console.log(i);
        if (i === 8) {
          break;
        }
      }

      let i = 1;

      while (i <= 10) {
        if (i % 3 === 0) {
          i++;
          continue;
        }
        console.log(i);
        i++;
      }

      function doubleArray(nums) {
        const numsDoubled = [];

        for (let i = 0; i < nums.length; i++) {
          const num = nums[i];
          if (num === 0) {
            return numsDoubled;
          }
          numsDoubled.push(num * 2);
        }
        return numsDoubled;
      }
      console.log(doubleArray([1, 1, 3]));
      console.log(doubleArray([2, 2, 5, 0, 5]));
    </script>
  </body>
</html>

```
- todo list
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Todo List</title>
    <link rel="stylesheet" href="styles/11-todo-list.css">
  </head>
  <body>
    <p>Todo List</p>

    <div class="todo-input-grid">
      <input placeholder="Todo name"
        class="js-name-input name-input">
      <input type="date"
        class="js-due-date-input due-date-input">
      <button onclick="
        addTodo();
      " class="add-todo-button">Add</button>
    </div>

    <div class="js-todo-list todo-grid"></div>

    <script src="scripts/11-todo-list.js"></script>
  </body>
</html>
```
- todo list CSS

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

  for (let i = 0; i < todoList.length; i++) {
    const todoObject = todoList[i];
    //const name = todoObject.name;
    //const dueDate = todoObject.dueDate;
    const { name, dueDate } = todoObject;
    const html = `
      <div>${name}</div>
      <div>${dueDate}</div>
      <button onclick="
        todoList.splice(${i}, 1);
        renderTodoList();
      " class="delete-todo-button">Delete</button> 
    `;
    todoListHTML += html;
  }

  document.querySelector('.js-todo-list')
    .innerHTML = todoListHTML;
}

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
