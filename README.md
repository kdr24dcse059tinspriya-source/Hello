<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CSE Speaking Lab — Batch 2025-26</title>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&family=JetBrains+Mono:wght@400;700&family=Nunito:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #080b14;
  --bg2: #0d1120;
  --surface: #111827;
  --surface2: #1a2236;
  --border: #1e2d47;
  --border2: #263550;
  --accent: #38bdf8;
  --accent-glow: rgba(56,189,248,0.18);
  --green: #34d399;
  --green-glow: rgba(52,211,153,0.15);
  --red: #f87171;
  --yellow: #fbbf24;
  --text: #e2e8f0;
  --muted: #64748b;
  --muted2: #94a3b8;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'Nunito',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow-x:hidden}

/* BG pattern */
body::before{content:'';position:fixed;inset:0;
  background:radial-gradient(ellipse 80% 50% at 20% 10%,rgba(56,189,248,0.06) 0%,transparent 60%),
             radial-gradient(ellipse 60% 40% at 80% 80%,rgba(52,211,153,0.05) 0%,transparent 60%);
  pointer-events:none;z-index:0}
body::after{content:'';position:fixed;inset:0;
  background-image:linear-gradient(rgba(56,189,248,0.025) 1px,transparent 1px),linear-gradient(90deg,rgba(56,189,248,0.025) 1px,transparent 1px);
  background-size:32px 32px;pointer-events:none;z-index:0}

/* ── HEADER ── */
header{position:sticky;top:0;z-index:200;height:60px;border-bottom:1px solid var(--border);
  background:rgba(8,11,20,0.95);backdrop-filter:blur(16px);
  display:flex;align-items:center;justify-content:space-between;padding:0 1.5rem}
.logo{display:flex;align-items:center;gap:10px}
.logo-icon{width:34px;height:34px;border-radius:8px;background:linear-gradient(135deg,#0ea5e9,#34d399);
  display:flex;align-items:center;justify-content:center;font-size:1rem}
.logo-text{font-family:'Rajdhani',sans-serif;font-weight:700;font-size:1.15rem;letter-spacing:0.04em}
.logo-sub{font-family:'JetBrains Mono',monospace;font-size:0.6rem;color:var(--muted);letter-spacing:0.08em}
.header-btns{display:flex;gap:8px}
.hbtn{font-family:'JetBrains Mono',monospace;font-size:0.68rem;padding:7px 16px;border-radius:6px;
  border:1px solid var(--border2);background:transparent;color:var(--muted2);cursor:pointer;transition:all .2s;letter-spacing:.04em}
.hbtn.active{background:var(--accent);color:#000;border-color:var(--accent);font-weight:700}
.hbtn:not(.active):hover{border-color:var(--accent);color:var(--accent)}

/* ── MAIN ── */
main{position:relative;z-index:1;padding:1.5rem;max-width:1300px;margin:0 auto}

/* ── PAGE TRANSITIONS ── */
.page{animation:fadeUp .35s ease}
@keyframes fadeUp{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}

/* ── SECTION LABEL ── */
.slabel{font-family:'JetBrains Mono',monospace;font-size:0.62rem;color:var(--accent);
  border:1px solid rgba(56,189,248,.25);padding:3px 10px;border-radius:20px;display:inline-block;margin-bottom:.5rem;letter-spacing:.06em}
.page-title{font-family:'Rajdhani',sans-serif;font-weight:700;font-size:2.2rem;line-height:1.1;margin-bottom:.3rem}
.page-sub{color:var(--muted2);font-size:.88rem;margin-bottom:1.8rem}

/* ── SEARCH ── */
.search-wrap{margin-bottom:1.5rem;position:relative;max-width:420px}
.search-wrap input{width:100%;padding:10px 14px 10px 38px;background:var(--surface);border:1px solid var(--border2);
  border-radius:9px;color:var(--text);font-family:'Nunito',sans-serif;font-size:.9rem;outline:none;transition:border-color .2s}
.search-wrap input:focus{border-color:var(--accent)}
.search-wrap input::placeholder{color:var(--muted)}
.search-icon{position:absolute;left:12px;top:50%;transform:translateY(-50%);color:var(--muted);font-size:.9rem}

/* ── STUDENT GRID ── */
.s-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(185px,1fr));gap:.9rem}
.s-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;
  padding:1.1rem 1rem;cursor:pointer;transition:all .2s;text-align:center;position:relative;overflow:hidden}
