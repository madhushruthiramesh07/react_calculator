# Ex: 06 BMI Calculator
## Date: 18-09-2026

## AIM
To develop a responsive and interactive Body Mass Index (BMI) Calculator using React that allows users to input their height and weight, and calculates their BMI to categorize their health status (e.g., Underweight, Normal, Overweight, Obese).

## DESIGN STEPS

### STEP 1: Initialize React Project

<li>Create a new React app using create-react-app.</li>
<li>Install React Router using:</li>
npm install react-router-dom

### STEP 2: Set Up Routing

Create routing structure with react-router-dom:

<li>Home route (/) – Intro or Navigation</li>

<li>BMI Calculator route (/bmi)</li>

<li>Result route (/result)</li>

### STEP 3: Design the BMI Form Page

<li>Create a form to accept Height (in cm or m) and Weight (in kg).</li>

<li>On form submit, navigate to the result page with entered values via URL query params or context/state.</li>

## STEP 4: Handle Input Validation

<li>Check if height and weight are valid numbers.</li>

<li>Optionally, show error messages for invalid inputs.</li>

### STEP 5: Perform BMI Calculation

<li>In the result component:

<li>Extract height and weight from the route (URL or passed state).</li>

<li>Apply the BMI formula:</li>

![image](https://github.com/user-attachments/assets/ec785506-c96b-489e-8783-fb1a5d36101a)
​
 
<li>Convert height from cm to m if needed.</li></li>

### STEP 6: Display Result

<li>Show calculated BMI.</li>

<li>Show category based on BMI range:

<li>Underweight, Normal, Overweight, Obese, etc.</li></li>

### STEP 7: Navigation Options

<li>Provide a button to go back to the BMI form to calculate again.</li>

### STEP 8: Enhancements

<li>Add styling using CSS or Tailwind.</li>


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
The BMI Calculator successfully takes user input for height and weight, performs the BMI calculation in real-time using React state and event handling, and displays the BMI value along with the corresponding health category.
