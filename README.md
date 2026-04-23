<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Le Parcours du Combattant pour Leinah 🇩🇿❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;900&family=Poppins:wght@300;600;900&display=swap" rel="stylesheet">
    <style>
        /* ========================================= */
        /* VARIABLES & FOND MONDIAUX                 */
        /* ========================================= */
        :root {
            --primary: #900C3F;
            --gold: #D4AF37;
            --bg-dark: #1a0b12;
            --pink-dark: #ff4d6d;
            --dz-green: #006633;
        }

        body {
            margin: 0;
            padding: 0;
            min-height: 100vh;
            background: linear-gradient(135deg, #1a0b12, #4a001a);
            font-family: 'Poppins', sans-serif;
            color: #fff;
            overflow-x: hidden;
            scroll-behavior: smooth;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            user-select: none;
        }

        body[dir="rtl"] {
            font-family: 'Tajawal', sans-serif;
        }

        #main-container {
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 50px 0;
            z-index: 10;
            position: relative;
        }

        /* ========================================= */
        /* LE DESIGN DES CARTES (GLASSMORPHISM)      */
        /* ========================================= */
        .glass-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.95), rgba(255,204,213,0.95));
            backdrop-filter: blur(20px);
            border: 2px solid rgba(255,255,255,0.5);
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.5);
            padding: 40px;
            max-width: 700px;
            width: 90%;
            margin: 30px 0;
            text-align: center;
            position: relative;
            transition: all 0.5s ease;
            color: #333;
        }

        .locked-section {
            opacity: 0;
            transform: translateY(100px) scale(0.9);
            display: none;
            transition: all 1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .unlocked {
            display: block;
            animation: popIn 1s forwards;
        }

        @keyframes popIn {
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        /* ========================================= */
        /* TYPOGRAPHIE                               */
        /* ========================================= */
        h1 {
            color: var(--primary);
            font-size: 2.8rem;
            margin-bottom: 5px;
            text-shadow: 2px 2px 5px rgba(0,0,0,0.1);
        }

        h2 {
            color: #444;
            font-size: 1.8rem;
            border-bottom: 3px dashed var(--gold);
            padding-bottom: 10px;
            margin-top: 20px;
        }

        h3 {
            color: var(--primary);
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        .hayat-glow {
            color: #ff0055;
            font-size: 1.3em;
            text-transform: uppercase;
            font-weight: 900;
            text-shadow: 0 0 15px rgba(255,0,85,0.8), 0 0 30px rgba(255,0,85,0.5);
            display: inline-block;
            animation: heartbeat 1.5s infinite;
        }

        @keyframes heartbeat {
            0%, 30%, 60% { transform: scale(1); }
            15%, 45% { transform: scale(1.15); }
        }

        /* ========================================= */
        /* BOUTONS ET INTERACTIONS                   */
        /* ========================================= */
        .quiz-box {
            background: rgba(255,255,255,0.7);
            border-radius: 20px;
            padding: 25px;
            margin-bottom: 20px;
            border: 2px solid white;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
        }

        .btn {
            background: linear-gradient(45deg, var(--primary), var(--pink-dark));
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 900;
            font-family: inherit;
            font-size: 1.1rem;
            transition: 0.4s;
            margin: 10px;
            box-shadow: 0 5px 20px rgba(144,12,63,0.4);
            text-transform: uppercase;
        }

        .btn-small {
            padding: 8px 18px;
            font-size: 0.9rem;
            background: var(--pink-dark);
            text-transform: none;
        }

        .btn:hover {
            background: var(--gold);
            color: #000;
            transform: scale(1.1) rotate(-2deg);
            box-shadow: 0 10px 30px rgba(212,175,55,0.6);
        }

        .btn:active {
            transform: scale(0.95);
        }
        
        .troll-btn {
            background: var(--primary);
            font-size: 1.5rem;
            padding: 20px 40px;
        }

        .tiny-btn {
            display: none;
            font-size: 0.5rem;
            padding: 3px 8px;
            margin-top: 5px;
            opacity: 0.6;
            box-shadow: none;
        }

        .quiz-result {
            font-weight: 900;
            color: var(--primary);
            margin-top: 15px;
            min-height: 25px;
            font-size: 1.2rem;
        }

        /* ========================================= */
        /* JEUX SPECIFIQUES                          */
        /* ========================================= */
        .progress-container {
            width: 100%;
            background: #ddd;
            border-radius: 30px;
            height: 40px;
            margin: 20px 0;
            overflow: hidden;
            border: 3px solid white;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.2);
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #ff4d6d, #900C3F, var(--gold));
            width: 0%;
            transition: width 0.1s;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            color: white;
            font-weight: bold;
            padding-right: 10px;
        }

        .vault-input {
            width: 80%;
            padding: 15px;
            border-radius: 30px;
            border: 2px solid var(--primary);
            font-size: 1.2rem;
            text-align: center;
            font-family: inherit;
            margin-bottom: 15px;
            outline: none;
        }
        
        .memory-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
            margin-top: 20px;
        }

        .memory-card {
            width: 100%;
            aspect-ratio: 1;
            background: var(--primary);
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.3s;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2.5rem;
            color: transparent;
            border: 3px solid white;
        }

        .memory-card.flipped {
            background: white;
            color: var(--primary);
            transform: rotateY(180deg);
        }

        .memory-card.matched {
            background: var(--gold);
            color: white;
            pointer-events: none;
        }

        #titi-area {
            width: 100%;
            height: 250px;
            background: rgba(0,0,0,0.1);
            border-radius: 15px;
            position: relative;
            overflow: hidden;
            border: 2px dashed var(--primary);
        }

        .moving-titi {
            position: absolute;
            font-size: 2.5rem;
            cursor: crosshair;
            transition: 0.4s;
        }

        .keypad {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            max-width: 250px;
            margin: 0 auto;
        }

        .key {
            background: white;
            border: 2px solid var(--primary);
            color: var(--primary);
            font-size: 1.5rem;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            transition: 0.2s;
        }

        .code-display {
            font-size: 2rem;
            letter-spacing: 10px;
            background: #eee;
            border-radius: 10px;
            padding: 10px;
            margin-bottom: 20px;
            font-weight: bold;
            min-height: 40px;
        }

        .slot-machine {
            font-size: 1.5rem;
            background: black;
            color: gold;
            padding: 20px;
            border-radius: 15px;
            border: 4px solid var(--gold);
            margin: 20px 0;
            font-weight: bold;
            text-transform: uppercase;
            height: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .scanner-container {
            width: 150px;
            height: 150px;
            margin: 20px auto;
            border: 4px solid var(--primary);
            border-radius: 20px;
            position: relative;
            overflow: hidden;
            background: rgba(0,0,0,0.05);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 4rem;
            cursor: pointer;
        }

        .scan-line {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: #00ff00;
            box-shadow: 0 0 10px #00ff00, 0 0 20px #00ff00;
            display: none;
            animation: scanAnim 2s infinite linear;
        }

        @keyframes scanAnim {
            0% { top: 0; }
            50% { top: 100%; }
            100% { top: 0; }
        }

        .scratch-container {
            width: 100%;
            max-width: 300px;
            height: 150px;
            margin: 20px auto;
            position: relative;
            background: var(--gold);
            border-radius: 15px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            font-weight: bold;
            color: black;
            border: 4px solid var(--primary);
        }

        .scratch-grid {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: grid;
            grid-template-columns: repeat(10, 1fr);
            grid-template-rows: repeat(5, 1fr);
        }

        .scratch-block {
            background: #888;
            border: 1px solid #999;
            transition: opacity 0.2s;
        }

        #mahr-btn-rich {
            position: relative;
        }
        
        .patience-zone {
            width: 100%;
            height: 200px;
            background: rgba(144,12,63,0.1);
            border: 3px dashed var(--primary);
            border-radius: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 4rem;
            position: relative;
            margin-top: 20px;
        }

        .patience-timer {
            font-size: 3rem;
            font-weight: bold;
            color: var(--primary);
            position: absolute;
        }

        .find-ring-grid {
            display: grid;
            grid-template-columns: repeat(10, 1fr);
            gap: 5px;
            font-size: 1.5rem;
            background: rgba(255,255,255,0.5);
            padding: 10px;
            border-radius: 15px;
        }

        .find-item {
            cursor: pointer;
            transition: 0.2s;
        }

        .find-item:hover {
            transform: scale(1.3);
        }

        .marathon-card {
            background: white;
            padding: 20px;
            border-radius: 15px;
            margin-top: 20px;
            border: 2px solid var(--gold);
            min-height: 150px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        #ring-game-area {
            width: 100%;
            height: 350px;
            position: relative;
            border: 3px dashed var(--primary);
            border-radius: 20px;
            overflow: hidden;
            background: rgba(255,255,255,0.5);
            cursor: crosshair;
        }

        #ring-btn {
            position: absolute;
            top: 40%;
            left: 40%;
            font-size: 4rem;
            background: none;
            border: none;
            cursor: grab;
            transition: 0.1s;
            filter: drop-shadow(0 0 10px gold);
        }

        .wedding-section {
            background: linear-gradient(135deg, rgba(212,175,55,0.2), rgba(255,255,255,0.9));
            border: 5px double var(--gold);
            border-radius: 30px;
            padding: 40px;
            box-shadow: 0 0 40px rgba(212,175,55,0.8);
        }

        /* ========================================= */
        /* LA SECTION HISTOIRE FINALE                */
        /* ========================================= */
        .story-section {
            background: #0a0407;
            color: #ddd;
            border: 2px solid var(--primary);
            border-radius: 30px;
            padding: 40px;
            margin-top: 50px;
            text-align: left;
            box-shadow: 0 0 50px rgba(144, 12, 63, 0.5);
        }

        .story-section p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .story-title {
            color: var(--gold);
            font-size: 2.5rem;
            margin-bottom: 30px;
            text-align: center;
            border-bottom: 1px solid var(--primary);
            padding-bottom: 15px;
        }

        /* ========================================= */
        /* TRADUCTION & AUTRES                       */
        /* ========================================= */
        .secret-translator {
            position: fixed;
            bottom: 15px;
            right: 15px;
            opacity: 0.15;
            cursor: pointer;
            font-size: 25px;
            z-index: 100;
            transition: 0.3s;
            background: rgba(255,255,255,0.5);
            border-radius: 50%;
            padding: 10px;
        }

        .secret-translator:hover {
            opacity: 1;
            transform: scale(1.3) rotate(180deg);
            box-shadow: 0 0 20px gold;
        }

        .lang-ar { display: none; }
        .lang-fr { display: block; }
        
        [dir="rtl"] .lang-fr { display: none; }
        [dir="rtl"] .lang-ar { display: block; }
        [dir="rtl"] .story-section { text-align: right; }

        #sad-mode {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: #000;
            z-index: 99999;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            text-align: center;
        }

        #sad-text {
            font-size: 2.5rem;
            color: white;
            text-shadow: 0 0 20px rgba(255,0,0,0.8);
            margin-bottom: 20px;
            font-weight: 900;
        }

        /* Décorations pour alourdir le code HTML */
        .star-decor {
            position: absolute;
            color: rgba(255, 255, 255, 0.2);
            z-index: 0;
            font-size: 10px;
            pointer-events: none;
        }
        
        .hold-btn {
            padding: 30px;
            font-size: 1.5rem;
            border-radius: 50%;
            width: 150px;
            height: 150px;
            border: 5px solid white;
            box-shadow: 0 0 20px var(--primary);
            animation: pulse 2s infinite;
        }

        .detect-bar {
            width: 100%;
            height: 20px;
            background: #ddd;
            border-radius: 10px;
            margin-top: 20px;
            overflow: hidden;
        }

        .detect-fill {
            height: 100%;
            background: var(--dz-green);
            width: 0%;
            transition: width 0.1s;
        }
        
        .intruder-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            justify-content: center;
            margin-top: 20px;
            background: rgba(255,255,255,0.5);
            padding: 15px;
            border-radius: 15px;
            border: 2px solid var(--primary);
        }

        .intruder-item {
            font-size: 2rem;
            cursor: pointer;
            transition: 0.2s;
        }

        .intruder-item:hover {
            transform: scale(1.3);
        }
    </style>
