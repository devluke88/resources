---
description: >-
  Source:
  https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/dom-manipulation-and-events
---

# DOM

**Create Element**

```
const div = document.createElement('div');
```

**Append Element**

```
append childNode as the last child of parentNode
parentNode.appendChild(childNode)

insert newNode into parentNode before referenceNode
parentNode.insertBefore(newNode, referenceNode)
```

**Remove Element**

```
Remove child from parentNode on the DOM and return a reference to child
parentNode.removeChild(child)    
```

**Inline Style**

```
const div = document.createElement('div');  
div.style.color = 'blue';                                      
// adds the indicated style rule

div.style.cssText = 'color: blue; background: white';          
// adds several style rules

div.setAttribute('style', 'color: blue; background: white');    
// adds several style rules

div.style.background-color // doesn't work - attempts to subtract color from div.style.background
div.style.backgroundColor // accesses the div's background-color style
div.style['background-color'] // also works
div.style.cssText = "background-color: white" // ok in a string
```

**Editing Attributes**

```
div.setAttribute('id', 'theDiv');                              
// if id exists, update it to 'theDiv', else create an id
// with value "theDiv"

div.getAttribute('id');                                        
// returns value of specified attribute, in this case
// "theDiv"

div.removeAttribute('id');                                     
// removes specified attribute

// set property
div.style.setProperty('background-color','red');

// get property
console.log(div.style.getPropertyValue('background-color'));

```

**Classes**

```
div.classList.add('new');                                      
// adds class "new" to your new div

div.classList.remove('new');                                   
// removes "new" class from div

div.classList.toggle('active');                                
// if div doesn't have class "active" then add it, or if
// it does, then remove it
```

**Text and HTML content**

```
div.textContent = 'Hello World!'                               
// creates a text node containing "Hello World!" and
// inserts it in div

div.innerHTML = '<span>Hello World!</span>';                   
// renders the HTML inside div
```

**Attaching listeners to groups of nodes**

```
<div id="container">
    <button id="1">Click Me</button>
    <button id="2">Click Me</button>
    <button id="3">Click Me</button>
</div>

// buttons is a node list. It looks and acts much like an array.
const buttons = document.querySelectorAll('button');

// we use the .forEach method to iterate through each button
buttons.forEach((button) => {

  // and for each one we add a 'click' listener
  button.addEventListener('click', () => {
    alert(button.id);
  });
});
Source: https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/dom-manipulation-and-events#events
```

### Dom - Notes

