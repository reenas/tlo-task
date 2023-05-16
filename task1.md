Let's create a simple Todo manager and apply our learning of Javascript closures

The plan is:

We will start by creating a parent(in context of closure) function named as 'todoList'.
Now, inside todoList, we will define two child functions, 'add' to add a new task and 'markAsComplete' to mark the completed task.
And in the end, we will make sure that the todoList function returns the list of all todos along with the add and markAsComplete function.
The implementation
In this lesson, we will make use of the Node.js REPL. Open the terminal and run with the node command to go inside the REPL mode.

So, let's get coding!

First, we will define the todoList function.

const todoList = () =>
all = []
Here, we will define an array 'all' to store the todo tasks. And inside the 'all' array, we will store Todos as an object having three properties: title, dueDate, completed (of type boolean). For ex. { title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }

Next, let's define the add() function.

const todoList = () => {
all = []
const add = (todoTask) => {
all.push(todoTask)
console.log(`Added todo: ${todo}`))
}
The add() function takes a todoTask as argument which symbolises the task to be added, and pushes into the 'all' array and console log the task that is being added.

Similarly, we will define the markAsComplete() function.

const todoList = () => {
all = []
const add = (todoTask) => {
all.push(todoTask)
console.log(all)
}
const markAsComplete = (index) => {
all[index].completed = true
console.log(all)
}
Here, the markAsComplete() function takes an argument called index. It will mark the task as completed based on the specified index and updates the 'all' array.
To complete the todoList function, we will return the all array and add, markAsComplete functions.

const todoList = () => {
all = []
const add = (todoTask) => {
all.push(todoTask)
console.log(all)
}
const markAsComplete = (index) => {
all[index].completed = true
console.log(all)
}
return { all, add, markAsComplete };
}
Now it's time to test our code
First, in the terminal, we will call the todoList() function.

> const todos = todoList()
> Now, you will be able to see the list of all todos by:

> todos.all
> [] // It will return an empty array beacause we have not specified any todo task
> To add a new Todo we will call the add function:

> todos.add({ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }] // Output
> todos.add({ title: 'Have to buy potato', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> 
> todos.all//this will return the all specified todo tasks
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> To mark a Todo as complete

> todos.markAsComplete(1) // Here 1 is the array index
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: true }] // Output
> Yay! you have done it.

so, in this example, we have seen the todolist fuction is showing the practical implementation of javascript closures.
