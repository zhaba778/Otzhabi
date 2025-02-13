<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Для ксюхи ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(45deg, #ffe6e6, #ffb3d9, #ff99cc, #ff80bf);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Arial', sans-serif;
            overflow-x: hidden;
        }

        .container {
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            width: 90%;
            position: relative;
            display: none;
        }

        .initial-button {
            padding: 20px 40px;
            font-size: 24px;
            background: linear-gradient(45deg, #ff66b2, #ff99cc);
            border: none;
            border-radius: 50px;
            color: white;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .initial-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        h1 {
            color: #ff4d94;
            margin-bottom: 30px;
            font-size: 36px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        .compliment {
            margin: 20px 0;
            padding: 15px;
            background: linear-gradient(45deg, #ffb3d9, #ff99cc);
            border-radius: 15px;
            color: white;
            font-size: 20px;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeIn 0.5s forwards;
        }

        .rose {
            font-size: 40px;
            margin: 10px;
            animation: rotate 3s infinite linear;
            display: inline-block;
        }

        .button-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin: 20px 0;
        }

        .magic-button {
            padding: 10px 20px;
            background: linear-gradient(45deg, #ff66b2, #ff99cc);
            border: none;
            border-radius: 25px;
            color: white;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .magic-button:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .signature {
            margin-top: 30px;
            font-style: italic;
            color: #ff4d94;
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes rotate {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }

        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .heart {
            position: absolute;
            font-size: 20px;
            color: #ff4d94;
            animation: float 4s linear infinite;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) translateX(100px);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <button class="initial-button" onclick="showContent()">Нажми меня, Ксюха ❤️</button>

    <div class="container" id="mainContent">
        <h1>дорогая Ксюха!</h1>
        
        <div class="rose">🌹</div>
        <div class="rose">🌸</div>
        <div class="rose">🌹</div>

        <div class="compliment">Днём ты сияешь ярче солнца ☀️</div>
        <div class="compliment">Твоя улыбка освещает весь мой мир ✨</div>
        <div class="compliment">Ты самая прекрасная девушка на свете 💖</div>

        <div class="button-container">
            <button class="magic-button" onclick="showLove()">Больше любви!</button>
            <button class="magic-button" onclick="showHearts()">Магия сердец</button>
            <button class="magic-button" onclick="showCompliment()">Ещё комплимент</button>
            <button class="magic-button" onclick="showFlowers()">Цветочное чудо</button>
        </div>

        <div class="signature">С любовью, твой жабик ❤️</div>
    </div>

    <div class="hearts" id="hearts"></div>

    <script>
        function showContent() {
            document.querySelector('.initial-button').style.display = 'none';
            document.querySelector('.container').style.display = 'block';
            showHearts();
        }

        function showLove() {
            const compliments = [
                "ТВОИ ГЛАЗАА",
                "С тобой каждый день как праздник 🎉",
                "Ты делаешь меня самым счастливым 💫",
                "Твоя красота затмевает звезды ⭐"
            ];
            
            const newCompliment = document.createElement('div');
            newCompliment.className = 'compliment';
            newCompliment.textContent = compliments[Math.floor(Math.random() * compliments.length)];
            document.querySelector('.button-container').before(newCompliment);
        }

        function showHearts() {
            const heartsContainer = document.getElementById('hearts');
            for(let i = 0; i < 10; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.innerHTML = '❤️';
                    heart.style.left = Math.random() * 100 + 'vw';
                    heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    heartsContainer.appendChild(heart);
                    setTimeout(() => heart.remove(), 4000);
                }, i * 300);
            }
        }

        function showCompliment() {
            const newCompliments = [
                "Ты самая лучшая женщина на свете! ТВОИ ГЛАЗАА 🎨",
                "ночью ты сияешь ярче звезд",
                "Твои глаза - как звезды в ночи✨"
            ];
            
            const newCompliment = document.createElement('div');
            newCompliment.className = 'compliment';
            newCompliment.textContent = newCompliments[Math.floor(Math.random() * newCompliments.length)];
            document.querySelector('.button-container').before(newCompliment);
        }

        function showFlowers() {
            const flowers = ['🌹', '🌸', '🌺', '🌻', '🌼', '💐', '🌷'];
            const container = document.querySelector('.container');
            
            for(let i = 0; i < 5; i++) {
                const flower = document.createElement('div');
                flower.className = 'rose';
                flower.textContent = flowers[Math.floor(Math.random() * flowers.length)];
                container.insertBefore(flower, container.querySelector('.button-container'));
            }
        }
    </script>
</body>
</html>
