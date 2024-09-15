## Arrays and Loops
- array = is another type of value
- array represents a list of values 
- array stores values and array is also a value
- we can also write an array in muliple line
- index = position in the array
- in array we can put any type of value like int float string boolean object array itself
- arrays have properties and method
- if an array doesn't have value then it id called empty array
- loops let us run code over and over
- loop body, loop variable, loop condition, increment/decrement step
- the loop is going for ever is called = infinite loop
- iteration = how many times we run the loop body
- loops create a scope
- standard loop  -->> use for loop  ||   for non-standard loop  -->> while loop
- accumulator pattern ==>> 1. create a variable to store the result  2. loop through the array and update the result
- inside HTML we can't set paragraph tag inside another paragraph tag
- difference between div and p is div doesn't have built in padding margin but p has
- div doesn't have default styling but paragraph has
- arrays and loops
- 1. save the data 2. generate the HTML 3.make it interactive
- by default align-items: stretch; but if mother class in center then it will automatically center
- we can group two or more values together by object or object inside an array
- stretch in align-items is align items vertically stretch
- arrays are references
- break = exit a loop early do does using = return
- break in a loop = return in a function = return also break the loop
- continue = skip 1 iteration
- in for loop using continue incremnet will do automatically but while loop we have to do it manually
- in the last of function body console.log(result) = return result; then console.log(funtionname())
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
      console.log(typeof myArray); //
       

      console.log(myArray[1]);
      myArray[0] = 99;
      console.log(myArray);

      [1, 'hello', true, { name: 'socks' }, [1, 2]]

      console.log(typeof [1, 2]); // object (special type of object)
      console.log(Array.isArray([1, 2])); //true

      console.log(myArray.length);
      
      myArray.push(100); // adds a value in the end of the array + it removes value from an array
      console.log(myArray);

      myArray.splice(0, 1); (index, number of value we want to remove)
      console.log(myArray);
      */

      /*
      let i = 1;

      while (i <= 5) {
        console.log(i);
        i++;
      }
      console.log(i);

      for (let i = 1; i <= 5; i++) {
        console.log(i);
      }

      let randomNumber = 0;

      while (randomNumber < 0.5) {
        randomNumber = Math.random();
      }

      console.log(randomNumber);
      */

      /* //  looping through an array
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

      /* // accumulator patern
      const nums = [1, 1, 3];
      let total = 0; // accumulator variable

      for (let i = 0; i < nums.length; i++) {
        const num = nums[i];
        total += num;
      }
      console.log(total);

      const numsDoubled = []; // accumulator variable can be an array

      for (let i = 0; i < nums.length; i++) {
        const num = nums[i];
        numsDoubled.push(num * 2);
      }
      console.log(numsDoubled);
      */

      const array1 = [1, 2, 3];
      // const array1 = array2
      // avoid the reference problem
      const array2 = array1.slice();
      array2.push(4);
      console.log(array1);
      console.log(array2);

      const array3 = [1, 2, 3]
      // Destructuring
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
          // in while loop we have to increment the variable before continue;
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
/* const todoList = ['make dinner', wash dishes,];
let todoListHTML = ``;
for(let i=0; i<todoList.length; i++){
const todo = todoList[i];
const html = `
<p>
  ${todo}
  <button onclick="
    todoList.splice(${i},1);
    renderTodoList();
  ">Delete</button>
</p>
`;
todoListHTML += html;
}
console.log(todoLlistHTML);
*/
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
    // const todo = todoList[i];
    const todoObject = todoList[i];
    //const name = todoObject.name;
    //const dueDate = todoObject.dueDate;
    // destructuring variable name == property name
    const { name, dueDate } = todoObject;
    /*
    const html = `
    <p>
      ${name} ${dueDate}
      <button onclick="
          todoList.splice(${i}, 1);
          renderTodoList();
      ">Delete</button>
    </p>
    `;
    */
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

  // console.log(todoListHTML)

  document.querySelector('.js-todo-list')
    .innerHTML = todoListHTML;
}

