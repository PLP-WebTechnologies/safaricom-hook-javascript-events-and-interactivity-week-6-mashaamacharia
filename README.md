# Assignment: Creating Interactive Elements and Form Validation

## Objective:
Build a functional webpage that incorporates event handling, interactive elements, and form validation using JavaScript.

## Requirements:

Interactive Button with onclick:

Add a button that toggles the background color of the webpage between two colors.
Slider with Real-Time Feedback (oninput):

Add a slider that adjusts the size of a paragraph text dynamically.
Modal with Event Listeners:

Create a modal that displays when a button is clicked and hides when the user clicks a close button.

## Form with Validation:

Include a form with the following fields:
Name (required, minimum 3 characters).
Email (valid email format).
Password (minimum 8 characters, at least one uppercase letter and one number).
Display error messages if validation fails.
Prevent form submission if there are errors.
Bonus (Optional):

Add a dropdown menu that displays a custom message when the selected option changes (onchange).


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Webpage</title>
    <style>
        body {
            background-color: white;
            transition: background-color 0.5s;
        }
        .dark-mode {
            background-color: #333;
            color: white;
        }
    </style>
</head>
<body>
    <button id="toggleButton">Toggle Background Color</button>

    <script>
        const button = document.getElementById('toggleButton');
        button.onclick = () => {
            document.body.classList.toggle('dark-mode');
        };
    </script>
</body>
</html>


<body>
    <p id="text">Adjust my size using the slider below!</p>
    <input type="range" id="fontSizeSlider" min="10" max="100" value="16">

    <script>
        const slider = document.getElementById('fontSizeSlider');
        const text = document.getElementById('text');
        slider.oninput = () => {
            text.style.fontSize = `${slider.value}px`;
        };
    </script>
</body>


<body>
    <button id="openModal">Open Modal</button>

    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <p>This is a modal window.</p>
        </div>
    </div>

    <style>
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.5);
        }
        .modal-content {
            background-color: white;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
        }
        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>

    <script>
        const modal = document.getElementById('myModal');
        const btn = document.getElementById('openModal');
        const span = document.getElementsByClassName('close')[0];

        btn.onclick = () => {
            modal.style.display = 'block';
        };

        span.onclick = () => {
            modal.style.display = 'none';
        };

        window.onclick = (event) => {
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        };
    </script>
</body>

