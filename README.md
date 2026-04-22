DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour ma hayat Leinah 🇩🇿</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700&family=Poppins:wght@300;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #900C3F;
            --gold: #D4AF37;
            --bg-grad1: #ffccd5;
            --bg-grad2: #fbc2eb;
        }

        body {
            margin: 0;
            padding: 0;
            min-height: 100vh;
            background: linear-gradient(135deg, var(--bg-grad1), var(--bg-grad2));
            font-family: 'Poppins', sans-serif;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            overflow-x: hidden;
            transition: background 1s ease;
        }

        body[dir="rtl"] {
            font-family: 'Tajawal', sans-serif;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.6);
            border-radius: 30px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
            padding: 40px;
            max-width: 600px;
            width: 90%;
            margin: 20px 0;
            text-align: center;
            position: relative;
            z-index: 10;
            transition: opacity 1s ease;
        }

        h1 { color: var(--primary); text-shadow: 1px 1px 2px rgba(0,0,0,0.1); font-size: 2.2rem; margin-bottom: 5px;}
        
        .hayat-glow {
            color: #ff0055;
            font-size: 1.2em;
            text-transform: uppercase;
            font-weight: 900;
            text-shadow: 0 0 10px rgba(255, 0, 85, 0.5), 0 0 20px rgba(255, 0, 85, 0.3);
            display: inline-block;
            animation: heartbeat 1.5s infinite;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            15% { transform: scale(1.15); }
            30% { transform: scale(1); }
            45% { transform: scale(1.15); }
            60% { transform: scale(1); }
        }

        h2 { color: #555; font-size: 1.5rem; border-bottom: 2px dashed var(--gold); padding-bottom: 10px; margin-top: 30px;}
        h3 { color: var(--primary); font-size: 1.1rem; margin-bottom: 10px; }

        .quiz-box {
            background: rgba(255, 255, 255, 0.5);
            border-radius: 15px;
            padding: 15px;
            margin-bottom: 15px;
            border: 1px solid rgba(255, 255, 255, 0.8);
        }

        .btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            font-family: inherit;
            font-size: 1rem;
            transition: 0.3s;
            margin: 10px;
            box-shadow: 0 4px 15px rgba(144, 12, 63, 0.3);
        }

        .btn-small {
            padding: 8px 15px;
            font-size: 0.9rem;
            margin: 5px;
            background: #ff4d6d;
        }

        .btn:hover { background: var(--gold); color: #333; transform: scale(1.05); }

        .troll-btn {
            background: var(--primary);
            color: white;
            font-size: 1.2rem;
        }

        /* Le tout petit bouton de secours */
        .tiny-btn {
            display: none;
            font-size: 0.6rem;
            padding: 5px 10px;
            margin-top: 5px;
            background: var(--primary);
            color: white;
            opacity: 0.8;
            box-shadow: none;
        }

        .quiz-result { font-weight: bold; color: var(--primary); margin-top: 15px; min-height: 25px;}

        .wedding-section {
            background: rgba(212, 175, 55, 0.1);
            border: 2px solid var(--gold);
            border-radius: 20px;
            padding: 20px;
            margin-top: 20px;
        }

        .secret-translator {
            position: fixed;
            bottom: 15px;
            right: 15px;
            opacity: 0.15;
            cursor: pointer;
            font-size: 20px;
            z-index: 100;
            transition: 0.3s;
        }
        .secret-translator:hover { opacity: 0.8; transform: scale(1.2); }

        .lang-ar { display: none; }
        .lang-fr { display: block; }
        
        [dir="rtl"] .lang-fr { display: none; }
        [dir="rtl"] .lang-ar { display: block; }

        /* -------------- MODE TRISTE -------------- */
        #sad-mode {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background: #000;
            z-index: 9999;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
        }

        #sad-text {
            font-size: 1.8rem;
            color: white;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
            margin-bottom: 20px;
            padding: 0 20px;
        }

        #sad-mode img {
            max-width: 90%;
            border-radius: 10px;
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.3);
        }

        .rain {
            position: absolute;
            background: rgba(255,255,255,0.4);
            width: 2px;
            height: 20px;
            animation: fall linear infinite;
        }

        @keyframes fall {
            to { transform: translateY(100vh); }
        }

    </style>
