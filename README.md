// given code is of Basic Java Script calculator. 
// We just used some css and some js and all set. 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="calculator.css">
    <title>Calculator</title>

</head>
<body>
    <div class="calculator">
        <input type="text" placeholder="0" id="inputBox">
        <div>
            <button class="operator">AC</button>
            <button class="operator">DEL</button>
            <button class="operator">%</button>
            <button class="operator">/</button>
        </div>
        <div>
            <button>7</button>
            <button>8</button>
            <button>9</button>
            <button class="operator">*</button>
        </div>
        <div>
            <button>4</button>
            <button>5</button>
            <button>6</button>
            <button class="operator">-</button>
        </div>
        <div>
            <button>1</button>
            <button>2</button>
            <button>3</button>
            <button class="operator">+</button>
        </div>
        
        <div>
            <button>00</button>
            <button>0</button>
            <button>.</button>
            <button class="equalBtn">=</button>
        </div>

    </div>
    <script src="calculator.js"></script>
    
</body>
</html>

let input = document.getElementById('inputBox');
let buttons = document.querySelectorAll('button');
let string = "";


let arr = Array.from(buttons);

arr.forEach(button => {
    button.addEventListener('click', (e) => {
        if (e.target.innerHTML === '=') {
            try {
                string = eval(string); 
                input.value = string;
            } catch (err) {
                input.value = "Error";
            }
        } else if (e.target.innerHTML === 'AC') {
            string = ""; 
            input.value = string;
        } else if (e.target.innerHTML === 'DEL') {
            string = string.substring(0, string.length - 1); 
            input.value = string;
        } else {
            string += e.target.innerHTML; 
            input.value = string;
        }
    });
});

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(45deg, #0a0a0a, #3a4452);
}

.calculator {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px;
    border-radius: 16px;
    background: rgba(255, 255, 255, 0.05);
    box-shadow: 0px 3px 15px rgba(113, 115, 119, 0.5);
    max-width: 100%;
}

input {
    width: 100%;
    max-width: 320px;
    border: none;
    padding: 20px;
    margin: 10px;
    background: transparent;
    box-shadow: 0px 3px 15px rgba(84, 84, 84, 0.1);
    font-size: 32px;
    text-align: right;
    color: #ffffff;
}

input::placeholder {
    color: #ffffff;
}

.calculator div {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    width: 100%;
    max-width: 320px;
}

button {
    border: none;
    flex: 1;
    min-width: 60px;
    min-height: 60px;
    margin: 10px;
    border-radius: 50px;
    background: rgba(255, 255, 255, 0.1);
    color: #ffffff;
    font-size: 20px;
    box-shadow: -8px -8px 15px rgba(255, 255, 255, 0.1);
    cursor: pointer;
}

button:hover {
    background: rgba(255, 255, 255, 0.2);
}

.equalBtn {
    background-color: #fb7c14;
    color: #ffffff;
}

.operator {
    color: #6dee0a;
}


