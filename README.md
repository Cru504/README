<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta Mágica para Ti</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            color: #333;
            text-align: center;
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }
        .card-container {
            perspective: 1000px;
        }
        .card {
            background: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            width: 80%;
            transform-style: preserve-3d;
            backface-visibility: hidden;
            transform-origin: center;
            animation: openCard 2s ease-in-out forwards;
            position: relative;
        }
        h1 {
            color: #e74c3c;
            font-size: 2rem;
            margin-bottom: 15px;
        }
        .message {
            font-size: 1rem;
            line-height: 1.4;
        }
        .buttons {
            margin-top: 15px;
        }
        .buttons button {
            padding: 10px 15px;
            font-size: 1rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }
        .buttons button.yes {
            background-color: #2ecc71;
            color: white;
        }
        .buttons button.no {
            background-color: #e74c3c;
            color: white;
            position: relative;
        }
        @keyframes openCard {
            0% { transform: rotateY(-180deg); }
            100% { transform: rotateY(0deg); }
        }
    </style>
</head>
<body>
    <div class="card-container">
        <div class="card">
            <h1>Para Ti 💌</h1>
            <div class="message">
                <p>Querida Michelle,</p>
                <p>Quiero que sepas cuánto te quiero en varios idiomas:</p>
                <p><strong>Español:</strong> Te quiero mucho.</p>
                <p><strong>Inglés:</strong> I love you so much.</p>
                <p><strong>Francés:</strong> Je t'aime beaucoup.</p>
            </div>
            <div class="buttons">
                <button class="yes" onclick="mostrarMensaje()">Sí</button>
                <button class="no" onmouseover="moverBotonNo()">No</button>
            </div>
            <div id="mensajeOculto" style="display: none; margin-top: 15px; font-size: 1rem; color: #e74c3c;">
                ¡Sabía que dirías que sí! 💖
            </div>
        </div>
    </div>
    <script>
        function mostrarMensaje() {
            document.getElementById('mensajeOculto').style.display = 'block';
        }
        function moverBotonNo() {
            const botonNo = document.querySelector('.no');
            const x = Math.random() * (window.innerWidth - botonNo.offsetWidth);
            const y = Math.random() * (window.innerHeight - botonNo.offsetHeight);
            botonNo.style.position = 'absolute';
            botonNo.style.left = `${x}px`;
            botonNo.style.top = `${y}px`;
        }
    </script>
</body>
</html>
