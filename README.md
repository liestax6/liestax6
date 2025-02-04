<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cuenta Regresiva</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
        }
        #countdown {
            font-size: 2em;
            margin-bottom: 20px;
        }
        #linkContainer {
            display: none;
            margin-top: 20px;
        }
        a {
            font-size: 1.5em;
            color: blue;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <h1>Cuenta regresiva para el evento</h1>
    <div id="countdown"></div>
    <div id="linkContainer">
        <a href="https://tu-enlace-aqui.com" target="_blank">¡Accede aquí!</a>
    </div>

    <script>
        // Fecha de activación (14 de febrero a las 00:00)
        const targetDate = new Date("Feb 14, 2025 00:00:00").getTime();
        
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;
            
            if (distance > 0) {
                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);
                document.getElementById("countdown").innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
            } else {
                document.getElementById("countdown").innerHTML = "¡El evento ha comenzado!";
                document.getElementById("linkContainer").style.display = "block";
                clearInterval(timer);
            }
        }
        
        updateCountdown();
        const timer = setInterval(updateCountdown, 1000);
    </script>
</body>
</html>
