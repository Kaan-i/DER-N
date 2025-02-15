<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>İyi Geceler Bitanem</title>
    <style>
        body {
            background-color: black;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            font-family: 'Arial', sans-serif;
            text-align: center;
            overflow: hidden;
            position: relative;
        }
        #message {
            font-size: 28px;
            opacity: 0;
            transition: opacity 2s ease-in-out;
            position: relative;
            z-index: 2;
        }
        .heart {
            position: absolute;
            width: 30px;
            height: 30px;
            background-color: red;
            transform: rotate(-45deg);
            opacity: 0;
            animation: fadeIn 1s forwards, heartbeat 1.5s infinite ease-in-out;
        }
        .heart::before,
        .heart::after {
            content: "";
            position: absolute;
            width: 30px;
            height: 30px;
            background-color: red;
            border-radius: 50%;
        }
        .heart::before {
            top: -15px;
            left: 0;
        }
        .heart::after {
            left: 15px;
            top: 0;
        }
        @keyframes heartbeat {
            0%, 100% { transform: scale(1) rotate(-45deg); }
            50% { transform: scale(1.2) rotate(-45deg); }
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <h1 id="message">İyi Geceler, Bitanem ❤️</h1>
    
    <script>
        setTimeout(() => {
            document.getElementById("message").style.opacity = 1;
        }, 1000);

        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            document.body.appendChild(heart);

            heart.style.left = `${Math.random() * 100}vw`;
            heart.style.top = `${Math.random() * 100}vh`;
            heart.style.opacity = 0;

            setTimeout(() => {
                heart.style.opacity = 1;
            }, Math.random() * 2000);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(createHeart, 500);
    </script>
</body>
</html>
