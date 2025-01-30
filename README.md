
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
            animation: shrink 5s 5s forwards;
        }
        .card {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 90%;
            transform-style: preserve-3d;
            transform-origin: center; /* Cambiado a "center" para que gire desde el centro */
            animation: openCard 2s ease-in-out forwards;
            position: relative;
        }
        h1 {
            color: #e74c3c;
            font-size: 2.5rem;
            margin-bottom: 20px;
            animation: slideIn 1s ease-in-out;
        }
        .message {
            font-size: 1.2rem;
            line-height: 1.6;
            animation: fadeIn 3s ease-in-out;
        }
        .language {
            margin-top: 20px;
            font-style: italic;
            color: #555;
            animation: fadeIn 4s ease-in-out;
        }
        .heart {
            color: #e74c3c;
            font-size: 2rem;
            animation: beat 1.5s infinite;
        }
        .buttons {
            margin-top: 20px;
        }
        .buttons button {
            padding: 10px 20px;
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
        }
        @keyframes openCard {
            0% { transform: rotateY(0); }
            100% { transform: rotateY(-180deg); }
        }
        @keyframes shrink {
            0% { transform: scale(1); }
            100% { transform: scale(0.8); }
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes slideIn {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        @keyframes beat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            animation: fall linear infinite;
        }
        @keyframes fall {
            to { transform: translateY(100vh); }
        }
    </style>
</head>
<body>
    <div class="card-container">
        <div class="card">
            <h1>Para Ti 💌</h1>
            <div class="message">
                <p>Querida Michelle,</p>
                <p>Quiero que sepas cuánto te quiero, y por eso he decidido decírtelo en diferentes idiomas:</p>
                
                <div class="language">
                    <p><strong>Español:</strong> Te quiero mucho.</p>
                    <p><strong>Inglés:</strong> I love you so much.</p>
                    <p><strong>Francés:</strong> Je t'aime beaucoup.</p>
                    <p><strong>Italiano:</strong> Ti amo tanto.</p>
                    <p><strong>Alemán:</strong> Ich liebe dich sehr.</p>
                    <p><strong>Portugués:</strong> Eu te amo muito.</p>
                    <p><strong>Japonés:</strong> 大好きだよ (Daisuki da yo).</p>
                    <p><strong>Chino (Mandarín):</strong> 我很爱你 (Wǒ hěn ài nǐ).</p>
                    <p><strong>Coreano:</strong> 사랑해 (Saranghae).</p>
                    <p><strong>Ruso:</strong> Я тебя очень люблю (Ya tebya ochen' lyublyu).</p>
                </div>

                <p>Espero que esto te haga sonreír, porque tu felicidad es lo más importante para mí.</p>
                <p>Con todo mi cariño,</p>
                <p>Batman</p>
            </div>
            <div class="buttons">
                <button class="yes" onclick="mostrarMensaje()">Sí</button>
                <button class="no" onmouseover="moverBotonNo()">No</button>
            </div>
            <div id="mensajeOculto" style="display: none; margin-top: 20px; font-size: 1.2rem; color: #e74c3c;">
                ¡Sabía que dirías que sí! 💖
            </div>
            <div class="heart">❤️</div>
        </div>
    </div>

    <audio autoplay loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        Tu navegador no soporta la etiqueta de audio.
    </audio>

    <script>
        // Efecto de confeti al cargar la página
        document.addEventListener('DOMContentLoaded', () => {
            const colors = ['#e74c3c', '#3498db', '#2ecc71', '#f1c40f', '#9b59b6'];
            const card = document.querySelector('.card');

            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.left = `${Math.random() * 100}vw`;
                confetti.style.animationDuration = `${Math.random() * 2 + 1}s`;
                confetti.style.animationDelay = `${Math.random() * 2}s`;
                document.body.appendChild(confetti);
            }
        });

        // Función para mostrar el mensaje oculto
        function mostrarMensaje() {
            document.getElementById('mensajeOculto').style.display = 'block';
        }

        // Función para mover el botón "No"
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
