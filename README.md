<!-- LOL Hextech Theme · flashjose -->

<style>
  :root {
    --bg-deep:    #010A13;
    --bg-panel:   #091428;
    --bg-card:    #0D1117;
    --border:     #1E2328;
    --gold:       #C89B3C;
    --gold-light: #C8AA6E;
    --gold-dim:   rgba(200, 155, 60, 0.35);
    --cyan:       #0397AB;
    --t1-red:     #E2012D;
    --text-muted: #8B949E;
    --contrib-0:  #161B22;
    --contrib-1:  #0E4429;
    --contrib-2:  #006D32;
    --contrib-3:  #26A641;
    --contrib-4:  #39D353;
  }

  .readme-root {
    max-width: 820px;
    margin: 0 auto;
    color: #C8AA6E;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
  }

  .divider {
    height: 2px;
    margin: 0;
    background: linear-gradient(90deg, transparent, var(--gold-dim), var(--gold-light), var(--gold-dim), transparent);
  }

  .panel {
    background: linear-gradient(180deg, var(--bg-deep) 0%, var(--bg-panel) 100%);
    border: 1px solid var(--border);
    border-radius: 4px;
    box-shadow: 0 0 40px rgba(200, 155, 60, 0.06), inset 0 0 80px rgba(0, 0, 0, 0.35);
    padding: 28px 20px;
  }

  .panel-t1 {
    background: linear-gradient(180deg, #0A0000 0%, #140005 50%, #0A0000 100%);
    border: 1px solid rgba(226, 1, 45, 0.35);
    border-radius: 4px;
    box-shadow: 0 0 30px rgba(226, 1, 45, 0.08);
    padding: 28px 20px;
    position: relative;
    overflow: hidden;
  }

  .panel-t1::before {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at 50% 0%, rgba(226, 1, 45, 0.12), transparent 60%);
    pointer-events: none;
  }

  .section-title {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 13px;
    letter-spacing: 6px;
    color: var(--gold);
    opacity: 0.75;
    margin-bottom: 20px;
    text-transform: uppercase;
  }

  .heading-gold {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 28px;
    font-weight: 700;
    letter-spacing: 4px;
    color: var(--gold-light);
    text-shadow: 0 0 20px rgba(200, 155, 60, 0.25);
    margin: 0 0 8px;
    line-height: 1.35;
  }

  .heading-t1 {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 32px;
    font-weight: 900;
    letter-spacing: 8px;
    color: #FFE8EC;
    text-shadow: 0 0 18px rgba(226, 1, 45, 0.45);
    margin: 0 0 6px;
    position: relative;
    z-index: 1;
  }

  .subheading {
    font-family: "Courier New", Consolas, monospace;
    font-size: 12px;
    letter-spacing: 4px;
    color: var(--text-muted);
    margin-bottom: 18px;
  }

  .badge-row img {
    margin: 4px;
  }

  .tag-list {
    text-align: center;
    margin-top: 16px;
  }

  .tag {
    display: inline-block;
    margin: 6px;
    padding: 7px 16px;
    border: 1px solid var(--gold-dim);
    border-radius: 3px;
    background: rgba(200, 155, 60, 0.06);
    color: var(--gold-light);
    font-family: "Courier New", Consolas, monospace;
    font-size: 13px;
    letter-spacing: 2px;
  }

  .tag-t1 {
    border-color: rgba(226, 1, 45, 0.45);
    background: rgba(226, 1, 45, 0.08);
    color: #FF8090;
  }

  .quote {
    color: #B8A0A0;
    font-family: Georgia, serif;
    font-size: 14px;
    font-style: italic;
    letter-spacing: 1px;
    line-height: 1.8;
    position: relative;
    z-index: 1;
  }

  /* —— Tetris contribution grid —— */
  @keyframes cell-drop {
    0%   { transform: translateY(-420px); opacity: 0; }
    8%   { opacity: 1; }
    62%  { transform: translateY(0); }
    72%  { transform: translateY(-10px); }
    82%  { transform: translateY(0); }
    100% { transform: translateY(0); opacity: 1; }
  }

  .contrib-wrap {
    display: inline-block;
    background: var(--bg-card);
    border: 1px solid #21262D;
    border-radius: 8px;
    padding: 16px 14px 14px;
    box-shadow: inset 0 0 30px rgba(0, 0, 0, 0.35);
    text-align: left;
  }

  .contrib-months {
    display: grid;
    grid-template-columns: 22px repeat(19, 16px);
    gap: 0;
    margin-bottom: 6px;
    color: var(--text-muted);
    font-family: monospace;
    font-size: 10px;
  }

  .contrib-months span:nth-child(2)  { grid-column: 2 / 5; }
  .contrib-months span:nth-child(3)  { grid-column: 5 / 8; }
  .contrib-months span:nth-child(4)  { grid-column: 8 / 11; }
  .contrib-months span:nth-child(5)  { grid-column: 11 / 14; }
  .contrib-months span:nth-child(6)  { grid-column: 14 / 17; }
  .contrib-months span:nth-child(7)  { grid-column: 17 / 21; }

  .contrib-body {
    display: grid;
    grid-template-columns: 22px 1fr;
    gap: 0 6px;
    align-items: start;
  }

  .contrib-days {
    display: grid;
    grid-template-rows: repeat(7, 16px);
    color: var(--text-muted);
    font-family: monospace;
    font-size: 9px;
    line-height: 16px;
  }

  .contrib-grid {
    display: grid;
    grid-template-rows: repeat(7, 13px);
    grid-auto-flow: column;
    grid-auto-columns: 13px;
    gap: 3px;
  }

  .cell {
    width: 13px;
    height: 13px;
    border-radius: 3px;
    opacity: 0;
    animation: cell-drop 0.42s cubic-bezier(0.22, 0.61, 0.36, 1) forwards;
  }

  .c0 { background: var(--contrib-0); }
  .c1 { background: var(--contrib-1); }
  .c2 { background: var(--contrib-2); }
  .c3 { background: var(--contrib-3); }
  .c4 { background: var(--contrib-4); }

  .contrib-legend {
    margin-top: 12px;
    text-align: right;
    color: var(--text-muted);
    font-family: monospace;
    font-size: 10px;
  }

  .contrib-legend .swatch {
    display: inline-block;
    width: 11px;
    height: 11px;
    border-radius: 2px;
    margin: 0 2px;
    vertical-align: middle;
  }

  .stats-row img {
    margin: 8px 4px;
    border-radius: 6px;
  }

  @media (prefers-reduced-motion: reduce) {
    .cell {
      animation: none;
      opacity: 1;
      transform: none;
    }
  }
