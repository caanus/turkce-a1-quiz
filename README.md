# turkce-a1-quiz
Turkish A1.1 Language Quiz - Greetings &amp; Basic Phrases
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Türkçe A1.1 — Selamlaşma & Temel İfadeler</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #f0f4f8;
  --surface: #ffffff;
  --ink: #0f1f35;
  --mid: #4a6080;
  --soft: #8fa3bc;
  --blue: #1e5fa8;
  --blue-light: #ddeaf9;
  --teal: #0e8c7a;
  --teal-light: #d4f0eb;
  --red: #b83232;
  --red-light: #fce8e8;
  --gold: #c47f17;
  --gold-light: #fef3d8;
  --border: rgba(15,31,53,0.1);
  --r: 10px;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--bg);
  color: var(--ink);
  font-family: 'DM Sans', system-ui, sans-serif;
  font-weight: 300;
  min-height: 100vh;
}

/* ── TRANSLATE TOGGLE ── */
.translate-btn {
  position: fixed;
  top: 1rem;
  right: 1rem;
  z-index: 200;
  background: var(--blue);
  color: white;
  border: none;
  padding: 0.6rem 1.1rem;
  border-radius: 20px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.78rem;
  font-weight: 600;
  letter-spacing: 0.02em;
  cursor: pointer;
  box-shadow: 0 4px 14px rgba(15,31,53,0.3);
  transition: all 0.2s;
}
.translate-btn:hover { transform: translateY(-2px); box-shadow: 0 6px 18px rgba(15,31,53,0.35); }
.translate-btn.active { background: var(--teal); }

.en-text {
  display: none;
  font-size: 0.8rem;
  color: var(--mid);
  font-style: italic;
  margin-top: 0.4rem;
  line-height: 1.5;
}
body.show-en .en-text { display: block; }

.en-dark { color: rgba(255,255,255,0.45) !important; }

.section-en {
  margin: -0.6rem 0 1rem;
  padding-left: 0.15rem;
  font-size: 0.74rem;
}

.dialog-box .en-text {
  color: rgba(15,31,53,0.55);
  border-top: 1px dashed rgba(15,31,53,0.18);
  padding-top: 0.5rem;
}

/* ── VOCAB SECTION ── */
.vocab-section {
  background: var(--ink);
  color: white;
  padding: 3rem 1.5rem 2.5rem;
}

.vocab-inner { max-width: 760px; margin: 0 auto; }

.lang-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255,255,255,0.1);
  border: 1px solid rgba(255,255,255,0.2);
  border-radius: 20px;
  padding: 0.3rem 0.9rem;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.05em;
  margin-bottom: 1.4rem;
  color: rgba(255,255,255,0.8);
}

.flag { font-size: 1rem; }

.vocab-title {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(2rem, 5vw, 3.2rem);
  line-height: 1.1;
  margin-bottom: 0.5rem;
  font-weight: 400;
}

.vocab-title em {
  font-style: italic;
  color: rgba(255,255,255,0.55);
}

.vocab-sub {
  font-size: 0.9rem;
  color: rgba(255,255,255,0.55);
  margin-bottom: 0.4rem;
  font-weight: 300;
}

/* Vocab cards grid */
.vocab-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 0.75rem;
  margin-top: 2.2rem;
}

.vcard {
  background: rgba(255,255,255,0.07);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: var(--r);
  padding: 1rem 1.1rem;
  cursor: pointer;
  transition: background 0.2s, transform 0.15s;
  position: relative;
}

.vcard:hover { background: rgba(255,255,255,0.12); transform: translateY(-2px); }

.vcard-num {
  font-size: 0.65rem;
  font-weight: 600;
  color: rgba(255,255,255,0.3);
  letter-spacing: 0.1em;
  margin-bottom: 0.5rem;
}

.vcard-tr {
  font-family: 'DM Serif Display', serif;
  font-size: 1.3rem;
  color: white;
  line-height: 1.2;
  margin-bottom: 0.3rem;
}

.vcard-en {
  font-size: 0.82rem;
  color: rgba(255,255,255,0.5);
  font-weight: 400;
}

.vcard-pron {
  font-size: 0.75rem;
  color: rgba(255,255,255,0.35);
  font-style: italic;
  margin-top: 0.3rem;
}

.vcard-ex {
  display: none;
  margin-top: 0.8rem;
  padding-top: 0.8rem;
  border-top: 1px solid rgba(255,255,255,0.1);
  font-size: 0.8rem;
  color: rgba(255,255,255,0.6);
  line-height: 1.5;
}

.vcard.open .vcard-ex { display: block; }

.vcard-tip {
  font-size: 0.65rem;
  color: rgba(255,255,255,0.25);
  position: absolute;
  bottom: 0.7rem;
  right: 0.9rem;
  transition: opacity 0.2s;
}

.vcard.open .vcard-tip { opacity: 0; }

/* ── DIVIDER ── */
.divider {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 2rem 1.5rem 1.5rem;
  max-width: 760px;
  margin: 0 auto;
}

.divider-line { flex: 1; height: 1px; background: var(--border); }

.divider-label {
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.12em;
  color: var(--soft);
  white-space: nowrap;
}

/* ── SCOREBAR ── */
#scorebar {
  background: var(--surface);
  border-bottom: 1px solid var(--border);
  padding: 0.9rem 1.5rem;
  display: flex;
  justify-content: center;
  gap: 1.8rem;
  position: sticky;
  top: 0;
  z-index: 50;
  box-shadow: 0 2px 8px rgba(15,31,53,0.06);
  flex-wrap: wrap;
}

