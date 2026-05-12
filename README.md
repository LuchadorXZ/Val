<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Un mensaje para ti</title>
    <style>
        :root {
            --space-bg: #030613;
            --star-color: #ffffff;
            --accent: #a29bfe;
        }

        body {
            margin: 0;
            padding: 0;
            background-color: var(--space-bg);
            font-family: 'Segoe UI', Roboto, sans-serif;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        /* Fondo de estrellas animado */
        .background {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(ellipse at bottom, #1B2735 0%, #090A0F 100%);
            z-index: -1;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 40px 20px;
            border-radius: 30px;
            text-align: center;
            max-width: 350px;
            width: 85%;
            box-shadow: 0 0 40px rgba(162, 155, 254, 0.2);
            animation: float 4s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        .icon {
            font-size: 50px;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 10px var(--accent));
        }

        h1 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--accent);
            font-weight: 300;
            letter-spacing: 1px;
        }

        p {
            font-size: 1.05rem;
            line-height: 1.6;
            opacity: 0.9;
            margin-bottom: 30px;
        }

        .btn-love {
            text-decoration: none;
            color: white;
            background: linear-gradient(45deg, #6c5ce7, #a29bfe);
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: bold;
            display: inline-block;
            transition: 0.3s;
            box-shadow: 0 4px 15px rgba(108, 92, 231, 0.4);
        }

        .btn-love:active {
            transform: scale(0.9);
        }

        /* Estrellas pequeñas */
        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            opacity: 0.5;
            animation: twinkle var(--duration) infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }
    </style>
</head>
<body>

    <div class="background" id="star-field"></div>

    <div class="card">
        <div class="icon">✨</div>
        <h1>Incluso en la oscuridad...</h1>
        <p>Recuerda que las estrellas necesitan de la noche más profunda para brillar con toda su fuerza. <br><br>
           <b>Tu valor no cambia por cómo te traten los demás.</b> Eres un universo entero lleno de luz.</p>
        
        <a href="https://wa.me/584146738340" class="btn-love">Aquí estoy para ti</a>
    </div>

    <script>
        // Generador de estrellas aleatorias
        const field = document.getElementById('star-field');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            const size = Math.random() * 3 + 'px';
            star.style.width = size;
            star.style.height = size;
            star.style.top = Math.random() * 100 + '%';
            star.style.left = Math.random() * 100 + '%';
            star.style.setProperty('--duration', Math.random() * 3 + 2 + 's');
            field.appendChild(star);
        }
    </script>
</body>
</html>