</style>

<div align="center" class="readme-root">

<div class="divider" style="margin-bottom: 18px;"></div>

<!-- Hero -->
<div class="panel">

<div class="section-title">⚔ Summoner's Rift · Developer Profile</div>

<img src="./vscode-typing.svg" width="100%" style="max-width: 780px; border-radius: 6px; border: 1px solid #1E2328;" alt="VS Code typing animation" />

<br/><br/>

<div class="badge-row">
  <img src="https://img.shields.io/badge/IDE-VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" alt="VS Code" />
  <img src="https://img.shields.io/badge/Lang-C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++" />
  <br/>
  <img src="https://img.shields.io/badge/Game-League_of_Legends-C89B3C?style=for-the-badge&logo=riot-games&logoColor=white" alt="League of Legends" />
  <img src="https://img.shields.io/badge/Role-Jungle-8B0000?style=for-the-badge&logo=league-of-legends&logoColor=white" alt="Jungle" />
  <br/>
  <img src="https://img.shields.io/badge/Idol-FAKER-E2012D?style=for-the-badge&logo=league-of-legends&logoColor=white" alt="Faker" />
  <img src="https://img.shields.io/badge/Team-T1-E2012D?style=for-the-badge&logo=league-of-legends&logoColor=white" alt="T1" />
</div>

</div>

<div class="divider" style="margin: 20px 0;"></div>

<!-- Learning -->
<div class="panel">

<div class="heading-gold">I'M CURRENTLY LEARNING</div>
<div class="subheading">FORGING NEW SKILLS IN THE RIFT</div>

<div class="tag-list">
  <span class="tag">C++ Performance</span>
  <span class="tag">Game Hacking</span>
  <span class="tag">Reverse Engineering</span>
</div>

</div>

