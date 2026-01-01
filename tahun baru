<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Tahun Baru 2026!</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #020205;
            color: white;
            font-family: 'Inter', sans-serif;
        }

        /* Intro Screen - Cyber Aesthetic */
        #intro-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 100;
            background: radial-gradient(circle at center, #1a1a3a 0%, #020205 100%);
            transition: all 1s cubic-bezier(0.4, 0, 0.2, 1);
        }

        #intro-screen.fade-out {
            opacity: 0;
            pointer-events: none;
            transform: scale(1.2);
        }

        /* Hero Frame yang lebih kecil */
        .hero-frame {
            width: 260px;
            height: 260px;
            position: relative;
            margin-bottom: 2rem;
            animation: float-cool 4s ease-in-out infinite;
            border-radius: 35px;
            padding: 8px;
            background: linear-gradient(135deg, #ffd700, #ff00ff, #00d4ff);
            background-size: 300% 300%;
            animation: gradient-move 5s ease infinite, float-cool 4s ease-in-out infinite;
            box-shadow: 0 0 40px rgba(255, 215, 0, 0.25), 0 0 80px rgba(0, 212, 255, 0.15);
        }

        .hero-inner {
            width: 100%;
            height: 100%;
            background: #000;
            border-radius: 28px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: brightness(1.1) contrast(1.1);
        }

        @keyframes gradient-move {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes float-cool {
            0%, 100% { transform: translateY(0) rotate(-2deg); }
            50% { transform: translateY(-20px) rotate(2deg); }
        }

        .glow-text {
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.6);
            letter-spacing: 0.15em;
        }

        .btn-start {
            background: linear-gradient(90deg, #FFD700, #FF8C00);
            color: #000;
            padding: 1rem 3rem;
            font-weight: 800;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(255, 215, 0, 0.3);
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            text-transform: uppercase;
            font-size: 0.9rem;
        }

        .btn-start:hover {
            transform: scale(1.1) translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.5);
        }

        /* UI Konten Utama yang lebih ringkas (Kecil) */
        #main-ui {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            z-index: 10;
            width: 85%;
            max-width: 500px; /* Batas lebar maksimal */
            opacity: 0;
            pointer-events: none;
            transition: all 1s;
        }

        .show-ui { opacity: 1 !important; pointer-events: auto !important; transform: translate(-50%, -50%) scale(1) !important; }

        .glass-box {
            background: rgba(255, 255, 255, 0.04);
            backdrop-filter: blur(20px);
            padding: 2.5rem 1.5rem;
            border-radius: 2.5rem;
            border: 1px solid rgba(255, 255, 255, 0.12);
            box-shadow: 0 30px 70px rgba(0,0,0,0.7);
        }

        canvas { display: block; position: absolute; top: 0; left: 0; }

        /* Hati Tersembunyi */
        #hidden-heart {
            position: fixed;
            bottom: 25px;
            right: 25px;
            font-size: 2.5rem;
            cursor: pointer;
            opacity: 0.1;
            z-index: 50;
            transition: 0.4s;
        }
        #hidden-heart:hover { 
            opacity: 0.8; 
            transform: scale(1.2);
            filter: drop-shadow(0 0 15px #ff0055);
        }
    </style>