.sb-item { text-align: center; }
.sb-num {
  font-family: 'DM Serif Display', serif;
  font-size: 1.55rem;
  line-height: 1;
  font-weight: 400;
}
.sb-lbl { font-size: 0.62rem; font-weight: 500; color: var(--soft); margin-top: 0.1rem; letter-spacing: 0.06em; }
.sb-correct .sb-num { color: var(--teal); }
.sb-wrong .sb-num { color: var(--red); }
.sb-left .sb-num { color: var(--blue); }
.sb-pct .sb-num { color: var(--gold); }

.prog-wrap { max-width: 760px; margin: 0 auto; padding: 0 1.5rem; }
.prog-bg { height: 3px; background: var(--border); border-radius: 2px; margin-top: 0.3rem; overflow: hidden; }
.prog-fill { height: 100%; background: linear-gradient(90deg, var(--blue), var(--teal)); transition: width 0.4s ease; width: 0%; }

/* ── QUIZ ── */
main {
  max-width: 760px;
  margin: 0 auto;
  padding: 0 1.5rem 5rem;
}

.section-tag {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin: 1.8rem 0 1rem;
}

.section-tag::after { content: ''; flex: 1; height: 1px; background: var(--border); }

.section-tag span {
  font-size: 0.68rem;
  font-weight: 600;
  color: var(--soft);
  letter-spacing: 0.1em;
  white-space: nowrap;
}

