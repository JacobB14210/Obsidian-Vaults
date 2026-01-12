# How to run Javascript
- Can be used as external script file using script tag in HTML
- Running it in the browser console
- REPL
## Script Tag
### Inline Script in the Head
- Mainly used if the script does not need to directly interact with element on the page
	- Since the body is created when the script is created it won't recognize any element in the body on startup
	- Ideal for setting up functions and variables
```html
<!DOCTYPE html>
<html lang="en-US">
 
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Today's Date</title>
    <script>
        let d = new Date();
        alert("Today's date is " + d);
    </script>
</head>
 
<body>
</body>
 
</html>
```

### Inline Script in the Body
- HTML parser will pause work and execute the script at the exact point it is shown
	- Used for methods that need to immediately find and modify HTML elements
	- Best practice is to put at the end of the body to let all the other elements are parsed
```html
<!DOCTYPE html>
<html lang="en-US">
 
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Today's Date</title>
</head>
 
<body>
  <script>
      let d = new Date();
      document.body.innerHTML = "<h1>Today's date is " + d + "</h1>"
  </script>
</body>
 
</html>
```

## External Script
- Use a separate file with a .js extension for Javascript file
	- Link it in the script tag (Provide path to file from HTML)
	- Method can also be used for .css file to style the HTML

```html
<!DOCTYPE html>
<html lang="en-US">
 
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Today's Date</title>
    <link rel="stylesheet" href="css/style.css">
</head>
 
<body>
    <script src="js/script.js"></script>
</body>
 
</html>
```

# Basic Form Validation

```html
<!DOCTYPE html>
<html lang="en-US">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Form Validator</title>
</head>

<body>
    <form id="contact-form">
        <label for="email">Email:</label>
        <input type="text" id="email" placeholder="you@example.com">
        <button type="submit">Subscribe</button>
        <p id="error-message" style="color: red;"></p>
    </form>
    <script src="js/script.js"></script>
</body>

</html>
```

```js
const contactForm = document.getElementById('contact-form');
const emailInput = document.getElementById('email');
const errorMessage = document.getElementById('error-message');

contactForm.addEventListener('submit', function(event) {
    if (!emailInput.value.includes('@')) {
        event.preventDefault(); 
        
        errorMessage.textContent = 'Please enter a valid email address.';
    } else {
        errorMessage.textContent = '';
    }
});
```

- get elements by id
- add event listener and function to go with it
	- In the example add an event listener to 