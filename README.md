[Index · HTML.html](https://github.com/user-attachments/files/27944507/Index.HTML.html)[Uploading Index <!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>自己紹介</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@400;700&family=Zen+Kaku+Gothic+New:wght@300;400;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #a0f09a;
      --surface: #1a1a1a;
      --card: #ffffff;
      --accent: #3a9bbf;
      --accent2: #7eb8c8;
      --text: #1a3a4a;
      --text-muted: #6a96aa;
      --border: rgba(200, 169, 110, 0.2);
    }
 
    * { margin: 0; padding: 0; box-sizing: border-box; }
 
    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Zen Kaku Gothic New', sans-serif;
      font-weight: 300;
      line-height: 1.8;
      overflow-x: hidden;
    }

     /* ─── 背景グラデーション ─── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background:
        radial-gradient(ellipse at 20% 20%, rgba(180,225,245,0.45) 0%, transparent 55%),
        radial-gradient(ellipse at 80% 80%, rgba(200,235,250,0.4) 0%, transparent 55%);
      pointer-events: none;
      z-index: 0;
    }

    /* ─── ヘッダー ─── */
    header {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 4rem 2rem;
      overflow: hidden;
    }
 
    header::after {
      content: '';
      position: absolute;
      width: 600px;
      height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(58,155,191,0.15) 0%, transparent 70%);
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      pointer-events: none;
    }
 
    .name-label {
      font-family: 'Noto Serif JP', serif;
      font-size: clamp(0.7rem, 1.5vw, 0.85rem);
      letter-spacing: 0.4em;
      color: var(--accent);
      text-transform: uppercase;
      margin-bottom: 1.2rem;
      animation: fadeUp 0.8s ease both;
    }
 
    h1 {
      font-family: 'Noto Serif JP', serif;
      font-size: clamp(2.8rem, 8vw, 6rem);
      font-weight: 700;
      letter-spacing: 0.05em;
      line-height: 1.1;
      animation: fadeUp 0.8s 0.15s ease both;
    }
 
    h1 span {
      display: block;
      color: var(--accent);
    }
 
    .tagline {
      margin-top: 1.8rem;
      font-size: clamp(0.85rem, 2vw, 1rem);
      color: var(--text-muted);
      letter-spacing: 0.15em;
      animation: fadeUp 0.8s 0.3s ease both;
    }
 
    .scroll-hint {
      position: absolute;
      bottom: 2.5rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.5rem;
      color: var(--text-muted);
      font-size: 0.7rem;
      letter-spacing: 0.25em;
      animation: fadeUp 0.8s 0.6s ease both;
    }
 
    .scroll-hint::after {
      content: '';
      width: 1px;
      height: 50px;
      background: linear-gradient(to bottom, var(--accent), transparent);
      animation: scrollLine 1.5s ease-in-out infinite;
    }
 
    @keyframes scrollLine {
      0%, 100% { opacity: 0.3; transform: scaleY(0.6); transform-origin: top; }
      50% { opacity: 1; transform: scaleY(1); }
    }
 
    /* ─── セクション共通 ─── */
    main {
      position: relative;
      z-index: 1;
      max-width: 860px;
      margin: 0 auto;
      padding: 4rem 2rem 8rem;
      display: flex;
      flex-direction: column;
      gap: 4rem;
    }
 
    .section {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
 
    .section.visible {
      opacity: 1;
      transform: translateY(0);
    }
 
    .section-header {
      display: flex;
      align-items: center;
      gap: 1rem;
      margin-bottom: 1.8rem;
    }
 
    .section-num {
      font-family: 'Noto Serif JP', serif;
      font-size: 0.75rem;
      color: var(--accent);
      letter-spacing: 0.2em;
    }
 
    .section-title {
      font-family: 'Noto Serif JP', serif;
      font-size: clamp(1.3rem, 3vw, 1.7rem);
      font-weight: 700;
      letter-spacing: 0.08em;
    }
 
    .section-line {
      flex: 1;
      height: 1px;
      background: var(--border);
    }
 
    /* ─── カード ─── */
    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 2rem 2.5rem;
      position: relative;
      overflow: hidden;
    }
 
    .card::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px;
      height: 100%;
      background: linear-gradient(to bottom, var(--accent), transparent);
    }
 
    .card p {
      font-size: 1rem;
      color: var(--text);
      line-height: 2;
    }
 
    /* ─── 趣味グリッド ─── */
    .hobby-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: 1rem;
    }
 
    .hobby-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1.2rem 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
      font-size: 0.95rem;
      transition: border-color 0.3s, transform 0.3s;
    }
 
    .hobby-item:hover {
      border-color: var(--accent);
      transform: translateY(-3px);
    }
 
    .hobby-icon {
      font-size: 1.4rem;
    }
 
    /* ─── 連絡先 ─── */
    .contact-list {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }
 
    .contact-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1rem 1.5rem;
      display: flex;
      align-items: center;
      gap: 1rem;
      font-size: 0.95rem;
      transition: border-color 0.3s;
    }
 
    .contact-item:hover { border-color: var(--accent2); }
 
    .contact-label {
      color: var(--accent2);
      font-size: 0.8rem;
      letter-spacing: 0.1em;
      min-width: 80px;
    }
 
    /* ─── 目標 ─── */
    .goal-list {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
      counter-reset: goal;
    }
 
    .goal-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1.2rem 1.5rem 1.2rem 4rem;
      position: relative;
      font-size: 0.95rem;
      transition: border-color 0.3s;
      counter-increment: goal;
    }
 
    .goal-item:hover { border-color: var(--accent); }
 
    .goal-item::before {
      content: counter(goal, decimal-leading-zero);
      position: absolute;
      left: 1.2rem;
      top: 50%;
      transform: translateY(-50%);
      font-family: 'Noto Serif JP', serif;
      font-size: 1.1rem;
      color: var(--accent);
      font-weight: 700;
    }
 
    /* ─── 座右の銘 ─── */
    .quote-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 3rem 2.5rem;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
 
    .quote-card::after {
      content: '""';
      position: absolute;
      top: -1rem;
      left: 1.5rem;
      font-family: 'Noto Serif JP', serif;
      font-size: 8rem;
      color: rgba(58, 155, 191, 0.12);
      line-height: 1;
      pointer-events: none;
    }
 
    .quote-text {
      font-family: 'Noto Serif JP', serif;
      font-size: clamp(1.2rem, 3vw, 1.6rem);
      font-weight: 700;
      letter-spacing: 0.15em;
      line-height: 1.8;
      color: var(--accent);
      position: relative;
      z-index: 1;
    }
 
    .quote-sub {
      margin-top: 1rem;
      font-size: 0.85rem;
      color: var(--text-muted);
      letter-spacing: 0.1em;
    }
 
    /* ─── フッター ─── */
    footer {
      text-align: center;
      padding: 3rem 1rem;
      color: var(--text-muted);
      font-size: 0.8rem;
      letter-spacing: 0.15em;
      border-top: 1px solid var(--border);
    }
 
    /* ─── アニメーション ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
  /* ─── ナビゲーション ─── */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background: rgba(240, 247, 251, 0.85);
  transition: background 0.3s, border-color 0.3s;
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border);
}