.s-card::after{content:'';position:absolute;inset:0;background:linear-gradient(135deg,var(--accent),var(--green));
  opacity:0;transition:opacity .2s}
.s-card:hover{border-color:var(--accent);transform:translateY(-3px);box-shadow:0 8px 24px rgba(56,189,248,.12)}
.s-card:hover::after{opacity:.04}
.s-card.submitted{border-color:rgba(52,211,153,.4)}
.s-avatar{width:48px;height:48px;border-radius:50%;margin:0 auto .7rem;
  display:flex;align-items:center;justify-content:center;
  font-family:'Rajdhani',sans-serif;font-weight:700;font-size:1.1rem;color:#fff}
.s-name{font-weight:700;font-size:.8rem;margin-bottom:3px;line-height:1.3}
.s-roll{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:var(--muted);margin-bottom:.5rem}
.s-badge{font-size:.6rem;padding:2px 8px;border-radius:20px;border:1px solid;font-family:'JetBrains Mono',monospace}
.badge-done{color:var(--green);border-color:var(--green)}
.badge-pend{color:var(--muted);border-color:var(--border2)}

/* ── SPEAKING PAGE ── */
.back-btn{display:inline-flex;align-items:center;gap:6px;font-family:'JetBrains Mono',monospace;
  font-size:.72rem;color:var(--muted2);background:var(--surface);border:1px solid var(--border2);
  padding:7px 14px;border-radius:7px;cursor:pointer;margin-bottom:1.2rem;transition:all .2s}
.back-btn:hover{border-color:var(--accent);color:var(--accent)}
.speak-grid{display:grid;grid-template-columns:1fr 370px;gap:1.2rem}
@media(max-width:860px){.speak-grid{grid-template-columns:1fr}}

/* image panel */
.img-panel{border-radius:14px;overflow:hidden;aspect-ratio:16/9;position:relative;
  background:var(--surface);border:1px solid var(--border)}
.img-panel img{width:100%;height:100%;object-fit:cover}
.img-empty{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.8rem;height:100%;color:var(--muted)}
.img-empty svg{opacity:.25}
.img-corner{position:absolute;top:.8rem;right:.8rem;background:rgba(8,11,20,.75);
  border:1px solid var(--accent);color:var(--accent);padding:3px 10px;border-radius:20px;
  font-family:'JetBrains Mono',monospace;font-size:.65rem}
.img-foot{position:absolute;bottom:0;left:0;right:0;padding:.8rem 1rem;
  background:linear-gradient(transparent,rgba(0,0,0,.75));
  font-family:'JetBrains Mono',monospace;font-size:.7rem;color:rgba(255,255,255,.65)}

/* card */
.card{background:var(--surface);border:1px solid var(--border);border-radius:13px;padding:1.3rem}
.card-title{font-family:'Rajdhani',sans-serif;font-weight:700;font-size:.85rem;
  color:var(--accent);text-transform:uppercase;letter-spacing:.06em;margin-bottom:1rem;
  display:flex;align-items:center;gap:7px}

/* recorder */
.timer-wrap{display:flex;flex-direction:column;align-items:center;margin:.3rem 0 .8rem}
.timer-svg{position:relative;width:96px;height:96px}
.timer-svg svg{transform:rotate(-90deg)}
.timer-num{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;
  font-family:'JetBrains Mono',monospace;font-size:1.45rem;font-weight:700}
.timer-num.run{color:var(--accent);text-shadow:0 0 16px var(--accent)}
.timer-num.warn{color:var(--yellow)}
.timer-num.danger{color:var(--red)}

.waveform{height:44px;background:var(--surface2);border:1px solid var(--border);border-radius:8px;overflow:hidden;margin:.6rem 0}
.waveform canvas{width:100%;height:100%}

.rec-row{display:flex;gap:.6rem;flex-wrap:wrap;justify-content:center;margin-top:.8rem}
.btn{font-family:'JetBrains Mono',monospace;font-size:.7rem;padding:9px 18px;border-radius:7px;
  border:none;cursor:pointer;transition:all .2s;display:inline-flex;align-items:center;gap:5px;letter-spacing:.03em}
.btn-accent{background:var(--accent);color:#000;font-weight:700}
.btn-accent:hover:not(:disabled){box-shadow:0 0 18px rgba(56,189,248,.45);transform:translateY(-1px)}
.btn-red{background:var(--red);color:#fff}
.btn-red:hover:not(:disabled){box-shadow:0 0 18px rgba(248,113,113,.4)}
.btn-ghost{background:var(--surface2);color:var(--text);border:1px solid var(--border2)}
.btn-ghost:hover:not(:disabled){border-color:var(--accent);color:var(--accent)}
.btn-green{background:var(--green);color:#000;font-weight:700}
.btn-green:hover:not(:disabled){box-shadow:0 0 18px rgba(52,211,153,.4)}
.btn:disabled{opacity:.35;cursor:not-allowed;transform:none!important;box-shadow:none!important}
.btn-full{width:100%;justify-content:center;padding:12px}

.rec-dot{display:inline-block;width:8px;height:8px;border-radius:50%;background:var(--red);animation:blink 1s infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.2}}

/* results */
.score-row{display:flex;gap:.7rem;flex-wrap:wrap;margin:.8rem 0}
.score-chip{flex:1;min-width:80px;background:var(--surface2);border:1px solid var(--border2);
  border-radius:9px;padding:.6rem .5rem;text-align:center}
.score-chip .sc-label{font-family:'JetBrains Mono',monospace;font-size:.58rem;color:var(--muted);margin-bottom:3px}
.score-chip .sc-val{font-family:'Rajdhani',sans-serif;font-weight:700;font-size:1.5rem}
.sc-good{color:var(--green)}.sc-mid{color:var(--yellow)}.sc-bad{color:var(--red)}

.tbox{background:var(--surface2);border:1px solid var(--border2);border-radius:9px;
  padding:.9rem;font-size:.85rem;line-height:1.75;min-height:72px}
.cbox{background:rgba(52,211,153,.05);border:1px solid rgba(52,211,153,.2);border-radius:9px;padding:.9rem;font-size:.85rem;line-height:1.75}

.m-item{background:var(--surface2);border-left:3px solid var(--yellow);border-radius:0 8px 8px 0;
  padding:.75rem 1rem;margin-bottom:.55rem}
.m-type{font-family:'JetBrains Mono',monospace;font-size:.6rem;color:var(--yellow);margin-bottom:3px}
.m-orig{color:var(--red);font-size:.83rem;text-decoration:line-through}
.m-arrow{color:var(--muted);font-size:.72rem;margin:2px 0}
.m-fix{color:var(--green);font-size:.83rem;font-weight:600}
.m-exp{color:var(--muted2);font-size:.75rem;margin-top:3px}

.flabel{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:var(--muted);margin-bottom:.4rem;display:block}

/* ── TEACHER ── */
.t-header{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem;margin-bottom:1.8rem}
.t-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem}
@media(max-width:800px){.t-grid{grid-template-columns:1fr}}

.upload-zone{border:2px dashed var(--border2);border-radius:11px;padding:1.8rem 1.2rem;text-align:center;
  cursor:pointer;transition:all .2s;background:var(--surface2)}
.upload-zone:hover,.upload-zone.drag{border-color:var(--accent);background:rgba(56,189,248,.05)}
.upload-zone input{display:none}
.uz-icon{font-size:1.8rem;margin-bottom:.5rem;opacity:.5}
.uz-text{font-size:.85rem;color:var(--muted2)}

.finput{width:100%;padding:9px 13px;border-radius:8px;background:var(--surface2);
  border:1px solid var(--border2);color:var(--text);font-family:'Nunito',sans-serif;font-size:.88rem;
  outline:none;transition:border-color .2s}
.finput:focus{border-color:var(--accent)}
.fgroup{margin-bottom:.9rem}

.sched-item{background:var(--surface2);border:1px solid var(--border);border-radius:10px;
  padding:.9rem 1rem;display:flex;gap:.9rem;align-items:center;margin-bottom:.65rem}
.sched-thumb{width:54px;height:38px;border-radius:6px;object-fit:cover;border:1px solid var(--border);flex-shrink:0}
.sched-name{font-weight:600;font-size:.83rem}
.sched-date{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:var(--muted);margin-top:2px}
.sbadge{font-family:'JetBrains Mono',monospace;font-size:.6rem;padding:2px 8px;border-radius:20px;border:1px solid;white-space:nowrap}
.sb-live{color:var(--accent);border-color:var(--accent)}
.sb-up{color:var(--muted);border-color:var(--border2)}
.sb-past{color:var(--green);border-color:var(--green)}

/* progress bar */
.pbar-wrap{margin-bottom:.9rem}
.pbar-top{display:flex;justify-content:space-between;font-size:.78rem;margin-bottom:4px}
.pbar{height:5px;background:var(--surface2);border-radius:3px}
.pbar-fill{height:100%;background:var(--accent);border-radius:3px;transition:width .6s}

.prog-row{display:flex;justify-content:space-between;align-items:center;padding:5px 0;
  border-bottom:1px solid var(--border);font-size:.78rem}
.prog-row:last-child{border-bottom:none}

/* password change */
.cp-wrap{display:flex;flex-direction:column;gap:.5rem}

/* ── AUTH MODAL ── */
.modal-bg{display:none;position:fixed;inset:0;z-index:500;
  background:rgba(8,11,20,.92);backdrop-filter:blur(12px);
  align-items:center;justify-content:center;padding:1rem}
.modal-bg.show{display:flex}
.modal{background:var(--surface);border:1px solid var(--border2);border-radius:18px;
  padding:2.2rem 2rem;width:100%;max-width:390px;position:relative;
  animation:fadeUp .3s ease}
.modal-close{position:absolute;top:1rem;right:1rem;background:none;border:none;
  color:var(--muted);font-size:1.1rem;cursor:pointer;transition:color .2s}
.modal-close:hover{color:var(--text)}
.modal-avatar{width:60px;height:60px;border-radius:50%;background:linear-gradient(135deg,#0ea5e9,#34d399);
  display:flex;align-items:center;justify-content:center;font-size:1.5rem;margin:0 auto .9rem}
.modal-name{font-family:'Rajdhani',sans-serif;font-weight:700;font-size:1.3rem;text-align:center}
.modal-role{font-family:'JetBrains Mono',monospace;font-size:.62rem;color:var(--muted);text-align:center;margin-bottom:1.3rem}
.info-box{border-radius:9px;padding:.8rem 1rem;font-size:.8rem;margin-bottom:1rem;text-align:center}
.info-box.blue{background:rgba(56,189,248,.08);border:1px solid rgba(56,189,248,.2);color:var(--accent)}
.info-box.red{background:rgba(248,113,113,.07);border:1px solid rgba(248,113,113,.2);color:var(--red)}
.err-msg{font-family:'JetBrains Mono',monospace;font-size:.65rem;min-height:16px;margin-bottom:.6rem}

/* ── LOADING ── */
.loader{display:none;position:fixed;inset:0;z-index:600;
  background:rgba(8,11,20,.88);backdrop-filter:blur(8px);
  align-items:center;justify-content:center;flex-direction:column;gap:.9rem}
.loader.show{display:flex}
.spinner{width:44px;height:44px;border:3px solid var(--border2);
  border-top-color:var(--accent);border-radius:50%;animation:spin .75s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.loader-txt{font-family:'JetBrains Mono',monospace;font-size:.75rem;color:var(--muted2)}

/* ── TOASTS ── */
.toasts{position:fixed;bottom:1.5rem;right:1.5rem;z-index:700;display:flex;flex-direction:column;gap:.5rem}
.toast{background:var(--surface2);border:1px solid var(--border2);border-radius:9px;
  padding:.65rem 1.1rem;font-size:.82rem;display:flex;align-items:center;gap:7px;
  animation:fadeUp .3s ease;max-width:300px}
.toast.ok{border-left:3px solid var(--green)}
.toast.er{border-left:3px solid var(--red)}
.toast.in{border-left:3px solid var(--accent)}

/* past subs */
.sub-details{background:var(--surface2);border-radius:8px;border:1px solid var(--border);margin-bottom:.5rem;overflow:hidden}
.sub-details summary{padding:.65rem .9rem;cursor:pointer;display:flex;justify-content:space-between;align-items:center;font-size:.82rem;font-weight:600;list-style:none}
.sub-details summary::-webkit-details-marker{display:none}
.sub-body{padding:.7rem .9rem;font-size:.8rem;color:var(--muted2);line-height:1.6;border-top:1px solid var(--border)}

/* no image */
.no-img-msg{background:rgba(251,191,36,.07);border:1px solid rgba(251,191,36,.25);
  border-radius:10px;padding:.9rem 1.1rem;color:var(--yellow);font-size:.83rem;margin-bottom:1.2rem}

/* del btn */
.del-btn{background:none;border:none;color:var(--muted);font-size:.65rem;cursor:pointer;
  font-family:'JetBrains Mono',monospace;transition:color .2s}
.del-btn:hover{color:var(--red)}
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="logo">
    <div class="logo-icon">💻</div>
    <div>
      <div class="logo-text">CSE SPEAKING LAB</div>
      <div class="logo-sub">DEPT. OF COMPUTER SCIENCE &amp; ENGINEERING</div>
    </div>
  </div>
  <div class="header-btns">
    <button class="hbtn active" id="btnStudent" onclick="goStudent()">👤 Student</button>
    <button class="hbtn" id="btnTeacher" onclick="openAuth()">🎓 Tej Pratap</button>
  </div>
</header>

<!-- LOADER -->
<div class="loader" id="loader">
  <div class="spinner"></div>
  <div class="loader-txt" id="loaderTxt">Analysing your speech…</div>
</div>

<!-- TOASTS -->
<div class="toasts" id="toasts"></div>

<!-- ── AUTH MODAL ── -->
<div class="modal-bg" id="authModal">
  <div class="modal">
    <button class="modal-close" onclick="closeAuth()">✕</button>
    <div class="modal-avatar">🎓</div>
    <div class="modal-name">Tej Pratap</div>
    <div class="modal-role">TEACHER · CSE DEPT</div>

    <!-- SET PASSWORD -->
    <div id="viewSet">
      <div class="info-box blue">👋 First time? Set your password to secure Teacher mode.</div>
      <div class="fgroup"><label class="flabel">CREATE PASSWORD</label>
        <input type="password" class="finput" id="sp1" placeholder="Min 4 characters" oninput="chkSet()"></div>
      <div class="fgroup"><label class="flabel">CONFIRM PASSWORD</label>
        <input type="password" class="finput" id="sp2" placeholder="Re-enter password" oninput="chkSet()" onkeydown="if(event.key==='Enter')doSet()"></div>
      <div class="err-msg" id="setMsg"></div>
      <button class="btn btn-accent btn-full" id="btnSet" onclick="doSet()" disabled>🔒 Set Password &amp; Enter</button>
    </div>

    <!-- LOGIN -->
    <div id="viewLogin" style="display:none">
      <div class="fgroup"><label class="flabel">PASSWORD</label>
        <input type="password" class="finput" id="lp" placeholder="Enter your password" onkeydown="if(event.key==='Enter')doLogin()"></div>
      <div class="err-msg" id="loginMsg" style="color:var(--red)"></div>
      <button class="btn btn-accent btn-full" onclick="doLogin()">🔓 Enter Teacher Mode</button>
      <button onclick="showView('viewReset')" style="width:100%;background:none;border:none;color:var(--muted);font-size:.72rem;margin-top:.8rem;cursor:pointer;font-family:'JetBrains Mono',monospace;">Forgot password? Reset</button>
    </div>

    <!-- RESET -->
    <div id="viewReset" style="display:none">
      <div class="info-box red">⚠️ This will clear your current password. You'll set a new one.</div>
      <div style="display:flex;gap:.7rem;margin-top:.5rem">
        <button class="btn btn-ghost" style="flex:1;justify-content:center" onclick="showView('viewLogin')">Cancel</button>
        <button class="btn btn-red" style="flex:1;justify-content:center" onclick="doReset()">Reset</button>
      </div>
    </div>
  </div>
</div>

<!-- FALLBACK TEXT MODAL (when speech recognition unavailable) -->
<div id="fallbackModal" style="display:none;position:fixed;inset:0;z-index:500;background:rgba(8,11,20,.92);backdrop-filter:blur(12px);align-items:center;justify-content:center;padding:1rem">
  <div style="background:var(--surface);border:1px solid var(--border2);border-radius:16px;padding:2rem;width:100%;max-width:480px">
    <div style="font-family:'Rajdhani',sans-serif;font-weight:700;font-size:1.2rem;margin-bottom:.4rem">✍️ Type Your Speech</div>
    <div style="font-size:.82rem;color:var(--muted2);margin-bottom:1rem">Live speech-to-text wasn't captured. Please type what you spoke about the image so we can analyse it.</div>
    <textarea id="fallbackText" style="width:100%;min-height:140px;background:var(--surface2);border:1px solid var(--border2);border-radius:9px;color:var(--text);font-family:'Nunito',sans-serif;font-size:.88rem;padding:.8rem;outline:none;resize:vertical;line-height:1.6" placeholder="Type your spoken description here…"></textarea>
    <div style="display:flex;gap:.7rem;margin-top:1rem">
      <button class="btn btn-ghost" style="flex:1;justify-content:center" onclick="cancelFallback()">Cancel</button>
      <button class="btn btn-accent" style="flex:1;justify-content:center" onclick="submitFallback()">Analyse →</button>
    </div>
  </div>
</div>
<main>

  <!-- ══