<div class="divider" style="margin: 20px 0;"></div>

<!-- Faker -->
<div class="panel-t1">

<div class="heading-t1">FAKER</div>
<div class="subheading" style="color: #E2012D; opacity: 0.85;">THE UNKILLABLE DEMON KING · T1</div>

<div class="quote">
  "I don't play to be the best.<br/>
  I play because I love the game."
</div>

<div class="tag-list">
  <span class="tag tag-t1">×5 World Champion</span>
  <span class="tag tag-t1">T1 Mid Laner</span>
  <span class="tag tag-t1">GOAT</span>
</div>

</div>

<div class="divider" style="margin: 20px 0;"></div>

<!-- Stats -->
<div class="panel">

<div class="section-title" style="font-size: 18px; letter-spacing: 4px; opacity: 1; margin-bottom: 22px;">
  TETRIS CONTRIBUTIONS
</div>

<div class="contrib-wrap">

<div class="contrib-months">
  <span></span>
  <span>Jan</span><span>Feb</span><span>Mar</span><span>Apr</span><span>May</span><span>Jun</span>
</div>

<div class="contrib-body">
  <div class="contrib-days">
    <span></span><span>Mon</span><span></span><span>Wed</span><span></span><span>Fri</span><span></span>
  </div>

  <div class="contrib-grid">
    <!-- Col 0 -->
    <span class="cell c0" style="animation-delay:0.00s;"></span><span class="cell c0" style="animation-delay:0.02s;"></span><span class="cell c0" style="animation-delay:0.03s;"></span><span class="cell c0" style="animation-delay:0.04s;"></span><span class="cell c0" style="animation-delay:0.05s;"></span><span class="cell c0" style="animation-delay:0.06s;"></span><span class="cell c1" style="animation-delay:0.07s;"></span>
    <!-- Col 1 -->
    <span class="cell c0" style="animation-delay:0.06s;"></span><span class="cell c0" style="animation-delay:0.08s;"></span><span class="cell c1" style="animation-delay:0.09s;"></span><span class="cell c0" style="animation-delay:0.10s;"></span><span class="cell c0" style="animation-delay:0.11s;"></span><span class="cell c0" style="animation-delay:0.12s;"></span><span class="cell c0" style="animation-delay:0.13s;"></span>
    <!-- Col 2 -->
    <span class="cell c0" style="animation-delay:0.12s;"></span><span class="cell c0" style="animation-delay:0.14s;"></span><span class="cell c0" style="animation-delay:0.15s;"></span><span class="cell c2" style="animation-delay:0.16s;"></span><span class="cell c1" style="animation-delay:0.17s;"></span><span class="cell c0" style="animation-delay:0.18s;"></span><span class="cell c0" style="animation-delay:0.19s;"></span>
    <!-- Col 3 -->
    <span class="cell c1" style="animation-delay:0.18s;"></span><span class="cell c0" style="animation-delay:0.20s;"></span><span class="cell c0" style="animation-delay:0.21s;"></span><span class="cell c1" style="animation-delay:0.22s;"></span><span class="cell c3" style="animation-delay:0.23s;"></span><span class="cell c2" style="animation-delay:0.24s;"></span><span class="cell c0" style="animation-delay:0.25s;"></span>
    <!-- Col 4 -->
    <span class="cell c0" style="animation-delay:0.24s;"></span><span class="cell c2" style="animation-delay:0.26s;"></span><span class="cell c3" style="animation-delay:0.27s;"></span><span class="cell c1" style="animation-delay:0.28s;"></span><span class="cell c0" style="animation-delay:0.29s;"></span><span class="cell c0" style="animation-delay:0.30s;"></span><span class="cell c1" style="animation-delay:0.31s;"></span>
    <!-- Col 5 -->
    <span class="cell c0" style="animation-delay:0.30s;"></span><span class="cell c1" style="animation-delay:0.32s;"></span><span class="cell c4" style="animation-delay:0.33s;"></span><span class="cell c2" style="animation-delay:0.34s;"></span><span class="cell c0" style="animation-delay:0.35s;"></span><span class="cell c1" style="animation-delay:0.36s;"></span><span class="cell c3" style="animation-delay:0.37s;"></span>
    <!-- Col 6 -->
    <span class="cell c2" style="animation-delay:0.36s;"></span><span class="cell c3" style="animation-delay:0.38s;"></span><span class="cell c3" style="animation-delay:0.39s;"></span><span class="cell c2" style="animation-delay:0.40s;"></span><span class="cell c1" style="animation-delay:0.41s;"></span><span class="cell c0" style="animation-delay:0.42s;"></span><span class="cell c0" style="animation-delay:0.43s;"></span>
    <!-- Col 7 -->
    <span class="cell c0" style="animation-delay:0.42s;"></span><span class="cell c0" style="animation-delay:0.44s;"></span><span class="cell c4" style="animation-delay:0.45s;"></span><span class="cell c1" style="animation-delay:0.46s;"></span><span class="cell c3" style="animation-delay:0.47s;"></span><span class="cell c0" style="animation-delay:0.48s;"></span><span class="cell c2" style="animation-delay:0.49s;"></span>
    <!-- Col 8 -->
    <span class="cell c0" style="animation-delay:0.48s;"></span><span class="cell c2" style="animation-delay:0.50s;"></span><span class="cell c1" style="animation-delay:0.51s;"></span><span class="cell c4" style="animation-delay:0.52s;"></span><span class="cell c4" style="animation-delay:0.53s;"></span><span class="cell c3" style="animation-delay:0.54s;"></span><span class="cell c2" style="animation-delay:0.55s;"></span>
    <!-- Col 9 -->
    <span class="cell c3" style="animation-delay:0.54s;"></span><span class="cell c2" style="animation-delay:0.56s;"></span><span class="cell c4" style="animation-delay:0.57s;"></span><span class="cell c3" style="animation-delay:0.58s;"></span><span class="cell c1" style="animation-delay:0.59s;"></span><span class="cell c2" style="animation-delay:0.60s;"></span><span class="cell c1" style="animation-delay:0.61s;"></span>
    <!-- Col 10 -->
    <span class="cell c1" style="animation-delay:0.60s;"></span><span class="cell c4" style="animation-delay:0.62s;"></span><span class="cell c3" style="animation-delay:0.63s;"></span><span class="cell c2" style="animation-delay:0.64s;"></span><span class="cell c0" style="animation-delay:0.65s;"></span><span class="cell c0" style="animation-delay:0.66s;"></span><span class="cell c0" style="animation-delay:0.67s;"></span>
    <!-- Col 11 -->
    <span class="cell c0" style="animation-delay:0.66s;"></span><span class="cell c2" style="animation-delay:0.68s;"></span><span class="cell c1" style="animation-delay:0.69s;"></span><span class="cell c1" style="animation-delay:0.70s;"></span><span class="cell c0" style="animation-delay:0.71s;"></span><span class="cell c0" style="animation-delay:0.72s;"></span><span class="cell c0" style="animation-delay:0.73s;"></span>
    <!-- Col 12 -->
    <span class="cell c0" style="animation-delay:0.72s;"></span><span class="cell c3" style="animation-delay:0.74s;"></span><span class="cell c4" style="animation-delay:0.75s;"></span><span class="cell c4" style="animation-delay:0.76s;"></span><span class="cell c3" style="animation-delay:0.77s;"></span><span class="cell c2" style="animation-delay:0.78s;"></span><span class="cell c1" style="animation-delay:0.79s;"></span>
    <!-- Col 13 -->
    <span class="cell c1" style="animation-delay:0.78s;"></span><span class="cell c4" style="animation-delay:0.80s;"></span><span class="cell c4" style="animation-delay:0.81s;"></span><span class="cell c3" style="animation-delay:0.82s;"></span><span class="cell c0" style="animation-delay:0.83s;"></span><span class="cell c0" style="animation-delay:0.84s;"></span><span class="cell c2" style="animation-delay:0.85s;"></span>
    <!-- Col 14 -->
    <span class="cell c2" style="animation-delay:0.84s;"></span><span class="cell c3" style="animation-delay:0.86s;"></span><span class="cell c2" style="animation-delay:0.87s;"></span><span class="cell c0" style="animation-delay:0.88s;"></span><span class="cell c0" style="animation-delay:0.89s;"></span><span class="cell c1" style="animation-delay:0.90s;"></span><span class="cell c4" style="animation-delay:0.91s;"></span>
    <!-- Col 15 -->
    <span class="cell c3" style="animation-delay:0.90s;"></span><span class="cell c1" style="animation-delay:0.92s;"></span><span class="cell c0" style="animation-delay:0.93s;"></span><span class="cell c0" style="animation-delay:0.94s;"></span><span class="cell c1" style="animation-delay:0.95s;"></span><span class="cell c4" style="animation-delay:0.96s;"></span><span class="cell c3" style="animation-delay:0.97s;"></span>
    <!-- Col 16 -->
    <span class="cell c4" style="animation-delay:0.96s;"></span><span class="cell c2" style="animation-delay:0.98s;"></span><span class="cell c1" style="animation-delay:0.99s;"></span><span class="cell c0" style="animation-delay:1.00s;"></span><span class="cell c3" style="animation-delay:1.01s;"></span><span class="cell c2" style="animation-delay:1.02s;"></span><span class="cell c1" style="animation-delay:1.03s;"></span>
    <!-- Col 17 -->
    <span class="cell c2" style="animation-delay:1.02s;"></span><span class="cell c4" style="animation-delay:1.04s;"></span><span class="cell c3" style="animation-delay:1.05s;"></span><span class="cell c3" style="animation-delay:1.06s;"></span><span class="cell c1" style="animation-delay:1.07s;"></span><span class="cell c0" style="animation-delay:1.08s;"></span><span class="cell c0" style="animation-delay:1.09s;"></span>
    <!-- Col 18 -->
    <span class="cell c1" style="animation-delay:1.08s;"></span><span class="cell c3" style="animation-delay:1.10s;"></span><span class="cell c4" style="animation-delay:1.11s;"></span><span class="cell c1" style="animation-delay:1.12s;"></span><span class="cell c0" style="animation-delay:1.13s;"></span><span class="cell c0" style="animation-delay:1.14s;"></span><span class="cell c0" style="animation-delay:1.15s;"></span>
  </div>
