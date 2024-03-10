# Calculator_Project_Js
It containing some beginner level Javascript Programs.
This code creates a simple calculator functionality on a webpage. Let's break down line by line:

let input = document.getElementById('inputBox');

This line fetches an element from the HTML document using its id attribute.
It assumes there's an element with the id inputBox. This element is likely an <input> element that will display the calculator output.
The line stores that element in a variable named input.
let buttons = document.querySelectorAll('button');

This line selects all <button> elements on the webpage and stores them in a variable named buttons.
querySelectorAll is a function used to find multiple elements matching a CSS selector.
let string = "";

This line declares a variable named string and initializes it with an empty string.
This variable will be used to store the current expression entered by the user in the calculator.
let arr = Array.from(buttons);

This line converts the buttons variable (which likely holds a list-like object) into a proper JavaScript array using the Array.from method.
This is done because JavaScript arrays offer more functionality for iterating through elements.
The converted array is stored in the variable arr.
arr.forEach(button => { ... })

This line iterates through each button element in the arr array using a forEach loop.
The loop takes a function as an argument, and this function receives a single argument named button which represents the current button element being processed.
Inside the loop (button.addEventListener('click', (e) => { ... })):

This line attaches a click event listener to each button element.
The event listener is a function that will be executed whenever the user clicks on a button.
The function receives an event object (e) as an argument, which contains information about the click event.
Inside the event listener function:

The code checks the innerHTML (the text content) of the clicked button using e.target.innerHTML.

Based on the button text, different actions are performed:

if(e.target.innerHTML == '=') : This checks if the button clicked is labeled with =.

If yes, it evaluates the expression stored in the string variable using the eval function.
Note: Using eval can be dangerous as it can execute arbitrary code. It's generally recommended to avoid using eval for security reasons. There are safer alternatives for evaluating expressions.
The result of the evaluation is then stored back in the string variable.
Finally, the updated string (which now holds the result) is displayed in the input box using input.value = string;.
else if(e.target.innerHTML == 'AC'): This checks if the button clicked is labeled with AC (likely representing All Clear).

If yes, it simply resets the string variable to an empty string, effectively clearing the calculator display.
The cleared string is then displayed in the input box.
else if(e.target.innerHTML == 'DEL'): This checks if the button clicked is labeled with DEL (likely representing Delete).

If yes, it removes the last character from the string variable using the substring method.
The updated string (with the last character removed) is then displayed in the input box.
else: This block executes if none of the above conditions are met (i.e., the button clicked is a number or operator).

In this case, it simply appends the button's innerHTML (the digit or operator) to the string variable.
The updated string (with the new character appended) is then displayed in the input box.