body.dark nav {
 background: rgba(15, 30, 40, 0.92);
 border-color: var(--border);}

.nav-logo {
  font-family: 'Noto Serif JP', serif;
  font-weight: 700;
  color: var(--accent);
  font-size: 1rem;
  letter-spacing: 0.1em;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links a {
  color: var(--text);
  text-decoration: none;
  font-size: 0.85rem;
  letter-spacing: 0.1em;
  transition: color 0.3s;
}

.nav-links a:hover { color: var(--accent); }

/* ハンバーガーボタン（スマホのみ表示） */
.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  background: none;
  border: none;
  padding: 4px;
}

.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--accent);
  transition: all 0.3s;
}

/* ハンバーガー → ✕ に変化 */
.hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.open span:nth-child(2) { opacity: 0; }
.hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

/* スマホ用メニュー */
@media (max-width: 640px) {
  .hamburger { display: flex; }

  .nav-links {
    display: none;
    position: absolute;
    top: 100%;
    left: 0; right: 0;
    flex-direction: column;
    gap: 0;
    background: rgba(240, 247, 251, 0.97);
    transition: background 0.3s, border-color 0.3s;
    border-bottom: 1px solid var(--border);
  }

  .nav-links.open { display: flex; }

  .nav-links li a {
    display: block;
    padding: 1rem 2rem;
    border-bottom: 1px solid var(--border);
  }
}
/* ─── ダークモード ─── */