.qcard {
  background: var(--surface);
  border: 1.5px solid var(--border);
  border-radius: var(--r);
  margin-bottom: 1.1rem;
  overflow: hidden;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.qcard:hover { box-shadow: 0 4px 16px rgba(15,31,53,0.07); }
.qcard.ok { border-color: var(--teal); }
.qcard.ng { border-color: var(--red); }

.qhead {
  display: flex;
  align-items: flex-start;
  gap: 0.9rem;
  padding: 1.1rem 1.2rem 0.8rem;
}

.qn {
  font-family: 'DM Serif Display', serif;
  font-size: 1.15rem;
  color: var(--soft);
  min-width: 1.8rem;
  line-height: 1.2;
  font-weight: 400;
}

.qtag-pill {
  font-size: 0.6rem;
  font-weight: 600;
  padding: 0.18rem 0.55rem;
  border-radius: 20px;
  margin-top: 0.25rem;
  white-space: nowrap;
  flex-shrink: 0;
}

.tag-vocab { background: var(--blue-light); color: var(--blue); }
.tag-dialog { background: var(--teal-light); color: var(--teal); }
.tag-grammar { background: var(--gold-light); color: var(--gold); }
.tag-situation { background: #ede8f9; color: #5b30a6; }

.qtext {
  font-size: 0.95rem;
  line-height: 1.6;
  flex: 1;
  font-weight: 400;
  padding-top: 0.1rem;
}

.qtext strong { font-weight: 600; }

/* Dialog bubble style */
.dialog-box {
  background: #f7f9fc;
  border-left: 3px solid var(--blue);
  margin: 0 1.2rem 0.8rem;
  padding: 0.7rem 1rem;
  font-size: 0.88rem;
  line-height: 1.7;
  border-radius: 0 6px 6px 0;
  color: var(--mid);
}

.dialog-box b { color: var(--ink); font-weight: 600; }

.opts {
  padding: 0.4rem 1.2rem 1.1rem;
  display: grid;
  gap: 0.38rem;
}

.opt {
  display: flex;
  align-items: center;
  gap: 0.7rem;
  padding: 0.65rem 0.9rem;
  border: 1.5px solid var(--border);
  border-radius: 7px;
  cursor: pointer;
  transition: all 0.15s;
  font-size: 0.9rem;
  font-weight: 400;
  text-align: left;
  background: white;
  color: var(--ink);
}

.opt:hover:not(.disabled) {
  border-color: var(--blue);
  background: var(--blue-light);
  color: var(--blue);
}

.ol {
  width: 1.5rem;
  height: 1.5rem;
  border-radius: 50%;
  background: #eef2f7;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.72rem;
  font-weight: 600;
  flex-shrink: 0;
  transition: all 0.15s;
  color: var(--mid);
}

.opt:hover:not(.disabled) .ol { background: var(--blue); color: white; }

.opt.correct { border-color: var(--teal); background: var(--teal-light); color: var(--teal); }
.opt.correct .ol { background: var(--teal); color: white; }
.opt.wrong { border-color: var(--red); background: var(--red-light); color: var(--red); }
.opt.wrong .ol { background: var(--red); color: white; }
.opt.show-ok { border-color: var(--teal); background: var(--teal-light); color: var(--teal); }
.opt.show-ok .ol { background: var(--teal); color: white; }
.opt.disabled { cursor: default; }

.fb {
  display: none;
  padding: 0.65rem 1.2rem 0.9rem;
  font-size: 0.82rem;
  line-height: 1.55;
  border-top: 1px dashed var(--border);
}

.fb.show { display: block; }
.fb.ok-fb { color: var(--teal); }
.fb.ng-fb { color: var(--red); }
.fb .hint { color: var(--mid); margin-top: 0.25rem; font-style: italic; }

/* ── RESULT ── */
#result {
  display: none;
  background: var(--ink);
  color: white;
  border-radius: var(--r);
  padding: 3rem 2rem;
  text-align: center;
  margin-top: 2rem;
}
#result.show { display: block; }
#result h2 { font-family: 'DM Serif Display', serif; font-size: 1.8rem; color: rgba(255,255,255,0.7); margin-bottom: 0.3rem; font-weight: 400; }
.big-score { font-family: 'DM Serif Display', serif; font-size: 4.5rem; font-weight: 400; line-height: 1; margin: 0.8rem 0; }
.grade-line { font-size: 1rem; color: rgba(255,255,255,0.6); margin-bottom: 1.5rem; }
.r-grid { display: flex; justify-content: center; gap: 2rem; flex-wrap: wrap; margin-top: 1rem; }
.r-item { text-align: center; }
.r-num { font-family: 'DM Serif Display', serif; font-size: 2rem; font-weight: 400; }
.r-lbl { font-size: 0.65rem; font-weight: 500; color: rgba(255,255,255,0.45); letter-spacing: 0.1em; margin-top: 0.1rem; }
.rc { color: #7ecfc0; } .rw { color: #e88a8a; } .re { color: #f0c96e; }
.rbtn {
  margin-top: 2rem;
  padding: 0.85rem 2.2rem;
  background: white;
  color: var(--ink);
  border: none;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.9rem;
  font-weight: 600;
  cursor: pointer;
  border-radius: 8px;
  transition: all 0.2s;
  letter-spacing: 0.03em;
}
.rbtn:hover { background: #e8edf3; transform: translateY(-2px); }

@media(max-width:560px){
  .vocab-grid { grid-template-columns: repeat(2, 1fr); }
  .vocab-title { font-size: 1.8rem; }
  #scorebar { gap: 1rem; }
  .big-score { font-size: 3.5rem; }
  .translate-btn { top: 0.6rem; right: 0.6rem; padding: 0.5rem 0.85rem; font-size: 0.7rem; }
}
</style>
</head>
<body>

<button class="translate-btn" id="translateBtn" onclick="toggleTranslate()">🇬🇧 English</button>

<!-- ── VOCAB CARDS ────────────────────────────────────────── -->
<section class="vocab-section">
  <div class="vocab-inner">
    <div class="lang-badge"><span class="flag">🇹🇷</span> Türkçe A1.1</div>
    <h1 class="vocab-title">Selamlaşma &<br><em>Temel İfadeler</em></h1>
    <p class="vocab-sub">Önce kelimelerini öğren, sonra testi çöz. Kartlara tıkla → örnek cümle.</p>
    <div class="en-text en-dark">Learn the words first, then take the quiz. Click the cards → example sentence.</div>

    <div class="vocab-grid">

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">01</div>
        <div class="vcard-tr">Merhaba</div>
        <div class="vcard-en">Hello / Hi</div>
        <div class="vcard-pron">[mer-HA-ba]</div>
        <div class="vcard-ex">
          — <b>Merhaba!</b> Nasılsın?<br>
          → Hello! How are you?
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">02</div>
        <div class="vcard-tr">Günaydın</div>
        <div class="vcard-en">Good morning</div>
        <div class="vcard-pron">[gü-nay-DIN]</div>
        <div class="vcard-ex">
          — <b>Günaydın!</b> İyi sabahlar.<br>
          → Good morning! Have a good morning.
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">03</div>
        <div class="vcard-tr">İyi geceler</div>
        <div class="vcard-en">Good night</div>
        <div class="vcard-pron">[i-yi ge-ce-LER]</div>
        <div class="vcard-ex">
          — <b>İyi geceler,</b> yarın görüşürüz!<br>
          → Good night, see you tomorrow!
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">04</div>
        <div class="vcard-tr">Hoşça kal</div>
        <div class="vcard-en">Goodbye (said by leaver)</div>
        <div class="vcard-pron">[hoş-ça-KAL]</div>
        <div class="vcard-ex">
          — <b>Hoşça kal!</b> (sen gidiyorsun)<br>
          → Goodbye! (you are leaving)
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">05</div>
        <div class="vcard-tr">Güle güle</div>
        <div class="vcard-en">Goodbye (said by stayer)</div>
        <div class="vcard-pron">[gü-le gü-LE]</div>
        <div class="vcard-ex">
          — <b>Güle güle!</b> (sen kalıyorsun)<br>
          → Goodbye! (you are staying)
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">06</div>
        <div class="vcard-tr">Nasılsın?</div>
        <div class="vcard-en">How are you? (informal)</div>
        <div class="vcard-pron">[na-sıl-SIN]</div>
        <div class="vcard-ex">
          — <b>Nasılsın?</b> — İyiyim, teşekkürler!<br>
          → How are you? — I'm fine, thanks!
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">07</div>
        <div class="vcard-tr">İyiyim</div>
        <div class="vcard-en">I'm fine / I'm good</div>
        <div class="vcard-pron">[i-yi-YİM]</div>
        <div class="vcard-ex">
          — Nasılsın? — <b>İyiyim,</b> sen?<br>
          → How are you? — I'm fine, you?
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">08</div>
        <div class="vcard-tr">Teşekkür ederim</div>
        <div class="vcard-en">Thank you</div>
        <div class="vcard-pron">[te-şek-kür e-de-RİM]</div>
        <div class="vcard-ex">
          — <b>Teşekkür ederim!</b> — Rica ederim.<br>
          → Thank you! — You're welcome.
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">09</div>
        <div class="vcard-tr">Rica ederim</div>
        <div class="vcard-en">You're welcome</div>
        <div class="vcard-pron">[ri-ca e-de-RİM]</div>
        <div class="vcard-ex">
          — Teşekkürler! — <b>Rica ederim.</b><br>
          → Thanks! — You're welcome.
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

      <div class="vcard" onclick="this.classList.toggle('open')">
        <div class="vcard-num">10</div>
        <div class="vcard-tr">Özür dilerim</div>
        <div class="vcard-en">I'm sorry / Excuse me</div>
        <div class="vcard-pron">[ö-zür di-le-RİM]</div>
        <div class="vcard-ex">
          — <b>Özür dilerim,</b> geç kaldım.<br>
          → I'm sorry, I'm late.
        </div>
        <div class="vcard-tip">tıkla ↓</div>
      </div>

    </div>
  </div>
</section>

<!-- ── SCOREBAR ── -->
<div id="scorebar">
  <div class="sb-item sb-correct"><div class="sb-num" id="sc-c">0</div><div class="sb-lbl">Doğru</div></div>
  <div class="sb-item sb-wrong"><div class="sb-num" id="sc-w">0</div><div class="sb-lbl">Yanlış</div></div>
  <div class="sb-item sb-left"><div class="sb-num" id="sc-l">20</div><div class="sb-lbl">Kalan</div></div>
  <div class="sb-item sb-pct"><div class="sb-num" id="sc-p">—</div><div class="sb-lbl">Başarı</div></div>
</div>
<div class="prog-wrap"><div class="prog-bg"><div class="prog-fill" id="prog"></div></div></div>

<!-- ── QUIZ QUESTIONS ── -->
<main>

<div class="section-tag"><span>Bölüm 1 — Kelime Seçimi</span></div>
<div class="en-text section-en">Section 1 — Vocabulary Choice</div>

<!-- Q1 -->
<div class="qcard" id="q1">
  <div class="qhead"><div class="qn">1</div><div class="qtag-pill tag-vocab">Kelime</div><div class="qtext">Türkçede "Hello / Hi" anlamına gelen kelime hangisidir?<div class="en-text">Which word means "Hello / Hi" in Turkish?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(1,'A')"><span class="ol">A</span>Günaydın</div>
    <div class="opt" onclick="ans(1,'B')"><span class="ol">B</span>Merhaba</div>
    <div class="opt" onclick="ans(1,'C')"><span class="ol">C</span>İyi geceler</div>
    <div class="opt" onclick="ans(1,'D')"><span class="ol">D</span>Hoşça kal</div>
  </div>
  <div class="fb" id="fb1"></div>
</div>

<!-- Q2 -->
<div class="qcard" id="q2">
  <div class="qhead"><div class="qn">2</div><div class="qtag-pill tag-vocab">Kelime</div><div class="qtext">"Good morning" Türkçede nasıl söylenir?<div class="en-text">How do you say "Good morning" in Turkish?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(2,'A')"><span class="ol">A</span>İyi geceler</div>
    <div class="opt" onclick="ans(2,'B')"><span class="ol">B</span>Hoşça kal</div>
    <div class="opt" onclick="ans(2,'C')"><span class="ol">C</span>Günaydın</div>
    <div class="opt" onclick="ans(2,'D')"><span class="ol">D</span>Güle güle</div>
  </div>
  <div class="fb" id="fb2"></div>
</div>

<!-- Q3 -->
<div class="qcard" id="q3">
  <div class="qhead"><div class="qn">3</div><div class="qtag-pill tag-vocab">Kelime</div><div class="qtext">"İyiyim" cümlesinin İngilizce karşılığı nedir?<div class="en-text">What is the English equivalent of "İyiyim"?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(3,'A')"><span class="ol">A</span>I'm sorry</div>
    <div class="opt" onclick="ans(3,'B')"><span class="ol">B</span>Thank you</div>
    <div class="opt" onclick="ans(3,'C')"><span class="ol">C</span>You're welcome</div>
    <div class="opt" onclick="ans(3,'D')"><span class="ol">D</span>I'm fine</div>
  </div>
  <div class="fb" id="fb3"></div>
</div>

<!-- Q4 -->
<div class="qcard" id="q4">
  <div class="qhead"><div class="qn">4</div><div class="qtag-pill tag-vocab">Kelime</div><div class="qtext">"Teşekkür ederim" hangi anlama gelir?<div class="en-text">What does "Teşekkür ederim" mean?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(4,'A')"><span class="ol">A</span>Good night</div>
    <div class="opt" onclick="ans(4,'B')"><span class="ol">B</span>Excuse me</div>
    <div class="opt" onclick="ans(4,'C')"><span class="ol">C</span>Thank you</div>
    <div class="opt" onclick="ans(4,'D')"><span class="ol">D</span>How are you?</div>
  </div>
  <div class="fb" id="fb4"></div>
</div>

<!-- Q5 -->
<div class="qcard" id="q5">
  <div class="qhead"><div class="qn">5</div><div class="qtag-pill tag-vocab">Kelime</div><div class="qtext">"Özür dilerim" ne zaman kullanılır?<div class="en-text">When is "Özür dilerim" used?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(5,'A')"><span class="ol">A</span>Birine teşekkür etmek için</div>
    <div class="opt" onclick="ans(5,'B')"><span class="ol">B</span>Sabah birini selamlamak için</div>
    <div class="opt" onclick="ans(5,'C')"><span class="ol">C</span>Özür dilemek veya birinin dikkatini çekmek için</div>
    <div class="opt" onclick="ans(5,'D')"><span class="ol">D</span>Birini uğurlamak için</div>
  </div>
  <div class="fb" id="fb5"></div>
</div>

<div class="section-tag"><span>Bölüm 2 — Diyalog Tamamlama</span></div>
<div class="en-text section-en">Section 2 — Dialogue Completion</div>

<!-- Q6 -->
<div class="qcard" id="q6">
  <div class="qhead"><div class="qn">6</div><div class="qtag-pill tag-dialog">Diyalog</div><div class="qtext">Boşluğu doldurun:<div class="en-text">Fill in the blank:</div></div></div>
  <div class="dialog-box">— <b>___</b>! Nasılsın?<br>— İyiyim, teşekkürler!<div class="en-text">— ___! How are you?<br>— I'm fine, thanks!</div></div>
  <div class="opts">
    <div class="opt" onclick="ans(6,'A')"><span class="ol">A</span>İyi geceler</div>
    <div class="opt" onclick="ans(6,'B')"><span class="ol">B</span>Hoşça kal</div>
    <div class="opt" onclick="ans(6,'C')"><span class="ol">C</span>Merhaba</div>
    <div class="opt" onclick="ans(6,'D')"><span class="ol">D</span>Özür dilerim</div>
  </div>
  <div class="fb" id="fb6"></div>
</div>

<!-- Q7 -->
<div class="qcard" id="q7">
  <div class="qhead"><div class="qn">7</div><div class="qtag-pill tag-dialog">Diyalog</div><div class="qtext">Boşluğu doldurun:<div class="en-text">Fill in the blank:</div></div></div>
  <div class="dialog-box">— Teşekkür ederim!<br>— <b>___</b>.<div class="en-text">— Thank you!<br>— ___.</div></div>
  <div class="opts">
    <div class="opt" onclick="ans(7,'A')"><span class="ol">A</span>Merhaba</div>
    <div class="opt" onclick="ans(7,'B')"><span class="ol">B</span>Rica ederim</div>
    <div class="opt" onclick="ans(7,'C')"><span class="ol">C</span>Nasılsın</div>
    <div class="opt" onclick="ans(7,'D')"><span class="ol">D</span>Günaydın</div>
  </div>
  <div class="fb" id="fb7"></div>
</div>

<!-- Q8 -->
<div class="qcard" id="q8">
  <div class="qhead"><div class="qn">8</div><div class="qtag-pill tag-dialog">Diyalog</div><div class="qtext">Saat 08:00 sabahı. Ahmet işe giderken komşusuyla karşılaşıyor. Ne söyler?<div class="en-text">It's 8:00 in the morning. Ahmet runs into his neighbor on his way to work. What does he say?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(8,'A')"><span class="ol">A</span>İyi geceler!</div>
    <div class="opt" onclick="ans(8,'B')"><span class="ol">B</span>Hoşça kal!</div>
    <div class="opt" onclick="ans(8,'C')"><span class="ol">C</span>Günaydın!</div>
    <div class="opt" onclick="ans(8,'D')"><span class="ol">D</span>Özür dilerim!</div>
  </div>
  <div class="fb" id="fb8"></div>
</div>

<!-- Q9 -->
<div class="qcard" id="q9">
  <div class="qhead"><div class="qn">9</div><div class="qtag-pill tag-dialog">Diyalog</div><div class="qtext">Boşluğu doldurun:<div class="en-text">Fill in the blank:</div></div></div>
  <div class="dialog-box">— <b>___</b>? (How are you?)<br>— İyiyim, sen?<div class="en-text">— ___? (How are you?)<br>— I'm fine, you?</div></div>
  <div class="opts">
    <div class="opt" onclick="ans(9,'A')"><span class="ol">A</span>Nasılsın</div>
    <div class="opt" onclick="ans(9,'B')"><span class="ol">B</span>Merhaba</div>
    <div class="opt" onclick="ans(9,'C')"><span class="ol">C</span>İyiyim</div>
    <div class="opt" onclick="ans(9,'D')"><span class="ol">D</span>Güle güle</div>
  </div>
  <div class="fb" id="fb9"></div>
</div>

<!-- Q10 -->
<div class="qcard" id="q10">
  <div class="qhead"><div class="qn">10</div><div class="qtag-pill tag-dialog">Diyalog</div><div class="qtext">Boşluğu doldurun:<div class="en-text">Fill in the blank:</div></div></div>
  <div class="dialog-box">— Gece yarısı oluyor. Yatmadan önce eşine ne dersin?<br>— <b>___</b>!<div class="en-text">— It's almost midnight. What do you say to your spouse before going to bed?<br>— ___!</div></div>
  <div class="opts">
    <div class="opt" onclick="ans(10,'A')"><span class="ol">A</span>Günaydın</div>
    <div class="opt" onclick="ans(10,'B')"><span class="ol">B</span>Merhaba</div>
    <div class="opt" onclick="ans(10,'C')"><span class="ol">C</span>İyi geceler</div>
    <div class="opt" onclick="ans(10,'D')"><span class="ol">D</span>Rica ederim</div>
  </div>
  <div class="fb" id="fb10"></div>
</div>

<div class="section-tag"><span>Bölüm 3 — Duruma Göre Doğru İfade</span></div>
<div class="en-text section-en">Section 3 — Choosing the Right Expression for the Situation</div>

<!-- Q11 -->
<div class="qcard" id="q11">
  <div class="qhead"><div class="qn">11</div><div class="qtag-pill tag-situation">Durum</div><div class="qtext">Sen arkadaşını uğurluyorsun, o gidiyor. Sen ne dersin?<div class="en-text">You are seeing off a friend who is leaving. What do you say?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(11,'A')"><span class="ol">A</span>Hoşça kal</div>
    <div class="opt" onclick="ans(11,'B')"><span class="ol">B</span>Güle güle</div>
    <div class="opt" onclick="ans(11,'C')"><span class="ol">C</span>Teşekkür ederim</div>
    <div class="opt" onclick="ans(11,'D')"><span class="ol">D</span>İyi geceler</div>
  </div>
  <div class="fb" id="fb11"></div>
</div>

<!-- Q12 -->
<div class="qcard" id="q12">
  <div class="qhead"><div class="qn">12</div><div class="qtag-pill tag-situation">Durum</div><div class="qtext">Sen gidiyorsun, arkadaşın kalıyor. Sen ne dersin?<div class="en-text">You are leaving, your friend is staying. What do you say?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(12,'A')"><span class="ol">A</span>Güle güle</div>
    <div class="opt" onclick="ans(12,'B')"><span class="ol">B</span>Rica ederim</div>
    <div class="opt" onclick="ans(12,'C')"><span class="ol">C</span>Hoşça kal</div>
    <div class="opt" onclick="ans(12,'D')"><span class="ol">D</span>Günaydın</div>
  </div>
  <div class="fb" id="fb12"></div>
</div>

<!-- Q13 -->
<div class="qcard" id="q13">
  <div class="qhead"><div class="qn">13</div><div class="qtag-pill tag-situation">Durum</div><div class="qtext">Birine yanlışlıkla çarptın. Ne söylersin?<div class="en-text">You accidentally bumped into someone. What do you say?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(13,'A')"><span class="ol">A</span>Teşekkür ederim</div>
    <div class="opt" onclick="ans(13,'B')"><span class="ol">B</span>Nasılsın</div>
    <div class="opt" onclick="ans(13,'C')"><span class="ol">C</span>İyiyim</div>
    <div class="opt" onclick="ans(13,'D')"><span class="ol">D</span>Özür dilerim</div>
  </div>
  <div class="fb" id="fb13"></div>
</div>

<!-- Q14 -->
<div class="qcard" id="q14">
  <div class="qhead"><div class="qn">14</div><div class="qtag-pill tag-situation">Durum</div><div class="qtext">Arkadaşın sana yardım etti. Ona ne dersin?<div class="en-text">Your friend helped you. What do you say to them?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(14,'A')"><span class="ol">A</span>Özür dilerim</div>
    <div class="opt" onclick="ans(14,'B')"><span class="ol">B</span>Güle güle</div>
    <div class="opt" onclick="ans(14,'C')"><span class="ol">C</span>Teşekkür ederim</div>
    <div class="opt" onclick="ans(14,'D')"><span class="ol">D</span>İyi geceler</div>
  </div>
  <div class="fb" id="fb14"></div>
</div>

<!-- Q15 -->
<div class="qcard" id="q15">
  <div class="qhead"><div class="qn">15</div><div class="qtag-pill tag-situation">Durum</div><div class="qtext">Arkadaşın "Teşekkür ederim" dedi. Sen ne cevap verirsin?<div class="en-text">Your friend said "Thank you." What do you reply?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(15,'A')"><span class="ol">A</span>Günaydın</div>
    <div class="opt" onclick="ans(15,'B')"><span class="ol">B</span>Rica ederim</div>
    <div class="opt" onclick="ans(15,'C')"><span class="ol">C</span>Merhaba</div>
    <div class="opt" onclick="ans(15,'D')"><span class="ol">D</span>Nasılsın</div>
  </div>
  <div class="fb" id="fb15"></div>
</div>

<div class="section-tag"><span>Bölüm 4 — Çeviri & Gramer</span></div>
<div class="en-text section-en">Section 4 — Translation & Grammar</div>

<!-- Q16 -->
<div class="qcard" id="q16">
  <div class="qhead"><div class="qn">16</div><div class="qtag-pill tag-grammar">Çeviri</div><div class="qtext">"You're welcome" Türkçede nasıl söylenir?<div class="en-text">How do you say "You're welcome" in Turkish?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(16,'A')"><span class="ol">A</span>Nasılsın</div>
    <div class="opt" onclick="ans(16,'B')"><span class="ol">B</span>Özür dilerim</div>
    <div class="opt" onclick="ans(16,'C')"><span class="ol">C</span>Rica ederim</div>
    <div class="opt" onclick="ans(16,'D')"><span class="ol">D</span>İyiyim</div>
  </div>
  <div class="fb" id="fb16"></div>
</div>

<!-- Q17 -->
<div class="qcard" id="q17">
  <div class="qhead"><div class="qn">17</div><div class="qtag-pill tag-grammar">Çeviri</div><div class="qtext">"How are you?" sorusunu Türkçeye çevirin.<div class="en-text">Translate the question "How are you?" into Turkish.</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(17,'A')"><span class="ol">A</span>Nasılsın?</div>
    <div class="opt" onclick="ans(17,'B')"><span class="ol">B</span>Hoşça kal?</div>
    <div class="opt" onclick="ans(17,'C')"><span class="ol">C</span>İyiyim?</div>
    <div class="opt" onclick="ans(17,'D')"><span class="ol">D</span>Merhaba?</div>
  </div>
  <div class="fb" id="fb17"></div>
</div>

<!-- Q18 -->
<div class="qcard" id="q18">
  <div class="qhead"><div class="qn">18</div><div class="qtag-pill tag-grammar">Gramer</div><div class="qtext">"Güle güle" ile "Hoşça kal" arasındaki fark nedir?<div class="en-text">What is the difference between "Güle güle" and "Hoşça kal"?</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(18,'A')"><span class="ol">A</span>İkisi de aynı anlama gelir, fark yoktur</div>
    <div class="opt" onclick="ans(18,'B')"><span class="ol">B</span>"Güle güle" giden kişi söyler; "Hoşça kal" kalan kişi söyler</div>
    <div class="opt" onclick="ans(18,'C')"><span class="ol">C</span>"Güle güle" kalan kişi söyler; "Hoşça kal" giden kişi söyler</div>
    <div class="opt" onclick="ans(18,'D')"><span class="ol">D</span>"Güle güle" sabah; "Hoşça kal" akşam söylenir</div>
  </div>
  <div class="fb" id="fb18"></div>
</div>

<!-- Q19 -->
<div class="qcard" id="q19">
  <div class="qhead"><div class="qn">19</div><div class="qtag-pill tag-grammar">Çeviri</div><div class="qtext">Aşağıdaki İngilizce ifadeyi Türkçeye çevirin: "I'm sorry, I'm late."<div class="en-text">Translate the following English phrase into Turkish: "I'm sorry, I'm late."</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(19,'A')"><span class="ol">A</span>Teşekkür ederim, geç kaldım.</div>
    <div class="opt" onclick="ans(19,'B')"><span class="ol">B</span>Özür dilerim, geç kaldım.</div>
    <div class="opt" onclick="ans(19,'C')"><span class="ol">C</span>Rica ederim, geç kaldım.</div>
    <div class="opt" onclick="ans(19,'D')"><span class="ol">D</span>İyiyim, geç kaldım.</div>
  </div>
  <div class="fb" id="fb19"></div>
</div>

<!-- Q20 -->
<div class="qcard" id="q20">
  <div class="qhead"><div class="qn">20</div><div class="qtag-pill tag-grammar">Karma</div><div class="qtext">Aşağıdaki diyalogu doğru sıraya koyun:<br><small style="color:var(--mid)">1) Rica ederim!  2) Merhaba! Nasılsın?  3) İyiyim, teşekkür ederim!</small><div class="en-text">Put the following dialogue in the correct order:<br>1) You're welcome!  2) Hello! How are you?  3) I'm fine, thank you!</div></div></div>
  <div class="opts">
    <div class="opt" onclick="ans(20,'A')"><span class="ol">A</span>3 → 1 → 2</div>
    <div class="opt" onclick="ans(20,'B')"><span class="ol">B</span>2 → 3 → 1</div>
    <div class="opt" onclick="ans(20,'C')"><span class="ol">C</span>1 → 2 → 3</div>
    <div class="opt" onclick="ans(20,'D')"><span class="ol">D</span>2 → 1 → 3</div>
  </div>
  <div class="fb" id="fb20"></div>
