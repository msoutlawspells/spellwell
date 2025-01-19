<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spelling Practice for Kids</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f5f8fa;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #ffeb3b;
            color: #fff;
            text-align: center;
            padding: 20px;
            font-size: 2em;
        }
        main {
            padding: 20px;
            text-align: center;
        }
        h2 {
            font-size: 1.5em;
            color: #4caf50;
        }
        .button {
            background-color: #4caf50;
            color: white;
            font-size: 1.2em;
            padding: 15px 30px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            margin: 10px;
        }
        .button:hover {
            background-color: #45a049;
        }
        .form-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            display: inline-block;
        }
        input[type="text"] {
            font-size: 1.1em;
            padding: 10px;
            margin-bottom: 10px;
            width: 200px;
            border-radius: 5px;
            border: 1px solid #ddd;
        }
        input[type="submit"] {
            background-color: #ff5722;
            color: white;
            font-size: 1.2em;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background-color: #e64a19;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px;
            font-size: 0.9em;
        }
    </style>
</head>
<body>

<header>
    Spelling Practice for Kids!
</header>

<main>
    <h2>Welcome! Practice Your Spelling List for the Week!</h2>

    <!-- Form to Input Weekly Spelling Words -->
    <div class="form-container">
        <h3>Enter This Week's Spelling List</h3>
        <form id="spellingForm">
            <input type="text" id="word1" placeholder="Spelling Word 1" required><br>
            <input type="text" id="word2" placeholder="Spelling Word 2" required><br>
            <input type="text" id="word3" placeholder="Spelling Word 3" required><br>
            <input type="submit" value="Save List">
        </form>
    </div>

    <br>
    <button class="button" onclick="startQuiz()">Start Spelling Quiz</button>
    <button class="button" onclick="startGame()">Play Spelling Game</button>

    <br><br>
    <h2>Leaderboard</h2>
    <p>See how you're doing this week! Coming Soon...</p>
</main>

<footer>
    &copy; 2025 Spelling Fun! | Contact | Privacy Policy
</footer>

<script>
    // Store spelling words (In a real application, this could be saved in a database)
    let spellingWords = [];

    // Handle spelling list submission
    document.getElementById('spellingForm').addEventListener('submit', function(event) {
        event.preventDefault();
        
        spellingWords = [
            document.getElementById('word1').value,
            document.getElementById('word2').value,
            document.getElementById('word3').value,
        ];
        
        alert('Spelling List Saved! Get ready to practice!');
        
        // Clear form inputs
        document.getElementById('spellingForm').reset();
    });

    // Start the Spelling Quiz
    function startQuiz() {
        if (spellingWords.length === 0) {
            alert('Please enter a spelling list first!');
            return;
        }
        
        let quizHTML = '<h2>Quiz Time!</h2>';
        spellingWords.forEach((word, index) => {
            quizHTML += `
                <label>Spell the word: ${word}</label><br>
                <input type="text" id="answer${index}" placeholder="Your Answer"><br><br>
            `;
        });
        quizHTML += '<button class="button" onclick="checkAnswers()">Submit Quiz</button>';
        document.querySelector('main').innerHTML = quizHTML;
    }

    // Check quiz answers
    function checkAnswers() {
        let score = 0;
        spellingWords.forEach((word, index) => {
            const userAnswer = document.getElementById(`answer${index}`).value.trim().toLowerCase();
            if (userAnswer === word.toLowerCase()) {
                score++;
            }
        });

        alert(`You scored ${score} out of ${spellingWords.length}!`);
    }

    // Start the Spelling Game (Simple Placeholder)
    function startGame() {
        alert('Spelling Game Coming Soon! Stay Tuned!');
    }
</script>

</body>
</html>
