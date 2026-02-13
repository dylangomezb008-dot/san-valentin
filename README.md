<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>App de San Valentín</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffe6e6;
            padding: 50px;
            position: relative;
            overflow: hidden;
        }
        /* Corazones flotantes en el fondo */
        body::before {
            content: "❤️ 🐧 ❤️ 🐧 ❤️";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            font-size: 50px;
            opacity: 0.1;
            pointer-events: none;
            animation: float 10s infinite linear;
        }
        @keyframes float {
            0% { transform: translateY(100vh); }
            100% { transform: translateY(-100px); }
        }
        #buttons {
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
            border: 2px solid #ff69b4;
            border-radius: 5px;
            background-image: linear-gradient(to right, #ff69b4, #ffb6c1);
            color: white;
        }
        #yes {
            background-color: #ff69b4;
        }
        #no {
            background-color: #ccc;
            color: black;
            position: absolute;
        }
        #invitation {
            display: none;
            margin-top: 50px;
            font-size: 24px;
            color: #d63384;
        }
    </style>
</head>
<body>
    <h1>¿Quieres ser mi Valentín? 🐧 ❤️ 🐧</h1>
    <div id="buttons">
        <button id="yes">Sí ❤️</button>
        <button id="no">No</button>
    </div>
    <div id="invitation">
        <h2>¡Feliz San Valentín Te amooo Mutooooooo! 🐧 ❤️</h2>
        <p>Cita el 14 de febrero por la noche. Vístete elegante. Te amo. ❤️ 🐧</p>
    </div>

    <script>
        let yesSize = 16; // Tamaño inicial del botón Sí
        const yesButton = document.getElementById('yes');
        const noButton = document.getElementById('no');
        const invitation = document.getElementById('invitation');

        noButton.addEventListener('click', function() {
            // Aumentar el tamaño del botón Sí
            yesSize += 20;
            yesButton.style.fontSize = yesSize + 'px';
            yesButton.style.padding = (10 + (yesSize / 10)) + 'px ' + (20 + (yesSize / 5)) + 'px';

            // Mover el botón No a una posición aleatoria
            const maxX = window.innerWidth - noButton.offsetWidth;
            const maxY = window.innerHeight - noButton.offsetHeight;
            const randomX = Math.random() * maxX;
            const randomY = Math.random() * maxY;
            noButton.style.left = randomX + 'px';
            noButton.style.top = randomY + 'px';
        });

        yesButton.addEventListener('click', function() {
            // Mostrar la invitación
            invitation.style.display = 'block';
            // Ocultar los botones
            document.getElementById('buttons').style.display = 'none';
        });
    </script>
</body>
</html>