</head>
<body dir="ltr" id="body">

    <div id="mur-decoratif" style="position: absolute; width: 100%; height: 100%; overflow: hidden; z-index: 0;">
        <span class="star-decor" style="top: 10%; left: 5%;">✨</span>
        <span class="star-decor" style="top: 15%; left: 80%;">✨</span>
        <span class="star-decor" style="top: 25%; left: 40%;">✨</span>
        <span class="star-decor" style="top: 35%; left: 15%;">✨</span>
        <span class="star-decor" style="top: 45%; left: 90%;">✨</span>
        <span class="star-decor" style="top: 55%; left: 50%;">✨</span>
        <span class="star-decor" style="top: 65%; left: 25%;">✨</span>
        <span class="star-decor" style="top: 75%; left: 85%;">✨</span>
        <span class="star-decor" style="top: 85%; left: 10%;">✨</span>
        <span class="star-decor" style="top: 95%; left: 60%;">✨</span>
        <span class="star-decor" style="top: 12%; left: 22%;">❤️</span>
        <span class="star-decor" style="top: 32%; left: 72%;">❤️</span>
        <span class="star-decor" style="top: 52%; left: 32%;">❤️</span>
        <span class="star-decor" style="top: 72%; left: 92%;">❤️</span>
        <span class="star-decor" style="top: 92%; left: 42%;">❤️</span>
        <span class="star-decor" style="top: 18%; left: 55%;">✨</span>
        <span class="star-decor" style="top: 28%; left: 88%;">✨</span>
        <span class="star-decor" style="top: 38%; left: 12%;">✨</span>
        <span class="star-decor" style="top: 48%; left: 68%;">✨</span>
        <span class="star-decor" style="top: 58%; left: 35%;">✨</span>
        <span class="star-decor" style="top: 68%; left: 75%;">✨</span>
        <span class="star-decor" style="top: 78%; left: 20%;">✨</span>
        <span class="star-decor" style="top: 88%; left: 55%;">✨</span>
        <span class="star-decor" style="top: 98%; left: 80%;">✨</span>
    </div>

    <div id="main-container">
        
        <div class="glass-card" id="etape1">
            <div class="lang-fr">
                <h1>Pour ma <span class="hayat-glow">hayat</span> Leinah 🇩🇿✨</h1>
                <p>Mon plus beau trompe-l'œil : magnifique à l'extérieur, mais tu caches un caractère de fou à l'intérieur 😂.</p>
                <h2>Étape 1 : L'Échauffement 😈</h2>
                <p>Prouve que tu es prête. Clique 10 fois de suite pour ouvrir le site :</p>
                <div>
                    <button class="btn troll-btn" id="main-btn-fr" onclick="handleMainClick(this, 'fr')">JE T'AIME</button>
                    <br>
                    <button class="btn tiny-btn" id="tiny-btn-fr" onclick="handleTinyClick('fr')">je t'aime</button>
                </div>
            </div>
            <div class="lang-ar">
                <h1>إلى <span class="hayat-glow">حياتي</span> لينة 🇩🇿✨</h1>
                <p>أجمل خداع بصري: جميلة من الخارج، لكنك تخفين طبعاً مجنوناً في الداخل 😂.</p>
                <h2>المرحلة 1: الإحماء 😈</h2>
                <p>أثبتي أنك مستعدة. اضغطي 10 مرات متتالية لفتح الموقع:</p>
                <div>
                    <button class="btn troll-btn" id="main-btn-ar" onclick="handleMainClick(this, 'ar')">أنا أحبك</button>
                    <br>
                    <button class="btn tiny-btn" id="tiny-btn-ar" onclick="handleTinyClick('ar')">أنا أحبك</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape2">
            <div class="lang-fr">
                <h2>Étape 2 : Le Doudou 🧸</h2>
                <div class="quiz-box">
                    <h3>C'est qui le doudou numéro 1 ?</h3>
                    <button class="btn btn-small" onclick="checkDoudou('merwan')">Merwan</button>
                    <button class="btn btn-small" onclick="checkDoudou('titi')">Titi</button>
                    <p class="quiz-result" id="doudou-res-fr"></p>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 2: الدودو 🧸</h2>
                <div class="quiz-box">
                    <h3>من هو الدودو الأول؟</h3>
                    <button class="btn btn-small" onclick="checkDoudou('merwan')">مروان</button>
                    <button class="btn btn-small" onclick="checkDoudou('titi')">تيتي</button>
                    <p class="quiz-result" id="doudou-res-ar"></p>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape3">
            <div class="lang-fr">
                <h2>Étape 3 : Les Dossiers ⚖️</h2>
                <div class="quiz-box" id="couple-quiz-1">
                    <h3>Qui boude pour un oui ou pour un non ? 🙄</h3>
                    <button class="btn btn-small" onclick="checkCouple(1, 'moi')">Moi</button>
                    <button class="btn btn-small" onclick="checkCouple(1, 'toi')">Toi</button>
                    <p class="quiz-result" id="couple-res-1"></p>
                </div>
                <div class="quiz-box locked-section" id="couple-quiz-2">
                    <h3>Que dois-je t'acheter pour te calmer quand tu boudes ? 😋</h3>
                    <button class="btn btn-small" onclick="checkCouple(2, 'fleur')">Un bouquet de roses</button>
                    <button class="btn btn-small" onclick="checkCouple(2, 'chips')">Des chips poulet et une compote</button>
                    <p class="quiz-result" id="couple-res-2"></p>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 3: الملفات ⚖️</h2>
                <div class="quiz-box" id="couple-quiz-1-ar">
                    <h3>من يغضب لأتفه الأسباب؟ 🙄</h3>
                    <button class="btn btn-small" onclick="checkCouple(1, 'moi')">أنا</button>
                    <button class="btn btn-small" onclick="checkCouple(1, 'toi')">أنتِ</button>
                    <p class="quiz-result" id="couple-res-1-ar"></p>
                </div>
                <div class="quiz-box locked-section" id="couple-quiz-2-ar">
                    <h3>ماذا يجب أن أشتري لك لأهدئك؟ 😋</h3>
                    <button class="btn btn-small" onclick="checkCouple(2, 'fleur')">باقة ورود</button>
                    <button class="btn btn-small" onclick="checkCouple(2, 'chips')">شيبس دجاج وكومبوت</button>
                    <p class="quiz-result" id="couple-res-2-ar"></p>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape4">
            <div class="lang-fr">
                <h2>Étape 4 : Memory de nos kiffs 🧠</h2>
                <p>Trouve toutes les paires (Sushis, Trompe l'œil, etc.) pour avancer !</p>
                <div class="memory-grid" id="memory-grid"></div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 4: ذاكرة أشيائنا المفضلة 🧠</h2>
                <p>جدي كل الأزواج للتقدم!</p>
                <div class="memory-grid" id="memory-grid-ar"></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape5">
            <div class="lang-fr">
                <h2>Étape 5 : Attrape Titi 🐥</h2>
                <p>Il a volé ta compote ! Attrape-le 4 fois pour la récupérer.</p>
                <p style="font-weight:bold; color:var(--primary);">Score : <span id="titi-score">0</span> / 4</p>
                <div id="titi-area">
                    <div class="moving-titi" id="titi-target" onclick="catchTiti()">🐥</div>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 5: أمسكي تيتي 🐥</h2>
                <p>لقد سرق الكومبوت! أمسكيه 4 مرات لاستعادتها.</p>
                <p style="font-weight:bold; color:var(--primary);">النتيجة: <span id="titi-score-ar">0</span> / 4</p>
                <div id="titi-area-ar">
                    <div class="moving-titi" id="titi-target-ar" onclick="catchTiti()">🐥</div>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape6">
            <div class="lang-fr">
                <h2>Étape 6 : La Sécurité 🔐</h2>
                <p>Quel est mon seul et unique vrai rival ? (Une boisson légendaire)</p>
                <input type="text" class="vault-input" id="vault-input-fr" placeholder="Écris ici...">
                <button class="btn" onclick="checkVault('fr')">Ouvrir</button>
                <p class="quiz-result" id="vault-res-fr"></p>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 6: الأمان 🔐</h2>
                <p>من هو منافسي الوحيد؟ (مشروب أسطوري)</p>
                <input type="text" class="vault-input" id="vault-input-ar" placeholder="اكتبي هنا..." dir="rtl">
                <button class="btn" onclick="checkVault('ar')">فتح</button>
                <p class="quiz-result" id="vault-res-ar"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape7">
            <div class="lang-fr">
                <h2>Étape 7 : Preuve d'effort ⚡</h2>
                <p>Spam le bouton pour remplir la jauge ! (Allez la flemmasse, c'est facile)</p>
                <div class="progress-container">
                    <div class="progress-bar" id="love-bar">0%</div>
                </div>
                <button class="btn troll-btn" style="width:100%;" onclick="fillLoveBar()">❤️ SPAM MOI ❤️</button>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 7: دليل الجهد ⚡</h2>
                <p>اضغطي بسرعة لملء العداد! (هيا يا كسولة، إنه سهل)</p>
                <div class="progress-container">
                    <div class="progress-bar" id="love-bar-ar">0%</div>
                </div>
                <button class="btn troll-btn" style="width:100%;" onclick="fillLoveBar()">❤️ اضغطي بقوة ❤️</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape8">
            <div class="lang-fr">
                <h2>Étape 8 : Le Digicode DZ 🇩🇿</h2>
                <p>L'indicatif de la puissance absolue. Prouve tes origines.</p>
                <div class="code-display" id="code-display-fr">---</div>
                <div class="keypad">
                    <button class="key" onclick="pressKey(1)">1</button>
                    <button class="key" onclick="pressKey(2)">2</button>
                    <button class="key" onclick="pressKey(3)">3</button>
                    <button class="key" onclick="pressKey(4)">4</button>
                    <button class="key" onclick="pressKey(5)">5</button>
                    <button class="key" onclick="pressKey(6)">6</button>
                    <button class="key" onclick="pressKey(7)">7</button>
                    <button class="key" onclick="pressKey(8)">8</button>
                    <button class="key" onclick="pressKey(9)">9</button>
                    <button class="key" style="grid-column: 2;" onclick="pressKey(0)">0</button>
                </div>
                <p class="quiz-result" id="code-res-fr"></p>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 8: الرمز السري 🇩🇿</h2>
                <p>رمز القوة المطلقة. أثبتي أصولك.</p>
                <div class="code-display" id="code-display-ar">---</div>
                <div class="keypad">
                    <button class="key" onclick="pressKey(1)">1</button>
                    <button class="key" onclick="pressKey(2)">2</button>
                    <button class="key" onclick="pressKey(3)">3</button>
                    <button class="key" onclick="pressKey(4)">4</button>
                    <button class="key" onclick="pressKey(5)">5</button>
                    <button class="key" onclick="pressKey(6)">6</button>
                    <button class="key" onclick="pressKey(7)">7</button>
                    <button class="key" onclick="pressKey(8)">8</button>
                    <button class="key" onclick="pressKey(9)">9</button>
                    <button class="key" style="grid-column: 2;" onclick="pressKey(0)">0</button>
                </div>
                <p class="quiz-result" id="code-res-ar"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape9">
            <div class="lang-fr">
                <h2>Étape 9 : Casino du Destin 🎰</h2>
                <p>Tire le levier pour voir ce que je t'offre (C'est le destin qui décide).</p>
                <div class="slot-machine" id="slot-fr">❓❓❓</div>
                <button class="btn" id="btn-slot-fr" onclick="spinSlot('fr')">Tirer le levier</button>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 9: كازينو القدر 🎰</h2>
                <p>اسحبي الرافعة لترين هديتك (القدر هو من يقرر).</p>
                <div class="slot-machine" id="slot-ar">❓❓❓</div>
                <button class="btn" id="btn-slot-ar" onclick="spinSlot('ar')">اسحبي الرافعة</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape10">
            <div class="lang-fr">
                <h2>Étape 10 : Détecteur de Mensonge 📡</h2>
                <p>Maintiens ton doigt 3 secondes sans lâcher pour prouver que tu m'aimes pour de vrai.</p>
                <button class="btn hold-btn" id="hold-fr" onmousedown="startHold('fr')" onmouseup="endHold('fr')" onmouseleave="endHold('fr')" ontouchstart="startHold('fr')" ontouchend="endHold('fr')">MAINTIENS</button>
                <div class="detect-bar"><div class="detect-fill" id="fill-fr"></div></div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 10: كشف الكذب 📡</h2>
                <p>أبقي إصبعك 3 ثوانٍ دون إفلات لإثبات أنك تحبينني حقاً.</p>
                <button class="btn hold-btn" id="hold-ar" onmousedown="startHold('ar')" onmouseup="endHold('ar')" onmouseleave="endHold('ar')" ontouchstart="startHold('ar')" ontouchend="endHold('ar')">اضغطي مطولاً</button>
                <div class="detect-bar"><div class="detect-fill" id="fill-ar"></div></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape11">
            <div class="lang-fr">
                <h2>Étape 11 : Scanner Biométrique 🧬</h2>
                <p>Clique pour scanner ton cœur et vérifier ton ADN DZ.</p>
                <div class="scanner-container" id="scanner-btn-fr" onclick="runScanner('fr')">
                    ❤️
                    <div class="scan-line" id="scan-line-fr"></div>
                </div>
                <p class="quiz-result" id="scan-res-fr"></p>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 11: الفحص الحيوي 🧬</h2>
                <p>اضغطي لفحص قلبك والتحقق من الحمض النووي الجزائري الخاص بك.</p>
                <div class="scanner-container" id="scanner-btn-ar" onclick="runScanner('ar')">
                    ❤️
                    <div class="scan-line" id="scan-line-ar"></div>
                </div>
                <p class="quiz-result" id="scan-res-ar"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape12">
            <div class="lang-fr">
                <h2>Étape 12 : L'Intrus 👀</h2>
                <p>Trouve le Trompe-l'œil 🍰 caché parmi les Sushis 🍣 !</p>
                <div class="intruder-grid" id="intruder-grid-fr"></div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 12: الدخيل 👀</h2>
                <p>جدي الخداع البصري 🍰 المخفي بين السوشي 🍣!</p>
                <div class="intruder-grid" id="intruder-grid-ar"></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape13">
            <div class="lang-fr">
                <h2>Étape 13 : Gratte-Gratte 🎟️</h2>
                <p>Passe ton doigt pour dévoiler la surprise dorée !</p>
                <div class="scratch-container">
                    VIP MARIAGE💍
                    <div class="scratch-grid" id="scratch-grid-fr"></div>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 13: بطاقة الحظ 🎟️</h2>
                <p>امسحي لاكتشاف المفاجأة الذهبية!</p>
                <div class="scratch-container">
                    زفاف VIP💍
                    <div class="scratch-grid" id="scratch-grid-ar"></div>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape14">
            <div class="lang-fr">
                <h2>Étape 14 : Le Juste Prix (La Dot) 💰</h2>
                <p>Combien vaux-tu ? Choisis bien ta dot.</p>
                <button class="btn btn-small" onclick="alert('Mdrrr tu vaux bien plus que ça la ji3ena !')">100 €</button>
                <button class="btn btn-small" onclick="alert('Toujours pas, tu te sous-estimes lfm de mvi !')">10 000 €</button>
                <button class="btn" id="mahr-btn-rich-fr" onmouseover="fleeMahrBtn('fr')" ontouchstart="fleeMahrBtn('fr')">1 MILLIARD 💎</button>
                <br>
                <button class="btn tiny-btn" id="hidden-mahr-fr" style="display:none;" onclick="winMahr('fr')">J'ai pas de prix ❤️</button>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 14: المهر 💰</h2>
                <p>كم تساوين؟ اختاري مهرك.</p>
                <button class="btn btn-small" onclick="alert('ههه أنتِ تساوين أكثر بكثير يا جيعانة!')">100 €</button>
                <button class="btn btn-small" onclick="alert('لا، أنتِ تستهينين بنفسك يا مرأة حياتي!')">10 000 €</button>
                <button class="btn" id="mahr-btn-rich-ar" onmouseover="fleeMahrBtn('ar')" ontouchstart="fleeMahrBtn('ar')">مليار 💎</button>
                <br>
                <button class="btn tiny-btn" id="hidden-mahr-ar" style="display:none;" onclick="winMahr('ar')">ليس لي ثمن ❤️</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape15">
            <div class="lang-fr">
                <h2>Étape 15 : La Patience ⏳</h2>
                <p>Mets ton doigt/souris dans la case rouge et NE BOUGE PLUS pendant 5 secondes.</p>
                <div class="patience-zone" id="pz-fr" onmouseenter="startPatience('fr')" onmouseleave="failPatience('fr')" ontouchstart="startPatience('fr')" ontouchend="failPatience('fr')">
                    <span class="patience-timer" id="pt-fr">5</span>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 15: الصبر ⏳</h2>
                <p>ضعي إصبعك/الماوس في المربع الأحمر ولا تتحركي لمدة 5 ثوانٍ.</p>
                <div class="patience-zone" id="pz-ar" onmouseenter="startPatience('ar')" onmouseleave="failPatience('ar')" ontouchstart="startPatience('ar')" ontouchend="failPatience('ar')">
                    <span class="patience-timer" id="pt-ar">5</span>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape16">
            <div class="lang-fr">
                <h2>Étape 16 : Test de Vue 👁️</h2>
                <p>Trouve la bague 💍 cachée parmi tous ces Capri-Suns.</p>
                <div class="find-ring-grid" id="frg-fr"></div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 16: فحص النظر 👁️</h2>
                <p>جدي الخاتم 💍 المخفي بين الكابري سن.</p>
                <div class="find-ring-grid" id="frg-ar"></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape17">
            <div class="lang-fr">
                <h2>Étape 17 : L'Interrogatoire de la Mairie 📝</h2>
                <p>Réponds correctement aux 10 questions d'affilée. Une erreur = tu recommences tout.</p>
                <h3 style="color:var(--gold);">Question <span id="q-num-fr">1</span>/10</h3>
                <div class="marathon-card">
                    <h3 id="marathon-q-fr">Chargement...</h3>
                    <div id="marathon-btns-fr"></div>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 17: ماراثون البلدية 📝</h2>
                <p>أجيبي بشكل صحيح على 10 أسئلة متتالية. خطأ واحد = تبدأين من جديد.</p>
                <h3 style="color:var(--gold);">السؤال <span id="q-num-ar">1</span>/10</h3>
                <div class="marathon-card">
                    <h3 id="marathon-q-ar">جاري التحميل...</h3>
                    <div id="marathon-btns-ar"></div>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape18">
            <div class="lang-fr">
                <h2>Étape 18 : Code PIN du Cœur 🔢</h2>
                <p>Quel est le code ? Indice : L'année où l'on est aujourd'hui.</p>
                <div class="code-display" id="pin-display-fr">----</div>
                <div class="keypad">
                    <button class="key" onclick="pressPin(1)">1</button>
                    <button class="key" onclick="pressPin(2)">2</button>
                    <button class="key" onclick="pressPin(3)">3</button>
                    <button class="key" onclick="pressPin(4)">4</button>
                    <button class="key" onclick="pressPin(5)">5</button>
                    <button class="key" onclick="pressPin(6)">6</button>
                    <button class="key" onclick="pressPin(7)">7</button>
                    <button class="key" onclick="pressPin(8)">8</button>
                    <button class="key" onclick="pressPin(9)">9</button>
                    <button class="key" style="grid-column: 2;" onclick="pressPin(0)">0</button>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 18: الرمز السري للقلب 🔢</h2>
                <p>ما هو الرمز؟ تلميح: السنة الحالية.</p>
                <div class="code-display" id="pin-display-ar">----</div>
                <div class="keypad">
                    <button class="key" onclick="pressPin(1)">1</button>
                    <button class="key" onclick="pressPin(2)">2</button>
                    <button class="key" onclick="pressPin(3)">3</button>
                    <button class="key" onclick="pressPin(4)">4</button>
                    <button class="key" onclick="pressPin(5)">5</button>
                    <button class="key" onclick="pressPin(6)">6</button>
                    <button class="key" onclick="pressPin(7)">7</button>
                    <button class="key" onclick="pressPin(8)">8</button>
                    <button class="key" onclick="pressPin(9)">9</button>
                    <button class="key" style="grid-column: 2;" onclick="pressPin(0)">0</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape19">
            <div class="lang-fr">
                <h2>Étape 19 : Le Boss Final Ultime 💍</h2>
                <p>La bague se téléporte et disparaît ! Attrape-la pour en finir !</p>
                <div id="ring-game-area" onmousemove="moveRingUltimate()" ontouchmove="moveRingUltimate()">
                    <button id="ring-btn" onclick="winRingGame()">💍</button>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 19: الزعيم الأخير المطلق 💍</h2>
                <p>الخاتم ينتقل ويختفي! أمسكيه للانتهاء!</p>
                <div id="ring-game-area" onmousemove="moveRingUltimate()" ontouchmove="moveRingUltimate()">
                    <button id="ring-btn" onclick="winRingGame()">💍</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section wedding-section" id="etape21">
            <div class="lang-fr">
                <h1 style="font-size: 3.5rem; text-transform: uppercase;">InshAllah 💍👑</h1>
                <p style="font-size: 1.3rem; font-weight: bold;">Félicitations ma femme, tu as fini ce cauchemar !</p>
                <p>Tu as prouvé que t'es une vraie guerrière. On fera le plus beau des mariages, Karakou, Caftan, des montagnes de chips poulet et de sushis.</p>
                <p>Mais avant ça...</p>
                <button class="btn" style="margin-top: 30px; background: var(--gold); color: black; padding: 20px 40px; font-size: 1.5rem;" onclick="unlockStory()">Lis ça s'il te plaît 📖</button>
            </div>
            <div class="lang-ar">
                <h1 style="font-size: 3.5rem;">إن شاء الله 💍👑</h1>
                <p style="font-size: 1.3rem; font-weight: bold;">مبروك زوجتي، لقد أنهيتِ هذا الكابوس!</p>
                <p>أنتِ محاربة. سنقيم أجمل عرس، بالقفطان والكاراكو، وجبال من شيبس الدجاج والسوشي.</p>
                <p>ولكن قبل ذلك...</p>
                <button class="btn" style="margin-top: 30px; background: var(--gold); color: black; padding: 20px 40px; font-size: 1.5rem;" onclick="unlockStory()">اقرئي هذا من فضلك 📖</button>
            </div>
        </div>

        <div class="story-section locked-section" id="etape-histoire">
            <div class="lang-fr">
                <h2 class="story-title">À Cœur Ouvert 🖤</h2>
                <p>Maintenant que tu as fini toutes ces conneries, il faut que je te parle sah. Mon histoire, tu ne la connais peut-être pas en entier.</p>
                <p>Je suis né à Limoges. Mais direct après ma naissance, on m'a envoyé en Algérie, vivre chez la famille de mon père. Ça a été le début de l'enfer. C'était une vraie dinguerie comment sa famille nous a fait la misère, à ma mère et à moi. Ils nous pourrissaient la vie, tous les jours, avec de la méchanceté gratuite. Mon seul rempart, c'était ma mère. Je la préférais à tout, c'était ma seule lumière là-bas.</p>
                <p>À l'âge de 6 ans, je suis revenu définitivement en France. Mais le mal était fait. J'avais un énorme retard scolaire en français. À l'école, c'était terrible. Je me faisais harceler, rabaisser tous les jours. C'était tellement grave, la violence de l'école, qu'on a décidé de me renvoyer en Algérie, en pensant que ça serait pour mon bien.</p>
                <p>Mais là-bas... c'était pire. J'ai vécu un vrai cauchemar. J'ai vu ce qu'aucun gosse devrait voir. Une attaque à main armée direct sous mes yeux... j'ai vu mes potes tomber, se faire tuer devant moi. J'ai vu la mort, le sang, la vraie galère. Ça m'a détruit.</p>
                <p>J'ai fini par rentrer en France. Je me suis installé à Lille pour vivre toute ma vie. J'ai essayé de me reconstruire, mais j'avais le cœur bousillé, je pensais que j'allais rester dans le noir pour toujours.</p>
                <p>Et puis... tu es apparue, Leinah. Mon trompe-l'œil préféré. T'as effacé tout ce malheur. T'es ma récompense après toute cette galère. Je t'aime plus que tout, et InshAllah, tu seras la mère de mes enfants.</p>
                <div style="text-align:center; margin-top: 40px;">
                    <button class="btn" style="background: var(--gold); color: black;" onclick="explodeConfettiFinal()">Je t'aime ❤️</button>
                </div>
            </div>
            <div class="lang-ar">
                <h2 class="story-title">بقلب مفتوح 🖤</h2>
                <p>الآن وقد انتهيتِ من كل هذا، يجب أن أتحدث إليكِ بصدق. قصتي، ربما لا تعرفينها بالكامل.</p>
                <p>لقد ولدت في ليموج. ولكن بعد ولادتي مباشرة، تم إرسالي إلى الجزائر للعيش مع عائلة والدي. كانت تلك بداية الجحيم. لقد أذاقونا الويلات، أنا وأمي. كانوا يفسدون حياتنا كل يوم بلؤم لا مبرر له. حصني الوحيد كان أمي. كنت أفضلها على كل شيء، كانت نوري الوحيد هناك.</p>
                <p>في سن السادسة، عدت نهائياً إلى فرنسا. لكن الضرر كان قد وقع. كان لدي تأخر دراسي كبير في اللغة الفرنسية. في المدرسة، كان الأمر مروعاً. تعرضت للتنمر والإذلال كل يوم. كان الأمر خطيراً جداً لدرجة أنهم قرروا إعادتي إلى الجزائر، ظناً منهم أن ذلك لمصلحتي.</p>
                <p>لكن هناك... كان الأمر أسوأ. عشت كابوساً حقيقياً. رأيت ما لا ينبغي لأي طفل أن يراه. هجوم مسلح أمامي مباشرة... رأيت أصدقائي يسقطون ويُقتلون أمام عيني. رأيت الموت والدم والمعاناة الحقيقية. لقد دمرني ذلك.</p>
                <p>في النهاية، عدت إلى فرنسا. استقريت في ليل لأعيش بقية حياتي. حاولت إعادة بناء نفسي، لكن قلبي كان محطماً، اعتقدت أنني سأبقى في الظلام إلى الأبد.</p>
                <p>ثم... ظهرتِ أنتِ يا لينة. لقد محوتِ كل هذا البؤس. أنتِ مكافأتي بعد كل هذه المعاناة. أحبك أكثر من أي شيء، وإن شاء الله، ستكونين أم أطفالي.</p>
                <div style="text-align:center; margin-top: 40px;">
                    <button class="btn" style="background: var(--gold); color: black;" onclick="explodeConfettiFinal()">أحبك ❤️</button>
                </div>
            </div>
        </div>

    </div>

    <div id="sad-mode">
        <h1 id="sad-text"></h1>
        <img src="https://media.tenor.com/J7r5uN2nEbwAAAAC/neymar-crying.gif" alt="Triste">
    </div>

    <div class="secret-translator" id="translator" onclick="toggleLanguage()" title="Traduction">✨</div>

    <script>
        function unlockSection(id) {
            const section = document.getElementById(id);
            if(section && !section.classList.contains('unlocked')) {
                section.classList.add('unlocked');
                setTimeout(() => {
                    section.scrollIntoView({ behavior: 'smooth', block: 'center' });
                }, 600);
            }
        }

        /* ======================================================== */
        /* ETAPE 1: PIEGE                                           */
        /* ======================================================== */
        let clickCount = 0;
        function handleMainClick(btn, lang) {
            if (btn.dataset.isTrap === "true") {
                activateSadMode(lang);
                return;
            }
            clickCount++;
            if (clickCount === 8) { 
                document.getElementById('main-btn-fr').innerText = "Je t'aime pas"; 
                document.getElementById('main-btn-ar').innerText = "أنا لا أحبك";
                document.getElementById('main-btn-fr').style.background = "#333"; 
                document.getElementById('main-btn-ar').style.background = "#333";
                document.getElementById('main-btn-fr').dataset.isTrap = "true"; 
                document.getElementById('main-btn-ar').dataset.isTrap = "true";
                document.getElementById('tiny-btn-fr').style.display = 'inline-block'; 
                document.getElementById('tiny-btn-ar').style.display = 'inline-block';
            }
        }
        function handleTinyClick(lang) {
            clickCount++;
            if (clickCount >= 10) { 
                document.getElementById('main-btn-fr').innerText = "Validé ❤️"; 
                document.getElementById('main-btn-ar').innerText = "تم ❤️";
                document.getElementById('main-btn-fr').style.background = "var(--gold)"; 
                document.getElementById('main-btn-fr').dataset.isTrap = "false";
                document.getElementById('tiny-btn-fr').style.display = 'none'; 
                document.getElementById('tiny-btn-ar').style.display = 'none';
                unlockSection('etape2');
            }
        }

        /* ======================================================== */
        /* ETAPES 2 & 3: QUIZZ                                      */
        /* ======================================================== */
        function checkDoudou(a) { 
            if(a === 'titi') { 
                document.getElementById('doudou-res-fr').innerText = "Normal c'est lui le sang ❤️"; 
                document.getElementById('doudou-res-ar').innerText = "برافو ❤️"; 
                unlockSection('etape3'); 
            } else { 
                document.getElementById('doudou-res-fr').innerText = "Faux 😒"; 
            } 
        }

        function checkCouple(q, a) {
            if(q === 1 && a === 'toi') { 
                unlockSection('couple-quiz-2'); 
                unlockSection('couple-quiz-2-ar'); 
            }
            if(q === 2 && a === 'chips') { 
                document.getElementById('couple-res-2').innerText = "Bingo ! Chips poulet & Compote 🤤"; 
                document.getElementById('couple-res-2-ar').innerText = "صحيح! شيبس وكومبوت 🤤"; 
                unlockSection('etape4'); 
                initMemoryGame(); 
            }
            else if(q === 2) { 
                document.getElementById('couple-res-2').innerText = "Menteuse tu préfères manger 😂"; 
                document.getElementById('couple-res-2-ar').innerText = "كذابة تحبين الأكل 😂"; 
            }
        }

        /* ======================================================== */
        /* ETAPE 4: MEMORY SUSHIS ET TROMPE L'OEIL                  */
        /* ======================================================== */
        const cardsArray = ['🧃','🧃','🍣','🍣','🍰','🍰','🐥','🐥'];
        let firstCard = null, secondCard = null, matches = 0;
        
        function initMemoryGame() {
            const grid = document.getElementById('memory-grid'); 
            if(grid.innerHTML !== "") return;
            
            let shuffled = cardsArray.sort(() => 0.5 - Math.random());
            shuffled.forEach(emoji => { 
                const card = document.createElement('div'); 
                card.classList.add('memory-card'); 
                card.dataset.emoji = emoji; 
                card.onclick = () => flipCard(card); 
                grid.appendChild(card); 
            });
            
            document.getElementById('memory-grid-ar').innerHTML = grid.innerHTML; 
            document.querySelectorAll('#memory-grid-ar .memory-card').forEach(c => {
                c.onclick = () => flipCard(c);
            });
        }

        function flipCard(card) {
            if (card.classList.contains('flipped') || secondCard) return;
            
            card.classList.add('flipped');
            card.innerText = card.dataset.emoji;
            
            if (!firstCard) {
                firstCard = card;
            } else {
                secondCard = card;
                checkMemoryMatch();
            }
        }

        function checkMemoryMatch() {
            if (firstCard.dataset.emoji === secondCard.dataset.emoji) {
                firstCard.classList.add('matched');
                secondCard.classList.add('matched'); 
                firstCard = null;
                secondCard = null;
                matches++;
                if (matches === 4 || matches === 8) {
                    setTimeout(() => {
                        unlockSection('etape5');
                        initTiti();
                    }, 500);
                }
            } else { 
                setTimeout(() => { 
                    firstCard.classList.remove('flipped');
                    secondCard.classList.remove('flipped'); 
                    firstCard.innerText = '';
                    secondCard.innerText = ''; 
                    firstCard = null;
                    secondCard = null; 
                }, 600); 
            }
        }

        /* ======================================================== */
        /* ETAPE 5: TITI                                            */
        /* ======================================================== */
        let titiCount = 0, titiInterval;
        function initTiti() {
            titiInterval = setInterval(() => {
                const t1 = document.getElementById('titi-target');
                const t2 = document.getElementById('titi-target-ar');
                if(t1) { t1.style.left = Math.random() * 80 + '%'; t1.style.top = Math.random() * 80 + '%'; }
                if(t2) { t2.style.left = Math.random() * 80 + '%'; t2.style.top = Math.random() * 80 + '%'; }
            }, 800); 
        }
        function catchTiti() {
            titiCount++; 
            document.getElementById('titi-score').innerText = titiCount; 
            document.getElementById('titi-score-ar').innerText = titiCount;
            if(titiCount >= 4) { 
                clearInterval(titiInterval); 
                document.getElementById('titi-target').style.display = 'none'; 
                unlockSection('etape6'); 
            }
        }

        /* ======================================================== */
        /* ETAPE 6: MOT DE PASSE                                    */
        /* ======================================================== */
        function checkVault(lang) {
            const val = document.getElementById(lang === 'fr' ? 'vault-input-fr' : 'vault-input-ar').value.toLowerCase().replace(/\s/g, '');
            if(val === 'capri-sun' || val === 'caprisun' || val === 'كابريسن') { 
                unlockSection('etape7'); 
            }
        }

        /* ======================================================== */
        /* ETAPE 7: JAUGE                                           */
        /* ======================================================== */
        let loveProgress = 0;
        function fillLoveBar() {
            if(loveProgress >= 100) return; 
            loveProgress += 10;
            document.getElementById('love-bar').style.width = loveProgress + "%"; 
            document.getElementById('love-bar-ar').style.width = loveProgress + "%";
            setTimeout(() => { 
                if(loveProgress > 0 && loveProgress < 100) { 
                    loveProgress -= 3; 
                    if(loveProgress < 0) loveProgress = 0; 
                    document.getElementById('love-bar').style.width = loveProgress + "%"; 
                } 
            }, 800);
            if(loveProgress >= 100) {
                unlockSection('etape8');
            }
        }

        /* ======================================================== */
        /* ETAPE 8: DIGICODE                                        */
        /* ======================================================== */
        let currentCode = "";
        function pressKey(num) {
            if(currentCode.length >= 3) currentCode = ""; 
            currentCode += num;
            document.getElementById('code-display-fr').innerText = currentCode + "---".substring(currentCode.length);
            if(currentCode === "213") {
                unlockSection('etape9');
            }
        }

        /* ======================================================== */
        /* ETAPE 9: CASINO                                          */
        /* ======================================================== */
        let isSpinning = false;
        function spinSlot(lang) {
            if(isSpinning) return;
            isSpinning = true;
            const slot = document.getElementById(lang === 'fr' ? 'slot-fr' : 'slot-ar');
            const arr = ["La vaisselle", "Le grec", "Sushis illimités 🍣", "Trompe-l'œil 🍰"]; 
            let counter = 0;
            const spinInt = setInterval(() => {
                slot.innerText = arr[Math.floor(Math.random() * arr.length)];
                counter++;
                if(counter > 15) { 
                    clearInterval(spinInt); 
                    slot.innerText = lang === 'fr' ? "Sushis payés par ton homme 🍣" : "سوشي غير محدود 🍣"; 
                    slot.style.background = "var(--gold)"; 
                    slot.style.color = "black"; 
                    unlockSection('etape10'); 
                }
            }, 100);
        }

        /* ======================================================== */
        /* ETAPE 10: DETECTEUR                                      */
        /* ======================================================== */
        let holdProgress = 0, holdInterval;
        function startHold(lang) {
            holdProgress = 0;
            holdInterval = setInterval(() => {
                holdProgress += 5; 
                document.getElementById('fill-' + lang).style.width = holdProgress + "%";
                if(holdProgress >= 100) { 
                    clearInterval(holdInterval); 
                    document.getElementById('fill-' + lang).style.background = "var(--gold)"; 
                    document.getElementById('hold-' + lang).onmousedown = null; 
                    document.getElementById('hold-' + lang).ontouchstart = null; 
                    unlockSection('etape11'); 
                }
            }, 150);
        }
        function endHold(lang) { 
            clearInterval(holdInterval); 
            if(holdProgress < 100) {
                holdProgress = 0;
                document.getElementById('fill-' + lang).style.width = "0%";
            } 
        }

        /* ======================================================== */
        /* ETAPE 11: SCANNER                                        */
        /* ======================================================== */
        function runScanner(lang) {
            document.getElementById(lang === 'fr' ? 'scan-line-fr' : 'scan-line-ar').style.display = 'block';
            setTimeout(() => { 
                document.getElementById(lang === 'fr' ? 'scan-line-fr' : 'scan-line-ar').style.display = 'none'; 
                unlockSection('etape12'); 
                initIntruder(); 
            }, 2000);
        }

        /* ======================================================== */
        /* ETAPE 12: L'INTRUS                                       */
        /* ======================================================== */
        function initIntruder() {
            const grids = [document.getElementById('intruder-grid-fr'), document.getElementById('intruder-grid-ar')];
            grids.forEach(grid => {
                if(grid.innerHTML !== "") return;
                let arr = Array(23).fill('🍣'); 
                arr.push('🍰'); 
                arr = arr.sort(() => 0.5 - Math.random());
                arr.forEach(e => {
                    let div = document.createElement('div'); 
                    div.className = 'intruder-item'; 
                    div.innerText = e;
                    div.onclick = () => { 
                        if(e === '🍰') { 
                            div.style.transform = "scale(2)"; 
                            setTimeout(() => {
                                unlockSection('etape13');
                                initScratch();
                            }, 500); 
                        } else { 
                            div.style.opacity = '0.2'; 
                        } 
                    };
                    grid.appendChild(div);
                });
            });
        }

        /* ======================================================== */
        /* ETAPE 13: GRATTE-GRATTE                                  */
        /* ======================================================== */
        let scratchCount = 0;
        function initScratch() {
            const grids = [document.getElementById('scratch-grid-fr'), document.getElementById('scratch-grid-ar')];
            grids.forEach(grid => {
                if(grid.innerHTML !== "") return;
                for(let i=0; i<50; i++) {
                    let block = document.createElement('div'); 
                    block.className = 'scratch-block';
                    const clearBlock = () => { 
                        if(block.style.opacity !== '0') { 
                            block.style.opacity = '0'; 
                            scratchCount++; 
                            if(scratchCount >= 40 || scratchCount >= 90) {
                                unlockSection('etape14');
                            } 
                        } 
                    };
                    block.onmouseover = clearBlock; 
                    block.ontouchmove = clearBlock; 
                    grid.appendChild(block);
                }
            });
        }

        /* ======================================================== */
        /* ETAPE 14: LE JUSTE PRIX                                  */
        /* ======================================================== */
        function fleeMahrBtn(lang) {
            const btnFr = document.getElementById('mahr-btn-rich-fr'); 
            const btnAr = document.getElementById('mahr-btn-rich-ar');
            const x = Math.random() * 200 - 100; 
            const y = Math.random() * 50 - 25;
            
            if(btnFr) btnFr.style.transform = `translate(${x}px, ${y}px)`; 
            if(btnAr) btnAr.style.transform = `translate(${x}px, ${y}px)`;
            
            document.getElementById('hidden-mahr-fr').style.display = "inline-block";
            document.getElementById('hidden-mahr-ar').style.display = "inline-block";
        }
        function winMahr(lang) {
            alert(lang === 'fr' ? "Exactement. Tu n'as pas de prix lfm de mvi. ❤️" : "بالضبط. ليس لك ثمن. ❤️");
            unlockSection('etape15');
        }

        /* ======================================================== */
        /* ETAPE 15: LA PATIENCE                                    */
        /* ======================================================== */
        let patienceTimer, patienceTime = 5;
        function startPatience(lang) {
            clearInterval(patienceTimer);
            document.getElementById('pz-'+lang).style.background = "rgba(0,255,0,0.2)";
            patienceTimer = setInterval(() => {
                patienceTime--;
                document.getElementById('pt-'+lang).innerText = patienceTime;
                if(patienceTime <= 0) {
                    clearInterval(patienceTimer);
                    document.getElementById('pt-'+lang).innerText = "GAGNÉ !";
                    unlockSection('etape16'); 
                    initFindRing();
                }
            }, 1000);
        }
        function failPatience(lang) {
            clearInterval(patienceTimer); 
            patienceTime = 5;
            document.getElementById('pt-'+lang).innerText = patienceTime;
            document.getElementById('pz-'+lang).style.background = "rgba(144,12,63,0.1)";
        }

        /* ======================================================== */
        /* ETAPE 16: OÙ EST LA BAGUE                                */
        /* ======================================================== */
        function initFindRing() {
            const grids = [document.getElementById('frg-fr'), document.getElementById('frg-ar')];
            grids.forEach(grid => {
                if(grid.innerHTML !== "") return;
                let arr = Array(49).fill('🧃');
                arr.push('💍');
                arr = arr.sort(() => 0.5 - Math.random());
                arr.forEach(e => {
                    let div = document.createElement('div');
                    div.className = 'find-item';
                    div.innerText = e;
                    div.onclick = () => { 
                        if(e === '💍') { 
                            div.style.transform = "scale(2)"; 
                            setTimeout(() => {
                                unlockSection('etape17');
                                initMarathon();
                            }, 500); 
                        } else { 
                            div.style.opacity = '0.1'; 
                        } 
                    };
                    grid.appendChild(div);
                });
            });
        }

        /* ======================================================== */
        /* ETAPE 17: L'INTERROGATOIRE GEANT (MARATHON)              */
        /* ======================================================== */
        const marathonQ = [
            { qFr: "Qui est le plus beau ?", qAr: "من الأجمل؟", ansFr: ["Moi", "Moi"], ansAr: ["أنا", "أنا"], correct: 0 },
            { qFr: "Ta boisson ?", qAr: "مشروبك؟", ansFr: ["Eau", "Capri-Sun"], ansAr: ["ماء", "كابري سن"], correct: 1 },
            { qFr: "Le meilleur doudou ?", qAr: "أفضل دودو؟", ansFr: ["Imrane", "Titi"], ansAr: ["عمران", "تيتي"], correct: 1 },
            { qFr: "Qui boude vite ?", qAr: "من يغضب بسرعة؟", ansFr: ["Leinah", "Moi"], ansAr: ["لينة", "أنا"], correct: 0 },
            { qFr: "Ton animal spirituel ?", qAr: "حيوانك الروحي؟", ansFr: ["Gazelle", "Panda affamé"], ansAr: ["غزال", "باندا جائع"], correct: 1 },
            { qFr: "Les chips préférées ?", qAr: "الشيبس المفضل؟", ansFr: ["Fromage", "Poulet"], ansAr: ["جبن", "دجاج"], correct: 1 },
            { qFr: "Le repas du vendredi ?", qAr: "وجبة الجمعة؟", ansFr: ["Tacos", "Couscous"], ansAr: ["تاكوس", "كسكس"], correct: 1 },
            { qFr: "Le meilleur dessert ?", qAr: "أفضل حلوى؟", ansFr: ["Fruit", "Trompe l'oeil"], ansAr: ["فاكهة", "خداع بصري"], correct: 1 },
            { qFr: "Qui a toujours tort ?", qAr: "من يخطئ دائما؟", ansFr: ["L'homme", "La femme"], ansAr: ["الرجل", "المرأة"], correct: 0 },
            { qFr: "Tu m'aimes ?", qAr: "هل تحبينني؟", ansFr: ["Un peu", "À la folie"], ansAr: ["قليلا", "بجنون"], correct: 1 }
        ];
        let currentQ = 0;
        function initMarathon() {
            loadMarathonQ();
        }
        function loadMarathonQ() {
            if(currentQ >= marathonQ.length) { 
                document.getElementById('marathon-q-fr').innerText = "FÉLICITATIONS !"; 
                document.getElementById('marathon-btns-fr').innerHTML = ""; 
                unlockSection('etape18'); 
                return; 
            }
            
            let q = marathonQ[currentQ];
            document.getElementById('q-num-fr').innerText = currentQ + 1;
            document.getElementById('marathon-q-fr').innerText = q.qFr;
            let btnsFr = `<button class="btn" onclick="checkMarathon(0)">${q.ansFr[0]}</button><button class="btn" onclick="checkMarathon(1)">${q.ansFr[1]}</button>`;
            document.getElementById('marathon-btns-fr').innerHTML = btnsFr;

            document.getElementById('q-num-ar').innerText = currentQ + 1;
            document.getElementById('marathon-q-ar').innerText = q.qAr;
            let btnsAr = `<button class="btn" onclick="checkMarathon(0)">${q.ansAr[0]}</button><button class="btn" onclick="checkMarathon(1)">${q.ansAr[1]}</button>`;
            document.getElementById('marathon-btns-ar').innerHTML = btnsAr;
        }
        function checkMarathon(ans) {
            if(ans === marathonQ[currentQ].correct) {
                currentQ++;
                loadMarathonQ();
            } else {
                alert("FAUX ! Tu recommences tout depuis la question 1 ! 😈");
                currentQ = 0;
                loadMarathonQ();
            }
        }

        /* ======================================================== */
        /* ETAPE 18: CODE PIN ANNEE (2026)                          */
        /* ======================================================== */
        let currentPin = "";
        function pressPin(num) {
            const codeSecret = "2026";
            if(currentPin.length >= 4) currentPin = ""; 
            currentPin += num;
            
            document.getElementById('pin-display-fr').innerText = currentPin + "----".substring(currentPin.length);
            document.getElementById('pin-display-ar').innerText = currentPin + "----".substring(currentPin.length);
            
            if(currentPin.length === 4) {
                if(currentPin === codeSecret) { 
                    unlockSection('etape19'); 
                } else { 
                    setTimeout(() => { 
                        currentPin = ""; 
                        document.getElementById('pin-display-fr').innerText = "----"; 
                        document.getElementById('pin-display-ar').innerText = "----"; 
                    }, 500); 
                }
            }
        }

        /* ======================================================== */
        /* ETAPE 19: BAGUE ULTIME BOSS                              */
        /* ======================================================== */
        function moveRingUltimate() {
            const btn = document.getElementById('ring-btn');
            if(Math.random() > 0.1) { 
                btn.style.left = Math.random() * 80 + '%'; 
                btn.style.top = Math.random() * 80 + '%';
                btn.style.opacity = Math.random() > 0.5 ? "0" : "1";
            }
        }
        function winRingGame() {
            document.getElementById('ring-btn').innerText = "💖 ATTRAPÉE 💖";
            document.getElementById('ring-btn').style.transform = "scale(1.5)";
            document.getElementById('ring-btn').style.opacity = "1";
            document.getElementById('ring-game-area').onmousemove = null; 
            document.getElementById('ring-game-area').ontouchmove = null;
            setTimeout(() => {
                unlockSection('etape20');
            }, 1000);
        }

        /* ======================================================== */
        /* LECTURE HISTOIRE FINALE                                  */
        /* ======================================================== */
        function unlockStory() {
            document.getElementById('etape-histoire').style.display = 'block';
            setTimeout(() => {
                document.getElementById('etape-histoire').style.opacity = '1';
                document.getElementById('etape-histoire').style.transform = 'translateY(0)';
                document.getElementById('etape-histoire').scrollIntoView({ behavior: 'smooth', block: 'start' });
            }, 100);
        }

        /* ======================================================== */
        /* CONFETTIS FINAUX                                         */
        /* ======================================================== */
        function explodeConfettiFinal() {
            for(let i=0; i<200; i++) {
                const conf = document.createElement('div'); 
                conf.style.position = 'fixed'; 
                conf.style.width = '15px'; 
                conf.style.height = '15px';
                conf.style.background = ['#ff0055', '#d4af37', '#006633', '#ffffff'][Math.floor(Math.random() * 4)];
                conf.style.left = '50vw'; 
                conf.style.top = '50vh'; 
                conf.style.zIndex = '99999'; 
                conf.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                
                const angle = Math.random() * Math.PI * 2; 
                const velocity = 30 + Math.random() * 50;
                const tx = Math.cos(angle) * velocity * 20; 
                const ty = Math.sin(angle) * velocity * 20;
                
                conf.style.transition = 'all 3s cubic-bezier(0.1, 0.8, 0.3, 1)'; 
                document.body.appendChild(conf);
                
                setTimeout(() => { 
                    conf.style.transform = `translate(${tx}px, ${ty}px) rotate(${Math.random()*1080}deg)`; 
                    conf.style.opacity = '0'; 
                }, 50);
                
                setTimeout(() => {
                    conf.remove();
                }, 3000);
            }
        }

        /* ======================================================== */
        /* SAD MODE                                                 */
        /* ======================================================== */
        function activateSadMode(lang) {
            document.getElementById('main-container').style.display = 'none'; 
            document.getElementById('translator').style.display = 'none'; 
            document.body.style.background = '#000'; 
            document.getElementById('sad-mode').style.display = 'flex';
            document.getElementById('sad-text').innerText = lang === 'fr' ? "Je savais tu m'aimais pas c triste Leinah sah..." : "كنت علابالي بلي ماتحبينيش، صدمتيني يا لينة صح...";
        }

        /* ======================================================== */
        /* TRADUCTION                                               */
        /* ======================================================== */
        let isArabic = false;
        function toggleLanguage() { 
            isArabic = !isArabic; 
            document.getElementById('body').setAttribute('dir', isArabic ? 'rtl' : 'ltr'); 
        }
    </script>
</body>
</html>
