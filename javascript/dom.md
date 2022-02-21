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