Notes made from JavaScript DOM Crash Course - Traversy Media, source:\
[https://youtu.be/0ik6X4DJKCc](https://youtu.be/0ik6X4DJKCc)

#### Starter Template

```
<!doctype html>
<html lang="en">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">

        <!-- Bootstrap CSS -->
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/css/bootstrap.min.css" integrity="sha384-zCbKRCUGaJDkqS1kPbPd7TveP5iyJE0EjAuZQTgFLD2ylzuqKfdKlfG/eSrtxUkn" crossorigin="anonymous">
        
        <title>Item Lister</title>
    </head>
    <body>
        <header id="main-header" class="bg-success text-white p-4 mb-3">
            <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <h1 id="header-title">Item Lister</h1>
                </div>
                <div class="col-md-6 align-self-center">
                    <input type="text" class="form-control" id="filter" placeholder="Search Items...">
                </div>
            </div>
            </div>
        </header>
        <div class="container">
            <div id="main" class="card card-body">
                <h2 class="title">Add Items</h2>
                <form id="addForm" class="form-inline mb-3">
                    <input type="text" class="form-control mr-2" id="item">
                    <input type="submit" class="btn btn-dark" value="Submit">
                </form>
                <h2 class="title">Items</h2>
                <ul id="items" class="list-group">
                    <li class="list-group-item">Item 1 <button class="btn btn-danger btn-sm float-right delete">X</button></li>
                    <li class="list-group-item">Item 2 <button class="btn btn-danger btn-sm float-right delete">X</button></li>
                    <li class="list-group-item">Item 3 <button class="btn btn-danger btn-sm float-right delete">X</button></li>
                    <li class="list-group-item">Item 4 <button class="btn btn-danger btn-sm float-right delete">X</button></li>
                </ul>
            </div>
        </div>

    <!-- jQuery and Bootstrap Bundle (includes Popper) -->
    <script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-fQybjgWLrvvRgtW6bFlB7jaZrFsaBXjsOMm/tB9LTS58ONXgqbR9W8oWht/amnpF" crossorigin="anonymous"></script>
    </body>
    <script src="main.js"></script>
</html>
```

### Part 1

#### 1. Examine the document object

```
// 1. EXAMINE THE DOCUMENT OBJECT
console.dir(document); print out all elements - #document
console.dir(document.domain); // 127.0.0.1
console.dir(document.URL); // http://127.0.0.1:5500/index.html?
console.dir(document.title); // Item Lister
document.doctype; //<!DOCTYPE html>
document.head; // <head>...</head>
document.body; // <body>...</body>
document.all; // HTMLCollection of all things in dom, e.g [html, head, meta, ..., body]
document.forms; // HTMLCollection of all forms
document.links; // HTMLCollection of all links
document.images; // HTMLCollection of all images

// Change element accessing document
document.title = 123 // 123

```

#### 2. Get Element by ID

```
var headerTitle = document.getElementById('header-title'); // <h1 id="header-title">Item Lister</h1>

// Change element text
headerTitle.textContent = 'Hello'; // Change the element text, doesn't care about styling returns 'Hello'
headerTitle.innerText = 'Goodbye'; // Change the element text, take styling into consideration, returns 'Goodbye'
headerTitle.innerHTML = '<h3>Hello</h3>'; Put html element inside the selected element, <h1 id="header-title"><h3>Hello</h3></h1>

// Change element style
headerTitle.style.borderBottom = '1px solid blue'; // This allows you to choose any CSS property, but you need to use camel case, for example background-color is backgrounColor

```

#### 3. Get Element by Class

```
var items = document.getElementsByClassName('list-group-item');
console.log(items); // Returns HTMLCollection, elements with indices, e.g. [li.list-group-item, li.list-group-item, ...]
items[1].textCOntent = 'Hello 2'; // access second item in HTMLCollection and change the text
items[1].style.fontWeight = 'bold'; // change style
items[1].style.backgroundColor = 'yellow'; // change style

// Change the style of all elements in the list
for (var i = 0; i < items.length; i++) {
    items[i].style.backgroundColor = 'red';
}

```

#### 4. Query Selector

```
var header = document.querySelector('#main-header'); // get the header with id main-header
header.style.borderBottom = '2px solid green';

// Get the input element
var input = document.querySelector('input');
input.value = 'Hello World'; // this will populate the value for selected input

// Get the input by it's type
var submit = document.querySelector('input[type="submit"]');
submit.value = "SEND"; // Change the button to SEND

// Get element using class (first li)
var item = document.querySelector('.list-group-item'); // this will get first element from ul list (first li)
item.style.color = 'red'; 

// Get last li element from the list
var lastItem = document.querySelector('.list-group-item:last-child');

// Get nth child li
var secondItem = document.querySelector('.list-group-item:nth-child(2)'); // Use css sudo selectors

```

#### 5.  Query Selector All

```
var titles = document.querySelectorAll('.title');
console.log(titles) // This will return: NodeList(2) [h2.title, h2.title] ; similar to HTMLCollection, but will allow to run array functions
titles[0].textContent = 'Hello'; // Access the first element from the node list and add text 'Hello'

// Use odd elements
var odd = document.querySelectorAll('li:nth-child(odd)');
var even = document.querySelectorAll('li:nth-child(even)');

// You can now edit all odd and even elements with for loop
for (car i = 0; i < odd.length; i++) {
    odd[i].style.backgroundColor = '#f4f4f4';
    even[i].style.backgroundColor = '#ccc';
}

```

### Part 2

#### 1. Traversing the DOM

```
var itemList = document.querySelector('#items'); // <ul id="items" class="list-group">…</ul>flex

// parentNode property
itemList.parentNode; // Returns parent element: <div id="main" class="card card-body">…<ul>..<ul></div>flex
itemList.parentNode.style.backgroundColor = '#f4f4f4'; // This will change the parent node
itemList.parentNode.parenNode; // This will give us the parent node of the parent node of the ul, we can move up in hierarchy like that

// parentElement property - can be used intechangeable with parentNode
itemList.parentElement; // Returns parent element: <div id="main" class="card card-body">…<ul>..<ul></div>flex
itemList.parentElement.style.backgroundColor = '#f4f4f4'; // This will change the parent node
itemList.parentElement.parentElement; // This will give us the parent element of the parent node of the ul, we can move up in hierarchy like that

// childNodes property - includes also text node (whitespace, line brakes etc.)
itemList.childNodes; // This will return NodeList(9) [text, li.list-group-item,...]

// children property - does not include white space text etc., only actual elements
itemList.children; returns HTMLCollection(4) [li.list-group-item, ...]
itemList.children[1]; // get second element from the collection
itemList.children[1].style.backgroundColor = 'yellow'; // change background-color property on the second element

// firstChild property
itemList.firstChild; // returns first item but it might be text (whitespace), like with childNodes property

// firstElementChild property
itemList.firstElementChild; // Returns first child: <li class="list-group-item">…</li>

// lastChild property
itemList.lastChild

// lastElementChild property
itemList.lastElementChild.textContent = 'Hello';

// nextSibling property
itemList.nextSibling;

// nextElementSibling property
itemList.nextElementSibling;

// previousSibling property
itemList.previousSibling;

// previousElementSibling property
itemList.previousElementSibling;

```

#### 2. Create Element

```
// Create a div
var newDiv = document.createElement('div');

// Add class
newDiv.className = 'hello'; // <div class="hello"></div>

// Add ID
newDiv.id = 'hello1'; // <div class="hello" id="hello1"></div>

// Add attribute
newDiv.setAtrribute('title', 'Hello Div'); // <div class="hello" id="hello1" title="Hello Div"></div>

// Create text node
var newDivText = document.createTextNode('Hello World');

// Add text to div
newDiv.appendChild(newDivText); // <div class="hello" id="hello1" title="Hello Div">Hello World</div>

// Add created element to the DOM, get the hedaer container first
var container = document.querySelector('header .container');
var h1 = document.querySelector('header h1');
// Insert new element (newDiv) to container before h1
container.insertBefore(newDiv, h1); // 

```

### Part 3

#### 1. Events

```
var button = document.getElementbyId('button');
button.addEventListener('click', function () {
    // some function code
    console.log('Test');
});

// Use named function
button.addEventListener('click', buttonClicked);

// named function
function buttonClicked () {
    document.getElementById('header-title').textContent = 'Hello';
    document.querySelector('#main').style.backgroundColor = '#f4f4f4';
};

// named function with event passed as parameter
function buttonClicked(e) {
    e.target; // Returns element that was clicked
    e.target.id; // Returns id of the element
    e.target.className;
    e.target.classList; // Returns DomTokenList array, so list of all classes
    var output = document.getElementById('output');
    output.innerHTML = `<h3>${e.target.id}</h3>`;
    e.type; // returns type of the event, e.g. click, input, submit etc.
    e.clientX; // returns position of the mouse on the X axis from the browser window
    e.clientY; // returns position of the mouse on the Y axis from the browser window
}



```
