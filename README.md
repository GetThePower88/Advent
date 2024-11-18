# Advent
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Décompte</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }

        #countdown {
            font-size: 3rem;
            color: #e10600;
        }
    </style>
</head>
<body>
    <div id="countdown">10</div> <!-- Départ du décompte à 10 secondes, tu peux changer la valeur -->
    
    <script>
        // Initialisation du temps de décompte en secondes
        var countdownTime = 10; // Change ce nombre pour le temps souhaité en secondes
        var countdownElement = document.getElementById("countdown");

        // Fonction de mise à jour du décompte
        function updateCountdown() {
            countdownElement.textContent = countdownTime;

            // Vérifie si le décompte est arrivé à 0
            if (countdownTime === 0) {
                // Redirection vers une autre page
                window.location.href = "https://www.example.com"; // Remplace par ton URL
            } else {
                countdownTime--;
                setTimeout(updateCountdown, 1000); // Mise à jour toutes les secondes
            }
        }

        // Lancer le décompte
        updateCountdown();
    </script>
</body>
</html>
