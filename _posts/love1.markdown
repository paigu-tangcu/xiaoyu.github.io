```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>满屏爱心</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            background-color: black;
        }
     .heart {
            position: absolute;
            color: red;
            font-size: 20px;
            animation: fall 3s linear infinite;
        }
        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }
    </style>
</head>
<body>
    <script>
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 +'s';
            document.body.appendChild(heart);
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }
        setInterval(createHeart, 300);
    </script>
</body>
</html>
