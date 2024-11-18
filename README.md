<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Décompte de Noël</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f9f2ec;
            font-family: 'Comic Sans MS', cursive, sans-serif;
            color: #333;
            flex-direction: column;
        }

        h1 {
            color: #e10600;
            font-size: 3rem;
            margin-bottom: 20px;
        }

        #countdown {
            display: flex;
            gap: 10px;
            font-size: 2.5rem;
            font-weight: bold;
        }

        .time-box {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .time-label {
            font-size: 1rem;
            margin-top: 5px;
        }

        #seconds {
            color: #e10600; /* Rouge pour les secondes */
        }
    </style>
</head>
<body>
    <h1>Décompte avant Noël</h1>
    <div id="countdown">
        <div class="time-box">
            <span id="days">00</span>
            <span class="time-label">Jours</span>
        </div>
        <div class="time-box">
            <span id="hours">00</span>
            <span class="time-label">Heures</span>
        </div>
        <div class="time-box">
            <span id="minutes">00</span>
            <span class="time-label">Minutes</span>
        </div>
        <div class="time-box">
            <span id="seconds">00</span>
            <span class="time-label">Secondes</span>
        </div>
    </div>
    
    <script>
        // Date cible : 1er décembre à minuit
        var targetDate = new Date('December 1, 2024 00:00:00').getTime();

        // Fonction de mise à jour du décompte
        function updateCountdown() {
            var now = new Date().getTime();
            var timeLeft = targetDate - now;

            // Calcul des jours, heures, minutes et secondes restantes
            var days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            var hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            var minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            var seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            // Affichage des valeurs
            document.getElementById("days").textContent = days < 10 ? '0' + days : days;
            document.getElementById("hours").textContent = hours < 10 ? '0' + hours : hours;
            document.getElementById("minutes").textContent = minutes < 10 ? '0' + minutes : minutes;
            document.getElementById("seconds").textContent = seconds < 10 ? '0' + seconds : seconds;

            // Redirection si le décompte atteint zéro
            if (timeLeft < 0) {
                window.location.href = "https://www.example.com"; // Remplace par ton URL
            } else {
                setTimeout(updateCountdown, 1000); // Mise à jour toutes les secondes
            }
        }

        // Lancer le décompte
        updateCountdown();
    </script>
</body>
</html>
