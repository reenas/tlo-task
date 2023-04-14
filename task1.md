In this lesson, we will apply our knowledge of JavaScript Closures, to create a simple Todo manager.

The plan is:

We will create a parent(in context of closure) todoList function.
The todos array is stored in a closure and can only be accessed and modified through these methods.
Each todo is represented as an object with a title property and a completed property, which indicates whether the todo is complete or not.

The implementation
In this lesson, we will make use of the Node.js REPL. Open the terminal and run with the node command to go inside the REPL mode.

So, let's get started.

First, we will define the todoList function.

const todoList = () =>
all = []
Here, we will keep the list of all todos inside the all array. A Todo, would have three properties: title, dueDate, completed (of type boolean) The add method now takes two arguments: title and dueDate, which are used to create the new todo object. The completed property is initialized to false by default. For ex. { title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }

Next, let's define the add() function.
const todoList = () => {
  let all = [];

  return {
    add: function(title, dueDate) {
      all.push({
        title: title,
        dueDate: dueDate,
        completed: false
      });
    },
The add() function takes a todoTask as argument, and pushes into the all array.

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
The markAsComplete function takes a single argument index, which is used to access the todo object in the all array and set its completed property to true.

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
Let's test it out
First, in the terminal, we will call the todoList() function.

> const todos = todoList()
> Now, you will be able to see the list of all todos by:

> todos.all
> [] // It will return an empty array
> To add a new Todo:

> todos.add({ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }] // Output
> todos.add({ title: 'Have to buy potato', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> todos.all
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> To mark a Todo as complete

> todos.markAsComplete(1) // Here 1 is the array index
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: true }] // Output
> So, it's working!

As we've learned before, in this example, the two functions add and markAsComplete had preserved the legacy variable all when the todoList() function was executed, and continued to preserve (closure) it.
