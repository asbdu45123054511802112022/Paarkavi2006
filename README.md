<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fitness Tracker Dashboard</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="dashboard">
        <h1>Fitness Tracker Dashboard</h1>

        <div class="tracker">
            <h2>Calorie Tracker</h2>
            <input type="number" id="calories" placeholder="Enter calories">
            <button onclick="addCalories()">Add Calories</button>
            <p>Total Calories: <span id="totalCalories">0</span></p>
        </div>

        <div class="tracker">
            <h2>Step Counter</h2>
            <input type="number" id="steps" placeholder="Enter steps">
            <button onclick="addSteps()">Add Steps</button>
            <p>Total Steps: <span id="totalSteps">0</span></p>
        </div>

        <div class="tracker">
            <h2>Water Intake</h2>
            <input type="number" id="water" placeholder="Enter ml of water">
            <button onclick="addWater()">Add Water</button>
            <p>Total Water Intake: <span id="totalWater">0</span> ml</p>
        </div>

        <div class="progress">
            <h2>Daily Progress</h2>
            <div class="progress-bar">
                <div id="progress-fill"></div>
            </div>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: 
    display: flex;
    height: 100vh;
    align-items: center;
    justify-content: center;
    margin: 0;
}

.dashboard {
    background: 
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    width: 350px;
    text-align: center;
}

h1 {
    color: 
}

.tracker {
    background: 
    padding: 15px;
    border-radius: 8px;
    margin: 10px 0;
}

input {
    width: 70%;
    padding: 8px;
    margin-bottom: 10px;
    border: 1px solid 
    border-radius: 4px;
}

button {
    background-color: 
    color: white;
    border: none;
    padding: 8px 20px;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: 
}

.progress-bar {
    background: 
    border-radius: 20px;
    height: 20px;
    width: 100%;
    overflow: hidden;
    margin-top: 10px;
}

#progress-fill {
    background: 
    height: 100%;
    width: 0%;
    transition: width 0.5s ease;
}
let totalCalories = 0;
let totalSteps = 0;
let totalWater = 0;

function addCalories() {
    const calories = parseInt(document.getElementById('calories').value) || 0;
    totalCalories += calories;
    document.getElementById('totalCalories').textContent = totalCalories;
    updateProgress();
}

function addSteps() {
    const steps = parseInt(document.getElementById('steps').value) || 0;
    totalSteps += steps;
    document.getElementById('totalSteps').textContent = totalSteps;
    updateProgress();
}

function addWater() {
    const water = parseInt(document.getElementById('water').value) || 0;
    totalWater += water;
    document.getElementById('totalWater').textContent = totalWater;
    updateProgress();
}

function updateProgress() {
    const progress = Math.min((totalCalories / 2000) * 40 + 
                              (totalSteps / 10000) * 40 + 
                              (totalWater / 2000) * 20, 100);

    document.getElementById('progress-fill').style.width = progress + '%';
}
