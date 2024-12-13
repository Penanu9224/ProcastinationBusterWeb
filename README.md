# ProcastinationBusterWeb
Time Management tools
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Procrastination Buster</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom, #f2e9e4, #cfd8dc);
            color: #333;
        }
        header {
            background-color: #006994;
            color: white;
            text-align: center;
            padding: 20px 10px;
            position: relative;
        }
        .logo {
            position: absolute;
            top: 10px;
            left: 20px;
        }
        .logo img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
        }
        nav {
            background-color: #4e4e50;
            display: flex;
            justify-content: space-around;
            padding: 10px;
        }
        nav a {
            color: white;
            text-decoration: none;
            padding: 8px 15px;
            border-radius: 5px;
        }
        nav a:hover {
            background-color: #006994;
        }
        main {
            margin: 20px;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .section {
            margin-bottom: 20px;
        }
        .task-card {
            padding: 10px 15px;
            margin: 10px 0;
            background-color: #eceff1;
            border-left: 5px solid #006994;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
        }
        button {
            background-color: #006994;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #005073;
        }
        .motivation {
            background-color: #d1ecf1;
            border: 1px solid #bee5eb;
            color: #0c5460;
            padding: 15px;
            border-radius: 10px;
            font-size: 1.1em;
        }
        .tips {
            margin-top: 20px;
            padding: 15px;
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 10px;
            color: #333;
        }
        .images {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        .images img {
            width: 100%;
            max-width: 200px;
            border-radius: 10px;
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">
            <img src="https://via.placeholder.com/50" alt="Logo">
        </div>
        <h1>Procrastination Buster</h1>
        <p>Your personal companion to crush procrastination and achieve your dreams!</p>
    </header>
    <nav>
        <a href="#tasks">Tasks</a>
        <a href="#account">Account</a>
        <a href="#tools">Tools</a>
        <a href="#motivation">Motivation</a>
        <a href="#images">Gallery</a>
        <a href="#subscribe">Subscribe</a>
    </nav>
    <main>
        <!-- Task Tracker Section -->
        <section class="section" id="tasks">
            <h2>Track Your Tasks</h2>
            <input type="text" id="taskInput" placeholder="Enter a task..." style="width: 70%; padding: 10px;">
            <button onclick="addTask()">Add Task</button>
            <div id="taskList"></div>
        </section>

        <!-- Account Section -->
        <section class="section" id="account">
            <h2>Create an Account</h2>
            <p>Sign up to save your goals and receive notifications.</p>
            <form>
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required><br><br>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required><br><br>
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required><br><br>
                <button type="submit">Sign Up</button>
            </form>
        </section>

        <!-- Tools Section -->
        <section class="section" id="tools">
            <h2>Productivity Tools</h2>
            <ul>
                <li><a href="#">Time Management Templates</a></li>
                <li><a href="#">Financial Budgeting Sheets</a></li>
                <li><a href="#">Goal Tracker</a></li>
                <li><a href="#">Weight Checkers</a></li>
                <li><a href="#">Health Checkers</a></li>
                <li><a href="#">Travel Bucket Lists</a></li>
                <li><a href="#">Task Checklists</a></li>
            </ul>
        </section>

        <!-- Motivation Quotes Section -->
        <section class="section" id="motivation">
            <h2>Get Inspired</h2>
            <div id="motivationBox" class="motivation">Click below for a dose of motivation!</div>
            <button onclick="generateMotivation()">Inspire Me</button>
        </section>

        <!-- Gallery Section -->
        <section class="section" id="images">
            <h2>Gallery</h2>
            <p>Find inspiration in these activities:</p>
            <div class="images">
                <img src="https://via.placeholder.com/200" alt="Working">
                <img src="https://via.placeholder.com/200" alt="Training">
                <img src="https://via.placeholder.com/200" alt="Eating Healthy">
                <img src="https://via.placeholder.com/200" alt="Family Time">
                <img src="https://via.placeholder.com/200" alt="House Chores">
                <img src="https://via.placeholder.com/200" alt="Relaxing">
                <img src="https://via.placeholder.com/200" alt="Running Businesses">
                <img src="https://via.placeholder.com/200" alt="Achieving Academic Goals">
            </div>
        </section>

        <!-- Subscription Section -->
        <section class="section" id="subscribe">
            <h2>Subscribe to Access Tools</h2>
            <p>Choose a subscription plan to unlock all tools and resources.</p>
            <form>
                <label for="plan">Choose Your Plan:</label>
                <select id="plan" name="plan" required>
                    <option value="monthly">Monthly - $10</option>
                    <option value="yearly">Yearly - $100</option>
                </select><br><br>
                <label for="payment">Payment Method:</label>
                <select id="payment" name="payment" required>
                    <option value="credit">Credit/Debit Card</option>
                    <option value="paypal">PayPal</option>
                </select><br><br>
                <button type="submit">Subscribe Now</button>
            </form>
        </section>
    </main>
    <script>
        // Task Tracker
        function addTask() {
            const taskInput = document.getElementById('taskInput');
            const taskList = document.getElementById('taskList');
            const taskText = taskInput.value.trim();

            if (taskText) {
                const taskCard = document.createElement('div');
                taskCard.className = 'task-card';
                taskCard.innerHTML = `${taskText} <button onclick="removeTask(this)">Done</button>`;
                taskList.appendChild(taskCard);
                taskInput.value = '';
            }
        }

        function removeTask(button) {
            const taskCard = button.parentElement;
            taskCard.remove();
        }

        // Motivation Quotes Generator
        function generateMotivation() {
            const quotes = [
                "Believe you can and you're
