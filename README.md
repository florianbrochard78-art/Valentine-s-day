# Valentine-s-day
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Veux-tu être ma Valentine ?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffebee;
            margin: 0;
            overflow: hidden;
        }
        .container {
            text-align: center;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        h1 {
            color: #e91e63;
        }
        .buttons {
            margin-top: 20px;
        }
        #oui, #non {
            padding: 10px 20px;
            margin: 0 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.2s;
        }
        #oui {
            background-color: #e91e63;
            color: white;
        }
        #non {
            background-color: #f5f5f5;
            color: #333;
        }
        .heart {
            color: #e91e63;
            font-size: 20px;
            position: absolute;
            animation: float 5s infinite linear;
        }
        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-100vh) rotate(360deg); }
        }
        #message {
            display: none;
            margin-top: 20px;
            color: #e91e63;
            font-size: 24px;
            font-weight: bold;
            animation: fadeIn 1s;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>💖💖 Veux-tu être ma Valentine mon bébé d'amour ? 💖💖</h1>
        <div class="buttons">
            <button id="oui">💖OUIIII💖</button>
            <button id="non">NON.</button>
        </div>
        <div id="message">Je savais que tu dirais oui ! 😈💖</div>
    </div>

    <script>
        const oui = document.getElementById('oui');
        const non = document.getElementById('non');
        const message = document.getElementById('message');

        // Fonction pour créer des cœurs
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = '♥';
            heart.style.left = Math.random() * 100 + 'vw';
            document.body.appendChild(heart);

            // Supprimer le cœur après l'animation
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        // Créer un cœur toutes les 300ms
        setInterval(createHeart, 300);

        non.addEventListener('click', () => {
            // Le bouton "Oui" devient plus gros
            let currentSize = parseInt(window.getComputedStyle(oui).fontSize);
            oui.style.fontSize = (currentSize + 50) + 'px';

            // Le bouton "Non" devient plus petit
            let nonSize = parseInt(window.getComputedStyle(non).fontSize);
            {
                non.style.fontSize = (nonSize - 20) + 'px';
            }
        });

        oui.addEventListener('click', () => {
            // Affiche le message sur la même page
            message.style.display = 'block';
            // Cache les boutons
            non.style.display = 'none';
            oui.style.display = 'none';
        });
    </script>
</body>
</html>