</head>
<body>

    <div id="hidden-heart" onclick="popHeartFirework()">❤️</div>

    <div id="intro-screen">
        <div class="hero-frame">
            <div class="hero-inner">
                <img id="lego-img" 
                     src="https://images.unsplash.com/photo-1546702613-2615456b35d5?q=80&w=1000&auto=format&fit=crop" 
                     alt="LEGO Perayaan 2026" 
                     class="hero-img"
                     onerror="handleImageError(this)">
            </div>
        </div>
        <h1 class="text-4xl md:text-5xl font-black text-yellow-400 mb-2 italic glow-text">2026 CERIA!</h1>
        <p class="text-white/60 mb-10 text-center px-6 max-w-xs leading-relaxed uppercase tracking-widest text-xs">
            Momen baru penuh warna!
        </p>
        <button onclick="launch()" class="btn-start">Buka Kejutan 🎉</button>
    </div>

    <div id="main-ui" style="transform: translate(-50%, -50%) scale(0.9);">
        <div class="glass-box">
            <h2 class="text-5xl md:text-7xl font-black mb-4 text-transparent bg-clip-text bg-gradient-to-br from-yellow-200 via-yellow-500 to-orange-700 leading-tight">
                HAPPY 2026
            </h2>
            <p id="quote" class="text-lg md:text-xl font-light italic mb-8 text-white/90 tracking-wide leading-relaxed">
                "Semoga tahun ini menjadi tahun penuh tawa!"
            </p>
            <button onclick="changeQuote()" class="bg-white/5 hover:bg-white/10 border border-white/20 px-8 py-3 rounded-xl font-bold uppercase tracking-widest text-xs transition-all hover:border-yellow-500/50">
                Pesan Lainnya ✨
            </button>
        </div>
    </div>

    <canvas id="canvas"></canvas>

    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];
        let running = false;

        function handleImageError(img) {
            img.src = "https://images.unsplash.com/photo-1585366119957-e9730b6d0f60?q=80&w=1000&auto=format&fit=crop";
        }

        function resize() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resize);
        resize();

        function launch() {
            document.getElementById('intro-screen').classList.add('fade-out');
            setTimeout(() => {
                document.getElementById('main-ui').classList.add('show-ui');
            }, 300);
            running = true;
            animate();
            
            setInterval(() => { 
                if(Math.random() < 0.3) createFirework(); 
            }, 500);
        }

        const quotes = [
            "Semoga 2026 penuh dengan keajaiban!",
            "Waktunya bersinar lebih terang!",
            "Mari ciptakan petualangan seru!",
            "Senyummu adalah kembang api terbaik.",
            "Tahun baru, kebahagiaan baru!",
            "Langkahmu di 2026 semoga penuh warna!"
        ];

        function changeQuote() {
            const quoteEl = document.getElementById('quote');
            quoteEl.style.opacity = 0;
            quoteEl.style.transform = 'translateY(5px)';
            setTimeout(() => {
                quoteEl.innerText = `"${quotes[Math.floor(Math.random() * quotes.length)]}"`;
                quoteEl.style.opacity = 1;
                quoteEl.style.transform = 'translateY(0)';
            }, 400);
        }

        class Particle {
            constructor(x, y, color, velocity, size = 2) {
                this.x = x; this.y = y; this.color = color; this.velocity = velocity;
                this.alpha = 1;
                this.friction = 0.96;
                this.gravity = 0.15;
                this.size = size;
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 10;
                ctx.shadowColor = this.color;
                ctx.fill();
                ctx.restore();
            }
            update() {
                this.velocity.x *= this.friction;
                this.velocity.y *= this.friction;
                this.velocity.y += this.gravity;
                this.x += this.velocity.x;
                this.y += this.velocity.y;
                this.alpha -= 0.015;
            }
        }

        function createFirework(x, y, isHeart = false) {
            const posX = x || Math.random() * canvas.width;
            const posY = y || Math.random() * (canvas.height * 0.4);
            const color = isHeart ? '#ff0066' : `hsl(${Math.random() * 360}, 100%, 75%)`;
            
            if (isHeart) {
                for (let i = 0; i < Math.PI * 2; i += 0.12) {
                    const r = 10;
                    const vx = r * 16 * Math.pow(Math.sin(i), 3);
                    const vy = -r * (13 * Math.cos(i) - 5 * Math.cos(2 * i) - 2 * Math.cos(3 * i) - Math.cos(4 * i));
                    particles.push(new Particle(posX, posY, color, { x: vx / 8, y: vy / 8 }, 2.5));
                }
            } else {
                const count = 70;
                for (let i = 0; i < count; i++) {
                    const angle = Math.random() * Math.PI * 2;
                    const speed = Math.random() * 10 + 3;
                    particles.push(new Particle(posX, posY, color, {
                        x: Math.cos(angle) * speed,
                        y: Math.sin(angle) * speed
                    }, Math.random() * 2));
                }
            }
        }

        function popHeartFirework() {
            createFirework(window.innerWidth / 2, window.innerHeight / 2.5, true);
        }

        function animate() {
            if(!running) return;
            requestAnimationFrame(animate);
            ctx.fillStyle = 'rgba(2, 2, 5, 0.25)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            particles.forEach((p, i) => {
                if (p.alpha <= 0) particles.splice(i, 1);
                else { p.update(); p.draw(); }
            });
        }

        canvas.addEventListener('mousedown', (e) => {
            if(!running) return;
            createFirework(e.clientX, e.clientY, Math.random() < 0.2);
        });
        
        canvas.addEventListener('touchstart', (e) => {
            if(!running) return;
            createFirework(e.touches[0].clientX, e.touches[0].clientY, Math.random() < 0.3);
        });
    </script>
</body>
</html>

