<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أكبر إمتحان لـ Hayat 🇩🇿❤️</title>
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
            font-family: 'Tajawal', sans-serif;
            color: #fff;
            overflow-x: hidden;
            scroll-behavior: smooth;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            user-select: none;
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
        /* LE DESIGN DES CARTES                      */
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
            font-family: 'Poppins', sans-serif; /* Pour les prénoms latins */
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
            font-size: 0.8rem;
            padding: 5px 10px;
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
            direction: ltr; /* Pour que les chiffres s'affichent correctement */
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

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(144, 12, 63, 0.7); }
            70% { box-shadow: 0 0 0 30px rgba(144, 12, 63, 0); }
            100% { box-shadow: 0 0 0 0 rgba(144, 12, 63, 0); }
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
            font-family: 'Poppins', sans-serif;
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
            text-align: justify;
            box-shadow: 0 0 50px rgba(144, 12, 63, 0.5);
            line-height: 2;
        }

        .story-section p {
            font-size: 1.2rem;
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

    </style>
</head>
<body>

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
        <span class="star-decor" style="top: 5%; left: 30%;">✨</span>
        <span class="star-decor" style="top: 8%; left: 70%;">✨</span>
        <span class="star-decor" style="top: 40%; left: 5%;">✨</span>
        <span class="star-decor" style="top: 50%; left: 20%;">❤️</span>
        <span class="star-decor" style="top: 60%; left: 90%;">✨</span>
        <span class="star-decor" style="top: 80%; left: 40%;">❤️</span>
    </div>

    <div id="main-container">
        
        <div class="glass-card" id="etape1">
            <h1>إلى <span class="hayat-glow">Leinah</span> 🇩🇿✨</h1>
            <p>أجمل Trompe l'œil ديالي: شابة بزاف من برا، بصح مخبية كاركتير مهبول لداخل 😂.</p>
            <h2>المرحلة 1: التسخينات 😈</h2>
            <p>بيني بلي راكي واجدة. عبزي 10 مرات متابعين باش تفتحي السيت:</p>
            <div>
                <button class="btn troll-btn" id="main-btn" onclick="handleMainClick(this)">نحبك</button>
                <br>
                <button class="btn tiny-btn" id="tiny-btn" onclick="handleTinyClick()">نحبك</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape2">
            <h2>المرحلة 2: الدودو 🧸</h2>
            <div class="quiz-box">
                <h3>شكون هو الدودو الأول؟</h3>
                <button class="btn btn-small" onclick="checkDoudou('merwan')">Merwan</button>
                <button class="btn btn-small" onclick="checkDoudou('titi')">Titi الزعيم</button>
                <p class="quiz-result" id="doudou-res"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape3">
            <h2>المرحلة 3: الدواسة ⚖️</h2>
            <div class="quiz-box" id="couple-quiz-1">
                <h3>شكون يزعف على جال والو؟ 🙄</h3>
                <button class="btn btn-small" onclick="checkCouple(1, 'moi')">أنا</button>
                <button class="btn btn-small" onclick="checkCouple(1, 'toi')">أنتي</button>
                <p class="quiz-result" id="couple-res-1"></p>
            </div>
            <div class="quiz-box locked-section" id="couple-quiz-2">
                <h3>واش لازم نشريلك باش نرضيك كي تزعفي؟ 😋</h3>
                <button class="btn btn-small" onclick="checkCouple(2, 'fleur')">بوكي ورد</button>
                <button class="btn btn-small" onclick="checkCouple(2, 'chips')">شيبس دجاج و كومبوت</button>
                <p class="quiz-result" id="couple-res-2"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape4">
            <h2>المرحلة 4: ميموري تاع واش نحبو 🧠</h2>
            <p>حوسي على ڨاع الزواوج (سوشي، Trompe l'œil..) باش تجوزي!</p>
            <div class="memory-grid" id="memory-grid"></div>
        </div>

        <div class="glass-card locked-section" id="etape5">
            <h2>المرحلة 5: احكمي Titi 🐥</h2>
            <p>سرقلك الكومبوت ديالك! احكميه 4 مرات باش ترجعيها.</p>
            <p style="font-weight:bold; color:var(--primary);">النتيجة: <span id="titi-score">0</span> / 4</p>
            <div id="titi-area">
                <div class="moving-titi" id="titi-target" onclick="catchTiti()">🐥</div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape6">
            <h2>المرحلة 6: السيكيريتي 🔐</h2>
            <p>شكون هو العدو ديالي الوحيد؟ (مشروب أسطوري)</p>
            <input type="text" class="vault-input" id="vault-input" placeholder="أكتبي هنا..." dir="rtl">
            <button class="btn" onclick="checkVault()">فتح</button>
            <p class="quiz-result" id="vault-res"></p>
        </div>

        <div class="glass-card locked-section" id="etape7">
            <h2>المرحلة 7: بيني شطارتك ⚡</h2>
            <p>عبزي بالخف باش تعمري الجوج! (يا الفنيانة ساهلة)</p>
            <div class="progress-container">
                <div class="progress-bar" id="love-bar">0%</div>
            </div>
            <button class="btn troll-btn" style="width:100%;" onclick="fillLoveBar()">❤️ عبزي بالخف ❤️</button>
        </div>

        <div class="glass-card locked-section" id="etape8">
            <h2>المرحلة 8: كود ديزاد 🇩🇿</h2>
            <p>كود القوة المطلقة. بيني أصولك.</p>
            <div class="code-display" id="code-display">---</div>
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
            <p class="quiz-result" id="code-res"></p>
        </div>

        <div class="glass-card locked-section" id="etape9">
            <h2>المرحلة 9: كازينو الزهر 🎰</h2>
            <p>اجبدي المانيط وشوفي واش نهديلك (الزهر لي يقرر).</p>
            <div class="slot-machine" id="slot">❓❓❓</div>
            <button class="btn" id="btn-slot" onclick="spinSlot()">اجبدي المانيط</button>
        </div>

        <div class="glass-card locked-section" id="etape10">
            <h2>المرحلة 10: كاشف الكذب 📡</h2>
            <p>ابقى معبزة 3 ثواني بلا ما تطلڨي باش تبيني بلي تحبيني صح.</p>
            <button class="btn hold-btn" id="hold" onmousedown="startHold()" onmouseup="endHold()" onmouseleave="endHold()" ontouchstart="startHold()" ontouchend="endHold()">عبزي و ابقاي</button>
            <div class="detect-bar"><div class="detect-fill" id="fill"></div></div>
        </div>

        <div class="glass-card locked-section" id="etape11">
            <h2>المرحلة 11: سكانير القلب 🧬</h2>
            <p>عبزي باش تسكاني قلبك ونشوفو لاديان ديزاد ديالك.</p>
            <div class="scanner-container" id="scanner-btn" onclick="runScanner()">
                ❤️
                <div class="scan-line" id="scan-line"></div>
            </div>
            <p class="quiz-result" id="scan-res"></p>
        </div>

        <div class="glass-card locked-section" id="etape12">
            <h2>المرحلة 12: الدخيل 👀</h2>
            <p>حوسي على Trompe l'œil 🍰 المخبأ وسط السوشي 🍣!</p>
            <div class="intruder-grid" id="intruder-grid"></div>
        </div>

        <div class="glass-card locked-section" id="etape13">
            <h2>المرحلة 13: ڨراطي ڨراطي 🎟️</h2>
            <p>جوزي صبعك باش تشوفي السيربريز!</p>
            <div class="scratch-container">
                زواج VIP💍
                <div class="scratch-grid" id="scratch-grid"></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape14">
            <h2>المرحلة 14: السومة تاعك (المهر) 💰</h2>
            <p>شحال تسواي؟ خيري المهر ديالك.</p>
            <button class="btn btn-small" onclick="alert('ههه تسواي كثر من هكا يا الجيعانة!')">100 €</button>
            <button class="btn btn-small" onclick="alert('مزال، راكي طيحتي بقيمتك يا مراة حياتي!')">10 000 €</button>
            <button class="btn" id="mahr-btn-rich" onmouseover="fleeMahrBtn()" ontouchstart="fleeMahrBtn()">ملايار 💎</button>
            <br>
            <button class="btn tiny-btn" id="hidden-mahr" style="display:none;" onclick="winMahr()">مانتسواش بمال الدنيا ❤️</button>
        </div>

        <div class="glass-card locked-section" id="etape15">
            <h2>المرحلة 15: الصبر ⏳</h2>
            <p>حطي صبعك فالمربع الأحمر وماتتحركيش ڨاع لـ 5 ثواني.</p>
            <div class="patience-zone" id="pz" onmouseenter="startPatience()" onmouseleave="failPatience()" ontouchstart="startPatience()" ontouchend="failPatience()">
                <span class="patience-timer" id="pt">5</span>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape16">
            <h2>المرحلة 16: تيست تاع الشوف 👁️</h2>
            <p>حوسي على الخاتم 💍 المخبأ وسط Capri-Sun.</p>
            <div class="find-ring-grid" id="frg"></div>
        </div>

        <div class="glass-card locked-section" id="etape17">
            <h2>المرحلة 17: لونكيط تاع البلدية 📝</h2>
            <p>جاوبي صحيح على 10 أسئلة متابعين. تغلطي مرة = تعاودي من الزيرو.</p>
            <h3 style="color:var(--gold);">السؤال <span id="q-num">1</span>/10</h3>
            <div class="marathon-card">
                <h3 id="marathon-q">جاري التحميل...</h3>
                <div id="marathon-btns"></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape18">
            <h2>المرحلة 18: كود PIN تاع القلب 🔢</h2>
            <p>واشنو هو الكود؟ أنديس: العام لي رانا فيه دوكا.</p>
            <div class="code-display" id="pin-display">----</div>
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

        <div class="glass-card locked-section" id="etape19">
            <h2>المرحلة 19: البوس اللخراني 💍</h2>
            <p>الخاتم يهرب ويختفي! احكميه باش نكملو!</p>
            <div id="ring-game-area" onmousemove="moveRingUltimate()" ontouchmove="moveRingUltimate()">
                <button id="ring-btn" onclick="winRingGame()">💍</button>
            </div>
        </div>

        <div class="glass-card locked-section wedding-section" id="etape21">
            <h1 style="font-size: 3.5rem;">إن شاء الله 💍👑</h1>
            <p style="font-size: 1.3rem; font-weight: bold;">ألف مبروك مرتي، كملتي هاد الكوشمار!</p>
            <p>بينتي بلي راكي محاربة تاع الصح. نديرو أعظم عرس، كاراكو، قفطان، جبال تاع شيبس دجاج و سوشي.</p>
            <p>بصح قبل هاد الشي...</p>
            <button class="btn" style="margin-top: 30px; background: var(--gold); color: black; padding: 20px 40px; font-size: 1.5rem;" onclick="unlockStory()">اقراي هادي تعيشي 📖</button>
        </div>

        <div class="story-section locked-section" id="etape-histoire">
            <h2 class="story-title">من القلب للقلب 🖤</h2>
            <p>دوكا كي كملتي ڨاع هاد اللعب، لازم نهدر معاك صح. حكايتي بلاك ماتعرفيهاش كاملة.</p>
            <p>زت في Limoges. بصح غير زت، بعتوني للجزائر نعيش عند فاميلة بابا. تماك بدا الجحيم. كانت دنجري كيفاش فاميلتو دارو فينا الباطل، أنا ويما. كانو يمرمدونا كل يوم، الشر باطل. الحماية ديالي الوحيدة كانت يما. كنت نفضلها هي على كلش، كانت النور ديالي الوحيد تماك.</p>
            <p>فـ 6 سنين، وليت لفرنسا ديفينيتيف. بصح الضربة كانت مقيوسة. كان عندي روطار كبير فالمسيد فاللغة. فالمسيد كانت كارثة. كانو يحڨروني ويطيحولي كل يوم. العنف تاع المسيد لحق لدرجة كبيرة، حتى ديسيداو يعاودو يرجعوني للجزائر، كانو حاسبين فيها صلاحي.</p>
            <p>بصح تماك... كانت كتر. عشت كوشمار تاع الصح. شفت واش حتى طفل ما لازم يشوف. أطاك بالقرطاس قدام عيني... شفت صحابي يطيحو، يموتو قدامي. شفت الموت، الدم، الميزيرية الكحلة. هاد الشي دمرني.</p>
            <p>مع اللخر رجعت لفرنسا. استقريت في Lille باش نعيش ڨاع حياتي. سييت نوقف على رجليا، بصح قلبي كان مهشم، كنت حاسب بلي راح نبقى فالظلمة لتوغور.</p>
            <p>وممبعد... بنتي نتي، Leinah. أحلى Trompe l'œil ديالي. مسحتي ڨاع هاد الغمة. نتي هي الكادو ديالي مورا ڨاع هاد الميزيرية. نحبك كتر من كلش، وإن شاء الله، نتي لي راح تكوني يما دراري دياولي.</p>
            <div style="text-align:center; margin-top: 40px;">
                <button class="btn" style="background: var(--gold); color: black;" onclick="explodeConfettiFinal()">نحبك ❤️</button>
            </div>
        </div>

    </div>

    <div id="sad-mode">
        <h1 id="sad-text"></h1>
        <img src="https://media.tenor.com/J7r5uN2nEbwAAAAC/neymar-crying.gif" alt="Triste">
    </div>

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
        function handleMainClick(btn) {
            if (btn.dataset.isTrap === "true") {
                activateSadMode();
                return;
            }
            clickCount++;
            if (clickCount === 8) { 
                document.getElementById('main-btn').innerText = "مانحبكش"; 
                document.getElementById('main-btn').style.background = "#333"; 
                document.getElementById('main-btn').dataset.isTrap = "true"; 
                document.getElementById('tiny-btn').style.display = 'inline-block'; 
            }
        }
        function handleTinyClick() {
            clickCount++;
            if (clickCount >= 10) { 
                document.getElementById('main-btn').innerText = "مريقل ❤️"; 
                document.getElementById('main-btn').style.background = "var(--gold)"; 
                document.getElementById('main-btn').dataset.isTrap = "false";
                document.getElementById('tiny-btn').style.display = 'none'; 
                unlockSection('etape2');
            }
        }

        /* ======================================================== */
        /* ETAPES 2 & 3: QUIZZ                                      */
        /* ======================================================== */
        function checkDoudou(a) { 
            if(a === 'titi') { 
                document.getElementById('doudou-res').innerText = "باينة، هو الصح ❤️"; 
                unlockSection('etape3'); 
            } else { 
                document.getElementById('doudou-res').innerText = "غالط 😒"; 
            } 
        }

        function checkCouple(q, a) {
            if(q === 1 && a === 'toi') { 
                unlockSection('couple-quiz-2'); 
            }
            if(q === 2 && a === 'chips') { 
                document.getElementById('couple-res-2').innerText = "جبتيها! شيبس دجاج و كومبوت 🤤"; 
                unlockSection('etape4'); 
                initMemoryGame(); 
            }
            else if(q === 2) { 
                document.getElementById('couple-res-2').innerText = "كذابة تحبي غير الماكلة 😂"; 
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
                if (matches === 4) {
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
                if(t1) { t1.style.left = Math.random() * 80 + '%'; t1.style.top = Math.random() * 80 + '%'; }
            }, 800); 
        }
        function catchTiti() {
            titiCount++; 
            document.getElementById('titi-score').innerText = titiCount; 
            if(titiCount >= 4) { 
                clearInterval(titiInterval); 
                document.getElementById('titi-target').style.display = 'none'; 
                unlockSection('etape6'); 
            }
        }

        /* ======================================================== */
        /* ETAPE 6: MOT DE PASSE                                    */
        /* ======================================================== */
        function checkVault() {
            const val = document.getElementById('vault-input').value.toLowerCase().replace(/\s/g, '');
            if(val === 'capri-sun' || val === 'caprisun' || val === 'كابريسن') { 
                unlockSection('etape7'); 
            } else {
                document.getElementById('vault-res').innerText = "غالط... نسيتي المشروب تاعك؟ 😒";
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
            document.getElementById('code-display').innerText = currentCode + "---".substring(currentCode.length);
            if(currentCode === "213") {
                unlockSection('etape9');
            }
        }

        /* ======================================================== */
        /* ETAPE 9: CASINO                                          */
        /* ======================================================== */
        let isSpinning = false;
        function spinSlot() {
            if(isSpinning) return;
            isSpinning = true;
            const slot = document.getElementById('slot');
            const arr = ["المواعن", "طاڨوس", "سوشي آ فلونتي 🍣", "ترومب لوي 🍰"]; 
            let counter = 0;
            const spinInt = setInterval(() => {
                slot.innerText = arr[Math.floor(Math.random() * arr.length)];
                counter++;
                if(counter > 15) { 
                    clearInterval(spinInt); 
                    slot.innerText = "سوشي يخلصو راجلك 🍣"; 
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
        function startHold() {
            holdProgress = 0;
            holdInterval = setInterval(() => {
                holdProgress += 5; 
                document.getElementById('fill').style.width = holdProgress + "%";
                if(holdProgress >= 100) { 
                    clearInterval(holdInterval); 
                    document.getElementById('fill').style.background = "var(--gold)"; 
                    document.getElementById('hold').onmousedown = null; 
                    document.getElementById('hold').ontouchstart = null; 
                    unlockSection('etape11'); 
                }
            }, 150);
        }
        function endHold() { 
            clearInterval(holdInterval); 
            if(holdProgress < 100) {
                holdProgress = 0;
                document.getElementById('fill').style.width = "0%";
            } 
        }

        /* ======================================================== */
        /* ETAPE 11: SCANNER                                        */
        /* ======================================================== */
        function runScanner() {
            document.getElementById('scan-line').style.display = 'block';
            setTimeout(() => { 
                document.getElementById('scan-line').style.display = 'none'; 
                unlockSection('etape12'); 
                initIntruder(); 
            }, 2000);
        }

        /* ======================================================== */
        /* ETAPE 12: L'INTRUS                                       */
        /* ======================================================== */
        function initIntruder() {
            const grid = document.getElementById('intruder-grid');
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
        }

        /* ======================================================== */
        /* ETAPE 13: GRATTE-GRATTE                                  */
        /* ======================================================== */
        let scratchCount = 0;
        function initScratch() {
            const grid = document.getElementById('scratch-grid');
            if(grid.innerHTML !== "") return;
            for(let i=0; i<50; i++) {
                let block = document.createElement('div'); 
                block.className = 'scratch-block';
                const clearBlock = () => { 
                    if(block.style.opacity !== '0') { 
                        block.style.opacity = '0'; 
                        scratchCount++; 
                        if(scratchCount >= 40) {
                            unlockSection('etape14');
                        } 
                    } 
                };
                block.onmouseover = clearBlock; 
                block.ontouchmove = clearBlock; 
                grid.appendChild(block);
            }
        }

        /* ======================================================== */
        /* ETAPE 14: LE JUSTE PRIX                                  */
        /* ======================================================== */
        function fleeMahrBtn() {
            const btn = document.getElementById('mahr-btn-rich'); 
            const x = Math.random() * 200 - 100; 
            const y = Math.random() * 50 - 25;
            
            if(btn) btn.style.transform = `translate(${x}px, ${y}px)`; 
            document.getElementById('hidden-mahr').style.display = "inline-block";
        }
        function winMahr() {
            alert("هكداك. ماعندكش سومة يا مراة حياتي. ❤️");
            unlockSection('etape15');
        }

        /* ======================================================== */
        /* ETAPE 15: LA PATIENCE                                    */
        /* ======================================================== */
        let patienceTimer, patienceTime = 5;
        function startPatience() {
            clearInterval(patienceTimer);
            document.getElementById('pz').style.background = "rgba(0,255,0,0.2)";
            patienceTimer = setInterval(() => {
                patienceTime--;
                document.getElementById('pt').innerText = patienceTime;
                if(patienceTime <= 0) {
                    clearInterval(patienceTimer);
                    document.getElementById('pt').innerText = "ربحتي!";
                    unlockSection('etape16'); 
                    initFindRing();
                }
            }, 1000);
        }
        function failPatience() {
            clearInterval(patienceTimer); 
            patienceTime = 5;
            document.getElementById('pt').innerText = patienceTime;
            document.getElementById('pz').style.background = "rgba(144,12,63,0.1)";
        }

        /* ======================================================== */
        /* ETAPE 16: OÙ EST LA BAGUE                                */
        /* ======================================================== */
        function initFindRing() {
            const grid = document.getElementById('frg');
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
        }

        /* ======================================================== */
        /* ETAPE 17: L'INTERROGATOIRE GEANT (MARATHON)              */
        /* ======================================================== */
        const marathonQ = [
            { q: "شكون لي شباب كثر؟", ans: ["أنا", "أنا"], correct: 0 },
            { q: "مشروبك؟", ans: ["ما", "Capri-Sun"], correct: 1 },
            { q: "أعز دودو؟", ans: ["Imrane", "Titi"], correct: 1 },
            { q: "شكون يزعف بالخف؟", ans: ["Leinah", "أنا"], correct: 0 },
            { q: "الحيوان لي يشبهلك؟", ans: ["غزالة", "باندا جيعان"], correct: 1 },
            { q: "شيبس لي تموتي عليه؟", ans: ["فرماج", "دجاج"], correct: 1 },
            { q: "فطور تاع الجمعة؟", ans: ["طاڨوس", "طعام"], correct: 1 },
            { q: "أحسن ديسير؟", ans: ["ديسير", "Trompe l'oeil"], correct: 1 },
            { q: "شكون لي دايما غالط؟", ans: ["الراجل", "المرا"], correct: 0 },
            { q: "تحبيني؟", ans: ["شوية", "نهبل عليك"], correct: 1 }
        ];
        let currentQ = 0;
        function initMarathon() {
            loadMarathonQ();
        }
        function loadMarathonQ() {
            if(currentQ >= marathonQ.length) { 
                document.getElementById('marathon-q').innerText = "ألف مبروك!"; 
                document.getElementById('marathon-btns').innerHTML = ""; 
                unlockSection('etape18'); 
                return; 
            }
            
            let q = marathonQ[currentQ];
            document.getElementById('q-num').innerText = currentQ + 1;
            document.getElementById('marathon-q').innerText = q.q;
            let btns = `<button class="btn" onclick="checkMarathon(0)">${q.ans[0]}</button><button class="btn" onclick="checkMarathon(1)">${q.ans[1]}</button>`;
            document.getElementById('marathon-btns').innerHTML = btns;
        }
        function checkMarathon(ans) {
            if(ans === marathonQ[currentQ].correct) {
                currentQ++;
                loadMarathonQ();
            } else {
                alert("غالط! تعاودي ڨاع من السؤال الأول! 😈");
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
            
            document.getElementById('pin-display').innerText = currentPin + "----".substring(currentPin.length);
            
            if(currentPin.length === 4) {
                if(currentPin === codeSecret) { 
                    unlockSection('etape19'); 
                } else { 
                    setTimeout(() => { 
                        currentPin = ""; 
                        document.getElementById('pin-display').innerText = "----"; 
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
            document.getElementById('ring-btn').innerText = "💖 حكمتك 💖";
            document.getElementById('ring-btn').style.transform = "scale(1.5)";
            document.getElementById('ring-btn').style.opacity = "1";
            document.getElementById('ring-game-area').onmousemove = null; 
            document.getElementById('ring-game-area').ontouchmove = null;
            setTimeout(() => {
                unlockSection('etape21');
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
        function activateSadMode() {
            document.getElementById('main-container').style.display = 'none'; 
            document.body.style.background = '#000'; 
            document.getElementById('sad-mode').style.display = 'flex';
            document.getElementById('sad-text').innerText = "كنت علابالي بلي ماتحبينيش، صدمتيني يا Leinah صح...";
        }
    </script>
</body>
</html>
