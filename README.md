<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour ma hayat Leinah 🇩🇿</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700&family=Poppins:wght@300;600;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #900C3F;
            --gold: #D4AF37;
            --bg-grad1: #ffccd5;
            --bg-grad2: #fbc2eb;
            --dz-green: #006633;
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
            align-items: flex-start; /* Changé pour le scroll */
            flex-direction: column;
            overflow-x: hidden;
            transition: background 1s ease;
        }

        body[dir="rtl"] { font-family: 'Tajawal', sans-serif; }

        /* Conteneur principal massif */
        #main-container {
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 50px 0;
            z-index: 10;
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
            transition: all 0.5s ease;
        }

        /* Classes pour le système de déverrouillage */
        .locked-section {
            opacity: 0;
            transform: translateY(50px);
            display: none;
            transition: opacity 1s ease, transform 1s ease;
        }

        .unlocked {
            display: block;
            animation: slideUpFade 0.8s forwards;
        }

        @keyframes slideUpFade {
            to { opacity: 1; transform: translateY(0); }
        }

        h1 { color: var(--primary); text-shadow: 1px 1px 2px rgba(0,0,0,0.1); font-size: 2.5rem; margin-bottom: 5px;}
        h2 { color: #555; font-size: 1.8rem; border-bottom: 2px dashed var(--gold); padding-bottom: 10px; margin-top: 20px;}
        h3 { color: var(--primary); font-size: 1.2rem; margin-bottom: 10px; }

        .hayat-glow {
            color: #ff0055;
            font-size: 1.3em;
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

        .quiz-box {
            background: rgba(255, 255, 255, 0.6);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
            border: 2px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
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

        .btn-small { padding: 8px 15px; font-size: 0.9rem; margin: 5px; background: #ff4d6d; }
        .btn:hover { background: var(--gold); color: #333; transform: scale(1.05) translateY(-2px); box-shadow: 0 6px 20px rgba(212, 175, 55, 0.4);}
        .troll-btn { background: var(--primary); color: white; font-size: 1.2rem; }
        
        .tiny-btn {
            display: none; font-size: 0.6rem; padding: 5px 10px; margin-top: 5px;
            background: var(--primary); color: white; opacity: 0.8; box-shadow: none;
        }

        .quiz-result { font-weight: bold; color: var(--primary); margin-top: 15px; min-height: 25px; font-size: 1.1rem;}

        /* Jauge d'amour */
        .progress-container {
            width: 100%; background: #ddd; border-radius: 20px; height: 30px; margin: 20px 0; overflow: hidden; border: 2px solid white;
        }
        .progress-bar {
            height: 100%; background: linear-gradient(90deg, #ff4d6d, #900C3F); width: 0%; transition: width 0.1s;
        }

        /* Jeu de la bague */
        #ring-game-area {
            width: 100%; height: 200px; position: relative; border: 2px dashed var(--primary); border-radius: 15px; overflow: hidden; background: rgba(255,255,255,0.3); margin-top: 20px;
        }
        #ring-btn {
            position: absolute; top: 40%; left: 40%; font-size: 2rem; background: none; border: none; cursor: pointer; transition: 0.2s;
        }

        .wedding-section {
            background: rgba(212, 175, 55, 0.15); border: 3px double var(--gold); border-radius: 20px; padding: 30px; margin-top: 20px; box-shadow: 0 0 20px rgba(212, 175, 55, 0.2);
        }

        .secret-translator {
            position: fixed; bottom: 15px; right: 15px; opacity: 0.15; cursor: pointer; font-size: 20px; z-index: 100; transition: 0.3s;
        }
        .secret-translator:hover { opacity: 0.8; transform: scale(1.2) rotate(180deg); }

        .lang-ar { display: none; }
        .lang-fr { display: block; }
        [dir="rtl"] .lang-fr { display: none; }
        [dir="rtl"] .lang-ar { display: block; }

        /* MODE TRISTE */
        #sad-mode {
            display: none; position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background: #000; z-index: 9999; flex-direction: column; justify-content: center; align-items: center; color: white; text-align: center;
        }
        #sad-text { font-size: 1.8rem; color: white; text-shadow: 0 0 10px rgba(255, 255, 255, 0.5); margin-bottom: 20px; padding: 0 20px;}
        #sad-mode img { max-width: 90%; border-radius: 10px; box-shadow: 0 0 30px rgba(255, 0, 0, 0.3); }
        .rain { position: absolute; background: rgba(255,255,255,0.4); width: 2px; height: 20px; animation: fall linear infinite; }
        @keyframes fall { to { transform: translateY(100vh); } }

        /* Container magique pour les 2000 balises */
        #magic-dom-bloat { position: fixed; top:0; left:0; width:100%; height:100%; pointer-events: none; z-index: 0; overflow: hidden;}
    </style>
</head>
<body dir="ltr" id="body">

    <div id="magic-dom-bloat"></div>

    <div id="main-container">
        
        <div class="glass-card" id="etape1">
            <div class="lang-fr">
                <h1>Pour ma <span class="hayat-glow">hayat</span> Leinah 🇩🇿✨</h1>
                <p>La plus belle femme à mes yeux, et la ji3ena de Capri-Sun.</p>
                <h2>L'épreuve de l'amour 😈</h2>
                <p>Prouve-le en cliquant 10 fois de suite sur le bouton pour débloquer le site :</p>
                <div>
                    <button class="btn troll-btn" id="main-btn-fr" onclick="handleMainClick(this, 'fr')">Je t'aime</button><br>
                    <button class="btn tiny-btn" id="tiny-btn-fr" onclick="handleTinyClick('fr')">je t'aime</button>
                </div>
            </div>
            <div class="lang-ar">
                <h1>إلى <span class="hayat-glow">حياتي</span> لينة 🇩🇿✨</h1>
                <p>أجمل امرأة في عيني، و"الجيعانة" نتاع الكابري سن.</p>
                <h2>اختبار الحب 😈</h2>
                <p>أثبتي ذلك بالضغط 10 مرات متتالية لفتح الموقع:</p>
                <div>
                    <button class="btn troll-btn" id="main-btn-ar" onclick="handleMainClick(this, 'ar')">أنا أحبك</button><br>
                    <button class="btn tiny-btn" id="tiny-btn-ar" onclick="handleTinyClick('ar')">أنا أحبك</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape2">
            <div class="lang-fr">
                <h2>Spécial Leinah 🕵️‍♂️</h2>
                <div class="quiz-box">
                    <h3>Étape 1 : Quel est ton doudou favori ? 🧸</h3>
                    <button class="btn btn-small" onclick="checkDoudou('titi')">Titi</button>
                    <button class="btn btn-small" onclick="checkDoudou('merwan')">Merwan</button>
                    <button class="btn btn-small" onclick="checkDoudou('hamouda')">Hamouda</button>
                    <button class="btn btn-small" onclick="checkDoudou('hellokitty')">Hello Kitty</button>
                    <button class="btn btn-small" onclick="checkDoudou('winnie')">Winnie l'ourson</button>
                    <button class="btn btn-small" onclick="checkDoudou('stitch')">Stitch</button>
                    <p class="quiz-result" id="doudou-res-fr"></p>
                </div>
            </div>
            <div class="lang-ar">
                <h2>خاص لينة 🕵️‍♂️</h2>
                <div class="quiz-box">
                    <h3>المرحلة 1: من هو المفضل؟ 🧸</h3>
                    <button class="btn btn-small" onclick="checkDoudou('titi')">تيتي (Titi)</button>
                    <button class="btn btn-small" onclick="checkDoudou('merwan')">مروان (Merwan)</button>
                    <button class="btn btn-small" onclick="checkDoudou('hamouda')">حمودة (Hamouda)</button>
                    <button class="btn btn-small" onclick="checkDoudou('hellokitty')">هالو كيتي (Hello Kitty)</button>
                    <button class="btn btn-small" onclick="checkDoudou('winnie')">ويني الدبدوب (Winnie)</button>
                    <button class="btn btn-small" onclick="checkDoudou('stitch')">ستيتش (Stitch)</button>
                    <p class="quiz-result" id="doudou-res-ar"></p>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape3">
            <div class="lang-fr">
                <h2>Spécial Leinah 🧃</h2>
                <div class="quiz-box">
                    <h3>Étape 2 : Ta boisson de vie ?</h3>
                    <button class="btn btn-small" onclick="checkBoisson('caprisun')">Capri-Sun</button>
                    <button class="btn btn-small" onclick="checkBoisson('coca')">Coca-Cola</button>
                    <button class="btn btn-small" onclick="checkBoisson('icetea')">Ice Tea</button>
                    <button class="btn btn-small" onclick="checkBoisson('fanta')">Fanta</button>
                    <button class="btn btn-small" onclick="checkBoisson('redbull')">Red Bull</button>
                    <button class="btn btn-small" onclick="checkBoisson('tomate')">Jus de tomate</button>
                    <button class="btn btn-small" onclick="checkBoisson('selecto')">Selecto</button>
                    <button class="btn btn-small" onclick="checkBoisson('eau')">De l'eau</button>
                    <p class="quiz-result" id="capri-res-fr"></p>
                </div>
            </div>
            <div class="lang-ar">
                <h2>خاص لينة 🧃</h2>
                <div class="quiz-box">
                    <h3>المرحلة 2: مشروبك؟</h3>
                    <button class="btn btn-small" onclick="checkBoisson('caprisun')">كابري سن</button>
                    <button class="btn btn-small" onclick="checkBoisson('coca')">كوكا كولا</button>
                    <button class="btn btn-small" onclick="checkBoisson('icetea')">آيس تي</button>
                    <button class="btn btn-small" onclick="checkBoisson('fanta')">فانتا</button>
                    <button class="btn btn-small" onclick="checkBoisson('redbull')">ريد بول</button>
                    <button class="btn btn-small" onclick="checkBoisson('tomate')">عصير طماطم</button>
                    <button class="btn btn-small" onclick="checkBoisson('selecto')">سيلكتو</button>
                    <button class="btn btn-small" onclick="checkBoisson('eau')">الماء</button>
                    <p class="quiz-result" id="capri-res-ar"></p>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape4">
            <div class="lang-fr">
                <h2>L'énergie de l'amour ⚡</h2>
                <p>Clique super vite pour remplir la jauge à 100% !</p>
                <div class="progress-container">
                    <div class="progress-bar" id="love-bar"></div>
                </div>
                <button class="btn" onclick="fillLoveBar()">❤️ SPAM MOI ❤️</button>
            </div>
            <div class="lang-ar">
                <h2>طاقة الحب ⚡</h2>
                <p>اضغطي بسرعة لملء العداد إلى 100%!</p>
                <div class="progress-container">
                    <div class="progress-bar" id="love-bar-ar"></div>
                </div>
                <button class="btn" onclick="fillLoveBar()">❤️ اضغطي بقوة ❤️</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape5">
            <div class="lang-fr">
                <h2>Le test final 💍</h2>
                <p>Attrape la bague si tu es vraiment prête !</p>
                <div id="ring-game-area" onmousemove="moveRing()">
                    <button id="ring-btn" onclick="winRingGame()">💍</button>
                </div>
            </div>
            <div class="lang-ar">
                <h2>الاختبار الأخير 💍</h2>
                <p>أمسكي الخاتم إذا كنتِ مستعدة حقاً!</p>
                <div id="ring-game-area" onmousemove="moveRing()">
                    <button id="ring-btn" onclick="winRingGame()">💍</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section wedding-section" id="etape6">
            <div class="lang-fr">
                <h2>Notre futur InshAllah 💍👑</h2>
                <p>Félicitations ma hayat, tu as réussi toutes les épreuves !</p>
                <p>On fera le plus beau des mariages, avec le Karakou, le Caftan et tout ce qu'il faut pour te faire briller.</p>
                <p>PS : Prépare-toi à faire le couscous tous les vendredis (Je rigole, moi mon seul rôle ce sera de le manger 😋).</p>
                <h3 style="margin-top: 20px; font-size: 1.5rem;">Qu'Allah nous bénisse et nous unisse dans le bien ❤️</h3>
            </div>
            <div class="lang-ar">
                <h2>مستقبلنا إن شاء الله 💍👑</h2>
                <p>مبروك حياتي، لقد اجتزتي كل الاختبارات!</p>
                <p>سنقيم أجمل عرس، بالقفطان والكاراكو وكل ما يجعلك تتألقين.</p>
                <p>ملاحظة: سأتركك تطبخين الكسكس كل جمعة (أنا أمزح... سأقوم بأكله فقط 😋).</p>
                <h3 style="margin-top: 20px; font-size: 1.5rem;">اللهم بارك لنا واجمع بيننا في خير ❤️</h3>
            </div>
        </div>

    </div> <div id="sad-mode">
        <h1 id="sad-text"></h1>
        <img src="https://media.tenor.com/J7r5uN2nEbwAAAAC/neymar-crying.gif" alt="Neymar pleure" onerror="this.src='https://media1.giphy.com/media/3o6vXWg8OEq7aE21uE/giphy.gif'">
    </div>

    <div class="secret-translator" id="translator" onclick="toggleLanguage()" title="Chut, c'est un secret">✨</div>

    <script>
        // --- GÉNÉRATION MASSIVE DE BALISES POUR ALOURDIR LE DOM ---
        // Tu as demandé au moins 2000 balises. Ce script crée 2500 div invisibles !
        const domBloatContainer = document.getElementById('magic-dom-bloat');
        for(let i=0; i<2500; i++) {
            let spark = document.createElement('div');
            spark.className = 'magic-spark';
            // Quelques styles en ligne pour rajouter du code HTML généré
            spark.style.position = 'absolute';
            spark.style.width = '2px';
            spark.style.height = '2px';
            spark.style.background = 'rgba(255, 255, 255, 0.1)';
            spark.style.left = Math.random() * 100 + 'vw';
            spark.style.top = Math.random() * 100 + 'vh';
            domBloatContainer.appendChild(spark);
        }

        // --- GESTION DES ÉTAPES ---
        function unlockSection(id) {
            const section = document.getElementById(id);
            if(section && !section.classList.contains('unlocked')) {
                section.classList.add('unlocked');
                setTimeout(() => {
                    section.scrollIntoView({ behavior: 'smooth', block: 'center' });
                }, 300);
            }
        }

        // --- ÉTAPE 1 : LE PIÈGE ---
        let clickCount = 0;
        function handleMainClick(btn, lang) {
            if (btn.dataset.isTrap === "true") {
                activateSadMode(lang);
                return;
            }
            clickCount++;
            if (clickCount === 6) {
                const mainFr = document.getElementById('main-btn-fr');
                const mainAr = document.getElementById('main-btn-ar');
                
                mainFr.innerText = "Je t'aime pas"; mainAr.innerText = "أنا لا أحبك";
                mainFr.style.background = "#555"; mainAr.style.background = "#555";
                mainFr.dataset.isTrap = "true"; mainAr.dataset.isTrap = "true";

                document.getElementById('tiny-btn-fr').style.display = 'inline-block';
                document.getElementById('tiny-btn-ar').style.display = 'inline-block';
            }
        }

        function handleTinyClick(lang) {
            clickCount++;
            if (clickCount >= 10) {
                if (lang === 'fr') {
                    document.getElementById('main-btn-fr').innerText = "Mission Accomplie ❤️";
                } else {
                    document.getElementById('main-btn-ar').innerText = "تمت المهمة ❤️";
                }
                document.getElementById('main-btn-fr').style.background = "green";
                document.getElementById('main-btn-ar').style.background = "green";
                document.getElementById('main-btn-fr').dataset.isTrap = "false";
                document.getElementById('main-btn-ar').dataset.isTrap = "false";
                
                document.getElementById('tiny-btn-fr').style.display = 'none';
                document.getElementById('tiny-btn-ar').style.display = 'none';

                // Déverrouille l'étape 2
                unlockSection('etape2');
            }
        }

        // --- ÉTAPE 2 : DOUDOU ---
        function checkDoudou(answer) {
            const resFr = document.getElementById('doudou-res-fr');
            const resAr = document.getElementById('doudou-res-ar');
            let textFr = ""; let textAr = "";

            switch(answer) {
                case 'titi':
                    textFr = "Bravooo l'amour de ma vie ❤️🐥 (Étape suivante débloquée)"; 
                    textAr = "برافو يا حب حياتي ❤️🐥 (تم فتح المرحلة التالية)"; 
                    unlockSection('etape3'); // Déverrouillage !
                    break;
                case 'merwan': textFr = "Bahahaha mskn merwan 😂"; textAr = "هاهاهاها مسكين مروان 😂"; break;
                case 'hamouda': textFr = "C toi mon doudou pas l'inverse kharaya 😒"; textAr = "أنتِ الدودو نتاعي ماشي العكس يا الخراية 😒"; break;
                case 'hellokitty': textFr = "Nan tes bon mashAllah 😍"; textAr = "لا، أنتِ بون ما شاء الله 😍"; break;
                case 'winnie': textFr = "T sah la? 🤨"; textAr = "راكِ صح؟ 🤨"; break;
                case 'stitch': textFr = "C moi j'aime stitch pk tu vole? 👽"; textAr = "أنا اللي نحب ستيتش، علاش تسرقي؟ 👽"; break;
            }
            resFr.innerText = textFr; resAr.innerText = textAr;
        }

        // --- ÉTAPE 3 : BOISSON ---
        function checkBoisson(answer) {
            const resFr = document.getElementById('capri-res-fr');
            const resAr = document.getElementById('capri-res-ar');
            let textFr = ""; let textAr = "";

            switch(answer) {
                case 'caprisun':
                    textFr = "Bravoooo lfm de ma vie 🍹❤️ (Étape débloquée !)"; 
                    textAr = "برافو يا مرأة حياتي 🍹❤️ (تم فتح المرحلة!)"; 
                    unlockSection('etape4'); // Déverrouillage !
                    break;
                case 'coca': textFr = "Tes serieuse? 🤨"; textAr = "من نيتك؟ 🤨"; break;
                case 'icetea': textFr = "Ok leinah 🙄"; textAr = "أوكي لينة 🙄"; break;
                case 'fanta': textFr = "Jamais tu bois sa 🤥"; textAr = "عمرك ما تشربيها 🤥"; break;
                case 'redbull': textFr = "Bah wsh 🤯"; textAr = "واش بيك؟ 🤯"; break;
                case 'tomate': textFr = "C'est degeulasse 🤢"; textAr = "يععع مقرف 🤢"; break;
                case 'selecto': textFr = "T'es une vraie DZ mais non essaye encore 🍏"; textAr = "أنتِ جزائرية حرة بصح لا، زيدي خمي 🍏"; break;
                case 'eau': textFr = "Mdrrr depuis quand tu bois de l'eau toi tu mens 😂"; textAr = "ههههه من وكتاش تشربي الماء أنتِ تكذبي 😂"; break;
            }
            resFr.innerText = textFr; resAr.innerText = textAr;
        }

        // --- ÉTAPE 4 : JAUGE D'AMOUR ---
        let loveProgress = 0;
        function fillLoveBar() {
            if(loveProgress >= 100) return;
            loveProgress += 5; // Faut cliquer 20 fois
            document.getElementById('love-bar').style.width = loveProgress + "%";
            document.getElementById('love-bar-ar').style.width = loveProgress + "%";

            // Fait baisser la jauge si elle arrête de cliquer
            setTimeout(() => { if(loveProgress > 0 && loveProgress < 100) { loveProgress -= 2; document.getElementById('love-bar').style.width = loveProgress + "%"; document.getElementById('love-bar-ar').style.width = loveProgress + "%"; } }, 1000);

            if(loveProgress >= 100) {
                document.getElementById('love-bar').style.background = "gold";
                document.getElementById('love-bar-ar').style.background = "gold";
                unlockSection('etape5');
            }
        }

        // --- ÉTAPE 5 : JEU DE LA BAGUE ---
        let ringClicks = 0;
        function moveRing() {
            const btn = document.getElementById('ring-btn');
            // Rend la bague fuyante
            if(Math.random() > 0.3) {
                const x = Math.random() * 80; // 0 to 80%
                const y = Math.random() * 80;
                btn.style.left = x + '%';
                btn.style.top = y + '%';
            }
        }
        function winRingGame() {
            ringClicks++;
            if(ringClicks >= 1) { // Une seule fois suffit, c'est déjà dur à attraper !
                document.getElementById('ring-btn').innerText = "💖 ATTRAPÉE 💖";
                document.getElementById('ring-btn').style.transform = "scale(1.5)";
                unlockSection('etape6');
            }
        }

        // --- LE DRame (SAD MODE NEYMAR) ---
        let heartInterval;
        let rainInterval;
        function activateSadMode(lang) {
            document.getElementById('main-container').style.display = 'none';
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

        // --- TRADUCTION SECRÈTE ---
        let isArabic = false;
        function toggleLanguage() {
            const body = document.getElementById('body');
            isArabic = !isArabic;
            body.setAttribute('dir', isArabic ? 'rtl' : 'ltr');
        }

        // --- CŒURS EN ARRIÈRE-PLAN ---
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

            setTimeout(() => { heart.style.top = '-10vh'; heart.style.opacity = '0'; }, 50);
            setTimeout(() => { heart.remove(); }, 4000);
        }
        
        heartInterval = setInterval(spawnHeart, 800);
    </script>
</body>
</html>
