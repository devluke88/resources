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

Example 2

```
// https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Test_your_skills:_Loops

<html>
  <head>
    <meta charset="utf-8"/>
    <title>Loops: Task 2</title>
    <style>
      p {
        color: purple;
        margin: 0.5em 0;
      }

      * {
        box-sizing: border-box;
      }
    </style>
    <link rel="stylesheet" href="../styles.css" />
  </head>

  <body>

    <section class="preview">



    </section>

  </body>
  <script>
    const name = 'Francesca';
    const para = document.createElement('p');

    const phonebook = [
      { name : 'Chris', number : '1549' },
      { name : 'Li Kang', number : '9634' },
      { name : 'Anne', number : '9065' },
      { name : 'Francesca', number : '3001' },
      { name : 'Mustafa', number : '6888' },
      { name : 'Tina', number : '4312' },
      { name : 'Bert', number : '7780' },
      { name : 'Jada', number : '2282' },
    ]

    // Add your code here
    function search_number(name, para, phonebook) {
    	for (let i = 0; i < phonebook.length; i++) {
      	if (phonebook[i]["name"] === name) {
          const record = `Record found ${name}: ${phonebook[i]["number"]}.`;
          console.log(record);
         	return record;
        }
        else {
          console.log("Still searching");
          continue;
        }
        console.log(`Record for ${name} not found!`);
      }
      
		}
    para.textContent = search_number(name, para, phonebook);
    // Don't edit the code below here!
    const section = document.querySelector('section');
    section.appendChild(para);
  </script>

</html>


```

Example 3

```
// https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Test_your_skills:_Loops
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8"/>
    <title>Loops: Task 3</title>
    <style>
      p {
        color: purple;
        margin: 0.5em 0;
      }

      * {
        box-sizing: border-box;
      }
    </style>
    <link rel="stylesheet" href="../styles.css" />
  </head>

  <body>

    <section class="preview">



    </section>

  </body>
  <script>
    let i = 500;
    const para = document.createElement('p');

    function isPrime(num) {
      for(let i = 2; i < num; i++) {
        if(num % i === 0) {
          return false;
        }
      }

      return true;
    }


    // Add your code here
    
    while (i > 1) {
      // code to run
			if (isPrime(i) === true) {
      	para.textContent += `${i}; `;
      }
      i--;
	}

    // Don't edit the code below here!
    const section = document.querySelector('section');
    section.appendChild(para);
  </script>

</html>
```

```
// Objects
// https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript

function makePerson(first, last) {
  return {
    first: first,
    last: last,
    fullName: function() {
      return this.first + ' ' + this.last;
    },
    fullNameReversed: function() {
      return this.last + ', ' + this.first;
    }
  };
}

const s = makePerson('Simon', 'Willison');
s.fullName(); // "Simon Willison"
s.fullNameReversed(); // "Willison, Simon"

```
