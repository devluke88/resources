# Example Snippets

## Shopping list

```
// Code created as a part of exercise in:
// https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents#active_learning_a_dynamic_shopping_list

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shopping list example</title>
    <style>
      li {
        margin-bottom: 10px;
      }

      li button {
        font-size: 8px;
        margin-left: 20px;
        color: #666;
      }
    </style>
  </head>
  <body>

    <h1>My shopping list</h1>

    <div>
      <label for="item">Enter a new item:</label>
      <input type="text" name="item" id="item">
      <button>Add item</button>
    </div>
    
    <ul>

    </ul>

    <script>
			const list = document.querySelector('ul');
      const inp = document.querySelector('input');
      const but = document.querySelector('button');

      but.onclick = function() {
        let currentInput = inp.value;	
        inp.value = '';
        
        const listItem = document.createElement('li');
        const listText = document.createElement('span');
      	const deleteButton = document.createElement('button');
        listItem.appendChild(listText);
        listText.textContent = currentInput
      	listItem.appendChild(deleteButton);
        deleteButton.textContent = 'Delete';
        if (currentInput !== '') {
        	list.appendChild(listItem);
        }
        else {
        	alert("Item cannot be empty!");
        }
        
        
        deleteButton.onclick = function(event) {
        	list.removeChild(listItem)
        }
        inp.focus();
      }
      
    </script>
  </body>
</html>
```
