<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kaviii - My Eternal Valentine 🌹</title>
    <link href="https://fonts.googleapis.com/css2?family=Parisienne&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css">
    <style>
        :root {
            --rose: #ff5d8f;
            --gold: #ffd700;
            --cream: #fff0f3;
        }

        body {
            font-family: 'Parisienne', cursive;
            background: linear-gradient(45deg, var(--cream), #ffd1dc);
            color: #5a2a38;
            margin: 0;
            overflow-x: hidden;
            cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="%23ff5d8f" d="M12 4.248c-3.148-5.402-12-3.825-12 2.944 0 4.661 5.571 9.427 12 15.808 6.43-6.381 12-11.147 12-15.808 0-6.792-8.875-8.306-12-2.944z"/></svg>'), auto;
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(var(--rose) 20%, transparent 21%);
            background-size: 30px 30px;
            opacity: 0.1;
            transform: rotate(15deg);
        }

        .hero-content {
            text-align: center;
            opacity: 0;
            transform: translateY(50px);
            animation: heroEntrance 1.5s ease-out forwards;
        }

        @keyframes heroEntrance {
            to { opacity: 1; transform: translateY(0); }
        }

        .swiper-container {
            width: 100%;
            padding-top: 50px;
            padding-bottom: 50px;
        }

        .swiper-slide {
            background-position: center;
            background-size: cover;
            width: 300px;
            height: 400px;
            border-radius: 15px;
            box-shadow: 0 15px 50px rgba(0,0,0,0.2);
            overflow: hidden;
            transform: scale(0.8);
            transition: transform 0.5s;
        }

        .swiper-slide-active {
            transform: scale(1);
        }

        .love-letter {
            max-width: 800px;
            margin: 5rem auto;
            padding: 2rem;
            background: rgba(255,255,255,0.9);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            opacity: 0;
            transition: all 1s ease;
        }

        .love-letter.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .floating-heart {
            position: fixed;
            pointer-events: none;
            animation: float 3s ease-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
        }

        .interactive-box {
            position: relative;
            padding: 2rem;
            margin: 2rem;
            border-radius: 15px;
            background: rgba(255,255,255,0.9);
            transform-style: preserve-3d;
            transition: all 0.5s ease;
            cursor: pointer;
        }

        .interactive-box:hover {
            transform: rotateX(5deg) rotateY(5deg) translateY(-5px);
            box-shadow: 20px 20px 40px rgba(0,0,0,0.1);
        }

        .particle {
            position: absolute;
            pointer-events: none;
            animation: particleFloat 2s ease-out forwards;
        }

        @keyframes particleFloat {
            to { transform: translateY(-100px) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="hero">
        <div class="hero-content">
            <h1 style="font-size: 4em; margin: 0">Kaviii</h1>
            <p style="font-size: 2em">My Forever Valentine</p>
            <div style="font-size: 3em">🌹💘🌸</div>
        </div>
    </div>

    <!-- Swiper Gallery -->
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background-image: url('https://example.com/photo1.jpg')"></div>
            <div class="swiper-slide" style="background-image: url('https://example.com/photo2.jpg')"></div>
            <div class="swiper-slide" style="background-image: url('https://example.com/photo3.jpg')"></div>
        </div>
        <div class="swiper-pagination"></div>
    </div>

    <div class="love-letter">
        <h2>My Dearest Kaviii,</h2>
        <p>From the moment our souls intertwined...</p>
        <!-- Add your personalized message here -->
    </div>

    <script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
    <script>
        // Initialize Swiper
        new Swiper('.swiper-container', {
            effect: 'coverflow',
            grabCursor: true,
            centeredSlides: true,
            slidesPerView: 'auto',
            coverflowEffect: {
                rotate: 20,
                stretch: 0,
                depth: 200,
                modifier: 1,
                slideShadows: true,
            },
            pagination: {
                el: '.swiper-pagination',
            },
        });

        // Scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.love-letter').forEach(el => observer.observe(el));

        // Floating hearts
        document.addEventListener('click', (e) => {
            const heart = document.createElement('div');
            heart.className = 'floating-heart';
            heart.style.left = e.clientX + 'px';
            heart.style.top = e.clientY + 'px';
            heart.innerHTML = '💖';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 3000);
        });

        // Particle effect
        function createParticles(e) {
            for(let i=0; i<5; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = e.clientX + 'px';
                particle.style.top = e.clientY + 'px';
                particle.innerHTML = ['✨','🌸','💫','🌹','💖'][Math.floor(Math.random()*5)];
                document.body.appendChild(particle);
                setTimeout(() => particle.remove(), 2000);
            }
        }

        document.addEventListener('click', createParticles);
    </script>
</body>
</html>
