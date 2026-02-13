<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Valentine for Fatimezzahra</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ff4d6d;
            --secondary: #ff758f;
            --gold: #d4af37;
        }
        body {
            font-family: 'Poppins', sans-serif;
            background: #fff0f3;
            margin: 0;
            padding: 0;
            width: 100vw;
            height: 100vh;
            overflow: hidden; 
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        .font-romantic {
            font-family: 'Dancing Script', cursive;
        }
        .heart-bg {
            position: fixed;
            pointer-events: none;
            animation: floatUp 5s linear infinite;
            z-index: 0;
        }
        @keyframes floatUp {
            0% { transform: translateY(110vh) scale(0.5); opacity: 0; }
            50% { opacity: 0.8; }
            100% { transform: translateY(-10vh) scale(1.2); opacity: 0; }
        }

        .envelope-wrapper {
            position: relative;
            cursor: pointer;
            transition: transform 0.3s;
            z-index: 10;
        }
        .envelope {
            width: 260px;
            height: 170px;
            background: var(--primary);
            position: relative;
            border-radius: 0 0 10px 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        .envelope::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            border-left: 130px solid transparent;
            border-right: 130px solid transparent;
            border-top: 95px solid #ff758f;
            transform-origin: top;
            transition: all 0.5s 0.3s;
            z-index: 2;
        }
        .envelope.open::before {
            transform: rotateX(180deg);
            z-index: 0;
        }
        .letter {
            position: absolute;
            bottom: 5px;
            left: 50%;
            transform: translateX(-50%);
            width: 230px;
            height: 140px;
            background: white;
            transition: all 0.5s;
            padding: 15px;
            text-align: center;
            z-index: 1;
            border-radius: 5px;
        }
        .envelope.open .letter {
            bottom: 80px;
            height: 200px;
        }

        .glass {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.4);
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
        }

        .confetti {
            position: fixed;
            width: 15px;
            height: 15px;
            background: var(--primary);
            clip-path: path('M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z');
            animation: fall 3s ease-out forwards;
            z-index: 100;
        }
        @keyframes fall {
            to { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        #no-btn {
            transition: all 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            white-space: nowrap;
            padding: 12px 24px;
            pointer-events: auto;
        }

        .main-container {
            width: 100%;
            max-width: 400px;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            position: relative;
        }
    </style>
</head>
<body>

    <div id="hearts-container"></div>

    <div class="main-container">
        <!-- Screen 1: The Interactive Envelope -->
        <div id="screen-1" class="flex flex-col items-center justify-center z-10 w-full transition-opacity duration-500">
            <div class="mb-8 text-center animate-bounce px-4">
                <p class="text-pink-600 font-semibold tracking-widest text-xs mb-2 uppercase">L-moufaja2a dyal FATIMEZZAHRA</p>
                <h2 class="text-xl font-bold text-gray-800">Fatimezzahra, clicki hna ✨</h2>
            </div>
            
            <div class="envelope-wrapper" onclick="openEnvelope()">
                <div id="envelope" class="envelope">
                    <div class="letter shadow-inner flex flex-col items-center justify-center">
                        <p class="text-pink-500 font-romantic text-lg mb-1">My Dear Sister</p>
                        <p class="text-[9px] text-gray-400 uppercase tracking-tighter mb-2">Fatimezzahra</p>
                        <div class="w-8 h-8 bg-pink-100 rounded-full flex items-center justify-center">
                            <span class="animate-ping text-sm">✨</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Screen 2: The Main Question -->
        <div id="screen-2" class="hidden w-full flex flex-col items-center justify-center z-20">
            <!-- Added overflow-visible to ensure no-btn isn't clipped -->
            <div id="question-card" class="glass w-full p-8 rounded-[2rem] text-center border-2 border-pink-100 relative !overflow-visible">
                <div class="mb-4 flex justify-center">
                    <div class="relative">
                        <div class="absolute inset-0 animate-ping bg-pink-200 rounded-full opacity-50"></div>
                        <span class="text-5xl relative">👯‍♀️</span>
                    </div>
                </div>
                
                <h2 class="text-2xl font-romantic font-bold mb-3 text-[#ff4d6d]">Wach t-kouni my Bestie Valentine?</h2>
                <p id="tease-text" class="text-gray-500 text-xs mb-8 px-2">Fatimezzahra, nti machi gha khti, nti l-kbida!</p>
                
                <div class="flex flex-col gap-4 relative items-center w-full" id="btn-area">
                    <button id="yes-btn" onclick="celebrate()" class="w-full bg-[#ff4d6d] text-white py-4 rounded-2xl font-bold text-lg shadow-xl active:scale-95 transition-all z-30">
                        Sf,Wakha ✨
                    </button>
                    <button id="no-btn" class="w-full bg-gray-200 text-gray-400 py-3 rounded-2xl font-semibold z-[999] text-sm">
                        No 🙅‍♀️
                    </button>
                </div>
            </div>
        </div>

        <!-- Screen 3: The Final Message -->
        <div id="screen-3" class="hidden w-full flex flex-col items-center justify-center z-30 text-center">
            <div class="glass p-8 rounded-[2.5rem] w-full">
                <h1 class="text-5xl mb-4">💖</h1>
                <h2 class="text-2xl font-bold text-gray-800 mb-1">Fatimezzahra</h2>
                <h2 class="text-xl font-romantic font-bold text-[#ff4d6d] mb-6">A7sen Kht f l3alam</h2>
                <div class="space-y-4 text-gray-600 text-sm leading-relaxed italic">
                    <p>"fati wkha mfar9in ra ma nsikch ora k ba9a fl9lb o gha t-bqay dima hiya linsana li 3mrni nsha."</p>
                    <p>"fhad lValentine jit bach ngoul lik knbghik bzaf a khti zwina ."</p>
                    <p class="font-bold not-italic text-base text-gray-900 mt-6">- Khouk li kiybghik bzaf ❤️</p>
                </div>
                <button onclick="location.reload()" class="mt-8 text-pink-400 text-xs underline underline-offset-4">Revoir l-moufaja2a</button>
            </div>
        </div>
    </div>

    <script>
        // 1. Background Hearts
        function createHeart() {
            const container = document.getElementById('hearts-container');
            const heart = document.createElement('div');
            heart.classList.add('heart-bg');
            heart.innerHTML = ['✨', '💖', '⭐', '🌸'][Math.floor(Math.random() * 4)];
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.fontSize = (Math.random() * 15 + 15) + 'px';
            heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
            container.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 500);

        // 2. Navigation Logic
        function openEnvelope() {
            const env = document.getElementById('envelope');
            env.classList.add('open');
            setTimeout(() => {
                const s1 = document.getElementById('screen-1');
                s1.style.opacity = '0';
                setTimeout(() => {
                    s1.classList.add('hidden');
                    const s2 = document.getElementById('screen-2');
                    s2.classList.remove('hidden');
                    s2.style.opacity = '0';
                    setTimeout(() => s2.style.opacity = '1', 50);
                }, 500);
            }, 1000);
        }

        // 3. Dodge Button Logic (Improved for Mobile Clipping)
        const noBtn = document.getElementById('no-btn');
        const yesBtn = document.getElementById('yes-btn');
        const teaseText = document.getElementById('tease-text');
        const card = document.getElementById('question-card');
        
        let yesScale = 1;
        const funnyPhrases = [
            "Wallah ma t-qisih 😂",
            "Op-là! Hhh 😜",
            "Siri b7lk! 😂",
            "wa sf brki 3la sf wakha 🤡",
            "Hrebt lik 😂",
            "Try again 🌸",
            "No way! 🚫",
            "llah ihdik brki 3la sf wakha! 😂"
        ];

        const moveNo = (e) => {
            // Ensure card doesn't clip children
            card.style.overflow = "visible";
            card.style.backdropFilter = "none"; // Backdrop-filter creates a new containing block which clips fixed items

            const vWidth = window.innerWidth;
            const vHeight = window.innerHeight;
            const bWidth = noBtn.offsetWidth;
            const bHeight = noBtn.offsetHeight;

            // Safe boundaries
            const margin = 40;
            const maxX = vWidth - bWidth - margin;
            const maxY = vHeight - bHeight - margin;

            const randomX = Math.max(margin, Math.floor(Math.random() * maxX));
            const randomY = Math.max(margin, Math.floor(Math.random() * maxY));
            
            noBtn.style.position = 'fixed';
            noBtn.style.left = `${randomX}px`;
            noBtn.style.top = `${randomY}px`;
            noBtn.style.zIndex = "9999"; // Extreme priority
            
            noBtn.innerText = funnyPhrases[Math.floor(Math.random() * funnyPhrases.length)];
            
            if(yesScale < 2.5) {
                yesScale += 0.15;
                yesBtn.style.transform = `scale(${yesScale})`;
            }
            
            if(yesScale > 1.5) {
                teaseText.innerText = "Safi cliqui 'Yes' o hni rassek 😂";
                teaseText.style.color = "#ff4d6d";
                teaseText.style.fontWeight = "bold";
            }
        };

        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            moveNo();
        });
        
        noBtn.addEventListener('mouseover', moveNo);

        // 4. Celebration
        function celebrate() {
            document.getElementById('screen-2').classList.add('hidden');
            document.getElementById('screen-3').classList.remove('hidden');
            
            for(let i=0; i<80; i++) {
                setTimeout(() => {
                    const c = document.createElement('div');
                    c.classList.add('confetti');
                    c.style.left = Math.random() * 100 + 'vw';
                    c.style.top = '-20px';
                    c.style.backgroundColor = `hsl(${Math.random() * 30 + 330}, 80%, 60%)`;
                    c.style.animationDuration = (Math.random() * 2 + 1) + 's';
                    document.body.appendChild(c);
                    setTimeout(() => c.remove(), 3000);
                }, i * 15);
            }
        }
    </script>
</body>
</html>