</div>

<!-- Result -->
<div id="result">
  <h2>Tebrikler!</h2>
  <div class="big-score" id="final-s">—</div>
  <div class="grade-line" id="final-g"></div>
  <div class="r-grid">
    <div class="r-item"><div class="r-num rc" id="r-c">0</div><div class="r-lbl">Doğru</div></div>
    <div class="r-item"><div class="r-num rw" id="r-w">0</div><div class="r-lbl">Yanlış</div></div>
    <div class="r-item"><div class="r-num re" id="r-e">0</div><div class="r-lbl">Boş</div></div>
  </div>
  <button class="rbtn" onclick="restart()">Tekrar Çöz</button>
</div>

</main>

<script>
const D = {
  1:{c:'B',e:'✓ Doğru! "Merhaba" evrensel bir selamlama; her zaman kullanabilirsin.',h:''},
  2:{c:'C',e:'✓ Doğru! "Günaydın" kelimesi "gün + aydın" dan gelir → parlak gün!',h:''},
  3:{c:'D',e:'✓ Doğru! "İyiyim" = "I am fine". "-yim" eki "I am" anlamına gelir.',h:''},
  4:{c:'C',e:'✓ Doğru! "Teşekkür ederim" = "Thank you". Kısa hali: "Teşekkürler!"',h:''},
  5:{c:'C',e:'✓ Doğru! "Özür dilerim" hem "I\'m sorry" hem de "Excuse me" anlamında kullanılır.',h:''},
  6:{c:'C',e:'✓ Doğru! Selamlaşma "Merhaba" ile başlar, ardından "Nasılsın?" gelir.',h:'Dikkat: "İyi geceler" gece söylenir.'},
  7:{c:'B',e:'✓ Doğru! "Teşekkür ederim" → cevap olarak "Rica ederim" (= You\'re welcome).',h:''},
  8:{c:'C',e:'✓ Doğru! Sabah 08:00\'de "Günaydın!" denir. "İyi geceler" sadece gece söylenir.',h:''},
  9:{c:'A',e:'✓ Doğru! "Nasılsın?" = "How are you?" (gayri resmi / informal)',h:'Resmi hali: "Nasılsınız?"'},
  10:{c:'C',e:'✓ Doğru! Gece yatmadan önce "İyi geceler!" denir. = "Good night!"',h:''},
  11:{c:'B',e:'✓ Doğru! Arkadaşın gidiyor, sen kalıyorsun → "Güle güle!" dersin.',h:'"Hoşça kal" giden kişi söyler.'},
  12:{c:'C',e:'✓ Doğru! Sen gidiyorsun → "Hoşça kal!" dersin. Kalan sana "Güle güle!" der.',h:''},
  13:{c:'D',e:'✓ Doğru! Yanlışlıkla çarptığında "Özür dilerim" = "I\'m sorry / Excuse me".',h:''},
  14:{c:'C',e:'✓ Doğru! Yardım eden kişiye "Teşekkür ederim!" dersin.',h:''},
  15:{c:'B',e:'✓ Doğru! "Teşekkür ederim" → "Rica ederim" (= You\'re welcome).',h:''},
  16:{c:'C',e:'✓ Doğru! "Rica ederim" = "You\'re welcome". Aynı zamanda "Please" anlamında da kullanılır.',h:''},
  17:{c:'A',e:'✓ Doğru! "Nasılsın?" = "How are you?" (tekil/informal). Çoğul: "Nasılsınız?"',h:''},
  18:{c:'C',e:'✓ Doğru! "Güle güle" → kalan kişi söyler. "Hoşça kal" → giden kişi söyler. İkisi birbirinin tamamlayıcısıdır!',h:''},
  19:{c:'B',e:'✓ Doğru! "Özür dilerim, geç kaldım." = "I\'m sorry, I\'m late."',h:''},
  20:{c:'B',e:'✓ Doğru! Doğal sıra: 2) Merhaba! Nasılsın? → 3) İyiyim, teşekkür ederim! → 1) Rica ederim!',h:''}
};