function addTodo() {
  const inputElement = document.querySelector('.js-name-input');
  const name = inputElement.value;

  const dateInputElement = document.querySelector('.js-due-date-input');
  const dueDate = dateInputElement.value;

  /*
  todoList.push(name);
  console.log(todoList);
  */

  todoList.push({
    //name: name,
    //dueDate: dueDate,
    //shorthand property  property = variable name
    name,
    dueDate
  });
  //console.log(todoList);

  inputElement.value = '';

  renderTodoList();
}
```
- exercise
- 11a
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const nums = [10, 20, 30];
      nums[2] = 99;
      console.log(nums);

      // An alternative solution is:
      // nums[nums.length - 1] = 99;
    </script>
  </body>
</html>
```
- 11b
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function getLastValue(array) {
        const lastIndex = array.length - 1;
        return array[lastIndex];
      }
      console.log(getLastValue([1, 20, 22, 24, 5]));
      console.log(getLastValue(['hi', 'hello', 'hey']));
    </script>
  </body>
</html>
```
- 11c
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function arraySwap(array) {
        const lastIndex = array.length - 1;

        // We need to save the values first before
        // swapping. Otherwise, if we swap directly,
        // we would lose one of the values.
        const lastValue = array[lastIndex];
        const firstValue = array[0];

        array[0] = lastValue;
        array[lastIndex] = firstValue;

        return array;
      }
      console.log(arraySwap([1, 20, 22, 24, 5]));
      console.log(arraySwap(['hi', 'hello', 'hey']));
    </script>
  </body>
</html>
```
- 11d
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      for (let i = 0; i <= 10; i += 2) {
        console.log(i);
      }
    </script>
  </body>
</html>
```
- 11e
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      for (let i = 5; i >= 0; i--) {
        console.log(i);
      }
    </script>
  </body>
</html>
```
- 11f
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      let i = 0;

      while (i <= 10) {
        console.log(i);
        i += 2;
      }

      i = 5;

      while (i >= 0) {
        console.log(i);
        i--;
      }
    </script>
  </body>
</html>
```
- 11g
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      const array = [1, 2, 3];
      const result = [];

      for (let i = 0; i < array.length; i++) {
        result.push(array[i] + 1);
      }

      console.log(result);
    </script>
  </body>
</html>
```
- 11h
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function addOne(array) {
        const result = [];

        for (let i = 0; i < array.length; i++) {
          result.push(array[i] + 1);
        }

        return result;
      }

      console.log(addOne([1, 2, 3]));
      console.log(addOne([-2, -1, 0, 99]));
    </script>
  </body>
</html>
```
- 11i
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function addNum(array, num) {
        const result = [];

        for (let i = 0; i < array.length; i++) {
          result.push(array[i] + num);
        }

        return result;
      }

      console.log(addNum([1, 2, 3], 2));
      console.log(addNum([1, 2, 3], 3));
      console.log(addNum([-2, -1, 0, 99], 2));
    </script>
  </body>
</html>
```
- 11j
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function addArrays(array1, array2) {
        const result = [];

        for (let i = 0; i < array1.length; i++) {
          result.push(array1[i] + array2[i]);
        }

        return result;
      }

      console.log(addArrays([1, 1, 2], [1, 1, 3]));
      console.log(addArrays([1, 2, 3], [4, 5, 6]));
    </script>
  </body>
</html>
```
- 11k
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function countPositive(nums) {
        let result = 0;

        for (let i = 0; i < nums.length; i++) {
          if (nums[i] > 0) {
            result++;
          }
        }

        return result;
      }

      console.log(countPositive([1, -3, 5]));
      console.log(countPositive([-2, 3, -5, 7, 10]));
    </script>
  </body>
</html>
```
- 11l
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function minMax(nums) {
        // We'll set the starting values of min and max
        // as the first value in the array. (This is
        // just one way to set the starting values. You
        // can use another way if you like.)
        const result = {
          min: nums[0],
          max: nums[0]
        };

        for (let i = 0; i < nums.length; i++) {
          const value = nums[i];

          // If the value is less than the min,
          // update the min.
          if (value < result.min) {
            result.min = value;
          }

          // If the value is greater than the max,
          // update the max.
          if (value > result.max) {
            result.max = value;
          }
        }

        return result;
      }

      console.log(minMax([1, -3, 5]));
      console.log(minMax([-2, 3, -5, 7, 10]));

    </script>
  </body>
