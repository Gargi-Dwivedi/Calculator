# Calculator
A Calculator program made using html, css and javascript.
https://vercel.com/new/gargis-projects-07a17a24/success?developer-id=&external-id=&redirect-url=&branch=main&deploymentUrl=calculator-6mt912la5-gargis-projects-07a17a24.vercel.app&projectName=calculator&s=https%3A%2F%2Fgithub.com%2FGargi-Dwivedi%2FCalculator&gitOrgLimit=&hasTrialAvailable=1&totalProjects=1

code:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        /* Background Styling */
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #4a90e2, #50e3c2);
            color: white;
            overflow: hidden;
        }

        /* Calculator Card */
        .calculator {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 2rem;
            width: 340px;
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .calculator:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 36px rgba(0, 0, 0, 0.5);
        }

        /* Title */
        h1 {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: #ffffff;
            background: linear-gradient(90deg, #ff6bcb, #4a90e2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Input Group */
        .input-group {
            margin-bottom: 1.5rem;
        }
        label {
            display: block;
            font-weight: bold;
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 0.5rem;
        }
        input[type="number"] {
            width: 100%;
            padding: 0.8rem;
            font-size: 1.1rem;
            color: #333;
            border: none;
            border-radius: 8px;
            outline: none;
            background: rgba(255, 255, 255, 0.9);
            box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: background 0.3s ease;
        }
        input[type="number"]:focus {
            background: rgba(255, 255, 255, 1);
        }

        /* Buttons */
        .button-group {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.8rem;
            margin-bottom: 1rem;
        }
        button {
            padding: 0.8rem;
            font-size: 1.1rem;
            font-weight: bold;
            border: none;
            border-radius: 8px;
            color: white;
            background: linear-gradient(45deg, #ff6bcb, #4a90e2);
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            transition: transform 0.2s ease, box-shadow 0.3s ease;
        }
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
        }
        button:active {
            transform: translateY(0);
        }

        /* Result Display */
        #result {
            text-align: center;
            font-size: 1.6rem;
            font-weight: bold;
            color: white;
            padding: 1rem;
            border-radius: 8px;
            margin-top: 1rem;
            background: rgba(255, 255, 255, 0.2);
            box-shadow: inset 0 2px 6px rgba(0, 0, 0, 0.2);
            transition: background 0.3s ease, box-shadow 0.3s ease;
        }
        #result.show {
            background: linear-gradient(90deg, #50e3c2, #ff6bcb);
            box-shadow: 0 4px 20px rgba(255, 107, 203, 0.4);
        }
    </style>
</head>
<body>
    <div class="calculator">
        <h1>Calculator</h1>
        <div class="input-group">
            <label for="num1">Number 1:</label>
            <input type="number" id="num1" placeholder="Enter first number">
        </div>
        <div class="input-group">
            <label for="num2">Number 2:</label>
            <input type="number" id="num2" placeholder="Enter second number">
        </div>
        <div class="button-group">
            <button onclick="performOperation('add')">Add</button>
            <button onclick="performOperation('sub')">Subtract</button>
            <button onclick="performOperation('mul')">Multiply</button>
            <button onclick="performOperation('div')">Divide</button>
        </div>
        <div id="result">Result: </div>
    </div>

    <script>
        const num1Input = document.getElementById("num1")
        const num2Input = document.getElementById("num2")
        const resultDisplay = document.getElementById("result")

        function performOperation(operation) {
            const num1 = parseFloat(num1Input.value)
            const num2 = parseFloat(num2Input.value)
            let result;
            switch(operation){
                case "add":
                    result = num1 + num2
                    break
                case "sub":
                    result = num1 - num2
                    break
                case "mul":
                    result = num1 * num2
                    break
                case "div":
                    result = num1 / num2
                    break
                default:
                    result = "Invalid"
                    console.log("Invalid Operation")
                    break
            }
            resultDisplay.innerHTML = "Result: " + result;
            resultDisplay.classList.add("show");
            setTimeout(() => resultDisplay.classList.remove("show"), 1500);
        }
    </script>
</body>
</html>