let answered={}, correct=0, wrong=0;
const TOTAL=20;

function ans(n, sel){
  if(answered[n]) return;
  answered[n]=sel;
  const d=D[n];
  const card=document.getElementById('q'+n);
  const fb=document.getElementById('fb'+n);
  card.querySelectorAll('.opt').forEach((o,i)=>{
    o.classList.add('disabled');
    const l=['A','B','C','D'][i];
    if(l===d.c) o.classList.add(sel===d.c?'correct':'show-ok');
    if(l===sel && sel!==d.c) o.classList.add('wrong');
  });
  if(sel===d.c){
    correct++;
    card.classList.add('ok');
    fb.innerHTML='<b>✓ Doğru!</b> '+d.e.replace('✓ Doğru! ','')+(d.h?'<div class="hint">💡 '+d.h+'</div>':'');
    fb.className='fb show ok-fb';
  } else {
    wrong++;
    card.classList.add('ng');
    fb.innerHTML='<b>✗ Yanlış.</b> Doğru cevap: <b>'+d.c+'</b>. '+d.e.replace('✓ Doğru! ','')+(d.h?'<div class="hint">💡 '+d.h+'</div>':'');
    fb.className='fb show ng-fb';
  }
  updateScore();
  if(Object.keys(answered).length===TOTAL) setTimeout(showResult,700);
}

