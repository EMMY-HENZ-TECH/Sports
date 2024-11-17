<a href="https://ibb.co/R0Pg8Nt"><img src="https://i.ibb.co/d26fZtX/file-234y-XLTR5i37-YK5-DLu-Rq-IX2t.webp" alt="file-234y-XLTR5i37-YK5-DLu-Rq-IX2t" border="0"></a>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Football Betting Prediction</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: url('https://i.ibb.co/3B9S34C/file-Awrc-XFj-M9-TLn-OU2-X74v4-Ja-WC.webp') no-repeat center center fixed;
            background-size: cover;
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.9); /* Slightly transparent background */
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            width: 300px;
        }

        h1 {
            font-size: 24px;
            color: #333;
        }

        .input-group {
            margin: 15px 0;
        }

        .input-group label {
            display: block;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .input-group input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .predict-btn {
            background: #28a745;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        .predict-btn:hover {
            background: #218838;
        }

        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Football Prediction</h1>
        <div class="input-group">
            <label for="homeTeam">Home Team:</label>
            <input type="text" id="homeTeam" placeholder="Enter home team name">
        </div>
        <div class="input-group">
            <label for="awayTeam">Away Team:</label>
            <input type="text" id="awayTeam" placeholder="Enter away team name">
        </div>
        <button class="predict-btn" onclick="predict()">Predict</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function predict() {
            const homeTeam = document.getElementById('homeTeam').value.trim().toLowerCase();
            const awayTeam = document.getElementById('awayTeam').value.trim().toLowerCase();
            const resultDiv = document.getElementById('result');

            if (!homeTeam || !awayTeam) {
                resultDiv.textContent = "Please enter both team names!";
                return;
            }

            // Prediction logic
            let prediction;
            const strongTeams = ['manchester', 'real madrid', 'barcelona', 'bayern', 'juventus']; // Example strong teams

            if (strongTeams.some(team => homeTeam.includes(team)) && !strongTeams.some(team => awayTeam.includes(team))) {
                prediction = "Home Win";
            } else if (strongTeams.some(team => awayTeam.includes(team)) && !strongTeams.some(team => homeTeam.includes(team))) {
                prediction = "Away Win";
            } else {
                const homeAdvantage = Math.random() < 0.6; // 60% chance home advantage
                prediction = homeAdvantage ? "Home Win" : (Math.random() < 0.5 ? "Draw" : "Away Win");
            }

            // Display prediction
            resultDiv.textContent = `Prediction: ${prediction}`;
        }
    </script>
</body>
</html>
