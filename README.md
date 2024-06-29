<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DrochCoin</title>
    <style>
        body {
            background-color: #16dcf2;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Fulbo Argenta', 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        }
        @font-face {
            font-family: 'Fulbo Argenta';
            src: url('шшшшш.ttf') format('truetype');
        }
        .score {
            font-size: 100px;
        }
        .counter {
            font-size: 50px;
            opacity: 0;
            transition: opacity 0.6s ease-in-out;
        }
        .image {
            width: 400px; /* Увеличен размер изображения в 2 раза */
            height: 400px; /* Увеличен размер изображения в 2 раза */
            transition: transform 0.6s ease;
        }
        .progress-bar {
            width: calc(100% - 100px);
            height: 20px;
            background-color: #fcf235;
            margin: 10px;
            position: relative;
        }
        .progress-bar-inner {
            height: 100%;
            background-color: #FFBF00;
            width: 0;
        }
        .snack-bar {
            background-color: #FFB273;
            color: white;
            text-align: center;
            padding: 10px;
            position: fixed;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: none;
            white-space: nowrap; /* Предотвращает перенос текста */
        }
    </style>
</head>
<body>
    <div class="score" id="score">0</div>
    <div class="counter" id="counter"></div>
    <img src="бананчик.png" class="image" id="image" onclick="scoreUp()">
    <div class="progress-bar">
        <div class="progress-bar-inner" id="progress-bar-inner"></div>
    </div>
    <div class="snack-bar" id="snack-bar">╰⋃╯+100дроч╰⋃╯</div>

    <script>
        let score = 0;
        const scoreElement = document.getElementById('score');
        const counterElement = document.getElementById('counter');
        const imageElement = document.getElementById('image');
        const progressBarInner = document.getElementById('progress-bar-inner');
        const snackBar = document.getElementById('snack-bar');

        function scoreUp() {
            score += 1;
            scoreElement.textContent = score;
            imageElement.style.transform = 'scale(0.95)';
            progressBarInner.style.width = (score % 100) + '%';

            if (score % 100 === 0) {
                snackBar.style.display = 'block';
                setTimeout(() => {
                    snackBar.style.display = 'none';
                }, 2000);
                progressBarInner.style.width = '0%';
            }

            setTimeout(() => {
                imageElement.style.transform = 'scale(1)';
            }, 100);
        }
    </script>
</body>
</html>
