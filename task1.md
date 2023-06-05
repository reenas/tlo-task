In this lesson, we will use JavaScript Closures to create a simple Todo manager. A Todo manager is a tool that helps us keep track of our tasks and mark them as completed.

To do this, we will follow these steps:

We will create a function called todoList that will act as the parent function in the context of closure. This function will have an array called all that will store all the todos as objects. Each todo object will have three properties: title, dueDate, and completed (a boolean value).
Inside the todoList function, we will define two child functions: add and markAsComplete. The add function will take a todo object as an argument and push it into the all array. The markAsComplete function will take an index as an argument and update the completed property of the todo object at that index in the all array.
Finally, we will return the all array and the add and markAsComplete functions from the todoList function.
We will use the Node.js REPL to test our code. To enter the REPL mode, open the terminal and run the node command.

Let’s start coding.

First, we will define the todoList function and the all array.

const todoList = () => { all = []; // rest of the code }

Next, we will define the add function inside the todoList function.

const todoList = () => { all = []; const add = (todoTask) => { all.push(todoTask); console.log(all); }; // rest of the code }

The add function takes a todoTask object as an argument and adds it to the all array. It also prints the all array to the console.

Then, we will define the markAsComplete function inside the todoList function.

const todoList = () => { all = []; const add = (todoTask) => { all.push(todoTask); console.log(all); }; const markAsComplete = (index) => { all[index].completed = true; console.log(all); }; // rest of the code }

The markAsComplete function takes an index as an argument and changes the completed property of the todo object at that index in the all array to true. It also prints the all array to the console.

To finish the todoList function, we will return the all array and the add and markAsComplete functions from it.

const todoList = () => { all = []; const add = (todoTask) => { all.push(todoTask); console.log(all); }; const markAsComplete = (index) => { all[index].completed = true; console.log(all); }; return { all, add, markAsComplete }; };

Let’s test our code. First, we will call the todoList function and assign it to a variable called todos.

const todos = todoList();

Now, we can access the list of all todos by using todos.all.

todos.all; []; // It will return an empty array

To add a new todo, we can use todos.add and pass a todo object as an argument.

todos.add({ title: ‘I need to go to gym’, dueDate: ‘22-06-2022’, completed: false }); [{ title: ‘I need to go to gym’, dueDate: ‘22-06-2022’, completed: false }]; // Output

todos.add({ title: ‘Have to buy potato’, dueDate: ‘22-06-2022’, completed: false }); [{ title: ‘I need to go to gym’, dueDate: ‘22-06-2022’, completed: false }, { title: ‘Have to buy potato’, dueDate: ‘22-06-2022’, completed: false }]; // Output

todos.all; [{ title: ‘I need to go to gym’, dueDate: ‘22-06-2022’, completed: false }, { title: ‘Have to buy potato’, dueDate: ‘22-06-2022’, completed: false }]; // Output

To mark a todo as complete, we can use todos.markAsComplete and pass an index as an argument.

todos.markAsComplete(1); // Here 1 is the array index [{ title: ‘I need to go to gym’, dueDate: ‘22-06-2022’, completed: false }, { title: ‘Have to buy potato’, dueDate: ‘22-06-2022’, completed: true }]; // Output

It works!

As we have learned before, in this example, the add and markAsComplete functions have preserved (closure) the variable all when the todoList function was executed, and continued to access and update it.
