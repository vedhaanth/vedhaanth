

<style>
*{box-sizing:border-box;margin:0;padding:0}
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:0.4}}
@keyframes scanline{0%{transform:translateY(-100%)}100%{transform:translateY(400%)}}
@keyframes orbit{from{transform:rotate(0deg) translateX(38px) rotate(0deg)}to{transform:rotate(360deg) translateX(38px) rotate(-360deg)}}
@keyframes orbit2{from{transform:rotate(120deg) translateX(38px) rotate(-120deg)}to{transform:rotate(480deg) translateX(38px) rotate(-480deg)}}
@keyframes orbit3{from{transform:rotate(240deg) translateX(38px) rotate(-240deg)}to{transform:rotate(600deg) translateX(38px) rotate(-600deg)}}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
@keyframes barFill{from{width:0}to{width:var(--w)}}
@keyframes countUp{from{opacity:0}to{opacity:1}}
@keyframes floatDot{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}
@keyframes slideIn{from{opacity:0;transform:translateX(-12px)}to{opacity:1;transform:translateX(0)}}
@keyframes ripple{0%{transform:scale(0.8);opacity:0.8}100%{transform:scale(2.2);opacity:0}}

.preview{background:#0d1117;border-radius:12px;padding:28px 24px;overflow:hidden;font-family:'Fira Code',monospace}
.hero{text-align:center;margin-bottom:28px;animation:fadeUp 0.6s ease both}
.hero-name{font-size:26px;font-weight:700;color:#e6edf3;letter-spacing:-0.5px;margin-bottom:6px}
.hero-name span{color:#7F77DD}
.cursor{display:inline-block;width:2px;height:1.1em;background:#7F77DD;vertical-align:middle;margin-left:2px;animation:blink 1s step-end infinite}
.subtitle{font-size:13px;color:#8b949e;margin-bottom:14px;letter-spacing:0.03em}

.orbit-wrap{position:relative;width:88px;height:88px;margin:0 auto 20px}
.orbit-core{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);width:36px;height:36px;background:#7F77DD;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:15px;font-weight:700;color:#fff;z-index:2}
.orbit-core::after{content:'';position:absolute;width:36px;height:36px;border-radius:50%;border:2px solid #7F77DD;animation:ripple 2s ease-out infinite}
.dot{position:absolute;top:50%;left:50%;width:10px;height:10px;border-radius:50%;margin:-5px 0 0 -5px}
.d1{background:#1D9E75;animation:orbit 3s linear infinite}
.d2{background:#EF9F27;animation:orbit2 3s linear infinite}
.d3{background:#D4537E;animation:orbit3 3s linear infinite}

.terminal{background:#161b22;border:0.5px solid #30363d;border-radius:8px;padding:14px 16px;margin-bottom:18px;animation:fadeUp 0.7s 0.2s ease both;opacity:0}
.term-bar{display:flex;gap:6px;margin-bottom:10px}
.tb{width:10px;height:10px;border-radius:50%}
.tb1{background:#ff5f57}.tb2{background:#febc2e}.tb3{background:#28c840}
.term-line{font-size:12px;color:#8b949e;line-height:1.8}
.term-line .prompt{color:#1D9E75}
.term-line .cmd{color:#e6edf3}
.term-line .out{color:#7F77DD}
.term-line .str{color:#EF9F27}

.section-label{font-size:10px;font-weight:600;color:#8b949e;letter-spacing:0.12em;text-transform:uppercase;margin-bottom:10px;display:flex;align-items:center;gap:8px}
.section-label::after{content:'';flex:1;height:0.5px;background:#30363d}

.badges{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:20px;animation:fadeUp 0.7s 0.35s ease both;opacity:0}
.badge{padding:4px 10px;border-radius:20px;font-size:11px;font-weight:600;letter-spacing:0.02em;animation:floatDot 3s ease-in-out infinite}
.b-py{background:#3776AB22;color:#4B9FD5;border:0.5px solid #3776AB55;animation-delay:0s}
.b-ts{background:#3178C622;color:#5BA3E0;border:0.5px solid #3178C655;animation-delay:0.3s}
.b-rn{background:#61DAFB22;color:#61DAFB;border:0.5px solid #61DAFB55;animation-delay:0.6s}
.b-el{background:#47848F22;color:#7EC8D4;border:0.5px solid #47848F55;animation-delay:0.9s}
.b-tf{background:#FF6F0022;color:#FF9944;border:0.5px solid #FF6F0055;animation-delay:1.2s}
.b-ml{background:#7F77DD22;color:#AFA9EC;border:0.5px solid #7F77DD55;animation-delay:1.5s}
.b-cv{background:#5C3EE822;color:#9B7FEE;border:0.5px solid #5C3EE855;animation-delay:1.8s}
.b-aws{background:#FF990022;color:#FFB844;border:0.5px solid #FF990055;animation-delay:2.1s}

.stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:20px;animation:fadeUp 0.7s 0.5s ease both;opacity:0}
.stat-card{background:#161b22;border:0.5px solid #30363d;border-radius:8px;padding:12px 14px}
.stat-num{font-size:22px;font-weight:700;color:#e6edf3;margin-bottom:2px}
.stat-num .accent{color:#7F77DD}
.stat-lbl{font-size:11px;color:#8b949e}
.streak-fire{color:#EF9F27}

.skill-bars{margin-bottom:20px;animation:fadeUp 0.7s 0.65s ease both;opacity:0}
.bar-row{display:flex;align-items:center;gap:10px;margin-bottom:8px}
.bar-name{font-size:11px;color:#8b949e;width:70px;flex-shrink:0}
.bar-track{flex:1;height:5px;background:#30363d;border-radius:3px;overflow:hidden}
.bar-fill{height:100%;border-radius:3px;--w:0%;animation:barFill 1.2s cubic-bezier(.4,0,.2,1) both}
.bar-fill.py{background:#4B9FD5;--w:92%;animation-delay:0.7s}
.bar-fill.rn{background:#61DAFB;--w:85%;animation-delay:0.85s}
.bar-fill.ml{background:#7F77DD;--w:88%;animation-delay:1.0s}
.bar-fill.el{background:#7EC8D4;--w:80%;animation-delay:1.15s}
.bar-fill.tf{background:#FF9944;--w:78%;animation-delay:1.3s}
.bar-pct{font-size:10px;color:#8b949e;width:28px;text-align:right;flex-shrink:0}

.projects{display:grid;grid-template-columns:1fr 1fr;gap:10px;animation:fadeUp 0.7s 0.8s ease both;opacity:0}
.proj-card{background:#161b22;border:0.5px solid #30363d;border-radius:8px;padding:12px 14px;transition:border-color 0.2s}
.proj-card:hover{border-color:#7F77DD}
.proj-icon{font-size:18px;margin-bottom:6px}
.proj-name{font-size:13px;font-weight:600;color:#e6edf3;margin-bottom:3px}
.proj-desc{font-size:10px;color:#8b949e;line-height:1.5;margin-bottom:8px}
.proj-tags{display:flex;flex-wrap:wrap;gap:4px}
.proj-tag{font-size:9px;background:#30363d;color:#8b949e;padding:2px 6px;border-radius:3px}

.contrib{margin-top:18px;animation:fadeUp 0.7s 0.95s ease both;opacity:0}
.contrib-grid{display:flex;gap:2px;flex-wrap:wrap;margin-top:8px}
.cell{width:10px;height:10px;border-radius:2px;flex-shrink:0}

.footer{text-align:center;margin-top:20px;font-size:11px;color:#8b949e;animation:fadeUp 0.7s 1.1s ease both;opacity:0}
.footer .hl{color:#7F77DD}

.scanline-wrap{position:relative;overflow:hidden;border-radius:8px}
.scanline-wrap::after{content:'';position:absolute;top:0;left:0;right:0;height:40px;background:linear-gradient(transparent,rgba(127,119,221,0.04),transparent);animation:scanline 4s linear infinite;pointer-events:none}
</style>

<h2 class="sr-only">Animated GitHub profile README preview showing stats, projects, and tech stack</h2>

<div class="preview scanline-wrap">

  <div class="hero">
    <div class="orbit-wrap">
      <div class="orbit-core">V</div>
      <div class="dot d1"></div>
      <div class="dot d2"></div>
      <div class="dot d3"></div>
    </div>
    <div class="hero-name">hey, I'm <span id="typed-name"></span><span class="cursor"></span></div>
    <div class="subtitle" id="typed-sub"></div>
  </div>

  <div class="terminal">
    <div class="term-bar"><div class="tb tb1"></div><div class="tb tb2"></div><div class="tb tb3"></div></div>
    <div class="term-line"><span class="prompt">❯ </span><span class="cmd">python3 vedhaanth.py</span></div>
    <div class="term-line"><span class="out">{</span></div>
    <div class="term-line">&nbsp;&nbsp;<span class="str">"role"</span>: <span class="out">"ML Engineer + App Builder"</span>,</div>
    <div class="term-line">&nbsp;&nbsp;<span class="str">"focus"</span>: <span class="out">["Edge AI", "Mobile", "Desktop AI"]</span>,</div>
    <div class="term-line">&nbsp;&nbsp;<span class="str">"motto"</span>: <span class="out">"make ML run where it shouldn't"</span></div>
    <div class="term-line"><span class="out">}</span></div>
  </div>

  <div class="section-label">tech stack</div>
  <div class="badges">
    <span class="badge b-py">Python</span>
    <span class="badge b-ts">TypeScript</span>
    <span class="badge b-rn">React Native</span>
    <span class="badge b-el">Electron.js</span>
    <span class="badge b-tf">TFLite</span>
    <span class="badge b-ml">PyTorch</span>
    <span class="badge b-cv">OpenCV</span>
    <span class="badge b-aws">AWS</span>
  </div>

  <div class="section-label">github stats</div>
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-num"><span class="accent" id="commits-num">0</span></div>
      <div class="stat-lbl">total commits</div>
    </div>
    <div class="stat-card">
      <div class="stat-num"><span class="streak-fire">🔥</span> <span class="accent" id="streak-num">0</span></div>
      <div class="stat-lbl">day streak</div>
    </div>
    <div class="stat-card">
      <div class="stat-num"><span class="accent" id="stars-num">0</span></div>
      <div class="stat-lbl">stars earned</div>
    </div>
    <div class="stat-card">
      <div class="stat-num"><span class="accent" id="pr-num">0</span></div>
      <div class="stat-lbl">pull requests</div>
    </div>
  </div>

  <div class="section-label">skill proficiency</div>
  <div class="skill-bars">
    <div class="bar-row"><span class="bar-name">Python</span><div class="bar-track"><div class="bar-fill py"></div></div><span class="bar-pct">92%</span></div>
    <div class="bar-row"><span class="bar-name">ML / AI</span><div class="bar-track"><div class="bar-fill ml"></div></div><span class="bar-pct">88%</span></div>
    <div class="bar-row"><span class="bar-name">React Native</span><div class="bar-track"><div class="bar-fill rn"></div></div><span class="bar-pct">85%</span></div>
    <div class="bar-row"><span class="bar-name">Electron.js</span><div class="bar-track"><div class="bar-fill el"></div></div><span class="bar-pct">80%</span></div>
    <div class="bar-row"><span class="bar-name">TFLite</span><div class="bar-track"><div class="bar-fill tf"></div></div><span class="bar-pct">78%</span></div>
  </div>

  <div class="section-label">featured projects</div>
  <div class="projects">
    <div class="proj-card">
      <div class="proj-icon">🤖</div>
      <div class="proj-name">ZEN Assistant</div>
      <div class="proj-desc">Voice AI desktop app with wake word, OS commands & multi-LLM support</div>
      <div class="proj-tags"><span class="proj-tag">Electron.js</span><span class="proj-tag">Groq</span><span class="proj-tag">Whisper</span></div>
    </div>
    <div class="proj-card">
      <div class="proj-icon">📸</div>
      <div class="proj-name">Face Auth SDK</div>
      <div class="proj-desc">Offline liveness detection + face recognition under 20MB for mobile</div>
      <div class="proj-tags"><span class="proj-tag">TFLite</span><span class="proj-tag">React Native</span><span class="proj-tag">AES-256</span></div>
    </div>
  </div>

  <div class="contrib">
    <div class="section-label">contributions</div>
    <div class="contrib-grid" id="cgrid"></div>
  </div>

  <div class="footer">
    <div>always building · always shipping</div>
    <div style="margin-top:4px">open to collabs <span class="hl">→</span> let's build something wild</div>
  </div>

</div>

<script>
const name = "Vedhaanth";
const subs = ["ML Engineer · App Builder", "Edge AI · React Native · Electron.js", "Building where AI meets the real world"];
let ni = 0, si = 0, subIdx = 0, typing = true;
const nel = document.getElementById('typed-name');
const sel = document.getElementById('typed-sub');

function typeChar() {
  if (ni < name.length) { nel.textContent += name[ni++]; setTimeout(typeChar, 80); }
  else setTimeout(typeSub, 400);
}
function typeSub() {
  const sub = subs[subIdx % subs.length];
  if (typing && si < sub.length) { sel.textContent += sub[si++]; setTimeout(typeSub, 40); }
  else if (typing) { typing = false; setTimeout(typeSub, 2000); }
  else if (si > 0) { sel.textContent = sub.substring(0, --si); setTimeout(typeSub, 20); }
  else { typing = true; si = 0; subIdx++; setTimeout(typeSub, 300); }
}
setTimeout(typeChar, 300);

function countTo(id, target, duration) {
  const el = document.getElementById(id);
  let start = 0, step = target / (duration / 16);
  const t = setInterval(() => {
    start = Math.min(start + step, target);
    el.textContent = Math.round(start);
    if (start >= target) clearInterval(t);
  }, 16);
}
setTimeout(() => {
  countTo('commits-num', 847, 1400);
  countTo('streak-num', 23, 1000);
  countTo('stars-num', 112, 1200);
  countTo('pr-num', 64, 900);
}, 600);

const grid = document.getElementById('cgrid');
const colors = ['#21262d','#0e4429','#006d32','#26a641','#39d353'];
for (let i = 0; i < 52; i++) {
  const cell = document.createElement('div');
  cell.className = 'cell';
  const w = Math.random();
  cell.style.background = w < 0.3 ? colors[0] : w < 0.5 ? colors[1] : w < 0.7 ? colors[2] : w < 0.88 ? colors[3] : colors[4];
  cell.style.animationDelay = (i * 0.02) + 's';
  grid.appendChild(cell);
}
</script>
