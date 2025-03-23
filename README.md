<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        .calculator {
            border: 2px solid #333;
            border-radius: 10px;
            padding: 20px;
            background-color: white;
        }

        input {
            width: 220px;
            height: 40px;
            text-align: right;
            font-size: 20px;
            margin-bottom: 10px;
            padding: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        button {
            width: 50px;
            height: 50px;
            font-size: 20px;
            margin: 5px;
            border-radius: 5px;
            border: 1px solid #ccc;
            background-color: #f0f0f0;
            cursor: pointer;
        }

        button:hover {
            background-color: #ddd;
        }

        button:active {
            background-color: #bbb;
        }
    </style>
</head>
<body>

    <div class="calculator">
        <input type="text" id="display" disabled>
        <br>
        <button onclick="appendNumber(7)">7</button>
        <button onclick="appendNumber(8)">8</button>
        <button onclick="appendNumber(9)">9</button>
        <button onclick="appendOperator('+')">+</button>
        <br>
        <button onclick="appendNumber(4)">4</button>
        <button onclick="appendNumber(5)">5</button>
        <button onclick="appendNumber(6)">6</button>
        <button onclick="appendOperator('-')">-</button>
        <br>
        <button onclick="appendNumber(1)">1</button>
        <button onclick="appendNumber(2)">2</button>
        <button onclick="appendNumber(3)">3</button>
        <button onclick="appendOperator('*')">*</button>
        <br>
        <button onclick="appendNumber(0)">0</button>
        <button onclick="clearDisplay()">C</button>
        <button onclick="calculate()">=</button>
        <button onclick="appendOperator('/')">/</button>
    </div>

    <script>
        let display = document.getElementById('display');
        let currentInput = '';

        function appendNumber(number) {
            currentInput += number;
            display.value = currentInput;
        }

        function appendOperator(operator) {
            if (currentInput !== '') {
                currentInput += operator;
                display.value = currentInput;
            }
        }

        function clearDisplay() {
            currentInput = '';
            display.value = '';
        }

        function calculate() {
            try {
                currentInput = eval(currentInput).toString();
                display.value = currentInput;
            } catch (error) {
                display.value = 'Erro';
                currentInput = '';
            }
        }
    </script>

</body>
</html>
