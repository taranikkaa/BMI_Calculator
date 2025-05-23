# Ex06 BMI Calculator
## Date:23/05/2025

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM

### APP.JS :
```
import React, { useState } from 'react';
import './App.css';

function App() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = () => {
    if (!weight || !height) {
      alert("Please enter both weight and height!");
      return;
    }

    const heightInMeters = height / 100;
    const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);
    setBmi(bmiValue);

    if (bmiValue < 18.5) {
      setMessage("Underweight");
    } else if (bmiValue >= 18.5 && bmiValue < 24.9) {
      setMessage("Normal weight");
    } else if (bmiValue >= 25 && bmiValue < 29.9) {
      setMessage("Overweight");
    } else {
      setMessage("Obese");
    }
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>
      <div className="form">
        <input
          type="number"
          placeholder="Weight (kg)"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
        <input
          type="number"
          placeholder="Height (cm)"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
        <button onClick={calculateBMI}>Calculate</button>
      </div>

      {bmi && (
        <div className="result">
          <h2>Your BMI is: {bmi}</h2>
          <p>{message}</p>
        </div>
    
      )}
      <div>
        <footer>
          DONE BY : TARANIKKA A
        </footer>
      </div>
    </div>
  );
}

export default App;
```
### APP.CSS:
```
body {
  margin: 0;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background: url('https://images.unsplash.com/photo-1598970434795-0c54fe7c0642?auto=format&fit=crop&w=1350&q=80') no-repeat center center fixed;
  background-size: cover;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  position: relative;
}

/* Dark translucent overlay to make text readable */
body::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 0;
}

body {
  margin: 0;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background: url('https://images.unsplash.com/photo-1598970434795-0c54fe7c0642?auto=format&fit=crop&w=1350&q=80') no-repeat center center fixed;
  background-size: cover;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

body::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 0;
}

.container {
  position: relative;
  z-index: 1;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.25);
  width: 350px;
  height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: center; /* vertical centering */
  align-items: center;     /* horizontal centering */
  padding: 20px;
  text-align: center;
}

h1 {
  margin-bottom: 20px;
  color: #2c3e50;
  font-weight: bold;
}

.form {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

.form input {
  width: 80%;
  padding: 12px;
  border: 1px solid #aaa;
  border-radius: 10px;
  font-size: 16px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

button {
  width: 85%;
  background: linear-gradient(90deg, #6a11cb 0%, #2575fc 100%);
  color: white;
  padding: 12px 0;
  border: none;
  font-size: 16px;
  border-radius: 8px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
}

button:hover {
  background: linear-gradient(90deg, #5f0ac0, #1f64ff);
  transform: scale(1.05);
}

.result {
  margin-top: 20px;
}

.result h2 {
  color: #6a11cb;
  font-size: 24px;
}

button {
  width: 95%;
  padding: 12px;
}



button {
  background: linear-gradient(90deg, #6a11cb 0%, #2575fc 100%);
  color: rgb(255, 255, 255);
  padding: 12px 20px;
  border: none;
  font-size: 16px;
  border-radius: 8px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
}

button:hover {
  background: linear-gradient(90deg, #5f0ac0, #1f64ff);
  transform: scale(1.05);
}

.result {
  margin-top: 20px;
}

.result h2 {
  color: #6a11cb;
  font-size: 24px;
}
```

## OUTPUT

![Screenshot (30)](https://github.com/user-attachments/assets/d6537ba1-3d88-45f7-a717-0829ef95298b)


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