</html>
```
- 11m
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function minMax(nums) {
        // We'll set the starting values of min and max
        // to null this time.
        const result = {
          min: null,
          max: null
        };

        for (let i = 0; i < nums.length; i++) {
          const value = nums[i];

          // If the min is null OR the value is
          // less than the min, update the min.
          if (result.min === null || value < result.min) {
            result.min = value;
          }

          // If the max is null OR the value is
          // greater than the max, update the max.
          if (result.max === null || value > result.max) {
            result.max = value;
          }

          // We have to use 2 if-statements above instead of
          // an if-else statement. This makes sure both the
          // min and max are set if they are null.
        }

        return result;
      }

      console.log(minMax([1, -3, 5]));
      console.log(minMax([-2, 3, -5, 7, 10]));

      console.log(minMax([]));
      console.log(minMax([3]));
    </script>
  </body>
</html>
```
- 11n
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function countWords(words) {
        const result = {};

        for (let i = 0; i < words.length; i++) {
          const word = words[i];

          // result[word] adds/accesses a property using whatever is
          // saved inside the 'word' variable.
          // If word = 'apple', result[word] will do result['apple']
          // If word = 'grape', result[word] will do result['grape']
          if (!result[word]) {
            result[word] = 1;
          } else {
            result[word]++;
          }
        }

        return result;
      }

      console.log(countWords(['apple', 'grape', 'apple', 'apple']));
    </script>
  </body>
</html>
```
- 11o
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      let words = ['hello', 'world', 'search', 'good'];

      // Set the index to -1 at the start (so we'll assume
      // the string 'search' doesn't exist in the array).
      // If we find the string 'search' in the array, we
      // will update the index.
      let index = -1;

      for (let i = 0; i < words.length; i++) {
        if (words[i] === 'search') {
          index = i;
        }
      }

      console.log(index);

      words = ['not', 'found'];
      index = -1;

      for (let i = 0; i < words.length; i++) {
        if (words[i] === 'search') {
          index = i;
        }
      }

      console.log(index);
    </script>
  </body>
</html>
```
- 11p
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      let words = ['hello', 'world', 'search', 'good', 'search'];
      let index = -1;

      for (let i = 0; i < words.length; i++) {
        if (words[i] === 'search') {
          index = i;
          // Once we find 'search', immediately exit
          // the loop since we want the index of the
          // first appearance of 'search'.
          break;
        }
      }

      console.log(index);

      words = ['not', 'found'];
      index = -1;

      for (let i = 0; i < words.length; i++) {
        if (words[i] === 'search') {
          index = i;
          break;
        }
      }

      console.log(index);
    </script>
  </body>
