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
  const [height, setHeight] = useState("");
  const [weight, setWeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [category, setCategory] = useState("");

  const calculateBMI = () => {
    if (!height || !weight || height <= 0 || weight <= 0) {
      alert("Please enter valid height and weight.");
      return;
    }

    // Convert height from centimetres to metres
    const heightInMeters = height / 100;

    // BMI formula
    const calculatedBMI = weight / (heightInMeters * heightInMeters);

    setBmi(calculatedBMI.toFixed(2));

    // Categorize BMI
    if (calculatedBMI < 18.5) {
      setCategory("Underweight");
    } else if (calculatedBMI < 25) {
      setCategory("Normal");
    } else if (calculatedBMI < 30) {
      setCategory("Overweight");
    } else {
      setCategory("Obese");
    }
  };

  const resetCalculator = () => {
    setHeight("");
    setWeight("");
    setBmi(null);
    setCategory("");
  };

  return (
    <div className="app">
      <div className="calculator">
        <h1>BMI Calculator</h1>
        <p className="subtitle">
          Calculate your Body Mass Index
        </p>

        <div className="input-group">
          <label>Height (cm)</label>
          <input
            type="number"
            placeholder="Enter your height"
            value={height}
            onChange={(e) => setHeight(e.target.value)}
          />
        </div>

        <div className="input-group">
          <label>Weight (kg)</label>
          <input
            type="number"
            placeholder="Enter your weight"
            value={weight}
            onChange={(e) => setWeight(e.target.value)}
          />
        </div>

        <div className="buttons">
          <button onClick={calculateBMI}>
            Calculate BMI
          </button>

          <button className="reset" onClick={resetCalculator}>
            Reset
          </button>
        </div>

        {bmi && (
          <div className="result">
            <h2>Your BMI</h2>

            <div className="bmi-value">
              {bmi}
            </div>

            <p className="category">
              {category}
            </p>
          </div>
        )}

        <div className="reference">
          <h3>BMI Categories</h3>

          <p>Underweight: Below 18.5</p>
          <p>Normal: 18.5 – 24.9</p>
          <p>Overweight: 25 – 29.9</p>
          <p>Obese: 30 and above</p>
        </div>
      </div>
    </div>
  );
}

export default App;

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, sans-serif;
  background: #f1f5f9;
}

.app {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
}

.calculator {
  width: 100%;
  max-width: 450px;
  background: white;
  padding: 35px;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: #1e293b;
  margin-bottom: 8px;
}

.subtitle {
  text-align: center;
  color: #64748b;
  margin-bottom: 30px;
}

.input-group {
  margin-bottom: 20px;
}

.input-group label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
  color: #334155;
}

.input-group input {
  width: 100%;
  padding: 13px;
  border: 1px solid #cbd5e1;
  border-radius: 10px;
  font-size: 16px;
  outline: none;
}

.input-group input:focus {
  border-color: #10b981;
}

.buttons {
  display: flex;
  gap: 10px;
  margin-top: 25px;
}

button {
  flex: 1;
  padding: 13px;
  border: none;
  border-radius: 10px;
  background: #10b981;
  color: white;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background: #059669;
}

button.reset {
  background: #64748b;
}

button.reset:hover {
  background: #475569;
}

.result {
  margin-top: 30px;
  padding: 20px;
  text-align: center;
  border-radius: 15px;
  background: #ecfdf5;
}

.result h2 {
  color: #334155;
}

.bmi-value {
  font-size: 45px;
  font-weight: bold;
  color: #059669;
  margin: 10px 0;
}

.category {
  font-size: 20px;
  font-weight: bold;
  color: #047857;
}

.reference {
  margin-top: 25px;
  padding: 20px;
  background: #f8fafc;
  border-radius: 12px;
}

.reference h3 {
  margin-bottom: 12px;
  color: #334155;
}

.reference p {
  margin: 6px 0;
  color: #64748b;
}

@media (max-width: 500px) {
  .calculator {
    padding: 25px;
  }

  .buttons {
    flex-direction: column;
  }
}
```
## OUTPUT 

<img width="1533" height="820" alt="Screenshot 2026-09-03 103756" src="https://github.com/user-attachments/assets/55487621-0c46-4191-b523-099f9594af64" />

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
