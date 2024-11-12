<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            margin: 0; /* Remove default margin */
        }
        #calculator {
            width: 100%;
            max-width: 400px; /* Maximum width for larger screens */
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        #display {
            width: 100%;
            height: 40px;
            text-align: right;
            padding: 10px;
            font-size: 24px;
            border: 1px solid #ccc;
            border-radius: 5px;
            margin-bottom: 10px;
            box-sizing: border-box; /* Include padding in total width */
        }
        .button-row {
            display: flex;
            justify-content: space-between;
            margin: 5px 0; /* Space between button rows */
        }
        button {
            flex: 1; /* Make buttons flexible */
            height: 50px;
            margin: 0 5px; /* Space between buttons */
            font-size: 18px;
            border: none;
            border-radius: 5px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s; /* Smooth transition */
        }
        button:hover {
            background-color: #0056b3;
        }
        @media (max-width: 400px) {
            button {
                font-size: 16px; /* Adjust font size for smaller screens */
            }
        }
    </style>
</head>
<body>

<div id="calculator">
    <input type="text" id="display" disabled>
    <div class="button-row">
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button onclick="appendToDisplay('/')">/</button>
    </div>
    <div class="button-row">
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button onclick="appendToDisplay('*')">*</button>
    </div>
    <div class="button-row">
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('-')">-</button>
    </div>
    <div class="button-row">
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="appendToDisplay('.')">.</button>
        <button onclick="calculate()">=</button>
        <button onclick="appendToDisplay('+')">+</button>
    </div>
</div>

<script>
    function appendToDisplay(value) {
        document.getElementById('display').value += value;
    }

    function clearDisplay() {
        document.getElementById('display').value = '';
    }

    function calculate() {
        const display = document.getElementById('display');
        try {
            display.value = eval(display.value);
        } catch (error) {
            display.value = 'Error';
        }
    }
</script>

</body>
</html>