body.dark {
  --bg: #0f1e2b;
  --accent: #5bb8d4;
  --accent2: #7eb8c8;
  --text: #e8e2d9;
  --text-muted: #888880;
  --border: rgba(91, 184, 212, 0.2);
}
body.dark::before {
  background:
    radial-gradient(ellipse at 20% 20%, rgba(13,31,45,0.8) 0%, transparent 55%),
    radial-gradient(ellipse at 80% 80%, rgba(15,30,43,0.8) 0%, transparent 55%);
}

body.dark header {
  position: relative;
  min-height: 100vh;
}

/* 切り替えボタン */
.theme-btn {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  z-index: 200;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: 1px solid var(--border);
  background: var(--card);
  color: var(--text);
  font-size: 1.3rem;
  cursor: pointer;
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
  transition: transform 0.3s, box-shadow 0.3s;
}

.theme-btn:hover {
  transform: scale(1.1);
  box-shadow: 0 6px 20px rgba(0,0,0,0.2);
}
  </style>
</head>
<body>
 
<nav>
  <span class="nav-logo">My Portfolio</span>
  <ul class="nav-links" id="navLinks">
    <li><a href="#about">自己紹介</a></li>
    <li><a href="#hobbies">趣味</a></li>
    <li><a href="#contact">連絡先</a></li>
    <li><a href="#goals">目標</a></li>
    <li><a href="#motto">座右の銘</a></li>
  </ul>
  <button class="hamburger" id="hamburger">
    <span></span><span></span><span></span>
  </button>
