# Ex04 Simple Calculator - React Project
## Date:22-03-2026
## Name : Madhu Shruthi A.R
## Reg No : 212225040216

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
```
import { useState } from "react";
import "./App.css";

function App() {
  const [display, setDisplay] = useState("");

  const handleClick = (value) => {
    setDisplay(display + value);
  };

  const calculate = () => {
    try {
      setDisplay(eval(display).toString());
    } catch {
      setDisplay("Error");
    }
  };

  const clear = () => {
    setDisplay("");
  };

  return (
    <div className="calculator">
      <h1>Simple Calculator</h1>

      <input
        type="text"
        value={display}
        readOnly
        placeholder="0"
      />

      <div className="buttons">
        <button onClick={clear}>C</button>
        <button onClick={() => handleClick("/")}>÷</button>
        <button onClick={() => handleClick("*")}>×</button>
        <button onClick={() => handleClick("-")}>−</button>

        <button onClick={() => handleClick("7")}>7</button>
        <button onClick={() => handleClick("8")}>8</button>
        <button onClick={() => handleClick("9")}>9</button>
        <button onClick={() => handleClick("+")}>+</button>

        <button onClick={() => handleClick("4")}>4</button>
        <button onClick={() => handleClick("5")}>5</button>
        <button onClick={() => handleClick("6")}>6</button>
        <button onClick={calculate}>=</button>

        <button onClick={() => handleClick("1")}>1</button>
        <button onClick={() => handleClick("2")}>2</button>
        <button onClick={() => handleClick("3")}>3</button>
        <button onClick={() => handleClick("0")}>0</button>
      </div>
    </div>
  );
}

export default App;
```

app.css

```
#root {
  min-height: 100vh;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f2f2f2;
}

.calculator {
  width: 300px;
  margin: 80px auto;
  padding: 25px;
  background: white;
  border-radius: 15px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
  text-align: center;
}

.calculator h1 {
  margin-bottom: 20px;
}

.calculator input {
  width: 90%;
  height: 50px;
  margin-bottom: 20px;
  font-size: 24px;
  text-align: right;
  padding: 0 10px;
  border: 1px solid #ccc;
  border-radius: 8px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.buttons button {
  height: 55px;
  font-size: 20px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  background: #e6e6e6;
}

.buttons button:hover {
  background: #d0d0d0;
}
```
## OUTPUT 

![alt text](<Screenshot 2026-08-22 103935.png>)

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
