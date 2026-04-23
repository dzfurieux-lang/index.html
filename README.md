<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>L'Épreuve Ultime pour Leinah 🇩🇿❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;900&family=Poppins:wght@300;600;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #900C3F; --gold: #D4AF37; --bg-dark: #1a0b12; --pink-dark: #ff4d6d;
        }

        body {
            margin: 0; padding: 0; min-height: 100vh;
            background: linear-gradient(135deg, #1a0b12, #4a001a);
            font-family: 'Poppins', sans-serif; color: #fff;
            overflow-x: hidden; scroll-behavior: smooth;
            -webkit-touch-callout: none; /* Empêche la sélection sur mobile */
            -webkit-user-select: none; user-select: none;
        }

        body[dir="rtl"] { font-family: 'Tajawal', sans-serif; }

        #main-container { width: 100%; display: flex; flex-direction: column; align-items: center; padding: 50px 0; z-index: 10; position: relative; }

        .glass-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.95), rgba(255,204,213,0.95));
            backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px);
            border: 2px solid rgba(255, 255, 255, 0.5); border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5); padding: 40px;
            max-width: 700px; width: 90%; margin: 30px 0; text-align: center;
            position: relative; transition: all 0.5s ease; color: #333;
        }

        .locked-section { opacity: 0; transform: translateY(100px) scale(0.9); display: none; transition: all 1s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .unlocked { display: block; animation: popIn 1s forwards; }
        @keyframes popIn { to { opacity: 1; transform: translateY(0) scale(1); } }

        h1 { color: var(--primary); font-size: 2.8rem; margin-bottom: 5px; text-shadow: 2px 2px 5px rgba(0,0,0,0.1); }
        h2 { color: #444; font-size: 1.8rem; border-bottom: 3px dashed var(--gold); padding-bottom: 10px; margin-top: 20px;}
        h3 { color: var(--primary); font-size: 1.3rem; margin-bottom: 15px; }

        .hayat-glow {
            color: #ff0055; font-size: 1.3em; text-transform: uppercase; font-weight: 900;
            text-shadow: 0 0 15px rgba(255, 0, 85, 0.8), 0 0 30px rgba(255, 0, 85, 0.5);
            display: inline-block; animation: heartbeat 1.5s infinite;
        }
        @keyframes heartbeat { 0%, 30%, 60% { transform: scale(1); } 15%, 45% { transform: scale(1.15); } }

        .quiz-box { background: rgba(255, 255, 255, 0.7); border-radius: 20px; padding: 25px; margin-bottom: 20px; border: 2px solid white; box-shadow: 0 8px 20px rgba(0,0,0,0.1); }
        
        .btn { background: linear-gradient(45deg, var(--primary), var(--pink-dark)); color: white; border: none; padding: 12px 25px; border-radius: 50px; cursor: pointer; font-weight: 900; font-family: inherit; font-size: 1.1rem; transition: 0.4s; margin: 10px; box-shadow: 0 5px 20px rgba(144, 12, 63, 0.4); text-transform: uppercase; }
        .btn-small { padding: 8px 18px; font-size: 0.9rem; background: var(--pink-dark); text-transform: none; }
        .btn:hover { background: var(--gold); color: #000; transform: scale(1.1) rotate(-2deg); box-shadow: 0 10px 30px rgba(212, 175, 55, 0.6);}
        .btn:active { transform: scale(0.95); }
        
        .troll-btn { background: var(--primary); font-size: 1.5rem; padding: 20px 40px; }
        .tiny-btn { display: none; font-size: 0.5rem; padding: 3px 8px; margin-top: 5px; opacity: 0.6; box-shadow: none; }
        .quiz-result { font-weight: 900; color: var(--primary); margin-top: 15px; min-height: 25px; font-size: 1.2rem;}

        /* JEU MEMORY */
        .memory-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin-top: 20px; }
        .memory-card { width: 100%; aspect-ratio: 1; background: var(--primary); border-radius: 10px; cursor: pointer; position: relative; transition: transform 0.3s; transform-style: preserve-3d; display: flex; justify-content: center; align-items: center; font-size: 2rem; color: transparent; border: 3px solid white; }
        .memory-card.flipped { background: white; color: var(--primary); transform: rotateY(180deg); }
        .memory-card.matched { background: var(--gold); color: white; pointer-events: none; }

        /* JEU DE CHASSE TITI */
        #titi-area { width: 100%; height: 250px; background: rgba(0,0,0,0.1); border-radius: 15px; position: relative; overflow: hidden; border: 2px dashed var(--primary); }
        .moving-titi { position: absolute; font-size: 2.5rem; cursor: crosshair; transition: 0.5s; }

        /* JAUGE */
        .progress-container { width: 100%; background: #ddd; border-radius: 30px; height: 40px; margin: 20px 0; overflow: hidden; border: 3px solid white; box-shadow: inset 0 0 10px rgba(0,0,0,0.2); }
        .progress-bar { height: 100%; background: linear-gradient(90deg, #ff4d6d, #900C3F, var(--gold)); width: 0%; transition: width 0.1s; display: flex; align-items: center; justify-content: flex-end; color: white; font-weight: bold; padding-right: 10px; }

        /* DIGICODE DZ */
        .keypad { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; max-width: 250px; margin: 0 auto; }
        .key { background: white; border: 2px solid var(--primary); color: var(--primary); font-size: 1.5rem; padding: 15px; border-radius: 10px; cursor: pointer; font-weight: bold; transition: 0.2s; }
        .key:active { background: var(--primary); color: white; }
        .code-display { font-size: 2rem; letter-spacing: 10px; background: #eee; border-radius: 10px; padding: 10px; margin-bottom: 20px; font-weight: bold; min-height: 40px;}

        /* CASINO DU DESTIN */
        .slot-machine { font-size: 1.5rem; background: black; color: gold; padding: 20px; border-radius: 15px; border: 4px solid var(--gold); margin: 20px 0; font-weight: bold; text-transform: uppercase; height: 35px; display: flex; align-items: center; justify-content: center; overflow: hidden; }

        /* DETECTEUR DE MENSONGE */
        .hold-btn { padding: 30px; font-size: 1.5rem; border-radius: 50%; width: 150px; height: 150px; border: 5px solid white; box-shadow: 0 0 20px var(--primary); animation: pulse 2s infinite; }
        @keyframes pulse { 0% { box-shadow: 0 0 0 0 rgba(144, 12, 63, 0.7); } 70% { box-shadow: 0 0 0 30px rgba(144, 12, 63, 0); } 100% { box-shadow: 0 0 0 0 rgba(144, 12, 63, 0); } }
        .detect-bar { width: 100%; height: 20px; background: #ddd; border-radius: 10px; margin-top: 20px; overflow: hidden;}
        .detect-fill { height: 100%; background: #006633; width: 0%; transition: width 0.1s; }

        /* BAGUE */
        #ring-game-area { width: 100%; height: 300px; position: relative; border: 3px dashed var(--primary); border-radius: 20px; overflow: hidden; background: rgba(255,255,255,0.5); cursor: crosshair; }
        #ring-btn { position: absolute; top: 40%; left: 40%; font-size: 4rem; background: none; border: none; cursor: grab; transition: 0.05s; filter: drop-shadow(0 0 10px gold); }

        .vault-input { width: 80%; padding: 15px; border-radius: 30px; border: 2px solid var(--primary); font-size: 1.2rem; text-align: center; font-family: inherit; margin-bottom: 15px; outline: none; }

        .wedding-section { background: linear-gradient(135deg, rgba(212, 175, 55, 0.2), rgba(255,255,255,0.9)); border: 5px double var(--gold); border-radius: 30px; padding: 40px; box-shadow: 0 0 40px rgba(212, 175, 55, 0.8); }

        .secret-translator { position: fixed; bottom: 15px; right: 15px; opacity: 0.15; cursor: pointer; font-size: 25px; z-index: 100; transition: 0.3s; background: rgba(255,255,255,0.5); border-radius: 50%; padding: 10px; }
        .secret-translator:hover { opacity: 1; transform: scale(1.3) rotate(180deg); box-shadow: 0 0 20px gold; }

        .lang-ar { display: none; } .lang-fr { display: block; }
        [dir="rtl"] .lang-fr { display: none; } [dir="rtl"] .lang-ar { display: block; }

        #sad-mode { display: none; position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background: #000; z-index: 99999; flex-direction: column; justify-content: center; align-items: center; color: white; text-align: center; }
        #sad-text { font-size: 2.5rem; color: white; text-shadow: 0 0 20px rgba(255, 0, 0, 0.8); margin-bottom: 20px; font-weight: 900;}
        #sad-mode img { max-width: 90%; border-radius: 20px; box-shadow: 0 0 50px rgba(255, 0, 0, 0.5); }
    </style>
</head>
<body dir="ltr" id="body">

    <div id="main-container">
        
        <div class="glass-card" id="etape1">
            <div class="lang-fr">
                <h1>Pour ma <span class="hayat-glow">hayat</span> Leinah 🇩🇿✨</h1>
                <p>La plus belle femme à mes yeux, et la ji3ena ultime de Capri-Sun.</p>
                <h2>Étape 1 : Le test d'endurance 😈</h2>
                <p>Prouve-le. Clique 15 fois de suite pour ouvrir le site :</p>
                <div>
                    <button class="btn troll-btn" id="main-btn-fr" onclick="handleMainClick(this, 'fr')">JE T'AIME</button><br>
                    <button class="btn tiny-btn" id="tiny-btn-fr" onclick="handleTinyClick('fr')">je t'aime</button>
                </div>
            </div>
            <div class="lang-ar">
                <h1>إلى <span class="hayat-glow">حياتي</span> لينة 🇩🇿✨</h1>
                <p>أجمل امرأة في عيني، و"الجيعانة" نتاع الكابري سن.</p>
                <h2>المرحلة 1: اختبار التحمل 😈</h2>
                <p>أثبتي ذلك. اضغطي 15 مرة متتالية لفتح الموقع:</p>
                <div>
                    <button class="btn troll-btn" id="main-btn-ar" onclick="handleMainClick(this, 'ar')">أنا أحبك</button><br>
                    <button class="btn tiny-btn" id="tiny-btn-ar" onclick="handleTinyClick('ar')">أنا أحبك</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape2">
            <div class="lang-fr">
                <h2>Étape 2 : Le Doudou 🕵️‍♂️</h2>
                <div class="quiz-box">
                    <h3>Qui est le boss de la chambre ? 🧸</h3>
                    <button class="btn btn-small" onclick="checkDoudou('titi')">Titi le boss</button>
                    <button class="btn btn-small" onclick="checkDoudou('merwan')">Merwan</button>
                    <button class="btn btn-small" onclick="checkDoudou('hamouda')">Hamouda</button>
                    <button class="btn btn-small" onclick="checkDoudou('hellokitty')">Hello Kitty</button>
                    <button class="btn btn-small" onclick="checkDoudou('winnie')">Winnie l'ourson</button>
                    <button class="btn btn-small" onclick="checkDoudou('stitch')">Stitch</button>
                    <p class="quiz-result" id="doudou-res-fr"></p>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 2: الدودو 🕵️‍♂️</h2>
                <div class="quiz-box">
                    <h3>من هو زعيم الغرفة؟ 🧸</h3>
                    <button class="btn btn-small" onclick="checkDoudou('titi')">تيتي الزعيم</button>
                    <button class="btn btn-small" onclick="checkDoudou('merwan')">مروان</button>
                    <button class="btn btn-small" onclick="checkDoudou('hamouda')">حمودة</button>
                    <button class="btn btn-small" onclick="checkDoudou('hellokitty')">هالو كيتي</button>
                    <button class="btn btn-small" onclick="checkDoudou('winnie')">ويني</button>
                    <button class="btn btn-small" onclick="checkDoudou('stitch')">ستيتش</button>
                    <p class="quiz-result" id="doudou-res-ar"></p>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape3">
            <div class="lang-fr">
                <h2>Étape 3 : Qui de nous deux ? ⚖️</h2>
                <div class="quiz-box" id="couple-quiz-1">
                    <h3>Qui boude le plus pour rien ? 🙄</h3>
                    <button class="btn btn-small" onclick="checkCouple(1, 'moi')">Moi (Ton homme)</button>
                    <button class="btn btn-small" onclick="checkCouple(1, 'toi')">Toi (Leinah)</button>
                    <p class="quiz-result" id="couple-res-1"></p>
                </div>
                <div class="quiz-box locked-section" id="couple-quiz-2">
                    <h3>Qui a toujours faim h24 ? 🍕</h3>
                    <button class="btn btn-small" onclick="checkCouple(2, 'moi')">Moi</button>
                    <button class="btn btn-small" onclick="checkCouple(2, 'toi')">Toi (La ji3ena)</button>
                    <p class="quiz-result" id="couple-res-2"></p>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 3: من منا؟ ⚖️</h2>
                <div class="quiz-box" id="couple-quiz-1-ar">
                    <h3>من يغضب لأتفه الأسباب؟ 🙄</h3>
                    <button class="btn btn-small" onclick="checkCouple(1, 'moi')">أنا</button>
                    <button class="btn btn-small" onclick="checkCouple(1, 'toi')">أنتِ (لينة)</button>
                    <p class="quiz-result" id="couple-res-1-ar"></p>
                </div>
                <div class="quiz-box locked-section" id="couple-quiz-2-ar">
                    <h3>من جائع 24/24؟ 🍕</h3>
                    <button class="btn btn-small" onclick="checkCouple(2, 'moi')">أنا</button>
                    <button class="btn btn-small" onclick="checkCouple(2, 'toi')">أنتِ (الجيعانة)</button>
                    <p class="quiz-result" id="couple-res-2-ar"></p>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape4">
            <div class="lang-fr">
                <h2>Étape 4 : Le Memory de l'Amour 🧠</h2>
                <p>Trouve toutes les paires pour passer à la suite !</p>
                <div class="memory-grid" id="memory-grid"></div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 4: لعبة الذاكرة 🧠</h2>
                <p>جدي كل الأزواج للمرور للتالي!</p>
                <div class="memory-grid" id="memory-grid-ar"></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape5">
            <div class="lang-fr">
                <h2>Étape 5 : Attrape Titi ! 🐥</h2>
                <p>Titi s'est enfui. Clique sur lui 5 fois pour le calmer.</p>
                <p style="font-weight:bold; color:var(--primary);">Score : <span id="titi-score">0</span> / 5</p>
                <div id="titi-area">
                    <div class="moving-titi" id="titi-target" onclick="catchTiti()">🐥</div>
                </div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 5: أمسكي تيتي! 🐥</h2>
                <p>تيتي هرب. اضغطي عليه 5 مرات لتهدئته.</p>
                <p style="font-weight:bold; color:var(--primary);">النتيجة: <span id="titi-score-ar">0</span> / 5</p>
                <div id="titi-area-ar">
                    <div class="moving-titi" id="titi-target-ar" onclick="catchTiti()">🐥</div>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape6">
            <div class="lang-fr">
                <h2>Étape 6 : La Sécurité 🔐</h2>
                <p>Quel est mon vrai rival ? Écris son nom.</p>
                <input type="text" class="vault-input" id="vault-input-fr" placeholder="La boisson ultime...">
                <button class="btn" onclick="checkVault('fr')">Ouvrir</button>
                <p class="quiz-result" id="vault-res-fr"></p>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 6: الأمان 🔐</h2>
                <p>من هو منافسي الحقيقي؟ اكتبي اسمه.</p>
                <input type="text" class="vault-input" id="vault-input-ar" placeholder="المشروب المطلق..." dir="rtl">
                <button class="btn" onclick="checkVault('ar')">فتح</button>
                <p class="quiz-result" id="vault-res-ar"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape7">
            <div class="lang-fr">
                <h2>Étape 7 : L'Épreuve Physique ⚡</h2>
                <p>Prouve-moi ton amour : remplis la jauge ! (C'est beaucoup plus facile je te promets 😂)</p>
                <div class="progress-container">
                    <div class="progress-bar" id="love-bar">0%</div>
                </div>
                <button class="btn troll-btn" style="width:100%;" onclick="fillLoveBar()">❤️ SPAM MOI ❤️</button>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 7: الاختبار البدني ⚡</h2>
                <p>أثبتي لي حبك: املئي العداد! (لقد جعلته أسهل بكثير أعدك 😂)</p>
                <div class="progress-container">
                    <div class="progress-bar" id="love-bar-ar">0%</div>
                </div>
                <button class="btn troll-btn" style="width:100%;" onclick="fillLoveBar()">❤️ اضغطي بقوة ❤️</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape8">
            <div class="lang-fr">
                <h2>Étape 8 : Le Digicode DZ 🇩🇿</h2>
                <p>Trouve le code secret. Indice : C'est l'indicatif de notre beau pays.</p>
                <div class="code-display" id="code-display-fr">---</div>
                <div class="keypad">
                    <button class="key" onclick="pressKey(1)">1</button><button class="key" onclick="pressKey(2)">2</button><button class="key" onclick="pressKey(3)">3</button>
                    <button class="key" onclick="pressKey(4)">4</button><button class="key" onclick="pressKey(5)">5</button><button class="key" onclick="pressKey(6)">6</button>
                    <button class="key" onclick="pressKey(7)">7</button><button class="key" onclick="pressKey(8)">8</button><button class="key" onclick="pressKey(9)">9</button>
                    <button class="key" style="grid-column: 2;" onclick="pressKey(0)">0</button>
                </div>
                <p class="quiz-result" id="code-res-fr"></p>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 8: الرمز السري 🇩🇿</h2>
                <p>جدي الرمز. تلميح: إنه رمز الاتصال لبلدنا الجميل.</p>
                <div class="code-display" id="code-display-ar">---</div>
                <div class="keypad">
                    <button class="key" onclick="pressKey(1)">1</button><button class="key" onclick="pressKey(2)">2</button><button class="key" onclick="pressKey(3)">3</button>
                    <button class="key" onclick="pressKey(4)">4</button><button class="key" onclick="pressKey(5)">5</button><button class="key" onclick="pressKey(6)">6</button>
                    <button class="key" onclick="pressKey(7)">7</button><button class="key" onclick="pressKey(8)">8</button><button class="key" onclick="pressKey(9)">9</button>
                    <button class="key" style="grid-column: 2;" onclick="pressKey(0)">0</button>
                </div>
                <p class="quiz-result" id="code-res-ar"></p>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape9">
            <div class="lang-fr">
                <h2>Étape 9 : La Roue de la Fortune 🎰</h2>
                <p>Clique pour tirer au sort ton cadeau ! (Attention, le hasard fait bien les choses)</p>
                <div class="slot-machine" id="slot-fr">❓❓❓</div>
                <button class="btn troll-btn" id="btn-slot-fr" onclick="spinSlot('fr')">Tirer le levier</button>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 9: عجلة الحظ 🎰</h2>
                <p>اضغطي لسحب هديتك! (الصدفة تفعل المعجزات)</p>
                <div class="slot-machine" id="slot-ar">❓❓❓</div>
                <button class="btn troll-btn" id="btn-slot-ar" onclick="spinSlot('ar')">اسحبي الرافعة</button>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape10">
            <div class="lang-fr">
                <h2>Étape 10 : Le Détecteur de Sincérité 📡</h2>
                <p>Maintiens ton doigt appuyé sur le bouton pendant 3 secondes sans lâcher pour prouver que tout ça n'est pas un mensonge.</p>
                <button class="btn hold-btn" id="hold-fr" onmousedown="startHold('fr')" onmouseup="endHold('fr')" onmouseleave="endHold('fr')" ontouchstart="startHold('fr')" ontouchend="endHold('fr')">MAINTIENS</button>
                <div class="detect-bar"><div class="detect-fill" id="fill-fr"></div></div>
            </div>
            <div class="lang-ar">
                <h2>المرحلة 10: جهاز كشف الكذب 📡</h2>
                <p>أبقي إصبعك مضغوطاً على الزر لمدة 3 ثوانٍ دون إفلات لإثبات أن كل هذا ليس كذبة.</p>
                <button class="btn hold-btn" id="hold-ar" onmousedown="startHold('ar')" onmouseup="endHold('ar')" onmouseleave="endHold('ar')" ontouchstart="startHold('ar')" ontouchend="endHold('ar')">اضغطي مطولاً</button>
                <div class="detect-bar"><div class="detect-fill" id="fill-ar"></div></div>
            </div>
        </div>

        <div class="glass-card locked-section" id="etape11">
            <div class="lang-fr">
                <h2>Le Boss Final 💍</h2>
                <p>La bague bouge vite. Si tu arrives à cliquer dessus, on se marie. Sinon, c'est mort.</p>
                <div id="ring-game-area" onmousemove="moveRing()" ontouchmove="moveRing()">
                    <button id="ring-btn" onclick="winRingGame()">💍</button>
                </div>
            </div>
            <div class="lang-ar">
                <h2>الزعيم الأخير 💍</h2>
                <p>الخاتم يتحرك بسرعة. إذا ضغطت عليه نتزوج، وإلا انتهى الأمر.</p>
                <div id="ring-game-area" onmousemove="moveRing()" ontouchmove="moveRing()">
                    <button id="ring-btn" onclick="winRingGame()">💍</button>
                </div>
            </div>
        </div>

        <div class="glass-card locked-section wedding-section" id="etape12">
            <div class="lang-fr">
                <h1 style="font-size: 3.5rem; text-transform: uppercase;">InshAllah 💍👑</h1>
                <p style="font-size: 1.3rem; font-weight: bold;">Félicitations ma Hayat, tu as survécu à ce site de psychopathe !</p>
                <p>Tu as prouvé que t'es une vraie guerrière et que tu mérites le monde. On fera le plus beau des mariages, avec le Karakou étincelant, le Caftan, et des Zgharit jusqu'à Alger.</p>
                <p>Prépare-toi à faire le couscous tous les vendredis (Je rigole, moi mon seul rôle ce sera de le manger 😋).</p>
                <div style="background: rgba(255,255,255,0.8); padding: 20px; border-radius: 15px; margin-top: 20px; border: 3px dashed var(--primary);">
                    <h3 style="margin:0; font-size: 2rem;">Qu'Allah nous bénisse et nous unisse ❤️</h3>
                </div>
                <button class="btn" style="margin-top: 30px; background: var(--gold); color: black; padding: 20px 40px; font-size: 1.5rem;" onclick="explodeConfetti()">🎉 OUI JE LE VEUX 🎉</button>
            </div>
            <div class="lang-ar">
                <h1 style="font-size: 3.5rem;">إن شاء الله 💍👑</h1>
                <p style="font-size: 1.3rem; font-weight: bold;">مبروك حياتي، لقد نجوتِ من هذا الموقع المجنون!</p>
                <p>أثبتِ أنك محاربة حقيقية وتستحقين العالم. سنقيم أجمل عرس، بالقفطان الملكي والكاراكو والزغاريد حتى الجزائر العاصمة.</p>
                <p>ملاحظة: سأتركك تطبخين الكسكس كل جمعة (أنا أمزح... سأقوم بالجلوس وأكله فقط 😋).</p>
                <div style="background: rgba(255,255,255,0.8); padding: 20px; border-radius: 15px; margin-top: 20px; border: 3px dashed var(--primary);">
                    <h3 style="margin:0; font-size: 2rem;">اللهم بارك لنا واجمع بيننا في خير ❤️</h3>
                </div>
                <button class="btn" style="margin-top: 30px; background: var(--gold); color: black; padding: 20px 40px; font-size: 1.5rem;" onclick="explodeConfetti()">🎉 أقبل بك 🎉</button>
            </div>
        </div>

    </div>

    <div id="sad-mode">
        <h1 id="sad-text"></h1>
        <img src="https://media.tenor.com/J7r5uN2nEbwAAAAC/neymar-crying.gif" alt="Neymar pleure">
    </div>
    <div class="secret-translator" id="translator" onclick="toggleLanguage()" title="Traduction">✨</div>

    <script>
        function unlockSection(id) {
            const section = document.getElementById(id);
            if(section && !section.classList.contains('unlocked')) {
                section.classList.add('unlocked');
                setTimeout(() => { section.scrollIntoView({ behavior: 'smooth', block: 'center' }); }, 500);
            }
        }

        // ================= ÉTAPE 1 : PIÈGE =================
        let clickCount = 0;
        function handleMainClick(btn, lang) {
            if (btn.dataset.isTrap === "true") { activateSadMode(lang); return; }
            clickCount++;
            if (clickCount === 8) { 
                document.getElementById('main-btn-fr').innerText = "Je t'aime pas"; document.getElementById('main-btn-ar').innerText = "أنا لا أحبك";
                document.getElementById('main-btn-fr').style.background = "#333"; document.getElementById('main-btn-ar').style.background = "#333";
                document.getElementById('main-btn-fr').dataset.isTrap = "true"; document.getElementById('main-btn-ar').dataset.isTrap = "true";
                document.getElementById('tiny-btn-fr').style.display = 'inline-block'; document.getElementById('tiny-btn-ar').style.display = 'inline-block';
            }
        }

        function handleTinyClick(lang) {
            clickCount++;
            if (clickCount >= 15) { 
                document.getElementById('main-btn-fr').innerText = "Validé ❤️"; document.getElementById('main-btn-ar').innerText = "تم ❤️";
                document.getElementById('main-btn-fr').style.background = "var(--gold)"; document.getElementById('main-btn-ar').style.background = "var(--gold)";
                document.getElementById('main-btn-fr').dataset.isTrap = "false"; document.getElementById('main-btn-ar').dataset.isTrap = "false";
                document.getElementById('tiny-btn-fr').style.display = 'none'; document.getElementById('tiny-btn-ar').style.display = 'none';
                unlockSection('etape2');
            }
        }

        // ================= ÉTAPE 2 & 3 : QUIZZ =================
        function checkDoudou(answer) {
            if(answer === 'titi') {
                document.getElementById('doudou-res-fr').innerText = "Bravooo l'amour de ma vie ❤️🐥"; document.getElementById('doudou-res-ar').innerText = "برافو يا حب حياتي ❤️🐥";
                unlockSection('etape3'); 
            } else {
                document.getElementById('doudou-res-fr').innerText = "T'es sah là ? Essaye encore ! 😒"; document.getElementById('doudou-res-ar').innerText = "من نيتك؟ زيدي خمي 😒";
            }
        }

        function checkCouple(question, answer) {
            if(question === 1) {
                if(answer === 'toi') {
                    document.getElementById('couple-res-1').innerText = "Évidemment mdr, la reine de la bouderie 👑"; document.getElementById('couple-res-1-ar').innerText = "طبعاً ههه، ملكة الزعاف 👑";
                    unlockSection('couple-quiz-2'); unlockSection('couple-quiz-2-ar');
                } else {
                    document.getElementById('couple-res-1').innerText = "Menteuse, assume ! 😂"; document.getElementById('couple-res-1-ar').innerText = "كذابة، اعترفي! 😂";
                }
            } else if(question === 2) {
                if(answer === 'toi') {
                    document.getElementById('couple-res-2').innerText = "La ji3ena number 1 🍕❤️ (Débloqué)"; document.getElementById('couple-res-2-ar').innerText = "الجيعانة رقم 1 🍕❤️ (تم الفتح)";
                    unlockSection('etape4'); initMemoryGame(); 
                } else {
                    document.getElementById('couple-res-2').innerText = "Ptdr tu mens tellement mal 🤥"; document.getElementById('couple-res-2-ar').innerText = "ههه تكذبي بزاف 🤥";
                }
            }
        }

        // ================= ÉTAPE 4 : MEMORY =================
        const cardsArray = ['🐥','🐥','🧃','🧃','🇩🇿','🇩🇿','💍','💍','❤️','❤️','👑','👑'];
        let firstCard = null, secondCard = null, matches = 0;
        function initMemoryGame() {
            const grid = document.getElementById('memory-grid');
            if(grid.innerHTML !== "") return;
            let shuffled = cardsArray.sort(() => 0.5 - Math.random());
            shuffled.forEach(emoji => {
                const card = document.createElement('div'); card.classList.add('memory-card'); card.dataset.emoji = emoji; card.onclick = () => flipCard(card); grid.appendChild(card);
            });
            document.getElementById('memory-grid-ar').innerHTML = grid.innerHTML;
            document.querySelectorAll('#memory-grid-ar .memory-card').forEach(c => { c.onclick = () => flipCard(c); });
        }
        function flipCard(card) {
            if (card.classList.contains('flipped') || secondCard) return;
            card.classList.add('flipped'); card.innerText = card.dataset.emoji;
            if (!firstCard) { firstCard = card; } else { secondCard = card; checkMemoryMatch(); }
        }
        function checkMemoryMatch() {
            if (firstCard.dataset.emoji === secondCard.dataset.emoji) {
                firstCard.classList.add('matched'); secondCard.classList.add('matched');
                firstCard = null; secondCard = null; matches++;
                if (matches === 6 || matches === 12) { setTimeout(() => { alert("Tu as une bonne mémoire ma femme ! 🧠❤️"); unlockSection('etape5'); initTiti(); }, 500); }
            } else {
                setTimeout(() => { firstCard.classList.remove('flipped'); secondCard.classList.remove('flipped'); firstCard.innerText = ''; secondCard.innerText = ''; firstCard = null; secondCard = null; }, 800);
            }
        }

        // ================= ÉTAPE 5 : CHASSE TITI =================
        let titiCount = 0, titiInterval;
        function initTiti() {
            titiInterval = setInterval(() => {
                const t1 = document.getElementById('titi-target'), t2 = document.getElementById('titi-target-ar');
                if(t1) { t1.style.left = Math.random() * 80 + '%'; t1.style.top = Math.random() * 80 + '%'; }
                if(t2) { t2.style.left = Math.random() * 80 + '%'; t2.style.top = Math.random() * 80 + '%'; }
            }, 800); 
        }
        function catchTiti() {
            titiCount++;
            document.getElementById('titi-score').innerText = titiCount; document.getElementById('titi-score-ar').innerText = titiCount;
            const t1 = document.getElementById('titi-target'), t2 = document.getElementById('titi-target-ar');
            t1.style.transform = "scale(1.5)"; t2.style.transform = "scale(1.5)";
            setTimeout(() => { t1.style.transform = "scale(1)"; t2.style.transform = "scale(1)"; }, 200);
            if(titiCount >= 5) { clearInterval(titiInterval); t1.style.display = 'none'; t2.style.display = 'none'; unlockSection('etape6'); }
        }

        // ================= ÉTAPE 6 : MOT DE PASSE =================
        function checkVault(lang) {
            const val = document.getElementById(lang === 'fr' ? 'vault-input-fr' : 'vault-input-ar').value.toLowerCase().replace(/\s/g, '');
            const res = document.getElementById(lang === 'fr' ? 'vault-res-fr' : 'vault-res-ar');
            if(val === 'capri-sun' || val === 'caprisun' || val === 'كابريسن' || val === 'كابريسن') {
                res.innerText = lang === 'fr' ? "Bien joué, c'est lui mon rival 😂🧃" : "أحسنتِ، هذا هو منافسي 😂🧃"; unlockSection('etape7');
            } else {
                res.innerText = lang === 'fr' ? "Faux... Tu as oublié le sang de tes veines ?" : "خطأ... هل نسيت مشروبك المفضل؟";
            }
        }

        // ================= ÉTAPE 7 : JAUGE D'AMOUR NERFÉE =================
        let loveProgress = 0;
        function fillLoveBar() {
            if(loveProgress >= 100) return;
            loveProgress += 5; // BEAUCOUP PLUS FACILE (20 clics)
            
            document.getElementById('love-bar').style.width = loveProgress + "%"; document.getElementById('love-bar').innerText = Math.floor(loveProgress) + "%";
            document.getElementById('love-bar-ar').style.width = loveProgress + "%"; document.getElementById('love-bar-ar').innerText = Math.floor(loveProgress) + "%";

            setTimeout(() => { 
                if(loveProgress > 0 && loveProgress < 100) { 
                    loveProgress -= 2; // Baisse plus doucement
                    if(loveProgress < 0) loveProgress = 0;
                    document.getElementById('love-bar').style.width = loveProgress + "%"; document.getElementById('love-bar-ar').style.width = loveProgress + "%"; 
                } 
            }, 800);

            if(loveProgress >= 100) {
                document.getElementById('love-bar').style.background = "var(--gold)"; document.getElementById('love-bar-ar').style.background = "var(--gold)";
                document.getElementById('love-bar').innerText = "100% ❤️"; document.getElementById('love-bar-ar').innerText = "100% ❤️";
                unlockSection('etape8');
            }
        }

        // ================= ÉTAPE 8 : DIGICODE DZ =================
        let currentCode = "";
        function pressKey(num) {
            if(currentCode.length >= 3) currentCode = "";
            currentCode += num;
            
            let displayStr = currentCode + "---".substring(currentCode.length);
            document.getElementById('code-display-fr').innerText = displayStr;
            document.getElementById('code-display-ar').innerText = displayStr;

            if(currentCode.length === 3) {
                if(currentCode === "213") {
                    document.getElementById('code-display-fr').style.background = "#006633"; document.getElementById('code-display-fr').style.color = "white";
                    document.getElementById('code-display-ar').style.background = "#006633"; document.getElementById('code-display-ar').style.color = "white";
                    document.getElementById('code-res-fr').innerText = "Code DZ Validé 🇩🇿🔓"; document.getElementById('code-res-ar').innerText = "تم التحقق 🇩🇿🔓";
                    unlockSection('etape9');
                } else {
                    document.getElementById('code-res-fr').innerText = "Faux ! T'es pas une vraie DZ ? 🤨"; document.getElementById('code-res-ar').innerText = "خطأ! لست جزائرية حقيقية؟ 🤨";
                    setTimeout(() => { currentCode = ""; document.getElementById('code-display-fr').innerText = "---"; document.getElementById('code-display-ar').innerText = "---"; }, 1000);
                }
            }
        }

        // ================= ÉTAPE 9 : CASINO =================
        const slotItemsFr = ["Faire la vaisselle 🧽", "Payer un grec 🍟", "Rien, t'es punie 🚫", "Un bisou de ton homme 😘", "Faire un massage 💆‍♀️"];
        const slotItemsAr = ["غسل الأطباق 🧽", "شراء عشاء 🍟", "لا شيء، أنت معاقبة 🚫", "قبلة من زوجك 😘", "عمل مساج 💆‍♀️"];
        let isSpinning = false;
        function spinSlot(lang) {
            if(isSpinning) return;
            isSpinning = true;
            const slot = document.getElementById(lang === 'fr' ? 'slot-fr' : 'slot-ar');
            const arr = lang === 'fr' ? slotItemsFr : slotItemsAr;
            let counter = 0;
            
            const spinInt = setInterval(() => {
                slot.innerText = arr[Math.floor(Math.random() * arr.length)];
                counter++;
                if(counter > 30) {
                    clearInterval(spinInt);
                    slot.innerText = lang === 'fr' ? "Un bisou de ton homme 😘" : "قبلة من زوجك 😘"; // TOMBE TOUJOURS LÀ DESSUS
                    slot.style.background = "var(--gold)"; slot.style.color = "black";
                    document.getElementById(lang === 'fr' ? 'btn-slot-fr' : 'btn-slot-ar').style.display = 'none';
                    setTimeout(() => unlockSection('etape10'), 1000);
                }
            }, 80);
        }

        // ================= ÉTAPE 10 : DÉTECTEUR =================
        let holdTimer, holdProgress = 0, holdInterval;
        function startHold(lang) {
            holdProgress = 0;
            holdInterval = setInterval(() => {
                holdProgress += 3.5;
                document.getElementById('fill-' + lang).style.width = holdProgress + "%";
                if(holdProgress >= 100) {
                    clearInterval(holdInterval);
                    document.getElementById('fill-' + lang).style.background = "var(--gold)";
                    document.getElementById('hold-' + lang).innerText = "VALIDÉ ✔️";
                    document.getElementById('hold-' + lang).onmousedown = null; document.getElementById('hold-' + lang).ontouchstart = null;
                    unlockSection('etape11');
                }
            }, 100);
        }
        function endHold(lang) {
            clearInterval(holdInterval);
            if(holdProgress < 100) {
                holdProgress = 0; document.getElementById('fill-' + lang).style.width = "0%";
            }
        }

        // ================= ÉTAPE 11 : BAGUE =================
        function moveRing() {
            const btn = document.getElementById('ring-btn');
            if(Math.random() > 0.15) { 
                btn.style.left = Math.random() * 80 + '%'; btn.style.top = Math.random() * 80 + '%';
            }
        }
        function winRingGame() {
            document.getElementById('ring-btn').innerText = "💖 ATTRAPÉE 💖";
            document.getElementById('ring-btn').style.transform = "scale(1.5)";
            document.getElementById('ring-game-area').onmousemove = null; document.getElementById('ring-game-area').ontouchmove = null;
            setTimeout(() => { unlockSection('etape12'); }, 1000);
        }

        // ================= FINAL CONFETTIS =================
        function explodeConfetti() {
            for(let i=0; i<150; i++) {
                const conf = document.createElement('div');
                conf.style.position = 'fixed'; conf.style.width = '15px'; conf.style.height = '15px';
                conf.style.background = ['#ff0055', '#d4af37', '#006633', '#ffffff'][Math.floor(Math.random() * 4)];
                conf.style.left = '50vw'; conf.style.top = '50vh'; conf.style.zIndex = '99999';
                conf.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                
                const angle = Math.random() * Math.PI * 2;
                const velocity = 30 + Math.random() * 50;
                const tx = Math.cos(angle) * velocity * 20; const ty = Math.sin(angle) * velocity * 20;
                conf.style.transition = 'all 2.5s cubic-bezier(0.1, 0.8, 0.3, 1)';
                document.body.appendChild(conf);

                setTimeout(() => { conf.style.transform = `translate(${tx}px, ${ty}px) rotate(${Math.random()*1080}deg)`; conf.style.opacity = '0'; }, 50);
                setTimeout(() => { conf.remove(); }, 2500);
            }
        }

        // ================= MODE TRISTE NEYMAR =================
        let rainInterval;
        function activateSadMode(lang) {
            document.getElementById('main-container').style.display = 'none'; document.getElementById('translator').style.display = 'none'; document.body.style.background = '#000';
            document.getElementById('sad-mode').style.display = 'flex';
            document.getElementById('sad-text').innerText = lang === 'fr' ? "Je savais tu m'aimais pas c triste Leinah sah..." : "كنت علابالي بلي ماتحبينيش، صدمتيني يا لينة صح...";
            rainInterval = setInterval(() => {
                const drop = document.createElement('div'); drop.classList.add('rain'); drop.style.left = Math.random() * 100 + 'vw'; drop.style.top = '-50px'; drop.style.animationDuration = (Math.random() * 0.8 + 0.3) + 's';
                document.getElementById('sad-mode').appendChild(drop); setTimeout(() => drop.remove(), 1200);
            }, 30);
        }

        // ================= TRADUCTION =================
        let isArabic = false;
        function toggleLanguage() {
            isArabic = !isArabic; document.getElementById('body').setAttribute('dir', isArabic ? 'rtl' : 'ltr');
        }
    </script>
</body>
</html>
