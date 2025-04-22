<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>    
</head>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #000000;
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    #result {
        width: 300px;
        height: 55px;
        font-size: 25px;
        text-align: right;
        background-color: rgb(255, 255, 255);
        color: rgb(0, 0, 0);
        border:0;
        border-radius: 10px;
        margin-bottom: 20px;
    }
    .calculator-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    
    }
    button {
        padding: 15px;
        font-size: 25px;
        border: none;
        border-radius: 55px;
        cursor: pointer;

    }
    #myButton {
        background-color: rgb(48, 48, 48);
        color: white;
    }
    #myButtonoperation {
        background-color: rgb(255, 128, 0);
        color: white;
    }
    #myButtontop {
        background-color: rgb(95, 95, 95);
        color: rgb(255, 255, 255);
    }
</style>
<body>
    <h1 style="color: aliceblue;">Simple Calculator</h1>
    <input type="text" id="result">

    <div class="calculator-grid">
        <button id="myButtontop" onclick="clearDisplay()">AC</button>
        <button id="myButtontop" onclick="deletelast()">←</button>
        <button id="myButtontop" onclick="appendvalue('%')">%</button>
        <button id="myButtonoperation" onclick="appendvalue('/')">÷</button>

        <button id="myButton" onclick="appendvalue('7')">7</button>
        <button id="myButton" onclick="appendvalue('8')">8</button>
        <button id="myButton" onclick="appendvalue('9')">9</button>
        <button id="myButtonoperation" onclick="appendvalue('*')">x</button>

        <button id="myButton" onclick="appendvalue('4')">4</button>
        <button id="myButton" onclick="appendvalue('5')">5</button>
        <button id="myButton" onclick="appendvalue('6')">6</button>
        <button id="myButtonoperation" onclick="appendvalue('-')">-</button>

        <button id="myButton" onclick="appendvalue('1')">1</button>
        <button id="myButton" onclick="appendvalue('2')">2</button>
        <button id="myButton" onclick="appendvalue('3')">3</button>
        <button id="myButtonoperation" onclick="appendvalue('+')">+</button>

        <button id="myButton" onclick="appendvalue('0')">0</button>
        <button id="myButton" onclick="appendvalue('00')">00</button>
        <button id="myButton" onclick="appendvalue('.')">.</button>
        <button id="myButtonoperation" onclick="calculate()">=</button>
    </div>

    <script>
        function appendvalue(value) {
            document.getElementById("result").value += value;
        }
        function clearDisplay() {
            document.getElementById("result").value = "";
        }
        function deletelast() {
            var currentValue = document.getElementById("result").value;
            document.getElementById("result").value = currentValue.slice(0, -1);
        }   
        function calculate() {
            try {
                const input= document.getElementById("result").value;
                const output = eval(input);
                document.getElementById("result").value = output;
            } catch{
                document.getElementById("result").value = "Error";
            }
        }
    </script>
</body>
</html>
