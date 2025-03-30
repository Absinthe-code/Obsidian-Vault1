Ecmascript
web assembly
noje js
Scripting
Interpreted
js engine or V8
Jit
Script tag
let 
camelcase
7 primitive data types
undefined value is standard
null
semicolons added  automatiaclli
const doesn't change value
global scope
local scope
block scope
var is hoisted
functions
return values
functions are just objects
function sxpression
higher order function
nested function
closures
call stack = ram?
heap memory = persistent between function calls
this = references a function depending on where is called
called from the global scope it references the window object in the browser
if attached to an object and called by the object it's a reference to the object
Bind method
Arrow function anonymous?
when passing arguments a primitive is passed by value, so i's copied
if the argument is an object it's called by reference so it's not a copy and it's stored in the heap memory
Object literan
object constructors
key value-pairs or proprieries
objects can inherit proprierties from each other with the prototype chain
different from class based inheritance, we are workin with real objects and not abstract classes
OOP
classes exists but they are just ojects and work with prototype inheritance
	they have a constructor which is just a function that is called when the object is created
	thei can fave proprierties and getter and setter to access them
	they more easly incapsulate functions by organizing them as methods on an objects instance
	or make them global with the class name by making them static (static mathod)
Built in data structures
	Arrays
	Sets hold a collection of unique ekements
	Maps hold key value pairs but cal be more esely looped over, all the proprierties will always be referenced and memory does not free
	Weakmap and weakset have proprierties that can be garbage collected 
	
Garbagr collection

Non blocking event loop
	when you write code in a scipt it's executed synchronously line by line
	with an event loop we can write asyncronous code that runs in aseparate thread pool while the rest of the applocation continue to execute
	modern webites have multiple things going on at the same time but they only have access to a single thread for computing called the main thread, without asyncronous code it would be impossible to miltitask
exampe setTimeout which talkes a function as an argument but wont actually call the function until x number of milliseconds have elapsed
It's called a callback function because it's called back later

Promise is a wrapper for a value that is unlnown right now that will resolve to a value in the future or reject to an error

the consumer of the promise can use methods like then and catch

Async functions automaticaly return a promise, in the body of the function we can pause its execution using the await keyword

in order to prevent error handling you should wrap this code in a try catch block 

Modules, by default all the code in a file (or module) is private to that file, however if we want to use that code elsewhere we can use export default, so that in another file we can use import statement to use the function there

its also possible to export multiple variables from a single file and then import them by name in another file

npm = node package manager
basically lets you use code from another developer

it installs the packages in the node_modules folder and provides the package.json file that lists all of the dependencies of your project

on the web the code will run in the browser which is based on the Document Object model where the UI is rapresented as a tree of HTML elements or nodes. the browser provides APIs to interact with these nodes, with the most important object being the document. 

the document allows us to grab individual HTML elements using amethod called query selector, it takes a CSS selector as an argument and will find the HTML element that has the same Name ID or Tag Name, it returns an instance of the elements class, which itself has a varaiety of proprierties and methods to get information about it or change its behaviour. we can access multiple elements at the same time using querySelectorAll 

addEventListener we can assign a function that will be called whenever that event takes place

most of web developement revolves around listening to events and updating the UI accordingly

However many developers dislike the fact that vanilla javascript is that it results in imperative code, where the UI is mutated directly, now many developes use frontend frameeworks that produce declarative code, where the UI is a function of its input data, these libraries encapsulate javascript HTML and CSS into components which are used toghether to form a component tree to represent the UI.

Most importantly inside a component, data is reactive, it can bound from the javascript directly into the HTML, anytime the data changes the UI will be updated automatically

After you have built your javascript app, all the components have to be combined into a single bundle that can be used by the browser to handle this process efficiently you'll need a tool called a module bundler, like veet or webpack.

somtimes the javascript is too big and it can cause performance issues, you can split the javascript into bunfle into multiple files then use dynamic imports in your code to only import thath javascript when it becomes needed

Javascript doesn't just run in the browser but also in the server. Node.js is the most popular runtime and you can execute javascript code at any time using the node command.

This opens the doors to framworls like electron, which combines node.js with a browser, to create full stack electron apps with javascript or ios and android apps with react native

Typescript and eslint to do static analisys to improve your code quality

