</html>
```
- 11q
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function findIndex(array, word) {
        for (let i = 0; i < array.length; i++) {
          if (array[i] === word) {
            // Instead of creating an accumulator
            // variable and updating it in the loop,
            // we can just return i directly, when
            // we find it since this is a function.
            return i;
          }
        }

        // If the function has not returned by now,
        // logically that means the word must not
        // exist in the array, so we'll return -1.
        return -1;
      }
    </script>
  </body>
</html>
```
- 11r
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function removeEgg(foods) {
        const result = [];

        for (let i = 0; i < foods.length; i++) {
          // If the string is 'egg', use continue to skip it.
          if (foods[i] === 'egg') {
            continue;
          }

          // We don't need to have an else here because
          // the only way to reach this code is if the 
          // if-statement above is false.
          result.push(foods[i]);
        }

        return result;
      }

      console.log(removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']));
    </script>
  </body>
</html>
```
- 11s
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function removeEgg(foods) {
        const result = [];
        let eggsRemoved = 0;

        for (let i = 0; i < foods.length; i++) {
          // Only skip 'egg' if we removed less than 2
          // of them so far.
          if (foods[i] === 'egg' && eggsRemoved < 2) {
            // Update the number of 'egg' we have removed.
            // This must be done before continue, otherwise,
            // doing continue first will just skip this code.
            eggsRemoved++;
            continue;
          }

          result.push(foods[i]);
        }

        return result;
      }

      console.log(removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']));
    </script>
  </body>
</html>
```
- 11t
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function removeEgg(foods) {
        // To remove the last 2 'egg', reverse the array first.
        const reversedFoods = foods.reverse();

        const result = [];
        let eggsRemoved = 0;

        for (let i = 0; i < reversedFoods.length; i++) {
          if (reversedFoods[i] === 'egg' && eggsRemoved < 2) {
            eggsRemoved++;
            continue;
          }

          result.push(reversedFoods[i]);
        }

        // At the end, remember to .reverse() back the result.
        return result.reverse();
      }

      console.log(removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']));
    </script>
  </body>
</html>
```
- 11u
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function removeEgg(foods) {
        // To prevent modifying the original array, we
        // can create a copy of the array using .slice()
        const foodsCopy = foods.slice();
        const reversedFoods = foodsCopy.reverse();

        // Advanced technique:
        // Since foods.slice() results in an array, we
        // can also use .reverse() directly like this:
        // foods.slice().reverse();
        
        // This technique is called "method chaining"
        // because we use one method after another
        // (like a chain of methods).
        const result = [];
        let eggsRemoved = 0;

        for (let i = 0; i < reversedFoods.length; i++) {
          if (reversedFoods[i] === 'egg' && eggsRemoved < 2) {
            eggsRemoved++;
            continue;
          }

          result.push(reversedFoods[i]);
        }

        return result.reverse();
      }

      const foods = ['egg', 'apple', 'egg', 'egg', 'ham'];
      console.log(removeEgg(foods));
      console.log(foods);
    </script>
  </body>
</html>
```
- 11v
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      for (let i = 1; i <= 20; i++) {
        // The trick to this problem is to check if
        // the number is divisible by 3 and 5 first.
        // Otherwise, it will always display 'Fizz'.
        if (i % 3 === 0 && i % 5 === 0) {
          console.log('FizzBuzz');

        } else if (i % 3 === 0) {
          console.log('Fizz');

        } else if (i % 5 === 0) {
          console.log('Buzz');
          
        } else {
          console.log(i);
        }
      }
    </script>
  </body>
</html>
```
- 11w
```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <script>
      function findIndex(array, word) {
        for (let i = 0; i < array.length; i++) {
          if (array[i] === word) {
            return i;
          }
        }

        return -1;
      }

      function unique(array) {
        const result = [];

        for (let i = 0; i < array.length; i++) {
          const word = array[i];

          // Using the findIndex() function from above, we
          // can check if the string is already in the
          // result array. If it's not in the result array
          // (index is -1), then add it to the result array.
          if (findIndex(result, word) === -1) {
            result.push(word);
          }
        }

        return result;
      }

      console.log(unique(['green', 'red', 'blue', 'red']));
      console.log(unique(['red', 'green', 'green', 'red']));
    </script>
  </body>
</html>
```
- 11x html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Todo List</title>
    <link rel="stylesheet" href="11x.css">
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

    <script src="11x.js"></script>
  </body>
</html>

```
- 11x css
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
- 11x js
```js
// When loading the page, load from localStorage.
const todoList = JSON.parse(localStorage.getItem('todoList')) || [{
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

        // Whenever we update the todo list, save in localStorage.
        saveToStorage();
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

  // Whenever we update the todo list, save in localStorage.
  saveToStorage();
}

function saveToStorage() {
  localStorage.setItem('todoList', JSON.stringify(todoList));
}
```
