<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BeSafe - Follow Us</title>

    <!-- Tailwind CSS & FontAwesome -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: 'Orbitron', sans-serif;
            overflow: hidden;
            background: radial-gradient(circle, #020024 10%, #090979 60%, #00d4ff 100%);
            transition: background 0.5s ease-in-out;
        }

        /* Animated Grid Background */
        .grid {
            position: absolute;
            width: 100%;
            height: 100%;
            background-size: 40px 40px;
            background-image: linear-gradient(to right, rgba(255, 255, 255, 0.1) 1px, transparent 1px),
                              linear-gradient(to bottom, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
            z-index: -1;
            animation: moveGrid 6s linear infinite;
        }

        @keyframes moveGrid {
            from { background-position: 0 0; }
            to { background-position: 40px 40px; }
        }

        /* Glass UI Card */
        .glass {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.5);
            padding: 30px;
            text-align: center;
            border: 2px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.5s ease-in-out, box-shadow 0.5s ease-in-out;
        }

        .glass:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 50px rgba(255, 255, 255, 0.7);
        }

        /* Futuristic Glowing Icons */
        .icon {
            position: relative;
            transition: transform 0.5s ease, filter 0.5s ease;
            filter: drop-shadow(0 0 10px rgba(255, 255, 255, 0.8));
        }

        .icon:hover {
            transform: translateY(-10px) scale(1.3);
            filter: drop-shadow(0 0 20px rgba(255, 255, 255, 1));
        }

        /* Facebook Special Glowing Color */
        .facebook-icon {
            background: linear-gradient(to right, #1877F2, #3b5998);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Floating Animation */
        .floating {
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-12px); }
            100% { transform: translateY(0px); }
        }

        /* Neon Glow Text */
        .glow-text {
            background: linear-gradient(to right, #ff00ff, #ffcc00, #00ffcc);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glowEffect 1.5s infinite alternate;
        }

        @keyframes glowEffect {
            0% { text-shadow: 0 0 10px rgba(255, 255, 255, 0.6); }
            100% { text-shadow: 0 0 20px rgba(255, 255, 255, 1); }
        }

        /* Parallax Hover Effect */
        .parallax {
            transform: perspective(1000px) rotateY(0deg) rotateX(0deg);
            transition: transform 0.1s ease-out;
        }

        /* Dark Mode */
        .dark-mode {
            background: #121212;
            color: white;
        }

        /* Particle Background */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -2;
        }

    </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen transition-all duration-500">

    <!-- Grid Animation -->
    <div class="grid"></div>

    <!-- Particle Background -->
    <div id="particles-js"></div>

    <!-- Dark Mode Toggle -->
    <button onclick="toggleDarkMode()" class="mb-6 px-6 py-3 bg-gray-900 text-white rounded-lg shadow-lg hover:bg-gray-700 transition-all">
        🌙 Toggle Dark Mode
    </button>

    <!-- Futuristic Social Media Card -->
    <div class="glass p-10 shadow-2xl w-96 floating parallax">
        <h1 class="text-3xl font-bold glow-text mb-6">Follow Us on Social Media</h1>
        
        <div class="flex justify-center space-x-6">
            <a href="https://www.facebook.com/share/1BwLbTbLuq/" target="_blank" class="icon">
                <i class="fab fa-facebook fa-3x facebook-icon"></i> 
            </a>
            <a href="https://www.instagram.com/mcu_gaming_live?igsh=MXRiMmRoa2s2NzR0Nw==" target="_blank" class="text-pink-500 hover:text-pink-700 icon">
                <i class="fab fa-instagram fa-3x"></i>
            </a>
            <a href="https://youtube.com/@mcugaminglive?si=DQ5fh-2KWmgfbGYD" target="_blank" class="text-red-500 hover:text-red-700 icon">
                <i class="fab fa-youtube fa-3x"></i>
            </a>
        </div>
    </div>

    <!-- Dark Mode Toggle Script -->
    <script>
        function toggleDarkMode() {
            document.body.classList.toggle("dark-mode");
        }

        // Parallax Effect
        document.addEventListener("mousemove", (e) => {
            const x = (window.innerWidth / 2 - e.pageX) / 30;
            const y = (window.innerHeight / 2 - e.pageY) / 30;
            document.querySelector(".parallax").style.transform = `perspective(1000px) rotateY(${x}deg) rotateX(${y}deg)`;
        });
    </script>

    <!-- Particle.js Library -->
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {
            "particles": {
                "number": { "value": 120, "density": { "enable": true, "value_area": 1000 }},
                "color": { "value": "#ffffff" },
                "shape": { "type": "circle" },
                "opacity": { "value": 0.6 },
                "size": { "value": 3, "random": true },
                "line_linked": { "enable": true, "color": "#ffffff", "opacity": 0.3, "width": 1 },
                "move": { "enable": true, "speed": 3 }
            },
            "retina_detect": true
        });
    </script>

</body>
</html>
