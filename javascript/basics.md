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
```
