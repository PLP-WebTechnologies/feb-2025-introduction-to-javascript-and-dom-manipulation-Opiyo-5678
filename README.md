# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.
  

Happy Coding! 💻✨

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript and DOM Manipulation</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
</head>
<body>
    <header>
        <h1>Welcome to JavaScript DOM Manipulation</h1>
    </header>
    <main>
        <section>
            <h2>Dynamic Content</h2>
            <p id="dynamicText">This text will change when you click the button.</p>
            <button id="changeTextButton">Change Text</button>
        </section>
        <section>
            <h2>Modify Styles</h2>
            <p id="styleText">Click the button to change my style!</p>
            <button id="changeStyleButton">Change Style</button>
        </section>
        <section>
            <h2>Add/Remove Elements</h2>
            <div id="elementContainer">
                <p>This is a paragraph inside the container.</p>
            </div>
            <button id="addElementButton">Add Element</button>
            <button id="removeElementButton">Remove Element</button>
        </section>
    </main>
    <footer>
        <p>&copy; 2023 Your Company</p>
    </footer>
</body>
</html>

style.css
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background-color: #f9f9f9;
    margin: 0;
    padding: 20px;
}

header {
    background: #333;
    color: #fff;
    padding: 10px 0;
    text-align: center;
}

main {
    margin: 20px 0;
}

section {
    margin-bottom: 20px;
    padding: 15px;
    background: #fff;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    margin-top: 10px;
    padding: 10px 15px;
    background: #007BFF;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background: #0056b3;
}

script.js
// Change text content dynamically
document.getElementById('changeTextButton').addEventListener('click', function() {
    document.getElementById('dynamicText').textContent = 'The text has been changed!';
});

// Modify CSS styles via JavaScript
document.getElementById('changeStyleButton').addEventListener('click', function() {
    const styleText = document.getElementById('styleText');
    styleText.style.color = 'red';
    styleText.style.fontWeight = 'bold';
    styleText.style.fontSize = '20px';
});

// Add or remove an element when a button is clicked
document.getElementById('addElementButton').addEventListener('click', function() {
    const newElement = document.createElement('p');
    newElement.textContent = 'This is a new paragraph added to the container.';
    document.getElementById('elementContainer').appendChild(newElement);
});

document.getElementById('removeElementButton').addEventListener('click', function() {
    const container = document.getElementById('elementContainer');
    const paragraphs = container.getElementsByTagName('p');
    if (paragraphs.length > 0) {
        container.removeChild(paragraphs[paragraphs.length - 1]);
    } else {
        alert('No more elements to remove!');
    }
});