</nav>
  <!-- ヘッダー（名前） -->
  <header>
    <p class="name-label">Portfolio &amp; Profile</p>
    <h1>
      福留 康介
      <span>Fukudome Kosuke</span>
    </h1>
    <p class="tagline">学生エンジニア / 鹿児島在住</p>
    <div class="scroll-hint">SCROLL</div>
  </header>
 
  <main>
 
    <!-- 自己紹介 -->
    <section class="section" id="about">
      <div class="section-header">
        <span class="section-num">01</span>
        <h2 class="section-title">自己紹介</h2>
        <div class="section-line"></div>
      </div>
      <div class="card">
        <p>
          はじめまして、こーすけと言われています。<br>
          N高校を卒業後、海外留学をするために勉強しています。<br>
          自動車の免許を取るために教習所に通い始め、運転の魅力にハマりました！<br>
          そして小説・実用書など本を読むことが好きです。
          自然が好きで朝散歩は欠かせない存在です！
          皆さんはどんな趣味がありますか？ぜひ教えてください！
        </p>
      </div>
    </section>
 
    <!-- 趣味 -->
    <section class="section" id="hobbies">
      <div class="section-header">
        <span class="section-num">02</span>
        <h2 class="section-title">趣味</h2>
        <div class="section-line"></div>
      </div>
      <div class="hobby-grid">
        <div class="hobby-item"><span class="hobby-icon">🚶</span>散歩</div>
        <div class="hobby-item"><span class="hobby-icon">🎮</span>LOL</div>
        <div class="hobby-item"><span class="hobby-icon">🎵</span>音楽鑑賞</div>
        <div class="hobby-item"><span class="hobby-icon">💪</span>バーピー</div>
        <div class="hobby-item"><span class="hobby-icon">📚</span>読書</div>
        <div class="hobby-item"><span class="hobby-icon">🍰</span>甘いもの</div>
      </div>
    </section>
 
    <!-- 連絡先 -->
    <section class="section" id="contact">
      <div class="section-header">
        <span class="section-num">03</span>
        <h2 class="section-title">連絡先</h2>
        <div class="section-line"></div>
      </div>
      <div class="contact-list">
        <div class="contact-item">
          <span class="contact-label">E-mail</span>
          <span>tk5.hgal29@gmail.com</span>
        </div>
        <div class="contact-item">
          <span class="contact-label">Instagram</span>
          <a href = "https://www.instagram.com/kosuke_happyy"
          target = "_blank"
          style = "color: var(--text); text-decoration: none;">
          @kosuke_happyy</a>
        </div>
        <div class="contact-item">
          <span class="contact-label">GitHub</span>
          <a href = "https://github.com/tk5hgal29-cell"
          target = "_blank"
          style = "color: var(--text); text-decoration: none;">
          tk5hgal29-cell</a>
        </div>
        <div class="contact-item">
          <span class="contact-label">Discord</span>
          <a href = "https://discord.com/users/yassdeath"
          target = "_blank"
          style = "color: var(--text); text-decoration: none;">
          yassdeath</a>
        </div>

      </div>
    </section>
 
    <!-- 目標 -->
    <section class="section" id="goals">
      <div class="section-header">
        <span class="section-num">04</span>
        <h2 class="section-title">目標</h2>
        <div class="section-line"></div>
      </div>
      <div class="goal-list">
        <div class="goal-item">IELTS6.5を取得し、外国人と円滑に会話できるようになる</div>
        <div class="goal-item">7時に起きて23時に寝る習慣を作る</div>
        <div class="goal-item">心理学とプログラミングを活かしみんなのためになるプロダクトを作る</div>
      </div>
    </section>
 
    <!-- 座右の銘 -->
    <section class="section" id="motto">
      <div class="section-header">
        <span class="section-num">05</span>
        <h2 class="section-title">座右の銘</h2>
        <div class="section-line"></div>
      </div>
      <div class="quote-card">
        <p class="quote-text">失敗は成功のもと</p>
        <p class="quote-sub">失敗してもめげずにそれを次の糧にする考え方が大事だと思う</p>
      </div>
    </section>
 
  </main>
 
  <footer>
    <p>© 2026 福留 康介. All rights reserved.</p>
  </footer>
 
  <button class="theme-btn" id="themeBtn">🌙</button>

  <script>
    // スクロールで各セクションをふわっと表示
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, { threshold: 0.15 });
 
    document.querySelectorAll('.section').forEach(el => observer.observe(el));

    // タイピングエフェクト
    const h1Text = document.querySelector('h1').childNodes[0]; // テキストノードを取得
    const spanText = document.querySelector('h1 span');

    const fullName = '福留 康介';
    const fullSub = 'Fukudome Kosuke';

    const speed = 120; // タイピングの速度（ミリ秒）

    h1Text.textContent = ''; // 最初は空にする
    spanText.textContent = ''; // 最初は空にする

    let i = 0; // タイピングのインデックス
    //spanを打つ関数
    function typeSpan(i = 0) {
      if (i < fullSub.length) {
        spanText.textContent += fullSub[i];
        setTimeout(() => typeSpan(i + 1), speed);
      }
    }

    function typeName(i = 0) {
      if (i < fullName.length) {
        h1Text.textContent += fullName[i];

        setTimeout(() => typeName(i + 1), speed);
      } else {
        setTimeout(() => typeSpan(), 300); // 名前のタイピングが終わって少ししたらspanのタイピングを開始
      }
    }

    setTimeout(typeName, 500); // ページ読み込み後にタイピング開始

    // ── ハンバーガーメニュー ──
const hamburger = document.getElementById('hamburger');
const navLinks  = document.getElementById('navLinks');

hamburger.addEventListener('click', () => {
  hamburger.classList.toggle('open');
  navLinks.classList.toggle('open');
});

// メニューのリンクを押したら閉じる
navLinks.querySelectorAll('a').forEach(link => {
  link.addEventListener('click', () => {
    hamburger.classList.remove('open');
    navLinks.classList.remove('open');
  });
});

// ── ダークモード切り替え ──
const themeBtn = document.getElementById('themeBtn');

themeBtn.addEventListener('click', () => {
  document.body.classList.toggle('dark');

  // ボタンのアイコンも切り替え
  const isDark = document.body.classList.contains('dark');
  themeBtn.textContent = isDark ? '☀️' : '🌙';
});

  </script>
</body>
</html>· HTML.html…]()
# -tk5hgal29-cell.github.io
I created my introduction.
