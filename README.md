//Stone Paper Scissor Game ( remove this line when you using it !)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Stone Paper Scissors Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #667eea, #764ba2);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0;
        }

        .game-box {
            background: white;
            padding: 30px;
            border-radius: 12px;
            width: 320px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        h1 {
            margin-bottom: 20px;
        }

        button {
            padding: 10px 18px;
            margin: 8px;
            font-size: 16px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            background: #667eea;
            color: white;
            transition: 0.3s;
        }

        button:hover {
            background: #5a67d8;
        }

        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }

        .choices {
            margin-top: 15px;
            font-size: 15px;
        }
    </style>
</head>
<body>

<div class="game-box">
    <h1>🪨📄✂️ Game</h1>

    <p>Choose one:</p>

    <button onclick="playGame('s')">Stone</button>
    <button onclick="playGame('p')">Paper</button>
    <button onclick="playGame('z')">Scissor</button>

    <div class="choices" id="choices"></div>
    <div class="result" id="result"></div>
</div>

<script>
    function game(you, computer) {
        if (you === computer)
            return -1;

        if (you === 's' && computer === 'p') return 0;
        if (you === 'p' && computer === 's') return 1;

        if (you === 's' && computer === 'z') return 1;
        if (you === 'z' && computer === 's') return 0;

        if (you === 'p' && computer === 'z') return 0;
        if (you === 'z' && computer === 'p') return 1;
    }

    function playGame(you) {
        let choices = ['s', 'p', 'z'];
        let computer = choices[Math.floor(Math.random() * 3)];

        let result = game(you, computer);

        document.getElementById("choices").innerHTML =
            `You chose: <b>${convert(you)}</b><br>
             Computer chose: <b>${convert(computer)}</b>`;

        if (result === 1)
            document.getElementById("result").innerHTML = "🎉 You Win!";
        else if (result === 0)
            document.getElementById("result").innerHTML = "😞 Computer Wins!";
        else
            document.getElementById("result").innerHTML = "🤝 It's a Tie!";
    }

    function convert(choice) {
        if (choice === 's') return "Stone";
        if (choice === 'p') return "Paper";
        if (choice === 'z') return "Scissor";
    }
</script>

</body>
</html>
