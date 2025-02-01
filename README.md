<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ojitos lindos, ¿Quieres ser mi San Valentín? ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;400;600&display=swap');

        body {
            background: linear-gradient(to bottom, #ff99cc, #ff66b2);
            font-family: 'Poppins', sans-serif;
            text-align: center;
            padding: 50px;
            overflow: hidden;
            color: white;
            position: relative;
        }

        .container {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.2);
            max-width: 400px;
            margin: auto;
            position: relative;
            z-index: 2;
            color: #ff4d6d;
            animation: pop 1s ease-in-out;
        }

        @keyframes pop {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        h1 {
            font-size: 30px;
            font-family: 'Pacifico', cursive;
        }

        p {
            font-size: 18px;
            font-weight: 400;
        }

        .buttons {
            margin-top: 20px;
            position: relative;
            height: 100px;
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            margin: 10px;
            font-size: 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s;
            font-family: 'Pacifico', cursive;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
        }

        .yes {
            background-color: #ff4d6d;
            color: white;
            animation: glow 1.5s infinite alternate;
        }

        @keyframes glow {
            0% { box-shadow: 0px 0px 10px rgba(255, 77, 109, 0.5); }
            100% { box-shadow: 0px 0px 20px rgba(255, 77, 109, 0.8); }
        }

        .yes:hover {
            background-color: #ff1a4c;
        }

        .no {
            background-color: #ccc;
            color: black;
            position: absolute;
            font-size: 18px;
            transition: transform 0.3s, left 0.3s, top 0.3s;
        }

        /* Animación de corazones flotantes */
        @keyframes floating {
            0% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }

        .heart {
            position: absolute;
            color: #ff4d6d;
            font-size: 30px;
            animation: floating 5s linear infinite;
        }
    </style>
</head>
<body>

    <!-- Corazones flotantes -->
    <script>
        function createHeart() {
            const heart = document.createElement("div");
            heart.innerHTML = "❤️";
            heart.classList.add("heart");
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 3 + 2 + "s";
            heart.style.fontSize = Math.random() * 20 + 20 + "px";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(createHeart, 500);
    </script>

    <div class="container">
        <h1>Ojitos lindos, ¿quieres ser mi San Valentín? ❤️</h1>
        <p>Ándale, sí, aunque estemos lejos, mi niña ❤️</p>
        <div class="buttons">
            <button class="btn yes" onclick="aceptar()">¡Sí, obvio! ❤️</button>
            <button class="btn no" id="noButton">No 😢</button>
        </div>
    </div>

    <script>
        function aceptar() {
            alert("Aunque no estemos cerca, quiero que sepas que te amo ❤️.");
        }

        // Función para que el botón "No" huya
        let intentos = 0; 
        document.getElementById("noButton").addEventListener("mouseover", function() {
            intentos++;
            var x = Math.random() * (window.innerWidth - 100);
            var y = Math.random() * (window.innerHeight - 100);

            // Cada vez que intentan presionar "No", se mueve más rápido
            this.style.position = "absolute";
            this.style.left = x + "px";
            this.style.top = y + "px";

            // Después de muchos intentos, el botón desaparece
            if (intentos > 7) {
                this.style.display = "none";
            }
        });
    </script>

</body>
</html>
