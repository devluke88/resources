# Basics

## If...else

```
if (condition) {
  code to run if condition is true;
} else if (condition 2) {
  code to run if condition is true;
} else {
  run some other code instead;
}

# Ternary operator - https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals#ternary_operator
( condition ) ? run this code : run this code instead
let greeting = ( isBirthday ) ? 'Happy birthday Mrs. Smith — we hope you have a great day!' : 'Good morning Mrs. Smith.';
```

## Switch

```
# Source: https://www.digitalocean.com/community/tutorials/how-to-use-the-switch-statement-in-javascript

# Example 1

switch (expression) {
    case x:
        // execute case x code block
        break;
    case y:
        // execute case y code block
        break;
    default:
        // execute default code block
}

# Example 2
// Set the student's grade
const grade = 87;

switch (true) {
    // If score is 90 or greater
    case grade >= 90:
        console.log("A");
        break;
    // If score is 80 or greater
    case grade >= 80:
        console.log("B");
        break;
    // If score is 70 or greater
    case grade >= 70:
        console.log("C");
        break;
    // If score is 60 or greater
    case grade >= 60:
        console.log("D");
        break;
    // Anything 59 or below is failing
    default:
        console.log("F");
}
```

## Function

```
// Multiplication function
function multiply(n1, n2) {
  return n1 * n2;
}

# Examples
<script>
    
      function add7(n) {
        return n + 7;
      }

      function multiply(n1, n2) {
        return parseInt(n1) * parseInt(n2);
      }

      function capitalize(string) {
        let result = string.toLowerCase();
        return result.charAt(0).toUpperCase() + result.slice(1);
      }

      function lastLetter(string) {
        return string.slice(-1);
      }
    
  </script>
```

## Arrow function

```
// Example 1
let func = (arg1, arg2, ..., argN) => expression;

let func = function(arg1, arg2, ..., argN) {
  return expression;
};

# Example 2
let sum = (a, b) => a + b;

# Example 3
let sayHi = () => alert("Hello!");

sayHi();

# Example 4 
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  () => alert('Hello') :
  () => alert("Greetings!");

welcome();

# Source: https://javascript.info/arrow-functions-basics
```

## Loops

```
// for...of
for (const item of array) {
  // code to run
}

// for
for (initializer; condition; final-expression) {
  // code to run
}

// while
initializer
while (condition) {
  // code to run

  final-expression
}

// do...while
initializer
do {
  // code to run

  final-expression
} while (condition)

Source: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code#which_loop_type_should_you_use
```