</div>

<div class="contrib-legend">
  Less
  <span class="swatch" style="background:#161B22;"></span>
  <span class="swatch" style="background:#0E4429;"></span>
  <span class="swatch" style="background:#006D32;"></span>
  <span class="swatch" style="background:#26A641;"></span>
  <span class="swatch" style="background:#39D353;"></span>
  More
</div>

</div>

<br/>

<div class="stats-row">
  <img src="https://github-readme-stats.vercel.app/api?username=flashjose&show_icons=true&theme=dark&hide_border=true&bg_color=010A13&title_color=C89B3C&icon_color=C89B3C&text_color=C8AA6E" alt="GitHub Stats" height="165" />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=flashjose&theme=dark&hide_border=true&background=010A13&ring=C89B3C&fire=C89B3C&currStreakLabel=C8AA6E&sideLabels=C8AA6E&dates=8B949E" alt="GitHub Streak" height="165" />
</div>

</div>

<div class="divider" style="margin: 20px 0;"></div>

<!-- Contact -->
<div class="panel" style="padding-bottom: 22px;">

<div class="section-title" style="opacity: 1; margin-bottom: 16px;">—— CONTACT ——</div>

<table border="0" align="center">
  <tr>
    <td align="center" width="200" style="padding: 8px 16px;">
      <strong style="color:#C8AA6E; font-family:Georgia,serif; letter-spacing:2px;">📧 Email</strong><br/>
      <a href="mailto:lashjosephsparrow@gmail.com">
        <img src="https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Gmail"/>
      </a>
    </td>
    <td align="center" width="200" style="padding: 8px 16px;">
      <strong style="color:#C8AA6E; font-family:Georgia,serif; letter-spacing:2px;">🐧 QQ</strong><br/>
      <img src="https://img.shields.io/badge/QQ-2024136766-0099FF?style=flat-square&logo=tencent-qq&logoColor=white" alt="QQ"/>
    </td>
  </tr>
</table>

</div>

<div class="divider" style="margin-top: 18px;"></div>

<div style="font-size: 11px; letter-spacing: 5px; color: #C89B3C; opacity: 0.45; margin-top: 14px; font-family: Georgia, serif;">
  ═══ ⚔ ═══
</div>

</div>