function updateScore(){
  const total=Object.keys(answered).length;
  const pct=total>0?Math.round(correct/total*100):0;
  document.getElementById('sc-c').textContent=correct;
  document.getElementById('sc-w').textContent=wrong;
  document.getElementById('sc-l').textContent=TOTAL-total;
  document.getElementById('sc-p').textContent=total>0?pct+'%':'—';
  document.getElementById('prog').style.width=(total/TOTAL*100)+'%';
}

function showResult(){
  const panel=document.getElementById('result');
  const empty=TOTAL-correct-wrong;
  const pct=Math.round(correct/TOTAL*100);
  document.getElementById('final-s').textContent=pct+'%';
  document.getElementById('r-c').textContent=correct;
  document.getElementById('r-w').textContent=wrong;
  document.getElementById('r-e').textContent=empty;
  let g;
  if(pct===100) g='🌟 Mükemmel! Tüm soruları doğru yaptın!';
  else if(pct>=80) g='🎉 Harika! Selamlaşmayı çok iyi öğrendin.';
  else if(pct>=60) g='👍 İyi! Birkaç kelimeyi tekrar et.';
  else if(pct>=40) g='📖 Kartlara geri dön ve tekrar çalış.';
  else g='🔁 Endişelenme! Kartları tekrar oku ve dene.';
  document.getElementById('final-g').textContent=g;
  panel.classList.add('show');
  panel.scrollIntoView({behavior:'smooth',block:'center'});
}

function restart(){
  answered={}; correct=0; wrong=0;
  document.querySelectorAll('.qcard').forEach(c=>c.classList.remove('ok','ng'));
  document.querySelectorAll('.opt').forEach((o,_)=>{ o.className='opt'; });
  // Re-bind clicks
  const qs=[...document.querySelectorAll('.qcard')];
  qs.forEach(card=>{
    const num=parseInt(card.id.replace('q',''));
    card.querySelectorAll('.opt').forEach((o,i)=>{
      const l=['A','B','C','D'][i];
      o.onclick=()=>ans(num,l);
    });
  });
  document.querySelectorAll('.fb').forEach(f=>{f.className='fb';f.innerHTML='';});
  document.getElementById('result').classList.remove('show');
  updateScore();
  window.scrollTo({top:0,behavior:'smooth'});
}

function toggleTranslate(){
  const btn=document.getElementById('translateBtn');
  const on=document.body.classList.toggle('show-en');
  btn.classList.toggle('active', on);
  btn.textContent = on ? '🇹🇷 Türkçe' : '🇬🇧 English';
}
</script>
</body>
</html>
