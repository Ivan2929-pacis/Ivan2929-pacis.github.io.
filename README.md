<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crush Kita</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background: linear-gradient(135deg, #ff7a18, #af002d);
            color: white;
            margin: 0;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            font-weight: bold;
            font-family: 'Pacifico', sans-serif;
            animation: glow 1.5s ease-in-out infinite;
        }

        button {
            padding: 15px 30px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            border: none;
            border-radius: 10px;
            transition: all 0.3s ease;
            margin: 10px;
        }

        #yesButton {
            background-color: #4CAF50;
            color: white;
        }

        #yesButton:hover {
            background-color: #45a049;
            transform: scale(1.1);
        }

        #noButton {
            background-color: #f44336;
            color: white;
            position: absolute;
            transition: all 0.3s ease;
        }

        #noButton:hover {
            background-color: #e63946;
            transform: scale(1.1);
        }

        h2 {
            margin-top: 20px;
            font-size: 1.5rem;
            font-weight: normal;
        }

        @keyframes glow {
            0% { box-shadow: 0 0 5px #fff, 0 0 10px #ff7a18, 0 0 15px #ff7a18; }
            50% { box-shadow: 0 0 10px #fff, 0 0 20px #ff7a18, 0 0 30px #ff7a18; }
            100% { box-shadow: 0 0 5px #fff, 0 0 10px #ff7a18, 0 0 15px #ff7a18; }
        }

        /* Cute anime character styling */
        .anime-character {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            animation: floatUp 3s ease-in-out infinite;
        }

        @keyframes floatUp {
            0% { transform: translateY(0) translateX(-50%); }
            50% { transform: translateY(-20px) translateX(-50%); }
            100% { transform: translateY(0) translateX(-50%); }
        }

        .anime-character img {
            width: 100%;
        }

    </style>
</head>
<body>
    <h1>Crush kita, crush mo rin ba ako?</h1>
    <button onclick="recordAnswer('Yes')" id="yesButton">Yes</button>
    <button id="noButton" onmouseover="moveNoButton()" onclick="recordAnswer('No')">No</button>

    <h2 id="response" style="margin-top: 20px; display: none;"></h2>

    <div class="anime-character">
        <img src="https://www.pngkit.com/png/full/888-8886971_cute-anime-girl-png-pic-cute-anime-character.png" alt="Cute Anime Character" />
    </div>

    <script>
        function moveNoButton() {
            const noButton = document.getElementById('noButton');
            const x = Math.random() * (window.innerWidth - noButton.offsetWidth);
            const y = Math.random() * (window.innerHeight - noButton.offsetHeight);
            noButton.style.left = `${x}px`;
            noButton.style.top = `${y}px`;
        }

        function recordAnswer(answer) {
            const response = document.getElementById('response');
            response.style.display = 'block';
            response.textContent = `You answered: ${answer}`;

            // Optional: Save to local storage for future reference
            localStorage.setItem('crushAnswer', answer);
        }
    </script>
</body>
</html>