</head>
<body dir="ltr" id="body">

    <div class="glass-card" id="main-card">
        
        <div class="lang-fr">
            <h1>Pour ma <span class="hayat-glow">hayat</span> Leinah 🇩🇿✨</h1>
            <p>La plus belle femme à mes yeux, et la ji3ena de Capri-Sun.</p>
            
            <h2>L'épreuve de l'amour 😈</h2>
            <p>Prouve-le en cliquant 10 fois de suite sur le bouton :</p>
            <div>
                <button class="btn troll-btn" id="main-btn-fr" onclick="handleMainClick(this, 'fr')">Je t'aime</button>
                <br>
                <button class="btn tiny-btn" id="tiny-btn-fr" onclick="handleTinyClick('fr')">je t'aime</button>
            </div>

            <h2>Petit Test 🕵️‍♂️</h2>
            
            <div class="quiz-box">
                <h3>Quel est ton doudou favori ? 🧸</h3>
                <button class="btn btn-small" onclick="checkDoudou('titi')">Titi</button>
                <button class="btn btn-small" onclick="checkDoudou('merwan')">Merwan</button>
                <button class="btn btn-small" onclick="checkDoudou('hamouda')">Hamouda</button>
                <button class="btn btn-small" onclick="checkDoudou('hellokitty')">Hello Kitty</button>
                <button class="btn btn-small" onclick="checkDoudou('winnie')">Winnie l'ourson</button>
                <button class="btn btn-small" onclick="checkDoudou('stitch')">Stitch</button>
                <p class="quiz-result" id="doudou-res-fr"></p>
            </div>

            <div class="quiz-box">
                <h3>Ta boisson de vie ? 🧃</h3>
                <button class="btn" onclick="showCapriSunResult()">Voir la réponse</button>
                <p class="quiz-result" id="capri-res-fr"></p>
            </div>

            <div class="wedding-section">
                <h2>Notre futur InshAllah 💍</h2>
                <p>On fera le plus beau des mariages, avec le Karakou, le Caftan et tout ce qu'il faut pour te faire briller.</p>
                <p>PS : Prépare-toi à faire le couscous tous les vendredis (Je rigole, moi mon seul rôle ce sera de le manger 😋).</p>
                <p><b>Qu'Allah nous bénisse et nous unisse dans le bien ❤️</b></p>
            </div>
        </div>

        <div class="lang-ar">
            <h1>إلى <span class="hayat-glow">حياتي</span> لينة 🇩🇿✨</h1>
            <p>أجمل امرأة في عيني، و"الجيعانة" نتاع الكابري سن.</p>
            
            <h2>اختبار الحب 😈</h2>
            <p>أثبتي ذلك بالضغط 10 مرات متتالية على الزر:</p>
            <div>
                <button class="btn troll-btn" id="main-btn-ar" onclick="handleMainClick(this, 'ar')">أنا أحبك</button>
                <br>
                <button class="btn tiny-btn" id="tiny-btn-ar" onclick="handleTinyClick('ar')">أنا أحبك</button>
            </div>

            <h2>اختبار سريع 🕵️‍♂️</h2>

            <div class="quiz-box">
                <h3>من هو المفضل؟ 🧸</h3>
                <button class="btn btn-small" onclick="checkDoudou('titi')">تيتي (Titi)</button>
                <button class="btn btn-small" onclick="checkDoudou('merwan')">مروان (Merwan)</button>
                <button class="btn btn-small" onclick="checkDoudou('hamouda')">حمودة (Hamouda)</button>
                <button class="btn btn-small" onclick="checkDoudou('hellokitty')">هالو كيتي (Hello Kitty)</button>
                <button class="btn btn-small" onclick="checkDoudou('winnie')">ويني الدبدوب (Winnie)</button>
                <button class="btn btn-small" onclick="checkDoudou('stitch')">ستيتش (Stitch)</button>
                <p class="quiz-result" id="doudou-res-ar"></p>
            </div>

            <div class="quiz-box">
                <h3>مشروبك؟ 🧃</h3>
                <button class="btn" onclick="showCapriSunResult()">رؤية الجواب</button>
                <p class="quiz-result" id="capri-res-ar"></p>
            </div>

            <div class="wedding-section">
                <h2>مستقبلنا إن شاء الله 💍</h2>
                <p>سنقيم أجمل عرس، بالقفطان والكاراكو.</p>
                <p>ملاحظة: سأتركك تطبخين الكسكس كل جمعة (أنا أمزح... سأقوم بأكله فقط 😋).</p>
                <p><b>اللهم بارك لنا واجمع بيننا في خير ❤️</b></p>
            </div>
        </div>
    </div>

    <div id="sad-mode">
        <h1 id="sad-text"></h1>
        <img src="https://media1.tenor.com/m/J7r5uN2nEbwAAAAd/neymar-crying.gif" alt="Neymar pleure">
        </div>

    <div class="secret-translator" id="translator" onclick="toggleLanguage()" title="Chut, c'est un secret">✨</div>

    <script>
        let heartInterval;
        let rainInterval;
        let clickCount = 0;

        // Logique de l'épreuve des 10 clics
        function handleMainClick(btn, lang) {
            // Si c'est devenu un piège et qu'elle clique : C'EST LA FIN
            if (btn.dataset.isTrap === "true") {
                activateSadMode(lang);
                return;
            }

            clickCount++;
            
            // Au 6ème clic (le prochain sera le 7ème), on transforme les boutons !
            if (clickCount === 6) {
                const mainFr = document.getElementById('main-btn-fr');
                const mainAr = document.getElementById('main-btn-ar');
                
                mainFr.innerText = "Je t'aime pas";
                mainAr.innerText = "أنا لا أحبك";
                
                mainFr.style.background = "#555";
                mainAr.style.background = "#555";
                
                mainFr.dataset.isTrap = "true";
                mainAr.dataset.isTrap = "true";

                // Fait apparaitre le tout petit bouton de survie
                document.getElementById('tiny-btn-fr').style.display = 'inline-block';
                document.getElementById('tiny-btn-ar').style.display = 'inline-block';
            }
        }

        // Si elle trouve le petit bouton et continue de cliquer
        function handleTinyClick(lang) {
            clickCount++;
            if (clickCount >= 10) {
                if (lang === 'fr') {
                    alert("Bravo ma hayat ! Tu m'aimes vraiment, tu as déjoué le piège ! 💍❤️");
                } else {
                    alert("برافو حياتي! أنتِ حقاً تحبينني، لقد تجاوزتي الفخ! 💍❤️");
                }
                
                // On cache les boutons de l'épreuve après la victoire
                document.getElementById('main-btn-fr').style.display = 'none';
                document.getElementById('main-btn-ar').style.display = 'none';
                document.getElementById('tiny-btn-fr').style.display = 'none';
                document.getElementById('tiny-btn-ar').style.display = 'none';
            }
        }

        function activateSadMode(lang) {
            document.getElementById('main-card').style.display = 'none';
            document.getElementById('translator').style.display = 'none';
            document.body.style.background = '#000';
            
            clearInterval(heartInterval);
            document.querySelectorAll('.heart-drop').forEach(e => e.remove());

            const sadMode = document.getElementById('sad-mode');
            sadMode.style.display = 'flex';

            if (lang === 'fr') {
                document.getElementById('sad-text').innerText = "Je savais tu m'aimais pas c triste Leinah sah...";
            } else {
                document.getElementById('sad-text').innerText = "كنت علابالي بلي ماتحبينيش، صدمتيني يا لينة صح...";
            }

            rainInterval = setInterval(spawnRain, 50);
        }

        function spawnRain() {
            const drop = document.createElement('div');
            drop.classList.add('rain');
            drop.style.left = Math.random() * 100 + 'vw';
            drop.style.top = '-20px';
            drop.style.animationDuration = (Math.random() * 1 + 0.5) + 's';
            document.getElementById('sad-mode').appendChild(drop);
            setTimeout(() => { drop.remove(); }, 1500);
        }

        // Le quiz pour les doudous
        function checkDoudou(answer) {
            const resFr = document.getElementById('doudou-res-fr');
            const resAr = document.getElementById('doudou-res-ar');
            let textFr = ""; let textAr = "";

            switch(answer) {
                case 'titi':
                    textFr = "bravoo l'amour de ma vie ❤️🐥";
                    textAr = "برافو يا حب حياتي ❤️🐥"; break;
                case 'merwan':
                    textFr = "bahahaha mskn merwan 😂";
                    textAr = "هاهاهاها مسكين مروان 😂"; break;
                case 'hamouda':
                    textFr = "c toi mon doudou pas l'inverse kharaya 😒";
                    textAr = "أنتِ الدودو نتاعي ماشي العكس يا الخراية 😒"; break;
                case 'hellokitty':
                    textFr = "nan tes bon mashAllah 😍";
                    textAr = "لا، أنتِ بون ما شاء الله 😍"; break;
                case 'winnie':
                    textFr = "t sah la? 🤨";
                    textAr = "راكِ صح؟ 🤨"; break;
                case 'stitch':
                    textFr = "c moi j'aime stitch pk tu vole? 👽";
                    textAr = "أنا اللي نحب ستيتش، علاش تسرقي؟ 👽"; break;
            }
            resFr.innerText = textFr; resAr.innerText = textAr;
        }

        // Le quiz pour le Capri Sun
        function showCapriSunResult() {
            document.getElementById('capri-res-fr').innerText = "Capri Sun ! Tu bois ça comme une enfant de 5 ans mais c'est pour ça que je t'aime 🍹❤️";
            document.getElementById('capri-res-ar').innerText = "كابري سن! تشربينه كأن عمرك 5 سنوات ولكنني أعشقك 🍹❤️";
        }

        // Traduction magique avec l'étoile
        let isArabic = false;
        function toggleLanguage() {
            const body = document.getElementById('body');
            isArabic = !isArabic;
            body.setAttribute('dir', isArabic ? 'rtl' : 'ltr');
        }

        // Petits cœurs d'ambiance
        function spawnHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart-drop');
            heart.innerText = '🤍';
            heart.style.position = 'fixed';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = '100vh';
            heart.style.opacity = '0.4';
            heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
            heart.style.transition = 'top 4s linear, opacity 4s linear';
            heart.style.zIndex = '1';
            heart.style.pointerEvents = 'none';
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.style.top = '-10vh';
                heart.style.opacity = '0';
            }, 50);

            setTimeout(() => { heart.remove(); }, 4000);
        }
        
        heartInterval = setInterval(spawnHeart, 800);
    </script>
</body>
</html>
