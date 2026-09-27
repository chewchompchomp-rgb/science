<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Science Obby: PSLE Science practice</title>
<meta name="description" content="Roblox-style PSLE Science 2026 practice: 18 blocks, 144 MCQ, 54 structured questions, arenas with exam timing.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Lexend:wght@400;600;700&display=swap" rel="stylesheet">
<style>
:root{
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px);
  padding-bottom:env(safe-area-inset-bottom,0px);
  --sky1:#6FC1F5; --sky2:#DCF2FF; --cloud:#ffffff;
  --paper:#FFF9E6; --paper2:#FFF2CC; --ink:#1E2A44; --ink2:#4E5A78; --line:#E3D9B8;
  --ok:#1FA45B; --okbg:#E1F7E9; --bad:#E0503A; --badbg:#FDE6E1; --warn:#B7791F;
  --coin:#FFC72C; --lava:#FF6A2C; --lava2:#FFB300;
  --div:#2E9E4F; --cyc:#2F7FD6; --sys:#EF8A2A; --int:#8A5CD6; --ene:#D9A400;
  --btn:#2F7FD6; --btn2:#215FA3; --white:#fff;
  --fs:19px; --scenetext:#1E2A44;
}
@media (prefers-color-scheme:dark){
  :root:not([data-theme="light"]){
    --sky1:#0F1B3D; --sky2:#233A6B; --cloud:#3B4F7D; --scenetext:#fff;
    --paper:#FFF6DD; --paper2:#F7E9C2; --line:#D9CFA8;
  }
}
:root[data-theme="dark"]{
  --sky1:#0F1B3D; --sky2:#233A6B; --cloud:#3B4F7D; --scenetext:#fff;
  --paper:#FFF6DD; --paper2:#F7E9C2; --line:#D9CFA8;
}
html{scroll-padding-top:env(safe-area-inset-top,0px);height:100%}
body{height:100%;margin:0;font-family:"Lexend",Verdana,Arial,sans-serif;font-size:var(--fs);line-height:1.6;letter-spacing:.01em;color:var(--ink);
  background:linear-gradient(var(--sky1),var(--sky2));overflow:hidden;-webkit-text-size-adjust:100%}
*,*::before,*::after{box-sizing:inherit}
button{font:inherit;cursor:pointer}
img,svg{max-width:100%}
b,strong{font-weight:700}
.kw{font-weight:700;color:var(--tc,#215FA3);border-bottom:3px solid var(--tc,#215FA3)}
.hide{display:none !important}

#app{height:100%;display:grid;grid-template-rows:auto 1fr;gap:8px;padding:8px}

/* HUD */
#hud{display:flex;align-items:center;gap:10px;flex-wrap:wrap;background:rgba(255,255,255,.55);border-radius:14px;padding:6px 12px;color:var(--ink)}
:root[data-theme="dark"] #hud{background:rgba(255,255,255,.14);color:#fff}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]) #hud{background:rgba(255,255,255,.14);color:#fff}}
#hud .logo{font-weight:700;font-size:1.05em;letter-spacing:.02em}
#hud .chip{display:inline-flex;align-items:center;gap:6px;background:var(--paper);color:var(--ink);border-radius:999px;padding:2px 12px;font-weight:600;font-size:.9em}
#hud .chip.coin b{color:#9A6B00}
#hud .spacer{flex:1}
#hud .icobtn{border:0;background:var(--paper);color:var(--ink);border-radius:999px;width:42px;height:42px;font-size:1.1em;display:inline-flex;align-items:center;justify-content:center}
#hud .icobtn:focus-visible,.btn:focus-visible,.opt:focus-visible,.chipbtn:focus-visible{outline:4px solid #FFD54F;outline-offset:2px}

/* MAIN */
#main{display:grid;grid-template-columns:2fr 3fr;gap:10px;min-height:0}
#scene{position:relative;border-radius:18px;overflow:hidden;min-height:0;background:linear-gradient(#8FD0F8,#D9F1FF)}
:root[data-theme="dark"] #scene{background:linear-gradient(#182B57,#2B4479)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]) #scene{background:linear-gradient(#182B57,#2B4479)}}
#scene svg{width:100%;height:100%;display:block}
#card{background:var(--paper);border-radius:18px;padding:18px 22px;overflow-y:auto;min-height:0;box-shadow:0 6px 0 rgba(0,0,0,.12);position:relative}
#card > .inner{max-width:62ch;margin:0 auto}

.title{font-size:1.5em;font-weight:700;line-height:1.25;margin:0 0 8px}
.sub{color:var(--ink2);margin:0 0 14px;font-size:.95em}
.small{font-size:.85em;color:var(--ink2)}
.centre{text-align:center}
.stage{display:inline-block;border-radius:999px;padding:2px 12px;font-weight:700;color:#fff;background:var(--tc,#2F7FD6);font-size:.85em;margin-bottom:8px}

/* Buttons */
.btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;border:0;border-radius:14px;padding:12px 22px;font-weight:700;font-size:1.05em;color:#fff;background:var(--btn);box-shadow:0 5px 0 var(--btn2);transition:transform .08s;min-height:54px;text-align:center}
.btn:active{transform:translateY(4px);box-shadow:0 1px 0 var(--btn2)}
.btn.big{width:100%;font-size:1.15em;min-height:62px}
.btn.ok{background:var(--ok);--btn2:#127A41;box-shadow:0 5px 0 #127A41}
.btn.grey{background:#8A94AD;--btn2:#5E6884;box-shadow:0 5px 0 #5E6884}
.btn.warn{background:#EF8A2A;--btn2:#B85F0F;box-shadow:0 5px 0 #B85F0F}
.btn.purple{background:#8A5CD6;--btn2:#5F3AA3;box-shadow:0 5px 0 #5F3AA3}
.btn.ghost{background:transparent;color:var(--ink);box-shadow:none;border:3px solid var(--line);min-height:48px}
.btn:disabled{opacity:.5;cursor:default}
.row{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
.row.end{justify-content:flex-end}
.row.between{justify-content:space-between}
.stack{display:flex;flex-direction:column;gap:10px}
.mt{margin-top:14px}

/* Options */
.opts{display:grid;gap:10px;margin-top:12px}
.opt{display:flex;align-items:center;gap:12px;border:3px solid var(--line);background:#fff;color:var(--ink);border-radius:14px;padding:10px 14px;text-align:left;font-size:1em;line-height:1.45;min-height:56px;box-shadow:0 4px 0 var(--line)}
.opt .let{flex:0 0 auto;width:38px;height:38px;border-radius:10px;background:var(--paper2);display:inline-flex;align-items:center;justify-content:center;font-weight:700}
.opt.correct{border-color:var(--ok);background:var(--okbg);box-shadow:0 4px 0 var(--ok)}
.opt.correct .let{background:var(--ok);color:#fff}
.opt.wrong{border-color:var(--bad);background:var(--badbg);box-shadow:0 4px 0 var(--bad)}
.opt.wrong .let{background:var(--bad);color:#fff}
.opt.dim{opacity:.55}
.opt:disabled{cursor:default}

/* Feedback */
.fb{border-radius:14px;padding:14px 16px;margin-top:14px;border:3px solid var(--line);background:#fff}
.fb.good{border-color:var(--ok);background:var(--okbg)}
.fb.bad{border-color:var(--bad);background:var(--badbg)}
.fb.hint{border-color:#F2C14E;background:#FFF6D6}
.fb h3{margin:0 0 6px;font-size:1.1em}
.fb p{margin:6px 0}
.pic{background:#fff;border:3px solid var(--line);border-radius:14px;padding:8px;margin:10px 0}
.pic svg{width:100%;height:auto;max-height:260px;display:block;margin:0 auto}
.pic.big svg{max-height:320px}

/* Learn cards */
.learn h2{font-size:1.35em;margin:0 0 8px;line-height:1.3}
.learn p{margin:8px 0;font-size:1.05em}
.learn ul{margin:6px 0 6px 20px;padding:0}
.learn li{margin:4px 0}
.dots{display:flex;gap:6px;justify-content:center;margin:8px 0}
.dots i{width:12px;height:12px;border-radius:50%;background:var(--line);display:inline-block}
.dots i.on{background:var(--tc,#2F7FD6)}

/* Timer */
.timer{height:14px;background:#EADFB8;border-radius:999px;overflow:hidden;margin:8px 0 4px}
.timer div{height:100%;background:linear-gradient(90deg,#1FA45B,#FFC72C,#FF6A2C);width:100%;transition:width 1s linear}
.timer.urgent div{background:#E0503A}

/* Chips (answer builder) */
.chips{display:flex;flex-wrap:wrap;gap:8px;margin:10px 0}
.chipbtn{border:3px solid var(--line);background:#fff;color:var(--ink);border-radius:12px;padding:8px 12px;text-align:left;font-size:.95em;line-height:1.4;box-shadow:0 3px 0 var(--line)}
.chipbtn.used{opacity:.35}
.chipbtn.sel{border-color:var(--tc,#2F7FD6);background:#EAF3FF}
.chipbtn.yes{border-color:var(--ok);background:var(--okbg)}
.chipbtn.no{border-color:var(--bad);background:var(--badbg)}
.answerbox{min-height:70px;border:3px dashed var(--line);border-radius:14px;padding:10px;background:#fff;margin-top:6px}
.answerbox .empty{color:var(--ink2)}
.answerbox .piece{display:inline-block;background:#EAF3FF;border-radius:10px;padding:4px 10px;margin:3px;border:2px solid #BBD5F5}
textarea.ans{width:100%;min-height:110px;font:inherit;font-size:1em;border:3px solid var(--line);border-radius:14px;padding:10px;background:#fff;color:var(--ink);resize:vertical}
.cer{display:grid;grid-template-columns:auto 1fr;gap:6px 10px;margin-top:8px}
.cer b{background:var(--paper2);border-radius:8px;padding:2px 8px;height:fit-content}
.model{background:#fff;border:3px solid var(--ok);border-radius:14px;padding:12px 14px;margin-top:10px}
.model .mk{background:#FFF0A6;border-radius:6px;padding:0 4px;font-weight:700}

/* Map */
.map{display:grid;gap:12px}
.island{border-radius:16px;padding:12px 14px;border:3px solid var(--tc);background:#fff}
.island h3{margin:0 0 8px;font-size:1.1em;display:flex;align-items:center;gap:8px}
.island h3 .tag{background:var(--tc);color:#fff;border-radius:999px;padding:0 10px;font-size:.8em}
.blocks{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:8px}
.blk{border:3px solid var(--line);border-radius:12px;padding:8px 10px;background:var(--paper);text-align:left;color:var(--ink);box-shadow:0 4px 0 var(--line);position:relative;min-height:74px;display:flex;flex-direction:column;justify-content:space-between}
.blk .nm{font-weight:700;font-size:.95em;line-height:1.3}
.blk .st{font-size:.85em;color:#B8860B;letter-spacing:.05em}
.blk.next{border-color:var(--tc);box-shadow:0 4px 0 var(--tc);outline-offset:3px;animation:glow 1.6s ease-in-out infinite}
.blk.done{background:var(--okbg)}
@keyframes glow{0%,100%{outline:4px solid rgba(255,213,79,0)}50%{outline:4px solid rgba(255,213,79,1)}}
.arena{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.arena .btn{min-height:70px;flex-direction:column;gap:2px;line-height:1.2}
.arena .btn small{font-weight:400;font-size:.75em;opacity:.9}
.plan{background:#fff;border:3px solid var(--line);border-radius:14px;padding:10px 14px;margin-top:10px;font-size:.92em}
.plan b{color:var(--ink)}

/* Avatars */
.avs{display:flex;gap:10px;flex-wrap:wrap;justify-content:center;margin:10px 0}
.av{border:3px solid var(--line);background:#fff;border-radius:14px;padding:6px;width:88px;height:98px;box-shadow:0 4px 0 var(--line)}
.av.sel{border-color:var(--ok);box-shadow:0 4px 0 var(--ok);background:var(--okbg)}
.av svg{width:100%;height:100%}
input.nm{font:inherit;font-size:1.05em;border:3px solid var(--line);border-radius:12px;padding:10px 12px;width:100%;background:#fff;color:var(--ink)}

/* Results */
.stars{font-size:2.4em;letter-spacing:.1em;text-align:center;margin:6px 0}
.score{font-size:2.6em;font-weight:700;text-align:center;line-height:1.1}
table.rep{width:100%;border-collapse:collapse;font-size:.92em;margin-top:8px}
table.rep th,table.rep td{border-bottom:2px solid var(--line);padding:6px 6px;text-align:left}
table.rep th{background:var(--paper2)}
table.q{border-collapse:collapse;margin:8px 0;font-size:.95em;background:#fff}
table.q th,table.q td{border:2px solid var(--line);padding:4px 10px;text-align:left}
table.q th{background:var(--paper2)}

/* Toasts / effects */
#toast{position:absolute;left:50%;top:14px;transform:translateX(-50%);background:var(--ink);color:#fff;padding:8px 16px;border-radius:999px;font-weight:700;opacity:0;transition:opacity .2s;pointer-events:none;z-index:5;white-space:nowrap}
#toast.on{opacity:1}
.shake{animation:shake .4s}
@keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-6px)}75%{transform:translateX(6px)}}
#confetti{position:fixed;inset:0;pointer-events:none;z-index:9}
.flash{perspective:1000px;margin:10px 0}
.flashcard{position:relative;min-height:200px;border-radius:16px;border:3px solid var(--tc);background:#fff;padding:18px;display:flex;align-items:center;justify-content:center;text-align:center;font-size:1.15em;font-weight:600;cursor:pointer;box-shadow:0 5px 0 var(--tc)}
.flashcard.back{background:var(--okbg)}

@media (prefers-reduced-motion:reduce){*{animation:none !important;transition:none !important}}

@media (max-width:820px){
  #app{padding:6px}
  #main{grid-template-columns:1fr;grid-template-rows:150px 1fr}
  #card{padding:14px 14px}
  .arena{grid-template-columns:1fr}
  :root{--fs:18px}
  #hud .logo{display:none}
}

/* Scene animation */
#scene .av{transition:transform .6s cubic-bezier(.35,1.4,.5,1);will-change:transform}
#scene .av .body{transform-box:fill-box;transform-origin:50% 100%}
#scene .av.hop .body{animation:hop .6s ease-out}
@keyframes hop{0%{transform:translateY(0)}45%{transform:translateY(-34px) scaleY(1.06)}100%{transform:translateY(0)}}
#scene .av.falling{animation:fall 1.1s ease-in forwards}
@keyframes fall{0%{transform:translate(var(--ax),var(--ay)) rotate(0deg)}30%{transform:translate(var(--ax),calc(var(--ay) - 26px)) rotate(-8deg)}100%{transform:translate(var(--ax),calc(var(--ay) + 520px)) rotate(75deg)}}
#scene .av.bounce .body{animation:bounce .8s ease-in-out infinite}
@keyframes bounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-24px)}}
#scene .cloud{animation:drift 26s ease-in-out infinite alternate}
#scene .cloud.c1{animation-duration:34s}
#scene .cloud.c2{animation-duration:42s}
@keyframes drift{from{transform:translateX(-18px)}to{transform:translateX(18px)}}
#scene .lava{transition:transform 1s linear}
#scene .coin{animation:coinbob 1.6s ease-in-out infinite}
@keyframes coinbob{0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}
#scene .lbl{fill:var(--scenetext)}
.opt.sel{border-color:var(--tc,#2F7FD6);background:#EAF3FF}
details summary::-webkit-details-marker{display:inline}
.qtext table{margin:8px 0}
@media (max-width:820px){#scene .lbl{display:none}}

</style>
</head>
<body>
<div id="app">
  <div id="hud" role="banner"></div>
  <div id="main">
    <div id="scene" aria-hidden="true"></div>
    <div id="card" role="main"></div>
  </div>
</div>
<canvas id="confetti" aria-hidden="true"></canvas>
<script>
// ---------- SVG picture library (part 1: helpers, tiles, flows, cycles) ----------
var IMG = {};
var INK = '#1E2A44', SOFT = '#4E5A78';
var TC = { div: '#2E9E4F', cyc: '#2F7FD6', sys: '#EF8A2A', int: '#8A5CD6', ene: '#D9A400' };
var TCL = { div: '#E3F5E8', cyc: '#E3EFFC', sys: '#FDEBD8', int: '#EEE6FA', ene: '#FFF4CC' };

function T(x, y, s, o) { o = o || {}; return '<text x="' + x + '" y="' + y + '" text-anchor="' + (o.a || 'middle') + '" font-size="' + (o.s || 18) + '" font-weight="' + (o.w || 600) + '" fill="' + (o.f || INK) + '"' + (o.extra || '') + '>' + s + '</text>'; }
function R(x, y, w, h, f, o) { o = o || {}; return '<rect x="' + x + '" y="' + y + '" width="' + w + '" height="' + h + '" rx="' + (o.r == null ? 12 : o.r) + '" fill="' + f + '" stroke="' + (o.st || 'none') + '" stroke-width="' + (o.sw || 3) + '"' + (o.extra || '') + '/>'; }
function C(x, y, r, f, o) { o = o || {}; return '<circle cx="' + x + '" cy="' + y + '" r="' + r + '" fill="' + f + '" stroke="' + (o.st || 'none') + '" stroke-width="' + (o.sw || 3) + '"/>'; }
function L(x1, y1, x2, y2, c, w, dash) { return '<line x1="' + x1 + '" y1="' + y1 + '" x2="' + x2 + '" y2="' + y2 + '" stroke="' + (c || INK) + '" stroke-width="' + (w || 4) + '" stroke-linecap="round"' + (dash ? ' stroke-dasharray="' + dash + '"' : '') + '/>'; }
function AR(x1, y1, x2, y2, c, w) {
  c = c || INK; w = w || 4; var a = Math.atan2(y2 - y1, x2 - x1), h = 13;
  var p1 = [x2 - h * Math.cos(a - .5), y2 - h * Math.sin(a - .5)], p2 = [x2 - h * Math.cos(a + .5), y2 - h * Math.sin(a + .5)];
  return L(x1, y1, x2 - 5 * Math.cos(a), y2 - 5 * Math.sin(a), c, w) + '<polygon points="' + x2 + ',' + y2 + ' ' + p1[0].toFixed(1) + ',' + p1[1].toFixed(1) + ' ' + p2[0].toFixed(1) + ',' + p2[1].toFixed(1) + '" fill="' + c + '"/>';
}
function SVG(w, h, inner) { return '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 ' + w + ' ' + h + '" font-family="Lexend,Verdana,Arial,sans-serif" role="img">' + inner + '</svg>'; }
function TL(x, y, arr, o) { o = o || {}; var lh = o.lh || 20, s = ''; for (var i = 0; i < arr.length; i++) s += T(x, y + i * lh, arr[i], o); return s; }
function E(x, y, e, s) { return '<text x="' + x + '" y="' + y + '" text-anchor="middle" font-size="' + (s || 40) + '">' + e + '</text>'; }

// tiles: [{e:'💧', l:'Water', d:'line1|line2'}]
function tiles(items, col, opts) {
  opts = opts || {};
  var n = items.length, cols = opts.cols || (n <= 3 ? n : n === 4 ? 4 : n === 5 ? 5 : 3);
  var rows = Math.ceil(n / cols), gap = 12, W = 600, hasD = items.some(function (i) { return i.d; });
  var th = hasD ? 128 : 100, tw = (W - gap * (cols + 1)) / cols, H = rows * (th + gap) + gap + (opts.cap ? 30 : 0);
  var s = '';
  if (opts.cap) s += T(300, 24, opts.cap, { s: 20, w: 700 });
  items.forEach(function (it, i) {
    var r = Math.floor(i / cols), c = i % cols, x = gap + c * (tw + gap), y = gap + r * (th + gap) + (opts.cap ? 30 : 0);
    s += R(x, y, tw, th, '#fff', { st: col, sw: 3, r: 14 });
    s += E(x + tw / 2, y + 44, it.e, 38);
    s += T(x + tw / 2, y + 72, it.l, { s: cols >= 5 ? 15 : 18, w: 700, f: col });
    if (it.d) { var d = it.d.split('|'); s += TL(x + tw / 2, y + 94, d, { s: 14, w: 500, lh: 17, f: SOFT }); }
  });
  return SVG(W, H, s);
}

// flow: [{e,l,d}] left to right; 5-6 items snake into two rows
function flow(items, col, opts) {
  opts = opts || {};
  var n = items.length, W = 600, s = '';
  var twoRows = n > 4, per = twoRows ? Math.ceil(n / 2) : n;
  var hasD = items.some(function (i) { return i.d; }), gapx = 34, bw = (W - 20 - (per - 1) * gapx) / per, bh = hasD ? 106 : 84, y0 = opts.cap ? 40 : 10;
  var H = (twoRows ? 2 * bh + 44 : bh) + y0 + 10;
  if (opts.cap) s += T(300, 26, opts.cap, { s: 20, w: 700 });
  var pos = [];
  items.forEach(function (it, i) {
    var row = twoRows && i >= per ? 1 : 0, idx = row ? i - per : i;
    var x = row ? (10 + (per - 1 - idx) * (bw + gapx)) : (10 + idx * (bw + gapx));
    var y = y0 + row * (bh + 44);
    pos.push([x, y]);
    s += R(x, y, bw, bh, '#fff', { st: col, sw: 3, r: 14 });
    if (it.e) s += E(x + bw / 2, y + 36, it.e, 30);
    s += T(x + bw / 2, y + (it.e ? 60 : 36), it.l, { s: it.l.length > 12 ? 15 : 17, w: 700, f: col });
    if (it.d) s += TL(x + bw / 2, y + (it.e ? 78 : 58), it.d.split('|'), { s: 13, w: 500, lh: 15, f: SOFT });
  });
  for (var i = 0; i < n - 1; i++) {
    var a = pos[i], b = pos[i + 1];
    if (twoRows && i === per - 1) s += AR(a[0] + bw / 2, a[1] + bh + 2, b[0] + bw / 2, b[1] - 3, col, 5);
    else if (twoRows && i >= per) s += AR(a[0] - 2, a[1] + bh / 2, b[0] + bw + 3, b[1] + bh / 2, col, 5);
    else s += AR(a[0] + bw + 2, a[1] + bh / 2, b[0] - 3, b[1] + bh / 2, col, 5);
  }
  return SVG(W, H, s);
}

// cycle: boxes around an ellipse with arrows, caption in the centre
function cycle(items, col, cap) {
  var n = items.length, W = 600, H = 330, cx = 300, cy = 165, rx = 210, ry = 108, bw = 166, bh = 82, s = '', pos = [];
  items.forEach(function (it, i) {
    var ang = -Math.PI / 2 + i * 2 * Math.PI / n, x = cx + rx * Math.cos(ang), y = cy + ry * Math.sin(ang);
    pos.push([x, y]);
  });
  for (var i = 0; i < n; i++) {
    var a = pos[i], b = pos[(i + 1) % n], ang = Math.atan2(b[1] - a[1], b[0] - a[0]);
    var dx = Math.cos(ang), dy = Math.sin(ang), k1 = 70, k2 = 74;
    s += AR(a[0] + dx * k1, a[1] + dy * k1, b[0] - dx * k2, b[1] - dy * k2, col, 5);
  }
  items.forEach(function (it, i) {
    var x = pos[i][0] - bw / 2, y = pos[i][1] - bh / 2;
    s += R(x, y, bw, bh, '#fff', { st: col, sw: 3, r: 14 });
    s += E(x + 30, y + bh / 2 + 12, it.e, 30);
    var ll = it.l.split('|');
    s += TL(x + 104, y + 26, ll, { s: 15, w: 700, f: col, lh: 17 });
    if (it.d) s += TL(x + 104, y + 28 + ll.length * 17, it.d.split('|'), { s: 11.5, w: 500, f: SOFT, lh: 13 });
  });
  if (cap) s += TL(cx, cy - 4, cap.split('|'), { s: 15, w: 600, f: SOFT, lh: 18 });
  return SVG(W, H, s);
}

// two-column compare: [{h:'Matter', col, items:[{e,l}]}, {...}]
function compare(a, b, ca, cb) {
  var W = 600, H = 68 + Math.max(a.items.length, b.items.length) * 44 + 20, s = '';
  [[a, ca, 10], [b, cb, 305]].forEach(function (z) {
    var d = z[0], col = z[1], x = z[2];
    s += R(x, 10, 285, H - 20, '#fff', { st: col, sw: 3, r: 14 });
    var hl = d.h.split('|');
    s += R(x, 10, 285, 52, col, { r: 14 }) + R(x, 36, 285, 26, col, { r: 0 });
    s += TL(x + 142, hl.length > 1 ? 32 : 42, hl, { s: 15, w: 700, f: '#fff', lh: 19 });
    d.items.forEach(function (it, i) { s += E(x + 40, 100 + i * 44, it.e, 26) + T(x + 70, 98 + i * 44, it.l, { s: 15, a: 'start', w: 600 }); });
  });
  return SVG(W, H, s);
}

// ---------- Diversity ----------
IMG.living = tiles([{ e: '💨', l: 'Need air' }, { e: '💧', l: 'Need water' }, { e: '🍎', l: 'Need food' }, { e: '📏', l: 'Grow' }, { e: '👋', l: 'Respond', d: 'react to changes' }, { e: '👶', l: 'Reproduce', d: 'make young' }], TC.div, { cap: 'All living things do these things' });
IMG.animals6 = tiles([{ e: '🐸', l: 'Amphibians', d: 'moist skin|land + water' }, { e: '🐦', l: 'Birds', d: 'feathers|lay eggs' }, { e: '🐟', l: 'Fish', d: 'fins, gills|live in water' }, { e: '🐞', l: 'Insects', d: '6 legs|3 body parts' }, { e: '🐶', l: 'Mammals', d: 'fur or hair|feed young milk' }, { e: '🦎', l: 'Reptiles', d: 'dry scaly skin|lay eggs' }], TC.div, { cap: '6 animal groups' });
IMG.fungi = tiles([{ e: '🍄', l: 'Mushroom', d: 'fungus' }, { e: '🍞', l: 'Mould', d: 'fungus on old bread' }, { e: '🥖', l: 'Yeast', d: 'fungus that makes|bread rise' }, { e: '🦠', l: 'Bacteria', d: 'tiny, need a|microscope to see' }], TC.div, { cap: 'Fungi and bacteria are living things too' });
IMG.materials = tiles([{ e: '🪵', l: 'Wood' }, { e: '🔩', l: 'Metal' }, { e: '🏺', l: 'Ceramic' }, { e: '🧤', l: 'Rubber' }, { e: '🪟', l: 'Glass' }, { e: '🧴', l: 'Plastic' }, { e: '🧵', l: 'Fabric' }], TC.div, { cols: 4, cap: 'Materials (what an object is made of)' });
IMG.props = tiles([{ e: '💪', l: 'Strength', d: 'holds a heavy load|without breaking' }, { e: '🌀', l: 'Flexibility', d: 'bends without|breaking' }, { e: '🛟', l: 'Float / sink', d: 'stays on the water|or goes down' }, { e: '☔', l: 'Waterproof', d: 'does NOT absorb|water' }, { e: '🔆', l: 'Transparency', d: 'lets most / some /|no light through' }], TC.div, { cols: 3, cap: '5 properties of materials' });
IMG.uses = tiles([{ e: '☔', l: 'Raincoat', d: 'waterproof' }, { e: '🪟', l: 'Window', d: 'lets most light through' }, { e: '🌉', l: 'Bridge cable', d: 'strong' }, { e: '🧤', l: 'Rubber glove', d: 'flexible + waterproof' }, { e: '🛟', l: 'Life float', d: 'floats' }, { e: '🥄', l: 'Wooden spoon', d: 'strong, poor conductor' }], TC.div, { cap: 'Choose the material for its property' });

// ---------- Cycles ----------
IMG.plantcycle = cycle([{ e: '🌰', l: 'Seed' }, { e: '🌱', l: 'Young plant|(seedling)' }, { e: '🌳', l: 'Adult plant', d: 'makes flowers|and seeds' }], TC.cyc, 'Plant life cycle|repeats again and again');
IMG.cycle3 = cycle([{ e: '🥚', l: 'Egg' }, { e: '🐥', l: 'Young', d: 'looks like a|small adult' }, { e: '🐔', l: 'Adult', d: 'lays eggs' }], TC.cyc, '3 stages|chicken, grasshopper,|cockroach');
IMG.cycle4 = cycle([{ e: '🥚', l: 'Egg' }, { e: '🐛', l: 'Larva', d: 'eats a lot,|looks different' }, { e: '🟤', l: 'Pupa', d: 'does not eat,|changes inside' }, { e: '🦋', l: 'Adult', d: 'lays eggs' }], TC.cyc, '4 stages|butterfly, beetle,|mosquito');
IMG.frogcycle = cycle([{ e: '🥚', l: 'Egg', d: 'in water' }, { e: '🐟', l: 'Tadpole', d: 'in water,|gills + tail' }, { e: '🐸', l: 'Adult frog', d: 'land + water' }], TC.cyc, 'Frog: 3 stages|the young does NOT|look like the adult');
IMG.mosquito = flow([{ e: '🥚', l: 'Eggs', d: 'laid ON water' }, { e: '🐛', l: 'Larva', d: 'wriggler, IN water' }, { e: '🟤', l: 'Pupa', d: 'tumbler, IN water' }, { e: '🦟', l: 'Adult', d: 'flies away' }], TC.cyc, { cap: 'No stagnant water = eggs, larvae and pupae cannot live' });
IMG.matter = compare({ h: 'MATTER|has mass + takes up space', items: [{ e: '🪨', l: 'stone (solid)' }, { e: '💧', l: 'water (liquid)' }, { e: '💨', l: 'air (gas) - yes, air too!' }] }, { h: 'NOT MATTER|no mass, no space', items: [{ e: '💡', l: 'light' }, { e: '🔥', l: 'heat' }, { e: '🔊', l: 'sound' }] }, TC.cyc, '#E0503A');
IMG.measure = tiles([{ e: '⚖️', l: 'Mass', d: 'beam balance / scale|grams (g), kilograms (kg)' }, { e: '🧪', l: 'Volume of liquid', d: 'measuring cylinder|millilitres (ml), litres (l)' }, { e: '💉', l: 'Volume of gas', d: 'syringe|(gas fills the space)' }], TC.cyc, { cap: 'Measuring matter' });
IMG.reproduce = tiles([{ e: '🐱', l: 'Parents', d: 'living things|reproduce' }, { e: '➡️', l: 'pass on', d: 'characteristics|to young' }, { e: '🐱', l: 'Young', d: 'same kind,|looks like parents' }], TC.cyc, { cap: 'Reproduction keeps the kind going (continuity)' });
IMG.dispersal = tiles([{ e: '🌬️', l: 'Wind', d: 'light, has wings|or hairs' }, { e: '🌊', l: 'Water', d: 'floats, fibrous husk|(coconut)' }, { e: '🐒', l: 'Animals', d: 'juicy fruit eaten, or|hooks stick to fur' }, { e: '💥', l: 'Splitting', d: 'pod dries, bursts|and flings seeds out' }], TC.cyc, { cols: 4, cap: 'How seeds are dispersed (spread away)' });
IMG.germinate = flow([{ e: '🌰', l: 'Seed', d: 'takes in water' }, { e: '🌱', l: 'Root then shoot', d: 'root grows down first' }, { e: '🌿', l: 'Young plant', d: 'leaves make food' }], TC.cyc, { cap: 'Germination needs: water + air + warmth (NOT light, NOT soil)' });
IMG.spores = tiles([{ e: '🌿', l: 'Fern', d: 'spores under|the leaves' }, { e: '🍄', l: 'Mushroom', d: 'spores under|the cap' }, { e: '🌬️', l: 'Spores', d: 'tiny, carried|by the wind' }], TC.cyc, { cap: 'Non-flowering plants and fungi reproduce by spores' });
IMG.humanrep = flow([{ e: '👨', l: 'Testes', d: 'make sperm|(male cell)' }, { e: '👩', l: 'Ovaries', d: 'make eggs|(female cell)' }, { e: '🔗', l: 'Fertilisation', d: 'sperm fuses|with egg' }, { e: '👶', l: 'Womb', d: 'fertilised egg|grows into baby' }], TC.cyc, { cap: 'Humans: male cell + female cell, same idea as plants' });
IMG.evap = tiles([{ e: '💨', l: 'More wind', d: 'blows water vapour|away faster' }, { e: '🌡️', l: 'Higher temperature', d: 'water gains|heat faster' }, { e: '↔️', l: 'Bigger surface', d: 'more water is|exposed to air' }], TC.cyc, { cap: 'Evaporation is faster with...' });

// ---------- Systems ----------
IMG.systems = tiles([{ e: '🍽️', l: 'Digestive', d: 'breaks down food' }, { e: '🫁', l: 'Respiratory', d: 'takes in oxygen,|gives out carbon dioxide' }, { e: '❤️', l: 'Circulatory', d: 'heart + blood carry|things around' }, { e: '🦴', l: 'Skeletal', d: 'bones support|and protect' }, { e: '💪', l: 'Muscular', d: 'muscles move|the body' }], TC.sys, { cols: 3, cap: 'Body systems work together' });
IMG.digest = flow([{ e: '👄', l: 'Mouth', d: 'teeth cut and grind,|saliva starts digesting' }, { l: 'Gullet', d: 'pushes food|down to stomach' }, { l: 'Stomach', d: 'digestive juices|break food down' }, { l: 'Small intestine', d: 'digestion finishes,|food absorbed into blood' }, { l: 'Large intestine', d: 'absorbs water from|undigested food' }, { l: 'Anus', d: 'undigested food|leaves the body' }], TC.sys, { cap: 'Digestive system: break food down, absorb it into the blood' });
IMG.resp = flow([{ e: '👃', l: 'Nose', d: 'air goes in' }, { l: 'Windpipe', d: 'tube to the lungs' }, { e: '🫁', l: 'Lungs', d: 'oxygen goes INTO blood,|carbon dioxide comes OUT' }], TC.sys, { cap: 'Breathe in: nose - windpipe - lungs. Breathe out: same way back' });
IMG.circ = flow([{ e: '❤️', l: 'Heart', d: 'pumps blood' }, { l: 'Blood vessels', d: 'tubes that carry blood|to every part' }, { e: '🩸', l: 'Blood', d: 'carries oxygen + digested food|to cells; carries CO2 away' }], TC.sys, { cap: 'The circulatory system is the delivery service' });
IMG.teamup = flow([{ e: '🍽️', l: 'Digestive', d: 'gives digested food' }, { e: '🫁', l: 'Respiratory', d: 'gives oxygen' }, { e: '🩸', l: 'Blood carries both', d: 'to every part of the body' }, { e: '⚡', l: 'Energy released', d: 'carbon dioxide made,|sent back to lungs' }], TC.sys, { cap: 'Three systems team up so the body gets energy' });
IMG.gills = tiles([{ e: '🐟', l: 'Fish', d: 'gills take oxygen|from WATER' }, { e: '🌿', l: 'Plants', d: 'tiny openings in leaves|let gases in and out' }, { e: '🧍', l: 'Humans', d: 'lungs take oxygen|from AIR' }], TC.sys, { cap: 'All living things take in oxygen and give out carbon dioxide' });
IMG.conduct = compare({ h: 'CONDUCTORS|current CAN pass', items: [{ e: '🔩', l: 'iron, steel' }, { e: '🥉', l: 'copper, aluminium' }, { e: '✏️', l: 'pencil lead (graphite)' }] }, { h: 'INSULATORS|current CANNOT pass', items: [{ e: '🧴', l: 'plastic, rubber' }, { e: '🪵', l: 'wood, paper' }, { e: '🪟', l: 'glass, air' }] }, TC.sys, '#E0503A');

// ---------- Interactions ----------
IMG.magnetmat = compare({ h: 'MAGNETIC|attracted by a magnet', items: [{ e: '🔩', l: 'iron' }, { e: '📎', l: 'steel (paper clip)' }, { e: '🧲', l: 'another magnet' }] }, { h: 'NON-MAGNETIC|not attracted', items: [{ e: '🥉', l: 'copper, aluminium, gold' }, { e: '🧴', l: 'plastic, rubber' }, { e: '🪵', l: 'wood, paper, glass' }] }, TC.int, '#E0503A');
IMG.uses_mag = tiles([{ e: '🧭', l: 'Compass', d: 'needle points|North-South' }, { e: '🚪', l: 'Fridge door', d: 'magnetic strip|keeps it shut' }, { e: '🏗️', l: 'Crane', d: 'electromagnet lifts|scrap iron' }, { e: '🚄', l: 'Maglev train', d: 'magnets lift|and push it' }], TC.int, { cols: 4, cap: 'Magnets in everyday life' });
IMG.effects = tiles([{ e: '▶️', l: 'Start moving', d: 'a stationary object' }, { e: '⏩', l: 'Speed up' }, { e: '⏪', l: 'Slow down' }, { e: '↪️', l: 'Change direction' }, { e: '⏹️', l: 'Stop', d: 'a moving object' }, { e: '🧽', l: 'Change shape' }], TC.int, { cap: 'What a force (push or pull) can do' });
IMG.forces4 = tiles([{ e: '🧲', l: 'Magnetic', d: 'push or pull between|magnets / iron, steel' }, { e: '🌍', l: 'Gravitational', d: 'pulls everything|towards Earth' }, { e: '🌀', l: 'Elastic spring', d: 'stretched / squashed|spring pushes back' }, { e: '🛞', l: 'Frictional', d: 'between touching surfaces,|slows things down' }], TC.int, { cols: 4, cap: '4 types of forces' });
IMG.foodchain = flow([{ e: '☀️', l: 'Sun', d: 'source of|energy' }, { e: '🌿', l: 'Grass', d: 'producer|(makes food)' }, { e: '🦗', l: 'Grasshopper', d: 'consumer|prey of frog' }, { e: '🐸', l: 'Frog', d: 'consumer|predator + prey' }, { e: '🐍', l: 'Snake', d: 'consumer|predator' }], TC.int, { cap: 'Arrow = "is eaten by" = energy flows this way' });
IMG.habitat = tiles([{ e: '🌷', l: 'Garden' }, { e: '🌾', l: 'Field' }, { e: '🪷', l: 'Pond' }, { e: '🏖️', l: 'Seashore' }, { e: '🌳', l: 'Tree' }, { e: '🌴', l: 'Mangrove swamp' }], TC.int, { cap: 'Different habitats support different communities' });
IMG.survive = tiles([{ e: '🌡️', l: 'Temperature' }, { e: '☀️', l: 'Light' }, { e: '💧', l: 'Water' }, { e: '🍎', l: 'Food' }, { e: '🐺', l: 'Other organisms', d: 'predators, competitors,|decomposers' }, { e: '🏃', l: 'If it gets bad...', d: 'adapt, move away|or die' }], TC.int, { cap: 'What affects survival' });
IMG.adapt = tiles([{ e: '🦆', l: 'Webbed feet', d: 'move in water|to get food' }, { e: '🐻‍❄️', l: 'Thick fur', d: 'cope with cold' }, { e: '🦎', l: 'Camouflage', d: 'escape predators' }, { e: '🦚', l: 'Bright feathers', d: 'attract a mate|(reproduce)' }, { e: '🦉', l: 'Hunts at night', d: 'behavioural' }, { e: '🐻', l: 'Hibernates', d: 'behavioural' }], TC.int, { cap: 'Structural = body part. Behavioural = what it does' });
IMG.plantadapt = tiles([{ e: '🌵', l: 'Cactus', d: 'spines lose less water,|thick stem stores water' }, { e: '🪷', l: 'Water lily', d: 'broad flat leaves float|to get light' }, { e: '🌴', l: 'Mangrove', d: 'breathing roots stick out|of the mud to get air' }], TC.int, { cap: 'Plant adaptations' });
IMG.impact = compare({ h: 'NEGATIVE impact|(harms nature)', items: [{ e: '🪓', l: 'deforestation' }, { e: '🏭', l: 'pollution (air, water, land)' }, { e: '🌡️', l: 'global warming' }, { e: '⛽', l: 'using up resources' }] }, { h: 'POSITIVE impact|(helps nature)', items: [{ e: '🌳', l: 'reforestation (planting)' }, { e: '♻️', l: 'conservation: reduce,' }, { e: '🛡️', l: 'reuse, recycle, protect' }, { e: '🌏', l: 'nature reserves' }] }, '#E0503A', TC.div);

// ---------- Energy ----------
IMG.sources = tiles([{ e: '☀️', l: 'Sun' }, { e: '🔥', l: 'Fire' }, { e: '🍳', l: 'Stove' }, { e: '🔌', l: 'Appliances' }, { e: '🤲', l: 'Rubbing', d: 'friction' }, { e: '🧍', l: 'Our body' }], TC.ene, { cap: 'Sources of heat' });
IMG.conductheat2 = compare({ h: 'GOOD conductors|of heat', items: [{ e: '🥄', l: 'metals: iron, steel,' }, { e: '🍳', l: 'copper, aluminium' }, { e: '⚡', l: 'heat passes QUICKLY' }] }, { h: 'POOR conductors|of heat', items: [{ e: '🪵', l: 'wood, plastic, rubber' }, { e: '💨', l: 'air, styrofoam, wool' }, { e: '🐢', l: 'heat passes SLOWLY' }] }, TC.ene, '#2F7FD6');
IMG.forms = tiles([{ e: '🏃', l: 'Kinetic', d: 'moving things' }, { e: '🔋', l: 'Potential', d: 'stored: battery, food,|stretched spring, raised' }, { e: '💡', l: 'Light' }, { e: '🔥', l: 'Heat' }, { e: '🔊', l: 'Sound' }, { e: '⚡', l: 'Electrical' }], TC.ene, { cap: '6 forms of energy' });
IMG.convert = flow([{ e: '🔋', l: 'Torch battery', d: 'potential energy' }, { e: '⚡', l: 'Electrical', d: 'in the wires' }, { e: '💡', l: 'Light + heat', d: 'from the bulb' }], TC.ene, { cap: 'Energy is converted (changed) from one form to another' });
IMG.energysun = flow([{ e: '☀️', l: 'Sun', d: 'light + heat' }, { e: '🌿', l: 'Plants', d: 'store energy in|food (potential)' }, { e: '🐔', l: 'Animals', d: 'eat plants' }, { e: '🧍', l: 'Us', d: 'eat plants|and animals' }], TC.ene, { cap: 'Almost all our energy can be traced back to the Sun' });
IMG.resp2 = flow([{ e: '🍚', l: 'Food', d: 'potential energy' }, { e: '➕', l: 'Oxygen', d: 'from breathing' }, { e: '⚡', l: 'Energy released', d: 'for moving, growing,|staying warm' }, { e: '💨', l: 'Carbon dioxide', d: 'given out|(+ water)' }], TC.ene, { cap: 'Respiration: ALL living things, ALL the time (plants too!)' });
IMG.photo2 = tiles([{ e: '☀️', l: 'Light energy', d: 'IN' }, { e: '💧', l: 'Water', d: 'IN (from roots)' }, { e: '💨', l: 'Carbon dioxide', d: 'IN (from air)' }, { e: '🍬', l: 'Sugar (food)', d: 'OUT - stored as starch' }, { e: '🫧', l: 'Oxygen', d: 'OUT - into the air' }], TC.ene, { cols: 5, cap: 'Photosynthesis happens in green leaves' });
IMG.conserve = tiles([{ e: '⛽', l: 'Fuels can run out', d: 'coal, oil, gas' }, { e: '🔌', l: 'Switch off', d: 'when not in use' }, { e: '☀️', l: 'Renewable', d: 'solar, wind, water|will not run out' }], TC.ene, { cap: 'Why conserve energy' });

// ---------- SVG picture library (part 2: drawn diagrams) ----------
(function () {
  var G = TC.div, B = TC.cyc, O = TC.sys, P = TC.int, Y = TC.ene, RED = '#E0503A', BLUE = '#2F7FD6', GREY = '#8A94AD';
  function bulb(x, y, on) { return C(x, y, 14, on ? '#FFE55C' : '#fff', { st: INK, sw: 3 }) + L(x - 7, y - 7, x + 7, y + 7, INK, 3) + L(x + 7, y - 7, x - 7, y + 7, INK, 3); }
  function batt(x, y) { return R(x - 3, y - 14, 6, 28, INK, { r: 0 }) + R(x + 11, y - 8, 6, 16, INK, { r: 0 }); }
  function bx(x, y, w, h, col, label, o) { o = o || {}; return R(x, y, w, h, o.fill || '#fff', { st: col, sw: 3, r: 12 }) + TL(x + w / 2, y + (o.ty || 28), label.split('|'), { s: o.s || 15, w: 700, f: o.f || col, lh: 18 }); }

  // Classification tree
  IMG.groups = SVG(600, 300,
    R(215, 8, 170, 42, G, { r: 12 }) + T(300, 36, 'Living things', { s: 18, w: 700, f: '#fff' }) +
    [40, 185, 330, 475].map(function (x) { return L(300, 50, x + 45, 88, G, 3); }).join('') +
    bx(10, 88, 120, 44, G, 'Plants 🌱') + bx(150, 88, 130, 44, G, 'Animals 🐾') + bx(300, 88, 120, 44, G, 'Fungi 🍄') + bx(440, 88, 150, 44, G, 'Bacteria 🦠') +
    TL(70, 158, ['Flowering 🌸', 'Non-flowering 🌿', '(ferns, moss)'], { s: 14, w: 600, lh: 18, f: SOFT }) +
    TL(215, 158, ['amphibians, birds,', 'fish, insects,', 'mammals, reptiles'], { s: 14, w: 600, lh: 18, f: SOFT }) +
    TL(360, 158, ['mould, mushroom,', 'yeast'], { s: 14, w: 600, lh: 18, f: SOFT }) +
    TL(515, 158, ['too small to see,', 'need a microscope'], { s: 14, w: 600, lh: 18, f: SOFT }) +
    R(10, 232, 580, 56, TCL.div, { r: 12 }) + TL(300, 255, ['We sort (classify) living things by things we can SEE:', 'feathers? fur? scales? 6 legs? flowers?'], { s: 15, w: 600, lh: 20 })
  );

  // Sorting flowchart
  IMG.classify = SVG(600, 300,
    bx(10, 20, 250, 48, G, 'Does it have feathers?') + AR(260, 44, 330, 44, G, 4) + T(295, 36, 'yes', { s: 13, f: SOFT }) + bx(335, 20, 110, 48, G, 'Bird 🐦') +
    AR(135, 68, 135, 108, G, 4) + T(155, 92, 'no', { s: 13, f: SOFT }) +
    bx(10, 110, 250, 48, G, 'Does it have fur or hair?') + AR(260, 134, 330, 134, G, 4) + T(295, 126, 'yes', { s: 13, f: SOFT }) + bx(335, 110, 130, 48, G, 'Mammal 🐶') +
    AR(135, 158, 135, 198, G, 4) + T(155, 182, 'no', { s: 13, f: SOFT }) +
    bx(10, 200, 250, 48, G, 'Does it have 6 legs?') + AR(260, 224, 330, 224, G, 4) + T(295, 216, 'yes', { s: 13, f: SOFT }) + bx(335, 200, 120, 48, G, 'Insect 🐞') +
    T(10, 285, 'no: check for scales, fins, moist skin...', { s: 14, f: SOFT, a: 'start' })
  );

  // Fair test
  IMG.fairtest = SVG(600, 260,
    R(60, 20, 480, 12, GREY, { r: 4 }) +
    [['Wood', 130], ['Plastic', 300], ['Metal', 470]].map(function (m) { return L(m[1], 32, m[1], 120, '#B08850', 14) + R(m[1] - 40, 120, 80, 40, INK, { r: 6 }) + T(m[1], 146, '1 kg', { s: 15, f: '#fff' }) + T(m[1], 190, m[0], { s: 17, w: 700, f: G }); }).join('') +
    R(20, 205, 560, 46, TCL.div, { r: 12 }) + TL(300, 225, ['SAME size, SAME load, SAME time.', 'Change ONLY the material = a fair test.'], { s: 15, lh: 19 })
  );

  // States of matter
  IMG.states = SVG(600, 250,
    bx(10, 10, 185, 200, B, 'Solid 🧊', { ty: 30, s: 18 }) + R(60, 70, 80, 60, '#BEE3FF', { st: B, sw: 3, r: 4 }) + TL(102, 160, ['Fixed shape ✓', 'Fixed volume ✓'], { s: 14, w: 600, lh: 18 }) +
    bx(207, 10, 185, 200, B, 'Liquid 💧', { ty: 30, s: 18 }) + '<path d="M260 60 L270 130 L330 130 L340 60 Z" fill="none" stroke="' + INK + '" stroke-width="3"/>' + '<path d="M266 95 L273 128 L327 128 L334 95 Z" fill="#7CC6F6"/>' + TL(300, 160, ['Takes shape of container', 'Fixed volume ✓'], { s: 13, w: 600, lh: 18 }) +
    bx(404, 10, 185, 200, B, 'Gas 💨', { ty: 30, s: 18 }) + R(440, 60, 110, 70, '#fff', { st: INK, sw: 3, r: 4 }) + [[455, 75], [500, 70], [535, 85], [470, 105], [520, 115], [490, 92]].map(function (p) { return C(p[0], p[1], 4, B); }).join('') + TL(497, 160, ['No fixed shape ✗', 'No fixed volume ✗', 'fills all the space'], { s: 13, w: 600, lh: 17 }) +
    T(300, 238, 'Matter = anything that has mass and takes up space', { s: 15, f: SOFT })
  );

  // Air is matter
  IMG.airmatter = SVG(600, 250,
    L(150, 40, 150, 170, INK, 6) + '<path d="M80 60 L220 80" stroke="' + INK + '" stroke-width="6" stroke-linecap="round"/>' +
    C(80, 96, 30, '#F9A8D4') + C(220, 106, 16, '#F9A8D4') + T(80, 150, 'full of air', { s: 14 }) + T(220, 150, 'empty', { s: 14 }) +
    T(150, 200, 'Full balloon is HEAVIER', { s: 15, w: 700, f: B }) + T(150, 222, 'air has MASS', { s: 15 }) +
    R(330, 100, 240, 100, '#BEE3FF', { r: 4 }) + '<path d="M420 60 L420 160 L480 160 L480 60" fill="#fff" stroke="' + INK + '" stroke-width="4"/>' + R(424, 136, 52, 20, '#BEE3FF', { r: 0 }) + T(450, 90, '📄', { s: 22 }) + T(450, 122, 'air', { s: 13, f: SOFT }) +
    T(450, 200, 'Paper stays DRY', { s: 15, w: 700, f: B }) + T(450, 222, 'air takes up SPACE', { s: 15 })
  );

  // Flower
  IMG.flower = SVG(600, 320,
    L(300, 200, 300, 300, '#4C9A2A', 8) +
    '<ellipse cx="300" cy="215" rx="70" ry="28" fill="#4C9A2A"/>' +
    [[-40, 0], [40, 0], [0, -30], [-25, -22], [25, -22]].map(function (p) { return '<ellipse cx="' + (300 + p[0]) + '" cy="' + (150 + p[1]) + '" rx="34" ry="52" fill="#F9A8D4" opacity=".95"/>'; }).join('') +
    '<ellipse cx="300" cy="195" rx="20" ry="16" fill="#8BC34A" stroke="#4C9A2A" stroke-width="3"/>' + [[292, 195], [300, 190], [308, 197]].map(function (p) { return C(p[0], p[1], 3, '#fff'); }).join('') +
    L(300, 185, 300, 120, '#8BC34A', 6) + '<ellipse cx="300" cy="112" rx="12" ry="9" fill="#8BC34A"/>' +
    [[-28, 20], [28, 20]].map(function (p) { return L(300, 185, 300 + p[0], 120 + p[1], '#E6C300', 4) + '<ellipse cx="' + (300 + p[0]) + '" cy="' + (114 + p[1]) + '" rx="12" ry="8" fill="#F5C518"/>'; }).join('') +
    L(300, 108, 390, 60, INK, 2) + TL(400, 58, ['STIGMA (female)', 'sticky, catches pollen'], { s: 14, a: 'start', lh: 17 }) +
    L(328, 134, 400, 118, INK, 2) + TL(408, 116, ['ANTHER (male)', 'makes POLLEN'], { s: 14, a: 'start', lh: 17 }) +
    L(320, 195, 400, 178, INK, 2) + TL(408, 176, ['OVARY (female)', 'has ovules -> seeds', 'ovary becomes the fruit'], { s: 14, a: 'start', lh: 17 }) +
    L(250, 150, 190, 90, INK, 2) + TL(190, 84, ['PETALS', 'bright + smell:', 'attract insects'], { s: 14, a: 'end', lh: 17 }) +
    L(240, 215, 190, 240, INK, 2) + TL(185, 238, ['SEPALS', 'protect the bud'], { s: 14, a: 'end', lh: 17 })
  );

  // Pollination
  IMG.pollination = SVG(600, 240,
    E(100, 120, '🌸', 70) + E(500, 120, '🌸', 70) + E(300, 100, '🐝', 46) +
    AR(150, 90, 262, 90, Y, 5) + AR(338, 90, 450, 90, Y, 5) +
    T(100, 170, 'Flower A: ANTHER', { s: 14, w: 700 }) + T(100, 190, 'pollen sticks to bee', { s: 13, f: SOFT }) +
    T(500, 170, 'Flower B: STIGMA', { s: 14, w: 700 }) + T(500, 190, 'pollen lands here', { s: 13, f: SOFT }) +
    T(300, 40, 'POLLINATION = pollen moves from anther to stigma', { s: 16, w: 700, f: B }) +
    T(300, 225, 'Then: male cell in pollen fuses with female cell in ovule = FERTILISATION -> seed', { s: 13, f: SOFT })
  );

  // Water states with arrows
  IMG.h2o = SVG(600, 290,
    bx(20, 100, 150, 80, B, 'ICE|solid 🧊', { ty: 34, s: 17 }) + bx(225, 100, 150, 80, B, 'WATER|liquid 💧', { ty: 34, s: 17 }) + bx(430, 100, 150, 80, B, 'WATER VAPOUR|gas 💨', { ty: 34, s: 15 }) +
    AR(170, 115, 225, 115, RED, 4) + TL(197, 58, ['MELTING', 'gains heat', 'at 0°C'], { s: 13, w: 700, f: RED, lh: 15 }) +
    AR(225, 165, 170, 165, BLUE, 4) + TL(197, 215, ['FREEZING', 'loses heat', 'at 0°C'], { s: 13, w: 700, f: BLUE, lh: 15 }) +
    AR(375, 115, 430, 115, RED, 4) + TL(402, 40, ['BOILING at 100°C', 'or EVAPORATION', 'at any temperature', 'gains heat'], { s: 13, w: 700, f: RED, lh: 15 }) +
    AR(430, 165, 375, 165, BLUE, 4) + TL(402, 215, ['CONDENSATION', 'loses heat'], { s: 13, w: 700, f: BLUE, lh: 15 }) +
    T(300, 275, 'Gain heat -> move right.  Lose heat -> move left.', { s: 15, f: SOFT })
  );

  // Water cycle
  IMG.watercycle = SVG(600, 300,
    E(60, 70, '☀️', 60) + R(0, 240, 600, 60, '#7CC6F6', { r: 0 }) + T(80, 275, 'sea / river', { s: 14, f: '#fff' }) +
    E(470, 70, '☁️', 70) + E(500, 75, '☁️', 60) +
    AR(230, 235, 320, 95, BLUE, 5) + TL(120, 150, ['1 EVAPORATION', 'water gains heat', '-> water vapour rises'], { s: 14, w: 700, f: BLUE, lh: 17 }) +
    TL(440, 128, ['2 CONDENSATION', 'vapour cools, loses heat', '-> tiny droplets = cloud'], { s: 14, w: 700, f: BLUE, lh: 17 }) +
    [430, 460, 490, 520].map(function (x) { return AR(x, 180, x - 10, 232, BLUE, 3); }).join('') + T(540, 210, '3 RAIN', { s: 14, w: 700, f: BLUE }) +
    AR(540, 262, 200, 262, '#fff', 4) + T(370, 285, '4 flows back to sea', { s: 13, w: 700, f: '#fff' }) +
    T(300, 30, 'The water cycle repeats forever', { s: 16, w: 700 })
  );

  // Plant parts
  IMG.plant = SVG(600, 300,
    R(0, 210, 600, 90, '#C4A26A', { r: 0 }) + L(200, 210, 200, 60, '#4C9A2A', 10) +
    '<ellipse cx="150" cy="120" rx="45" ry="20" fill="#5FBF4A" transform="rotate(-25 150 120)"/><ellipse cx="250" cy="150" rx="45" ry="20" fill="#5FBF4A" transform="rotate(25 250 150)"/>' +
    E(200, 60, '🌸', 40) +
    [[200, 210, 150, 280], [200, 210, 250, 280], [200, 210, 200, 290], [200, 210, 120, 250], [200, 210, 280, 250]].map(function (p) { return L(p[0], p[1], p[2], p[3], '#8B5A2B', 5); }).join('') +
    L(275, 138, 340, 100, INK, 2) + TL(345, 96, ['LEAF', 'makes food (sugar) using', 'light, water + carbon dioxide'], { s: 14, a: 'start', lh: 17 }) +
    L(205, 180, 340, 170, INK, 2) + TL(345, 166, ['STEM', 'holds up leaves + flowers', 'carries water up, food around'], { s: 14, a: 'start', lh: 17 }) +
    L(250, 260, 340, 245, INK, 2) + TL(345, 241, ['ROOT', 'holds plant firmly in soil', 'absorbs water + minerals'], { s: 14, a: 'start', lh: 17, f: '#fff' })
  );

  // Transport tubes
  IMG.tubes = SVG(600, 280,
    R(200, 20, 200, 240, '#DFF3D0', { st: '#4C9A2A', sw: 4, r: 10 }) +
    R(230, 30, 50, 220, '#BEE3FF', { r: 8 }) + AR(255, 240, 255, 45, BLUE, 6) +
    R(320, 30, 50, 220, '#FDEBD8', { r: 8 }) + AR(345, 45, 345, 240, O, 6) +
    TL(100, 60, ['WATER-carrying', 'tubes', 'water + minerals', 'ROOTS -> LEAVES', '(upwards)'], { s: 14, w: 700, f: BLUE, lh: 18 }) +
    TL(500, 60, ['FOOD-carrying', 'tubes', 'food (sugar)', 'LEAVES -> all parts', '(roots, fruits, flowers)'], { s: 14, w: 700, f: O, lh: 18 }) +
    T(300, 275, 'Inside the stem: two kinds of tubes', { s: 15, f: SOFT })
  );

  // Ring experiment
  IMG.ring = SVG(600, 280,
    E(300, 50, '🌿', 50) + L(300, 60, 300, 260, '#4C9A2A', 26) + R(287, 150, 26, 22, '#C4A26A', { r: 0 }) +
    '<ellipse cx="300" cy="138" rx="24" ry="12" fill="#4C9A2A"/>' +
    L(320, 135, 420, 110, INK, 2) + TL(425, 100, ['SWELLING above the ring', 'food from leaves cannot', 'go past the cut'], { s: 14, a: 'start', lh: 17, f: O }) +
    L(315, 160, 420, 175, INK, 2) + TL(425, 170, ['RING of food-carrying', 'tubes removed'], { s: 14, a: 'start', lh: 17 }) +
    L(300, 230, 420, 240, INK, 2) + TL(425, 236, ['Below: no food arrives', 'roots die after weeks'], { s: 14, a: 'start', lh: 17, f: RED }) +
    TL(120, 120, ['Water still goes UP', '(water tubes are', 'not cut) so leaves', 'stay fresh'], { s: 14, f: BLUE, w: 600, lh: 17 })
  );

  // Air composition
  IMG.air = SVG(600, 220,
    R(30, 60, 421, 60, B, { r: 0 }) + R(451, 60, 113, 60, G, { r: 0 }) + R(564, 60, 10, 60, GREY, { r: 0 }) +
    T(240, 98, 'Nitrogen  (most, about 78%)', { s: 17, w: 700, f: '#fff' }) + T(507, 98, 'Oxygen', { s: 15, w: 700, f: '#fff' }) + T(507, 140, 'about 21%', { s: 13, f: SOFT }) +
    L(569, 60, 569, 30, INK, 2) + T(500, 25, 'others: carbon dioxide, water vapour (about 1%)', { s: 13, f: SOFT }) +
    T(300, 190, 'Air is a MIXTURE of gases. We use the oxygen.', { s: 16, w: 700 })
  );

  // Circuit closed vs open
  function circuitPanel(x, closed) {
    var s = R(x, 40, 260, 170, '#fff', { st: O, sw: 3, r: 14 });
    var l = x + 40, r = x + 220, t = 70, b = 180;
    s += L(l, t, r, t, INK, 4) + L(l, t, l, b, INK, 4) + L(l, b, r, b, INK, 4) + L(r, t, r, 110, INK, 4) + L(r, 150, r, b, INK, 4);
    // battery on bottom
    s += R(x + 100, b - 16, 40, 32, '#fff', { r: 0 }) + batt(x + 116, b);
    // switch on right
    if (closed) s += L(r, 110, r, 150, INK, 4); else s += L(r, 110, r + 22, 140, INK, 4);
    s += C(r, 110, 4, INK) + C(r, 150, 4, INK);
    // bulb on top
    s += C(x + 130, t, 18, closed ? '#FFE55C' : '#fff', { st: INK, sw: 3 }) + L(x + 120, t - 9, x + 140, t + 9, INK, 3) + L(x + 140, t - 9, x + 120, t + 9, INK, 3);
    if (closed) s += [[-30, -22], [0, -32], [30, -22]].map(function (p) { return L(x + 130 + p[0] * .8, t + p[1] * .8, x + 130 + p[0], t + p[1], Y, 4); }).join('');
    return s;
  }
  IMG.circuit = SVG(600, 270,
    circuitPanel(20, true) + TL(150, 232, ['CLOSED circuit: complete loop', 'current flows, bulb lights'], { s: 13, w: 700, f: G, lh: 16 }) +
    circuitPanel(320, false) + TL(450, 232, ['OPEN circuit: there is a gap', 'no current, bulb is off'], { s: 13, w: 700, f: RED, lh: 16 }) +
    T(300, 24, 'Battery + wires + bulb + switch = electrical system', { s: 15, w: 700 })
  );

  // Series vs parallel
  IMG.seriespar = SVG(600, 312,
    R(10, 30, 280, 200, '#fff', { st: O, sw: 3, r: 14 }) + T(150, 22, 'SERIES: one path', { s: 16, w: 700, f: O }) +
    L(50, 70, 250, 70, INK, 4) + L(50, 70, 50, 190, INK, 4) + L(250, 70, 250, 190, INK, 4) + L(50, 190, 140, 190, INK, 4) + L(160, 190, 250, 190, INK, 4) + batt(140, 190) + bulb(110, 70, true) + bulb(190, 70, true) +
    TL(150, 245, ['more bulbs = each DIMMER', 'remove 1 bulb = ALL go off (open)'], { s: 13, lh: 17, f: SOFT, w: 700 }) +
    R(310, 30, 280, 200, '#fff', { st: O, sw: 3, r: 14 }) + T(450, 22, 'PARALLEL: own path each', { s: 16, w: 700, f: O }) +
    L(350, 60, 550, 60, INK, 4) + L(350, 60, 350, 190, INK, 4) + L(550, 60, 550, 190, INK, 4) + L(350, 190, 440, 190, INK, 4) + L(460, 190, 550, 190, INK, 4) + batt(440, 190) +
    L(400, 60, 400, 120, INK, 4) + L(500, 60, 500, 120, INK, 4) + L(400, 120, 500, 120, INK, 4) + bulb(400, 90, true) + bulb(500, 90, true) +
    TL(450, 245, ['each bulb as BRIGHT as alone', 'remove 1 bulb = other STAYS on'], { s: 13, lh: 17, f: SOFT, w: 700 }) +
    T(300, 300, 'More batteries in series = brighter bulbs', { s: 15, w: 700 })
  );

  // Circuit symbols
  IMG.symbols = SVG(600, 200,
    [[80, 'Battery'], [220, 'Bulb'], [360, 'Switch (open)'], [500, 'Switch (closed)']].map(function (z, i) {
      var x = z[0], s = R(x - 60, 30, 120, 100, '#fff', { st: O, sw: 3, r: 12 }) + T(x, 160, z[1], { s: 15, w: 700, f: O });
      if (i === 0) s += L(x - 40, 80, x - 6, 80, INK, 4) + batt(x, 80) + L(x + 20, 80, x + 40, 80, INK, 4);
      if (i === 1) s += L(x - 40, 80, x - 14, 80, INK, 4) + bulb(x, 80, false) + L(x + 14, 80, x + 40, 80, INK, 4);
      if (i === 2) s += L(x - 40, 80, x - 12, 80, INK, 4) + L(x - 12, 80, x + 12, 58, INK, 4) + C(x - 12, 80, 4, INK) + C(x + 12, 80, 4, INK) + L(x + 12, 80, x + 40, 80, INK, 4);
      if (i === 3) s += L(x - 40, 80, x + 40, 80, INK, 4) + C(x - 12, 80, 4, INK) + C(x + 12, 80, 4, INK);
      return s;
    }).join('') + T(300, 190, 'Lines = wires', { s: 13, f: SOFT })
  );

  // Magnet poles
  function mag(x, y, flip) { var a = flip ? ['S', 'N'] : ['N', 'S']; return R(x, y, 60, 30, a[0] === 'N' ? RED : BLUE, { r: 4 }) + R(x + 60, y, 60, 30, a[1] === 'N' ? RED : BLUE, { r: 4 }) + T(x + 30, y + 22, a[0], { s: 18, w: 700, f: '#fff' }) + T(x + 90, y + 22, a[1], { s: 18, w: 700, f: '#fff' }); }
  IMG.poles = SVG(600, 280,
    mag(60, 40, false) + mag(300, 40, false) + AR(190, 55, 230, 55, G, 5) + AR(290, 55, 250, 55, G, 5) + T(500, 62, 'unlike poles ATTRACT', { s: 15, w: 700, f: G }) +
    mag(60, 110, false) + mag(300, 110, true) + AR(230, 125, 190, 125, RED, 5) + AR(250, 125, 290, 125, RED, 5) + T(500, 132, 'like poles REPEL', { s: 15, w: 700, f: RED }) +
    mag(60, 180, true) + mag(300, 180, false) + AR(230, 195, 190, 195, RED, 5) + AR(250, 195, 290, 195, RED, 5) + T(500, 202, 'like poles REPEL', { s: 15, w: 700, f: RED }) +
    T(300, 255, 'Only REPEL proves it is a magnet. A hanging magnet rests N-S.', { s: 14, f: SOFT })
  );

  IMG.magnet = SVG(600, 220,
    mag(200, 60, false) + [[190, 110], [175, 125], [205, 128]].map(function (p) { return T(p[0], p[1], '📎', { s: 22 }); }).join('') + [[330, 110], [345, 125], [315, 128]].map(function (p) { return T(p[0], p[1], '📎', { s: 22 }); }).join('') +
    T(300, 170, 'Magnetic force is STRONGEST at the two poles', { s: 16, w: 700, f: P }) + T(300, 200, 'Magnets attract magnetic materials: iron and steel', { s: 14, f: SOFT })
  );

  // Making magnets
  IMG.makemag = SVG(600, 260,
    R(10, 30, 280, 200, '#fff', { st: P, sw: 3, r: 14 }) + T(150, 22, 'Stroke method', { s: 16, w: 700, f: P }) +
    R(60, 150, 180, 26, GREY, { r: 4 }) + T(150, 195, 'steel bar', { s: 13, f: SOFT }) + mag(90, 80, false) + AR(120, 120, 220, 145, INK, 4) +
    TL(150, 215, ['stroke one way, MANY times', 'lift and repeat, same pole'], { s: 12, lh: 15, f: SOFT }) +
    R(310, 30, 280, 200, '#fff', { st: P, sw: 3, r: 14 }) + T(450, 22, 'Electrical method', { s: 16, w: 700, f: P }) +
    R(400, 100, 120, 24, GREY, { r: 3 }) + '<path d="M405 96 q10 -18 20 0 q10 18 20 0 q10 -18 20 0 q10 18 20 0 q10 -18 20 0" fill="none" stroke="' + O + '" stroke-width="3"/>' +
    L(405, 110, 380, 110, O, 3) + L(380, 110, 380, 160, O, 3) + L(520, 112, 545, 112, O, 3) + L(545, 112, 545, 160, O, 3) + L(380, 160, 450, 160, O, 3) + L(470, 160, 545, 160, O, 3) + batt(450, 160) +
    T(460, 70, 'iron nail + coil of wire', { s: 12, f: SOFT }) +
    TL(450, 200, ['more coils / batteries = STRONGER', 'switch off = magnet stops'], { s: 12, lh: 15, f: SOFT })
  );

  // Gravity
  IMG.gravity = SVG(600, 260,
    C(300, 330, 160, '#5FBF4A') + C(300, 330, 160, 'none', { st: '#3B8FD9', sw: 8 }) +
    E(300, 90, '🍎', 46) + AR(300, 110, 300, 165, RED, 6) + T(360, 145, 'gravitational force', { s: 15, w: 700, f: RED, a: 'start' }) + T(360, 165, 'pulls towards Earth', { s: 13, f: SOFT, a: 'start' }) +
    TL(120, 60, ['WEIGHT = how hard', 'gravity pulls an object', 'more mass = more weight'], { s: 14, w: 600, lh: 18 }) +
    T(300, 240, 'Things fall DOWN because of gravity', { s: 16, w: 700, f: '#fff' })
  );

  // Friction
  IMG.friction = SVG(600, 260,
    R(0, 120, 600, 14, GREY, { r: 0 }) + R(230, 60, 90, 60, O, { r: 6 }) + T(275, 98, 'box', { s: 15, w: 700, f: '#fff' }) +
    AR(330, 90, 430, 90, G, 6) + T(380, 70, 'push (moving)', { s: 14, w: 700, f: G }) +
    AR(220, 110, 130, 110, RED, 6) + T(170, 145, 'FRICTION', { s: 14, w: 700, f: RED }) + T(170, 162, 'pushes the other way', { s: 12, f: SOFT }) +
    '<path d="M40 210 l10 -10 l10 10 l10 -10 l10 10 l10 -10 l10 10 l10 -10 l10 10 l10 -10 l10 10" fill="none" stroke="' + INK + '" stroke-width="3"/>' + T(100, 240, 'ROUGH = more friction', { s: 13, w: 700 }) +
    L(340, 210, 460, 210, INK, 3) + T(400, 240, 'SMOOTH = less friction', { s: 13, w: 700 }) +
    T(300, 30, 'Friction: between two touching surfaces, slows things down, makes HEAT', { s: 14, w: 700 })
  );

  // Spring
  function spring(x, y1, y2, col) { var n = 6, h = (y2 - y1) / n, d = 'M' + x + ' ' + y1; for (var i = 0; i < n; i++) d += ' l16 ' + (h / 2) + ' l-32 ' + (h / 2) + ' l16 0'; return '<path d="' + d + '" fill="none" stroke="' + (col || INK) + '" stroke-width="4"/>'; }
  IMG.spring = SVG(600, 270,
    R(40, 20, 520, 10, GREY, { r: 3 }) +
    spring(110, 30, 120) + T(110, 225, 'normal', { s: 15, w: 700 }) +
    spring(300, 30, 180) + R(280, 180, 40, 30, INK, { r: 4 }) + AR(345, 180, 345, 110, P, 5) + TL(300, 225, ['STRETCHED', 'spring pulls back up'], { s: 13, w: 700, f: P, lh: 16 }) +
    spring(490, 30, 90) + E(490, 128, '✋', 30) + AR(535, 55, 535, 105, P, 5) + TL(490, 225, ['SQUASHED', 'spring pushes back'], { s: 13, w: 700, f: P, lh: 16 }) +
    T(300, 262, 'More stretch or squash = bigger spring force. It returns to its shape.', { s: 13, f: SOFT })
  );

  // Force push pull
  IMG.force = SVG(600, 200,
    E(80, 110, '🧍', 60) + AR(120, 95, 200, 95, G, 6) + R(210, 70, 70, 50, O, { r: 6 }) + T(150, 150, 'PUSH', { s: 18, w: 700, f: G }) +
    E(520, 110, '🧍', 60) + L(330, 95, 480, 95, '#B08850', 5) + R(300, 70, 60, 50, O, { r: 6 }) + AR(400, 60, 470, 60, G, 6) + T(430, 150, 'PULL', { s: 18, w: 700, f: G }) +
    T(300, 40, 'A force is a push or a pull. You cannot see it - only what it does.', { s: 14, w: 700 })
  );

  // Food web
  IMG.foodweb = SVG(600, 320,
    AR(300, 262, 160, 205, P, 4) + AR(300, 262, 440, 205, P, 4) + AR(160, 175, 120, 118, P, 4) + AR(175, 175, 300, 118, P, 4) + AR(440, 175, 320, 118, P, 4) + AR(120, 88, 160, 40, P, 4) + AR(300, 88, 440, 40, P, 4) + AR(170, 34, 420, 34, P, 4) +
    [[300, 285, '🌿', 'plants'], [160, 200, '🦗', 'grasshopper'], [440, 200, '🐛', 'caterpillar'], [120, 110, '🐸', 'frog'], [300, 110, '🐦', 'bird'], [160, 45, '🐍', 'snake'], [440, 45, '🦅', 'hawk']].map(function (n) { return C(n[0], n[1] - 10, 30, '#fff', { st: P, sw: 3 }) + E(n[0], n[1], n[2], 30) + T(n[0], n[1] + 36, n[3], { s: 13, w: 700 }); }).join('') +
    TL(520, 120, ['A food web =', 'many food chains', 'joined together'], { s: 13, lh: 16, f: SOFT })
  );

  // Organism population community
  IMG.opc = SVG(600, 260,
    R(10, 10, 580, 240, '#DDF3FF', { st: B, sw: 3, r: 16 }) + T(300, 36, 'HABITAT: the pond (where they live)', { s: 15, w: 700, f: B }) +
    R(30, 50, 540, 185, '#EEE6FA', { st: P, sw: 3, r: 14 }) + T(300, 74, 'COMMUNITY: all the fish + all the frogs + all the water plants', { s: 14, w: 700, f: P }) +
    R(50, 88, 500, 130, '#E3F5E8', { st: G, sw: 3, r: 12 }) + T(300, 112, 'POPULATION: all the fish (same kind, same place)', { s: 14, w: 700, f: G }) +
    R(220, 126, 160, 78, '#fff', { st: O, sw: 3, r: 10 }) + T(300, 150, 'ORGANISM', { s: 14, w: 700, f: O }) + E(300, 190, '🐟', 30) +
    E(120, 180, '🐟🐟', 24) + E(480, 180, '🐟🐟', 24) + E(90, 228, '🐸', 22) + E(510, 228, '🪷', 22)
  );

  // Seeing
  IMG.see = SVG(600, 240,
    R(10, 30, 280, 180, '#fff', { st: Y, sw: 3, r: 14 }) + E(60, 130, '🔦', 44) + [[-20], [0], [20]].map(function (p) { return AR(90, 120 + p[0] * .3, 200, 120 + p[0], Y, 3); }).join('') + E(240, 130, '👁️', 40) +
    TL(150, 175, ['LIGHT SOURCE: gives out light', 'light goes straight to the eye'], { s: 12, lh: 15, w: 700 }) +
    R(310, 30, 280, 180, '#fff', { st: Y, sw: 3, r: 14 }) + E(350, 80, '🔦', 40) + AR(380, 80, 440, 130, Y, 3) + E(450, 150, '🍎', 40) + AR(465, 125, 530, 80, Y, 3) + E(550, 80, '👁️', 40) +
    TL(450, 175, ['OBJECT: light REFLECTS off it', 'into our eyes'], { s: 12, lh: 15, w: 700 }) +
    T(300, 230, 'No light = nothing can reflect = we see nothing', { s: 14, w: 700, f: SOFT })
  );

  // Shadow
  IMG.shadow = SVG(600, 240,
    E(60, 130, '🔦', 50) + [[-50], [-25], [0], [25], [50]].map(function (p) { var y = 120 + p[0]; return L(95, 120 + p[0] * .2, 500, y, Y, 3); }).join('') +
    R(280, 90, 20, 60, INK, { r: 3 }) + R(500, 40, 14, 170, GREY, { r: 2 }) + R(500, 87, 14, 66, INK, { r: 0 }) +
    R(300, 90, 200, 60, '#fff', { r: 0 }) + T(400, 125, 'no light here', { s: 13, f: SOFT }) +
    T(290, 80, 'object', { s: 13, w: 700 }) + T(540, 35, 'screen', { s: 13, w: 700 }) + T(560, 125, 'SHADOW', { s: 12, w: 700, f: INK }) +
    T(300, 225, 'Light travels in STRAIGHT lines. Blocked light = shadow.', { s: 15, w: 700 })
  );

  IMG.shadowsize = SVG(600, 260,
    E(50, 70, '🔦', 40) + L(80, 62, 500, 15, Y, 3) + L(80, 78, 500, 125, Y, 3) + R(130, 45, 12, 50, INK, { r: 2 }) + R(500, 5, 10, 130, GREY, { r: 2 }) + R(500, 15, 10, 110, INK, { r: 0 }) +
    T(320, 80, 'object NEAR the light = BIG shadow', { s: 14, w: 700, f: RED }) +
    E(50, 200, '🔦', 40) + L(80, 192, 500, 175, Y, 3) + L(80, 208, 500, 225, Y, 3) + R(440, 175, 12, 50, INK, { r: 2 }) + R(500, 140, 10, 110, GREY, { r: 2 }) + R(500, 175, 10, 50, INK, { r: 0 }) +
    T(280, 205, 'object NEAR the screen = SMALL shadow', { s: 14, w: 700, f: G })
  );

  // Heat / temperature
  IMG.heat = SVG(600, 240,
    R(280, 30, 40, 150, '#fff', { st: INK, sw: 3, r: 20 }) + C(300, 190, 26, RED) + R(292, 90, 16, 100, RED, { r: 6 }) +
    AR(340, 150, 340, 60, RED, 5) + TL(360, 80, ['GAINS heat', '-> temperature goes UP'], { s: 14, w: 700, f: RED, a: 'start', lh: 18 }) +
    AR(260, 60, 260, 150, BLUE, 5) + TL(240, 80, ['LOSES heat', '-> temperature goes DOWN'], { s: 14, w: 700, f: BLUE, a: 'end', lh: 18 }) +
    TL(300, 225, ['HEAT = a form of energy.  TEMPERATURE = how hot, measured in °C with a thermometer.'], { s: 13, w: 600 })
  );

  IMG.heatflow = SVG(600, 220,
    E(110, 120, '☕', 70) + T(110, 175, 'HOT (80°C)', { s: 15, w: 700, f: RED }) + [[-20], [0], [20]].map(function (p) { return AR(180, 100 + p[0], 380, 100 + p[0], RED, 5); }).join('') + T(280, 70, 'HEAT flows', { s: 16, w: 700, f: RED }) +
    E(460, 120, '✋', 70) + T(460, 175, 'COLD (30°C)', { s: 15, w: 700, f: BLUE }) +
    T(300, 205, 'from HOTTER to COLDER, until both are the SAME temperature', { s: 14, w: 700 })
  );

  IMG.expand = SVG(600, 230,
    R(100, 40, 200, 26, GREY, { r: 4 }) + T(200, 85, 'cold metal bar', { s: 14 }) +
    R(100, 120, 260, 26, RED, { r: 4 }) + AR(360, 133, 420, 133, RED, 5) + AR(100, 133, 40, 133, RED, 5) + T(230, 168, 'heated: gains heat -> EXPANDS (gets bigger)', { s: 14, w: 700, f: RED }) +
    TL(480, 55, ['Lose heat', '-> CONTRACTS', '(gets smaller)'], { s: 14, w: 700, f: BLUE, lh: 18 }) +
    T(300, 210, 'Solids, liquids AND gases expand when heated. Gaps in rails and bridges!', { s: 13, f: SOFT })
  );

  IMG.conductheat = SVG(600, 230,
    '<path d="M120 120 L140 200 L460 200 L480 120 Z" fill="#B0B8C8" stroke="' + INK + '" stroke-width="3"/>' + R(130, 125, 340, 20, '#F5A15A', { r: 0 }) +
    L(200, 60, 240, 150, '#C0C8D6', 10) + C(200, 55, 10, RED) + T(200, 30, 'metal spoon: handle gets HOT', { s: 13, w: 700, f: RED }) +
    L(400, 60, 360, 150, '#B08850', 10) + C(400, 55, 10, G) + T(400, 30, 'wooden spoon: handle stays COOL', { s: 13, w: 700, f: G }) +
    TL(300, 218, ['Metal = good conductor (heat passes fast).  Wood, plastic, air = poor conductors (slow).'], { s: 12, w: 600 })
  );

  // Photosynthesis leaf
  IMG.photo = SVG(600, 280,
    '<path d="M300 60 C 420 60 470 160 300 240 C 130 160 180 60 300 60 Z" fill="#5FBF4A" stroke="#3B8F2E" stroke-width="4"/>' + L(300, 70, 300, 232, '#3B8F2E', 3) +
    E(70, 60, '☀️', 44) + AR(105, 70, 200, 110, Y, 5) + T(120, 105, 'light energy', { s: 13, w: 700, f: Y }) +
    E(80, 220, '💨', 36) + AR(110, 210, 200, 180, B, 5) + T(120, 250, 'carbon dioxide (air)', { s: 13, w: 700, f: B }) +
    AR(300, 275, 300, 245, B, 5) + T(370, 268, 'water (from roots)', { s: 13, w: 700, f: B, a: 'start' }) +
    AR(400, 110, 495, 75, G, 5) + E(540, 75, '🫧', 36) + T(480, 45, 'OXYGEN out', { s: 13, w: 700, f: G }) +
    AR(400, 180, 500, 210, O, 5) + E(530, 220, '🍬', 36) + T(480, 250, 'SUGAR (food) made', { s: 13, w: 700, f: O }) +
    T(300, 30, 'PHOTOSYNTHESIS in the green leaf', { s: 16, w: 700, f: G })
  );

  // Kinetic / potential slide
  IMG.kepe = SVG(600, 260,
    '<path d="M60 60 C 250 60 300 220 540 220" fill="none" stroke="' + GREY + '" stroke-width="10"/>' +
    E(70, 48, '⚽', 30) + TL(120, 45, ['TOP: most POTENTIAL', 'energy (stored, high up)'], { s: 13, w: 700, lh: 16, f: P, a: 'start' }) +
    E(300, 140, '⚽', 30) + TL(330, 120, ['MIDDLE: potential', 'changing to kinetic'], { s: 13, w: 700, lh: 16, f: SOFT, a: 'start' }) +
    E(530, 205, '⚽', 30) + TL(480, 250, ['BOTTOM: most KINETIC energy (fastest)'], { s: 13, w: 700, f: G }) +
    T(200, 240, 'Throw a ball up: kinetic -> potential -> kinetic again', { s: 12, f: SOFT })
  );
})();

// ---------- Content: blocks 1-6 ----------
var BLOCKS = [];

BLOCKS.push({
  id: 'b1', theme: 'div', name: 'Living things', icon: '🐸', lvl: 'P3',
  learn: [
    { h: 'What makes something living?', t: 'Living things **need air, water and food**.\nThey **grow**, **respond** to changes around them, and **reproduce** (make young).\nA non-living thing does NOT do all of these. A robot moves, but it cannot grow or reproduce.', img: 'living' },
    { h: 'The 4 big groups', t: 'All living things are sorted into **plants, animals, fungi and bacteria**.\nPlants: **flowering** (make flowers, fruits, seeds) or **non-flowering** (ferns, mosses: no flowers, they use spores).', img: 'groups' },
    { h: 'The 6 animal groups', t: 'Look at the **outer covering** and the **body parts**:\n- **Birds** have feathers. **Mammals** have fur or hair. **Reptiles** have dry scales.\n- **Fish** have fins and gills. **Amphibians** (frogs) have moist skin, live in water and on land.\n- **Insects** have 6 legs and 3 body parts.', img: 'animals6' },
    { h: 'Fungi and bacteria are alive too', t: '**Fungi**: mould, mushroom, yeast. They cannot make their own food. They feed on other things (like old bread).\n**Bacteria**: so tiny you need a **microscope**. Some are useful (yoghurt), some make us sick.\nBoth **grow and reproduce**, so they are living.', img: 'fungi' },
    { h: 'How to classify', t: 'To **classify** = sort into groups using **similarities and differences you can observe**.\nGood sorting questions: Does it have feathers? Fur? Scales? Six legs? Does it make flowers?\nBad sorting questions: Is it cute? Is it big? (not a fixed characteristic)', img: 'classify' }
  ],
  facts: [
    ['Living things need... (3 things)', 'Air, water and food'],
    ['Living things can... (3 things)', 'Grow, respond and reproduce'],
    ['The 4 big groups of living things', 'Plants, animals, fungi, bacteria'],
    ['The 6 animal groups', 'Amphibians, birds, fish, insects, mammals, reptiles'],
    ['3 examples of fungi', 'Mould, mushroom, yeast']
  ],
  mcq: [
    { lv: 1, q: 'Which of the following is true of ALL living things?', o: ['They can move from place to place.', 'They can grow and reproduce.', 'They need sunlight to make food.', 'They have legs.'], a: 1, hint: 'Think about a plant. It cannot walk, but it is alive.', why: 'All living things grow, respond and reproduce, and need air, water and food. Plants do not walk, and animals do not make food from sunlight.', img: 'living' },
    { lv: 1, q: 'Mould, mushroom and yeast belong to which group of living things?', o: ['Plants', 'Animals', 'Fungi', 'Bacteria'], a: 2, hint: 'They cannot make their own food and they are not animals.', why: 'Mould, mushroom and yeast are fungi. Fungi cannot make their own food; they feed on other things.', img: 'fungi' },
    { lv: 1, q: 'A toy robot can move, flash lights and make sounds. Why is it NOT a living thing?', o: ['It is made of plastic.', 'It needs batteries.', 'It cannot grow or reproduce.', 'It cannot see.'], a: 2, hint: 'Which of the 6 things that living things do can a robot never do?', why: 'Moving is not enough. A living thing must grow, respond and reproduce, and need air, water and food. A robot cannot grow or reproduce.', img: 'living' },
    { lv: 1, q: 'Animal X has six legs and three body parts. Which group does it belong to?', o: ['Reptiles', 'Insects', 'Amphibians', 'Mammals'], a: 1, hint: 'Count the legs.', why: 'Insects have 6 legs and 3 body parts (head, thorax, abdomen).', img: 'animals6' },
    { lv: 2, q: 'Which pair shows two non-flowering plants?', o: ['Rose and hibiscus', 'Fern and moss', 'Mango tree and fern', 'Sunflower and orchid'], a: 1, hint: 'Non-flowering plants never make flowers. They reproduce with spores.', why: 'Ferns and mosses are non-flowering plants. Rose, hibiscus, mango, sunflower and orchid all make flowers.', img: 'groups' },
    { lv: 2, q: 'Ali sorted animals into two groups.<table class="q"><tr><th>Group P</th><th>Group Q</th></tr><tr><td>crow, sparrow, eagle</td><td>bat, dog, whale</td></tr></table>Which characteristic did Ali most likely use?', o: ['Whether the animal can fly', 'Whether the animal has feathers', 'Whether the animal lives in water', 'Whether the animal is big'], a: 1, hint: 'A bat can fly but it is in Group Q with the dog.', why: 'Group P are all birds (have feathers). Group Q are all mammals (fur or hair, feed young with milk). A bat can fly, so "can fly" cannot be the rule.', img: 'classify' },
    { lv: 2, q: 'Which characteristic is the BEST for classifying animals into groups?', o: ['The colour of the animal', 'How fast the animal runs', 'The outer covering of the animal', 'The name of the animal'], a: 2, hint: 'Feathers, fur, scales...', why: 'Outer covering (feathers, fur, dry scales, moist skin) is a fixed characteristic we can observe. Colour and speed can be different even within one group.', img: 'animals6' },
    { lv: 2, q: 'Bacteria are living things. Which statement supports this?', o: ['Bacteria can be seen without a microscope.', 'Bacteria have legs.', 'Bacteria can reproduce.', 'Bacteria need sunlight to make food.'], a: 2, hint: 'Living things make more of their own kind.', why: 'Bacteria reproduce (and grow, respond and need food, water and air). They are too small to see without a microscope, and they have no legs.', img: 'fungi' }
  ],
  oe: [
    { q: 'A car can move and it uses petrol. Give two reasons why a car is NOT a living thing.', m: 2, img: 'living', ans: ['A car cannot grow.', 'A car cannot reproduce (make young cars).'], decoy: ['A car is living because it needs petrol like food.', 'A car is made of metal.'], kw: ['grow', 'reproduce|young'] },
    { q: 'A mushroom does not move and cannot make its own food. (a) Which group of living things does it belong to? (b) Give one reason why it is a living thing.', m: 2, img: 'fungi', ans: ['(a) It is a fungus.', '(b) It can grow and reproduce (by spores).'], decoy: ['(a) It is a plant because it grows in soil.', '(b) It is non-living because it cannot move.'], kw: ['fung', 'grow|reproduce'] },
    { q: 'Mei put a crow and a sparrow in Group A, and a bat and a dog in Group B. A bat can fly. Explain why the bat is still in Group B.', m: 3, img: 'classify', ans: ['Mei sorted the animals by whether they have feathers (birds) or fur (mammals), not by whether they can fly.', 'A bat has fur and feeds its young with milk.', 'So the bat is a mammal, not a bird, even though it can fly.'], decoy: ['A bat is a bird because it can fly.', 'Mei sorted the animals by size.'], kw: ['feather', 'fur|hair|milk', 'mammal'] }
  ]
});

BLOCKS.push({
  id: 'b2', theme: 'div', name: 'Materials', icon: '🧱', lvl: 'P3',
  learn: [
    { h: 'Object vs material', t: 'A cup is an **object**. It can be made of plastic, glass, ceramic or metal. Those are **materials**.\nWe choose a material because of its **properties** (what it is like).', img: 'materials' },
    { h: 'The 5 properties', t: '- **Strength**: holds a heavy load without breaking.\n- **Flexibility**: bends without breaking.\n- **Floats or sinks** in water.\n- **Waterproof**: does NOT absorb water.\n- **Transparency**: lets **most, some or no light** pass through.', img: 'props' },
    { h: 'Match the property to the use', t: 'Raincoat: **waterproof**. Window: **lets most light through**. Bridge cable: **strong**.\nRubber glove: **flexible** and waterproof. Life float: **floats**.\nExam trick: ask "What must this object DO?" Then name the property.', img: 'uses' },
    { h: 'Testing materials fairly', t: 'To compare materials, keep everything the **same** (size, load, time) and change **only the material**.\nThat is a **fair test**. Then the result is caused by the material only.', img: 'fairtest' }
  ],
  facts: [
    ['Strength means...', 'Can hold a heavy load without breaking'],
    ['Flexibility means...', 'Can bend without breaking'],
    ['Waterproof means...', 'Does not absorb water'],
    ['Transparency means...', 'How much light passes through: most, some or none'],
    ['In a fair test, what do you change?', 'Only ONE thing (the material). Keep everything else the same']
  ],
  mcq: [
    { lv: 1, q: 'Which property makes plastic a good material for a raincoat?', o: ['It is strong.', 'It is waterproof.', 'It floats on water.', 'It lets most light through.'], a: 1, hint: 'What must a raincoat do to rain?', why: 'A raincoat must not absorb water. Plastic is waterproof, so the rain runs off and you stay dry.', img: 'uses' },
    { lv: 1, q: 'Which material lets MOST light pass through?', o: ['Wood', 'Metal', 'Clear glass', 'Ceramic'], a: 2, hint: 'Which one is used for windows?', why: 'Clear glass lets most light pass through, so we can see through it. Wood, metal and ceramic let no light through.', img: 'props' },
    { lv: 1, q: 'A plastic ruler can be bent without breaking. Which property is this?', o: ['Strength', 'Flexibility', 'Transparency', 'Waterproof'], a: 1, hint: 'Bend without breaking = ?', why: 'Flexibility is the ability to bend without breaking.', img: 'props' },
    { lv: 1, q: 'Which pair of properties is MOST important for a material used to make a swimming float?', o: ['Floats and waterproof', 'Strong and lets most light through', 'Flexible and sinks', 'Absorbs water and floats'], a: 0, hint: 'It must stay on top of the water and not get heavy with water.', why: 'A float must float on water and must be waterproof so it does not soak up water and sink.', img: 'uses' },
    { lv: 2, q: 'Four strips of the same size were hung with masses until they broke.<table class="q"><tr><th>Material</th><th>Mass when it broke</th></tr><tr><td>A</td><td>200 g</td></tr><tr><td>B</td><td>1500 g</td></tr><tr><td>C</td><td>800 g</td></tr><tr><td>D</td><td>50 g</td></tr></table>Which material is the strongest?', o: ['A', 'B', 'C', 'D'], a: 1, hint: 'Strongest = holds the MOST before breaking.', why: 'Material B held 1500 g before it broke, the largest mass. So B is the strongest.', img: 'fairtest' },
    { lv: 2, q: 'Mei drops water on four materials.<table class="q"><tr><th>Material</th><th>Absorbs water?</th><th>Floats?</th></tr><tr><td>P</td><td>Yes</td><td>Yes</td></tr><tr><td>Q</td><td>No</td><td>Yes</td></tr><tr><td>R</td><td>No</td><td>No</td></tr><tr><td>S</td><td>Yes</td><td>No</td></tr></table>Which material is best for making a small toy boat?', o: ['P', 'Q', 'R', 'S'], a: 1, hint: 'A boat must float and must not soak up water.', why: 'Q does not absorb water (waterproof) and it floats. P floats but absorbs water, so it would become heavy and sink.', img: 'props' },
    { lv: 2, q: 'Ali wants to find out which of three cloths is the most waterproof. Which of these must be the SAME for all three cloths?', o: ['The type of cloth', 'The amount of water poured', 'The colour of the cloth', 'The name of the shop'], a: 1, hint: 'Change only the material. Everything else must be the same.', why: 'For a fair test, the amount of water (and the size of cloth and time) must be the same. Only the type of cloth is changed.', img: 'fairtest' },
    { lv: 2, q: 'Which property must the material for a thick bedroom curtain have, so that the room is dark in the morning?', o: ['It lets most light pass through.', 'It lets no light pass through.', 'It floats on water.', 'It is strong.'], a: 1, hint: 'A dark room means the light is blocked.', why: 'To keep the room dark, the curtain material must let no light pass through.', img: 'props' }
  ],
  oe: [
    { q: 'Explain why glass is used for windows but NOT for the head of a hammer.', m: 2, img: 'props', ans: ['Glass lets most light pass through, so we can see through the window.', 'Glass is not strong and breaks easily when hit, so it cannot be used as a hammer head.'], decoy: ['Glass is flexible, so it bends when hit.', 'Glass floats on water.'], kw: ['light', 'break|strong'] },
    { q: 'Three threads of the same size were tested. Cotton broke at 500 g, wool broke at 800 g, nylon broke at 2000 g. Which thread is the best for a fishing line? Explain.', m: 2, img: 'fairtest', ans: ['Nylon.', 'It held the largest mass before breaking, so it is the strongest.'], decoy: ['Wool, because it is soft.', 'Cotton, because it broke first.'], kw: ['nylon', 'strong|largest|most'] },
    { q: 'Mei wants to find out which of three cloths (P, Q, R) absorbs the most water. Describe how she can carry out a fair test.', m: 2, img: 'fairtest', ans: ['Use the same size of each cloth and pour the same amount of water on each.', 'Wait the same time, then measure how much water each cloth absorbed (for example by weighing it).'], decoy: ['Use a bigger piece for the thickest cloth.', 'Pour more water on cloth R because it looks dry.'], kw: ['same', 'measure|weigh|amount'] }
  ]
});

BLOCKS.push({
  id: 'b3', theme: 'cyc', name: 'Life cycles', icon: '🦋', lvl: 'P3',
  learn: [
    { h: 'Plant life cycle', t: '**Seed** grows into a **young plant** (seedling), which grows into an **adult plant**.\nThe adult makes flowers and new seeds. The cycle repeats.', img: 'plantcycle' },
    { h: '3-stage animals', t: '**Egg, young, adult**. The young looks like a **small adult**.\nExamples: **chicken, grasshopper, cockroach**.', img: 'cycle3' },
    { h: '4-stage animals', t: '**Egg, larva, pupa, adult**. The larva looks **very different** from the adult. The pupa does not eat; it changes into the adult inside.\nExamples: **butterfly** (caterpillar = larva), **beetle** (grub = larva), **mosquito** (wriggler = larva, tumbler = pupa).', img: 'cycle4' },
    { h: 'The frog is special', t: '**Egg, tadpole, adult frog**: 3 stages, but the tadpole does NOT look like the adult.\nTadpole: lives in **water**, breathes with gills, has a tail. Adult: lives on land and in water.', img: 'frogcycle' },
    { h: 'Why life cycles matter', t: 'Mosquito **eggs, larvae and pupae live in water**.\nRemove stagnant water = no place for eggs = fewer mosquitoes = less dengue.\nKnowing the cycle lets us **predict** and **control** it.', img: 'mosquito' }
  ],
  facts: [
    ['Plant life cycle stages', 'Seed, young plant, adult plant'],
    ['3-stage life cycle (name the stages)', 'Egg, young, adult'],
    ['4-stage life cycle (name the stages)', 'Egg, larva, pupa, adult'],
    ['Which animals have 4 stages?', 'Butterfly, beetle, mosquito'],
    ['A frog: 3 stages, name them', 'Egg, tadpole, adult']
  ],
  mcq: [
    { lv: 1, q: 'Which animal has a 4-stage life cycle?', o: ['Chicken', 'Grasshopper', 'Butterfly', 'Cockroach'], a: 2, hint: 'Which one has a caterpillar stage?', why: 'A butterfly has 4 stages: egg, larva (caterpillar), pupa, adult. Chicken, grasshopper and cockroach have 3 stages.', img: 'cycle4' },
    { lv: 1, q: 'Which is the correct order of the life cycle of a butterfly?', o: ['egg, pupa, larva, adult', 'egg, larva, pupa, adult', 'larva, egg, pupa, adult', 'egg, young, adult'], a: 1, hint: 'The caterpillar (larva) comes before the pupa.', why: 'Egg hatches into a larva (caterpillar), which becomes a pupa, which becomes the adult butterfly.', img: 'cycle4' },
    { lv: 1, q: 'Which stages of a mosquito live in water?', o: ['Adult only', 'Egg, larva and pupa', 'Larva only', 'All four stages'], a: 1, hint: 'Only the adult flies away.', why: 'Mosquito eggs are laid on water, and the larva and pupa live in the water. The adult flies.', img: 'mosquito' },
    { lv: 1, q: 'In which stage does the animal NOT eat and change into the adult?', o: ['Egg', 'Larva', 'Pupa', 'Adult'], a: 2, hint: 'The stage just before adult.', why: 'The pupa does not eat. Inside, the animal changes into the adult.', img: 'cycle4' },
    { lv: 2, q: 'The young of a grasshopper looks like the adult but has no wings. Which other animal has young that look like the adult?', o: ['Cockroach', 'Beetle', 'Frog', 'Mosquito'], a: 0, hint: '3-stage animals have young that look like small adults.', why: 'A cockroach has a 3-stage life cycle (egg, young, adult); the young looks like a small adult. Beetle and mosquito have a larva that looks different. A tadpole does not look like a frog.', img: 'cycle3' },
    { lv: 2, q: 'A caterpillar belongs to which stage of the butterfly life cycle?', o: ['Egg', 'Larva', 'Pupa', 'Adult'], a: 1, hint: 'The hungry eating stage.', why: 'The caterpillar is the larva. It eats a lot and grows.', img: 'cycle4' },
    { lv: 2, q: 'Animal Z has 3 stages. Its young lives in water and breathes with gills. The adult lives on land and in water. What is animal Z?', o: ['Chicken', 'Grasshopper', 'Frog', 'Butterfly'], a: 2, hint: 'Gills in water, then land...', why: 'A frog: egg, tadpole (water, gills), adult frog (land and water).', img: 'frogcycle' },
    { lv: 2, q: 'Seed &rarr; ? &rarr; adult plant &rarr; seed. What is the missing stage?', o: ['Flower', 'Young plant', 'Fruit', 'Root'], a: 1, hint: 'A small plant that just grew from the seed.', why: 'The plant life cycle is seed, young plant (seedling), adult plant. The adult then makes seeds again.', img: 'plantcycle' }
  ],
  oe: [
    { q: 'Explain why removing stagnant water around our homes helps to reduce the number of mosquitoes.', m: 2, img: 'mosquito', ans: ['Mosquito eggs, larvae and pupae need water to live and develop.', 'Without stagnant water, they cannot develop into adults, so there are fewer mosquitoes.'], decoy: ['Adult mosquitoes drink the stagnant water.', 'Mosquitoes lay their eggs on dry leaves.'], kw: ['egg|larva|pupa', 'water'] },
    { q: 'Compare the life cycles of a grasshopper and a beetle. Give one similarity and one difference.', m: 2, img: 'cycle4', ans: ['Similarity: both start from an egg.', 'Difference: a grasshopper has 3 stages and its young looks like the adult, but a beetle has 4 stages with a larva and a pupa.'], decoy: ['Both have a pupa stage.', 'A grasshopper starts as a larva.'], kw: ['egg', '3|three|4|four|pupa'] },
    { q: 'A farmer found many young grasshoppers eating his crops. Why is it important to get rid of them while they are still young?', m: 2, img: 'cycle3', ans: ['The young will grow into adults.', 'The adults will lay many eggs, so the number of grasshoppers eating the crops will increase quickly.'], decoy: ['The young will turn into pupae and stop eating.', 'Young grasshoppers do not eat crops.'], kw: ['adult', 'egg|reproduce|more|increase'] }
  ]
});

BLOCKS.push({
  id: 'b4', theme: 'cyc', name: 'Matter', icon: '🧊', lvl: 'P4',
  learn: [
    { h: 'What is matter?', t: '**Matter** is anything that has **mass** and **takes up space** (occupies space).\nStone, water and air are all matter. Yes, **air is matter**.\nLight, heat and sound are NOT matter: no mass, no space.', img: 'matter' },
    { h: 'The 3 states', t: '- **Solid**: fixed shape, fixed volume.\n- **Liquid**: NO fixed shape (takes the shape of the container), fixed volume.\n- **Gas**: NO fixed shape, NO fixed volume (spreads to fill the whole container).', img: 'states' },
    { h: 'Measuring matter', t: '**Mass**: use a beam balance or weighing scale. Units: **g, kg**.\n**Volume** of a liquid: use a measuring cylinder. Units: **ml, l**.\nVolume of a gas: a syringe (a gas fills the space it is in).', img: 'measure' },
    { h: 'Proof that air is matter', t: 'A balloon full of air is **heavier** than an empty one: air has **mass**.\nPush an upside-down glass into water: the paper inside stays dry because the air **takes up space** so water cannot enter.', img: 'airmatter' }
  ],
  facts: [
    ['Matter is anything that...', 'Has mass and takes up space'],
    ['Solid: shape and volume?', 'Fixed shape, fixed volume'],
    ['Liquid: shape and volume?', 'No fixed shape, fixed volume'],
    ['Gas: shape and volume?', 'No fixed shape, no fixed volume'],
    ['Is air matter?', 'Yes: it has mass and takes up space']
  ],
  mcq: [
    { lv: 1, q: 'Which of the following is NOT matter?', o: ['Air', 'Water', 'Light', 'Sand'], a: 2, hint: 'Which one has no mass and takes up no space?', why: 'Light has no mass and does not take up space, so it is not matter. Air, water and sand all have mass and take up space.', img: 'matter' },
    { lv: 1, q: 'Which state of matter has NO fixed shape but has a fixed volume?', o: ['Solid', 'Liquid', 'Gas', 'All of them'], a: 1, hint: 'It takes the shape of its container, but the amount stays the same.', why: 'A liquid takes the shape of its container (no fixed shape) but its volume stays the same.', img: 'states' },
    { lv: 1, q: 'Which state of matter has NO fixed shape AND NO fixed volume?', o: ['Solid', 'Liquid', 'Gas', 'None of them'], a: 2, hint: 'It spreads out to fill any container.', why: 'A gas spreads to fill the whole container, so it has no fixed shape and no fixed volume.', img: 'states' },
    { lv: 1, q: 'Which instrument is used to measure the volume of a liquid?', o: ['Beam balance', 'Thermometer', 'Measuring cylinder', 'Ruler'], a: 2, hint: 'It has a scale in ml.', why: 'A measuring cylinder measures the volume of a liquid in ml. A beam balance measures mass.', img: 'measure' },
    { lv: 2, q: 'Water is poured from a tall glass into a wide bowl. What happens to the water?', o: ['Its shape and volume both change.', 'Its shape changes but its volume stays the same.', 'Its volume changes but its shape stays the same.', 'Nothing changes.'], a: 1, hint: 'A liquid has a fixed volume.', why: 'A liquid has no fixed shape, so it takes the shape of the bowl. But it has a fixed volume, so the amount of water stays the same.', img: 'states' },
    { lv: 2, q: 'A stone is put into a measuring cylinder with water. The water level rises from 50 ml to 62 ml. What does this show?', o: ['The stone has no mass.', 'The stone takes up space.', 'The stone floats.', 'The water has no volume.'], a: 1, hint: 'The water was pushed up. Why?', why: 'The stone occupies space, so it pushes the water up by 12 ml. This shows the stone takes up space (its volume is 12 ml).', img: 'measure' },
    { lv: 2, q: 'A basketball was weighed. Then more air was pumped in and it was weighed again. Its mass increased by 5 g. What does this show about air?', o: ['Air has mass.', 'Air has a fixed shape.', 'Air is a liquid.', 'Air has no volume.'], a: 0, hint: 'The only thing added was air.', why: 'Only air was added, and the mass went up. So air has mass, which means air is matter.', img: 'airmatter' },
    { lv: 2, q: 'Which observation shows that a gas has NO fixed volume?', o: ['A gas can be seen.', 'A gas from a small balloon spreads to fill a large empty bottle.', 'A gas has a smell.', 'A gas is lighter than water.'], a: 1, hint: 'No fixed volume = it can spread out or be squeezed.', why: 'A gas spreads out to fill whatever container it is in, so its volume is not fixed.', img: 'states' }
  ],
  oe: [
    { q: 'Balloon A is empty. Balloon B is filled with air. Balloon B is heavier than Balloon A. What does this show about air?', m: 2, img: 'airmatter', ans: ['Balloon B is heavier because the air inside it has mass.', 'This shows that air is matter.'], decoy: ['The balloon stretched, so it became heavier.', 'Air is not matter because we cannot see it.'], kw: ['mass', 'matter'] },
    { q: 'An upside-down glass with a dry ball of paper inside is pushed straight down into a basin of water. The paper stays dry. Explain why.', m: 2, img: 'airmatter', ans: ['The air trapped inside the glass takes up space.', 'So the water cannot enter the glass and the paper stays dry.'], decoy: ['The glass is waterproof, so water cannot enter.', 'The paper pushes the water away.'], kw: ['air', 'space|enter'] },
    { q: 'Explain why water can be poured from one container to another but a block of ice cannot.', m: 2, img: 'states', ans: ['Water is a liquid. It has no fixed shape, so it flows and can be poured.', 'Ice is a solid. It has a fixed shape, so it cannot flow.'], decoy: ['Ice has no fixed volume.', 'Water is a gas, so it can be poured.'], kw: ['liquid|no fixed shape|flow', 'solid|fixed shape'] }
  ]
});

BLOCKS.push({
  id: 'b5', theme: 'cyc', name: 'Reproduction', icon: '🌸', lvl: 'P5',
  learn: [
    { h: 'Why reproduce?', t: 'Living things **reproduce** to make more of their **own kind** (continuity).\nYoung get **characteristics** from their parents, so they look like them.\nA **cell** is the basic unit of life. Every living thing is made of cells.', img: 'reproduce' },
    { h: 'Parts of a flower', t: '- **Anther** (male): makes **pollen**.\n- **Stigma** (female): sticky, catches pollen.\n- **Ovary** (female): has **ovules**. Ovules become **seeds**; the ovary becomes the **fruit**.\n- **Petals**: bright colour and smell attract insects. **Sepals** protect the bud.', img: 'flower' },
    { h: 'Step 1 and 2: pollination, fertilisation', t: '**Pollination**: pollen moves from the **anther to the stigma** (carried by insects or wind).\n**Fertilisation**: the **male cell** from the pollen **fuses with the female cell** in the ovule. A **seed** forms.', img: 'pollination' },
    { h: 'Step 3: seed dispersal', t: 'Seeds are carried away by **wind** (light, wings, hairs), **water** (floats, fibrous husk), **animals** (juicy fruit eaten, hooks stick to fur) or **splitting** (pod bursts).\nWhy? To **avoid overcrowding**, so young plants do not **compete** for light, water and space.', img: 'dispersal' },
    { h: 'Step 4: germination', t: 'A seed **germinates** (starts to grow) when it has **water, air and warmth**.\nIt does NOT need light or soil to germinate. The root grows first, then the shoot.', img: 'germinate' },
    { h: 'No flowers? Use spores', t: 'Ferns and mushrooms reproduce by **spores**: tiny, made under the leaf or cap, carried by wind.', img: 'spores' },
    { h: 'Humans', t: '**Testes** make **sperm** (male cell). **Ovaries** make **eggs** (female cell).\n**Fertilisation**: a sperm **fuses with** an egg. The fertilised egg develops in the **womb** into a baby.\nSame idea as plants: **male cell + female cell**.', img: 'humanrep' }
  ],
  facts: [
    ['Which flower part makes pollen?', 'The anther (male part)'],
    ['Pollination is...', 'Pollen moving from the anther to the stigma'],
    ['Fertilisation is...', 'A male cell fuses with a female cell'],
    ['3 things a seed needs to germinate', 'Water, air, warmth'],
    ['4 ways seeds are dispersed', 'Wind, water, animals, splitting'],
    ['In humans, which organs make sperm and eggs?', 'Testes make sperm, ovaries make eggs']
  ],
  mcq: [
    { lv: 1, q: 'Which part of a flower makes pollen?', o: ['Stigma', 'Anther', 'Ovary', 'Petal'], a: 1, hint: 'The male part.', why: 'The anther is the male part of the flower. It makes pollen.', img: 'flower' },
    { lv: 1, q: 'What is pollination?', o: ['A seed growing into a young plant', 'Pollen moving from the anther to the stigma', 'A fruit falling from the tree', 'The male cell fusing with the female cell'], a: 1, hint: 'Pollen has to land on the sticky part.', why: 'Pollination is the transfer of pollen from the anther to the stigma. Fertilisation comes after that.', img: 'pollination' },
    { lv: 1, q: 'Which of these describes fertilisation?', o: ['The flower opens.', 'A seed is carried away by the wind.', 'A male reproductive cell fuses with a female reproductive cell.', 'The seed takes in water.'], a: 2, hint: 'Two cells join.', why: 'Fertilisation happens when a male cell (from the pollen, or a sperm) fuses with a female cell (in the ovule, or an egg).', img: 'humanrep' },
    { lv: 1, q: 'Which pair produces the reproductive cells in humans?', o: ['Heart and lungs', 'Testes and ovaries', 'Stomach and womb', 'Brain and blood'], a: 1, hint: 'Sperm and eggs.', why: 'Testes produce sperm and ovaries produce eggs.', img: 'humanrep' },
    { lv: 2, q: 'A fruit has small hooks on its outside. How are its seeds most likely dispersed?', o: ['By wind', 'By water', 'By animals', 'By splitting'], a: 2, hint: 'Hooks catch on something furry.', why: 'Hooks catch on the fur of animals passing by, so the seeds are carried away by animals.', img: 'dispersal' },
    { lv: 2, q: 'Which of the following are needed for a seed to germinate?', o: ['Water, light and soil', 'Water, air and warmth', 'Light, air and soil', 'Water, light and warmth'], a: 1, hint: 'Seeds can germinate in the dark on wet cotton wool.', why: 'A seed needs water, air and warmth to germinate. It does not need light or soil (it can germinate on wet cotton wool in the dark).', img: 'germinate' },
    { lv: 2, q: 'The seeds of plant X drop straight down and grow right under the parent plant. Why is this bad for the young plants?', o: ['They cannot germinate without wind.', 'They will compete with each other for light, water and space.', 'The parent plant will eat them.', 'They will not get enough carbon dioxide.'], a: 1, hint: 'Too many plants in one small spot.', why: 'When seeds are not dispersed, the young plants are overcrowded and compete for light, water and space. Many will not grow well.', img: 'dispersal' },
    { lv: 2, q: 'Which living thing reproduces by spores?', o: ['Fern', 'Rose', 'Mango tree', 'Sunflower'], a: 0, hint: 'It has no flowers.', why: 'A fern is a non-flowering plant. It reproduces by spores. The others make flowers and seeds.', img: 'spores' }
  ],
  oe: [
    { q: 'The flowers of plant P are brightly coloured and have a sweet smell. How does this help the plant to reproduce?', m: 2, img: 'pollination', ans: ['The bright petals and sweet smell attract insects to the flower.', 'The insects carry pollen from the anther to the stigma, so pollination can take place.'], decoy: ['The petals make seeds for the plant.', 'The smell helps the seeds to germinate faster.'], kw: ['attract|insect', 'pollen|pollinat'] },
    { q: 'Seeds were put in three set-ups. A: wet cotton wool, warm room. B: dry cotton wool, warm room. C: wet cotton wool, in a fridge. Only the seeds in A germinated. (a) What was set-up B testing? (b) What was set-up C testing? (c) What is the conclusion?', m: 3, img: 'germinate', ans: ['(a) Set-up B tests whether seeds need water to germinate.', '(b) Set-up C tests whether seeds need warmth to germinate.', '(c) Seeds need both water and warmth to germinate.'], decoy: ['(a) Set-up B tests whether seeds need light.', '(c) Seeds only need soil to germinate.'], kw: ['water', 'warm', 'water|warm'] },
    { q: 'Fertilisation in humans and in flowering plants is similar. Explain how.', m: 2, img: 'humanrep', ans: ['In both, a male reproductive cell fuses with a female reproductive cell.', 'In humans it is a sperm and an egg; in plants it is the male cell from the pollen and the female cell in the ovule.'], decoy: ['In both, fertilisation happens in the womb.', 'Plants do not need fertilisation to make seeds.'], kw: ['male', 'fuse|female'] }
  ]
});

BLOCKS.push({
  id: 'b6', theme: 'cyc', name: 'Water', icon: '💧', lvl: 'P5',
  learn: [
    { h: 'Water in 3 states', t: '**Ice** (solid), **water** (liquid), **water vapour** or steam (gas).\nWater vapour is a gas you **cannot see**. The white cloud near a kettle is tiny water droplets, not the vapour.', img: 'h2o' },
    { h: 'Gain heat: move right', t: '- **Melting**: ice gains heat and becomes water at **0 &deg;C**.\n- **Boiling**: water gains heat and becomes steam at **100 &deg;C**, bubbles all through the water.\n- **Evaporation**: water becomes water vapour at **any temperature**, only at the **surface**. Slow and quiet.', img: 'h2o' },
    { h: 'Lose heat: move left', t: '- **Condensation**: water vapour **loses heat** and becomes water droplets. That is why a cold can gets wet outside.\n- **Freezing**: water loses heat and becomes ice at **0 &deg;C**.', img: 'h2o' },
    { h: 'Faster evaporation', t: 'Evaporation is faster with **more wind**, **higher temperature** and a **larger exposed surface area**.\nSo: spread the wet cloth out, put it in the sun, in a windy place.', img: 'evap' },
    { h: 'The water cycle', t: '1. The Sun heats the sea: water **evaporates** into water vapour, which rises.\n2. High up it cools and **condenses** into tiny droplets = **clouds**.\n3. Droplets join, get heavy and fall as **rain**.\n4. Water flows back to rivers and the sea. Repeat.', img: 'watercycle' },
    { h: 'Why water matters', t: 'All living things **need water** to survive.\nFresh water is limited. **Pollution** (chemicals, rubbish, oil) makes water unsafe for living things, so we must conserve and protect it.', img: 'watercycle' }
  ],
  facts: [
    ['Ice melts at...', '0 degrees Celsius (also the freezing point of water)'],
    ['Water boils at...', '100 degrees Celsius'],
    ['Water vapour becoming water droplets is called...', 'Condensation (loses heat)'],
    ['3 things that make evaporation faster', 'More wind, higher temperature, bigger exposed surface area'],
    ['Water cycle, 3 steps', 'Evaporation, condensation (clouds), rain']
  ],
  mcq: [
    { lv: 1, q: 'Ice at 0 &deg;C gains heat and turns into water. What is this process called?', o: ['Freezing', 'Melting', 'Boiling', 'Condensation'], a: 1, hint: 'Solid to liquid.', why: 'Melting is solid to liquid. Ice melts at 0 degrees Celsius when it gains heat.', img: 'h2o' },
    { lv: 1, q: 'Water droplets form on the OUTSIDE of a cold can of drink. Where does the water come from?', o: ['From inside the can', 'From the water vapour in the air', 'From the table', 'From the ice inside'], a: 1, hint: 'The can is closed. The water must come from outside.', why: 'Water vapour in the air touches the cold can, loses heat and condenses into water droplets on the outside.', img: 'h2o' },
    { lv: 1, q: 'At what temperature does water boil?', o: ['0 &deg;C', '37 &deg;C', '50 &deg;C', '100 &deg;C'], a: 3, hint: 'Higher than body temperature.', why: 'Water boils at 100 degrees Celsius. Ice melts at 0 degrees Celsius.', img: 'h2o' },
    { lv: 1, q: 'Wet clothes can dry even on a cool, cloudy day. Which process dries them?', o: ['Boiling', 'Melting', 'Evaporation', 'Freezing'], a: 2, hint: 'It happens at any temperature.', why: 'Evaporation happens at any temperature, at the surface of the water. Boiling only happens at 100 degrees Celsius.', img: 'evap' },
    { lv: 2, q: 'Four identical wet towels were hung to dry. Which towel will dry the FASTEST?', o: ['Folded, in the shade, no wind', 'Spread out, in the sun, windy', 'Folded, in the sun, no wind', 'Spread out, in the shade, no wind'], a: 1, hint: 'More surface, more heat, more wind.', why: 'Evaporation is fastest with a bigger exposed surface area (spread out), higher temperature (sun) and more wind.', img: 'evap' },
    { lv: 2, q: 'How do clouds form in the water cycle?', o: ['Water vapour rises, cools and condenses into tiny water droplets.', 'Rain freezes in the sky.', 'Sea water is blown up by the wind.', 'Water vapour gains heat and boils.'], a: 0, hint: 'High up in the sky, it is cold.', why: 'Water vapour rises, loses heat high up, and condenses into tiny droplets. Many droplets together make a cloud.', img: 'watercycle' },
    { lv: 2, q: 'A beaker of ice was heated. The graph of temperature against time stayed flat at 0 &deg;C for 4 minutes before rising. What was happening during those 4 minutes?', o: ['The ice was melting.', 'The water was boiling.', 'The water was freezing.', 'The heater was off.'], a: 0, hint: 'Temperature stays the same while the state changes.', why: 'While ice melts, the heat gained is used to change the state, so the temperature stays at 0 degrees Celsius until all the ice has melted.', img: 'h2o' },
    { lv: 2, q: 'What is the difference between boiling and evaporation?', o: ['Boiling happens at any temperature; evaporation only at 100 &deg;C.', 'Boiling happens at 100 &deg;C throughout the water; evaporation happens at any temperature at the surface.', 'Boiling makes ice; evaporation makes steam.', 'There is no difference.'], a: 1, hint: 'Bubbles all through the water vs quiet drying at the top.', why: 'Boiling happens at 100 degrees Celsius with bubbles throughout the water. Evaporation happens at any temperature, only at the surface.', img: 'h2o' }
  ],
  oe: [
    { q: 'Explain how water droplets form on the outside of a glass of iced water.', m: 2, img: 'h2o', ans: ['The water vapour in the air touches the cold glass and loses heat.', 'It condenses into water droplets on the outside of the glass.'], decoy: ['The water inside the glass leaks through the glass.', 'The ice melts and flows out of the glass.'], kw: ['water vapour|vapour', 'condens|lose heat|loses heat'] },
    { q: 'Two identical containers each had 100 ml of water. A was covered with a lid. B was left open. Both were placed in the sun for 3 hours. (a) Which container will have less water? (b) Explain why.', m: 3, img: 'evap', ans: ['(a) Container B.', '(b) The water in B is exposed to the air, so it gains heat and evaporates into water vapour which escapes into the air.', 'In A, the lid stops the water vapour from escaping, so the water stays in the container.'], decoy: ['(a) Container A, because it is warmer under the lid.', '(b) The water in B boils away.'], kw: ['B', 'evaporat', 'lid|cover|escape'] },
    { q: 'The water cycle keeps giving us water. Explain why we still must not pollute rivers and the sea.', m: 2, img: 'watercycle', ans: ['All living things need clean water to survive.', 'Polluted water harms living things, and clean fresh water is limited.'], decoy: ['The water cycle removes all the pollution, so it does not matter.', 'Sea water is not part of the water cycle.'], kw: ['living things|survive', 'harm|limited|pollut'] }
  ]
});

// ---------- Content: blocks 7-12 ----------

BLOCKS.push({
  id: 'b7', theme: 'sys', name: 'Plant parts', icon: '🌱', lvl: 'P4/P5',
  learn: [
    { h: 'Every part has a job', t: '- **Roots**: **absorb water** and mineral salts from the soil. They also **hold the plant firmly** in the ground.\n- **Stem**: **holds up** the leaves and flowers. It **carries water and food** to other parts.\n- **Leaves**: **make food** using light, water and carbon dioxide. Tiny openings let gases in and out.\n- **Flowers**: for **reproduction** (make seeds).', img: 'plant' },
    { h: 'Two kinds of tubes in the stem', t: '**Water-carrying tubes** carry water and minerals from the **roots UP to the leaves**.\n**Food-carrying tubes** carry food (sugar) made in the **leaves to ALL other parts**: stem, roots, flowers, fruits.\nRemember: water goes **up**, food goes **everywhere**.', img: 'tubes' },
    { h: 'The celery test', t: 'Put a celery stalk in **red water**. After some hours the leaves show **red patches**.\nThe red water travelled **up** through the **water-carrying tubes**.\nThis is the classic PSLE question. The answer is always: water-carrying tubes.', img: 'tubes' },
    { h: 'The ring experiment', t: 'Cut a **ring** of bark off a tree. The **food-carrying tubes** are cut, but the water-carrying tubes inside are not.\n- **Above** the ring: food from the leaves piles up, so it **swells**.\n- **Below** the ring: **no food** reaches the roots. After weeks, the **roots die**.\n- The leaves stay fresh because **water still goes up**.', img: 'ring' },
    { h: 'No leaves = no food', t: 'If all the leaves are removed, the plant **cannot make food**.\nNo food = no energy to grow and stay alive. The plant becomes weak and dies.\nExam tip: when a part is removed, name its **job**, then say what the plant **cannot do** now.', img: 'plant' }
  ],
  facts: [
    ['What do roots do? (2 jobs)', 'Absorb water and minerals; hold the plant firmly in the soil'],
    ['What does the stem do?', 'Holds up the leaves and flowers; carries water and food'],
    ['What do leaves do?', 'Make food using light, water and carbon dioxide'],
    ['Water-carrying tubes carry water from... to...', 'From the roots up to the leaves'],
    ['Food-carrying tubes carry food from... to...', 'From the leaves to all other parts of the plant']
  ],
  mcq: [
    { lv: 1, q: 'Which part of a plant absorbs water from the soil?', o: ['Leaf', 'Flower', 'Root', 'Stem'], a: 2, hint: 'The part that is in the soil.', why: 'Roots absorb water and mineral salts from the soil. They also hold the plant firmly.', img: 'plant' },
    { lv: 1, q: 'Which part of a plant makes food?', o: ['Root', 'Leaf', 'Stem', 'Flower'], a: 1, hint: 'The green part that catches light.', why: 'Leaves make food (sugar) using light, water and carbon dioxide.', img: 'plant' },
    { lv: 1, q: 'Water-carrying tubes carry water from the...', o: ['leaves to the roots', 'roots to the leaves', 'flowers to the stem', 'fruit to the roots'], a: 1, hint: 'Water comes from the soil and goes UP.', why: 'Water is absorbed by the roots and carried UP through the water-carrying tubes to the leaves.', img: 'tubes' },
    { lv: 1, q: 'Which part holds up the leaves and carries water and food to other parts?', o: ['Root', 'Stem', 'Flower', 'Seed'], a: 1, hint: 'The tubes are inside this part.', why: 'The stem holds up the leaves and flowers, and its tubes carry water and food.', img: 'plant' },
    { lv: 2, q: 'A celery stalk was put in red water. After 3 hours, the leaves had red patches. Which part carried the red water to the leaves?', o: ['Food-carrying tubes', 'Water-carrying tubes', 'Tiny openings on the leaves', 'Roots'], a: 1, hint: 'Red WATER moved UP.', why: 'The water-carrying tubes in the stem carried the red water upwards to the leaves.', img: 'tubes' },
    { lv: 2, q: 'A ring of bark was removed from a tree, cutting the food-carrying tubes. Which part will get LESS food?', o: ['The leaves above the ring', 'The roots below the ring', 'The flowers', 'The whole tree equally'], a: 1, hint: 'Food is made in the leaves. Where can it NOT go now?', why: 'Food made in the leaves cannot pass the cut, so the parts below the ring (including the roots) get less food. Part above the ring swells with food.', img: 'ring' },
    { lv: 2, q: 'The roots of a potted plant were cut off. Two days later the plant wilted (drooped). Why?', o: ['It could not make food.', 'It could not absorb water.', 'It could not get sunlight.', 'It could not stand up.'], a: 1, hint: 'What do roots absorb?', why: 'Roots absorb water. Without roots, no water enters the plant, so it wilts.', img: 'plant' },
    { lv: 2, q: 'In the ring experiment, the leaves above the ring stayed fresh and green for weeks. Why?', o: ['The leaves do not need water.', 'Water still reached the leaves through the water-carrying tubes, which were not cut.', 'The roots sent food up to the leaves.', 'The ring made more food.'], a: 1, hint: 'Only ONE kind of tube was cut.', why: 'Only the food-carrying tubes (near the outside) were cut. The water-carrying tubes still carried water up to the leaves.', img: 'ring' }
  ],
  oe: [
    { q: 'A white flower was placed in blue-coloured water. After a day, the petals turned blue. Explain how the petals turned blue.', m: 2, img: 'tubes', ans: ['The water-carrying tubes in the stem carried the blue water up from the cut end of the stem.', 'The blue water reached the petals, so they turned blue.'], decoy: ['The petals absorbed the blue water from the air.', 'The food-carrying tubes carried the blue water to the petals.'], kw: ['water-carrying|water carrying', 'petal|up'] },
    { q: 'A ring of bark was removed from a tree trunk. Weeks later, the part just above the ring became swollen and the roots started to die. Explain why the roots died.', m: 2, img: 'ring', ans: ['The food-carrying tubes were cut, so food made in the leaves could not be transported down to the roots.', 'The roots had no food to give them energy, so they died.'], decoy: ['The roots could not absorb water because the ring was removed.', 'The leaves stopped making food.'], kw: ['food-carrying|food carrying|food', 'energy|no food'] },
    { q: 'All the leaves of a healthy plant were removed. Predict what will happen to the plant after a few weeks and explain why.', m: 2, img: 'plant', ans: ['The plant will become weak and die.', 'Without leaves, the plant cannot make food, so it has no energy to stay alive.'], decoy: ['The plant will grow faster because it saves water.', 'The roots will make food instead.'], kw: ['die|weak', 'food'] }
  ]
});

BLOCKS.push({
  id: 'b8', theme: 'sys', name: 'Digestion', icon: '🍽️', lvl: 'P4',
  learn: [
    { h: 'Body systems', t: 'A **system** = parts that **work together** to do a job.\n- **Digestive**: breaks down food.\n- **Respiratory**: takes in oxygen, gives out carbon dioxide.\n- **Circulatory**: heart and blood carry things around.\n- **Skeletal**: bones support and protect. **Muscular**: muscles move the body.', img: 'systems' },
    { h: 'Why digest?', t: 'Food is too big to go into the blood.\n**Digestion** breaks food into **tiny pieces** that can be **absorbed into the blood**.\nThe blood carries the digested food to every part of the body.', img: 'digest' },
    { h: 'The path of food', t: '**Mouth** &rarr; **gullet** &rarr; **stomach** &rarr; **small intestine** &rarr; **large intestine** &rarr; **anus**.\nTrap: the **small** intestine comes BEFORE the **large** intestine.', img: 'digest' },
    { h: 'What happens where', t: '- **Mouth**: teeth cut and grind. Saliva starts to digest.\n- **Gullet**: only **pushes** food down. No digestion.\n- **Stomach**: **digestive juices** break food down.\n- **Small intestine**: digestion is **completed**. Digested food is **absorbed into the blood**.\n- **Large intestine**: **water** is absorbed.\n- **Anus**: undigested food leaves the body.', img: 'digest' },
    { h: 'Systems team up', t: 'The **digestive** system gives digested food. The **respiratory** system gives oxygen.\nThe **circulatory** system (blood) carries both to every part of the body to **release energy**.', img: 'teamup' }
  ],
  facts: [
    ['Path of food (6 parts, in order)', 'Mouth, gullet, stomach, small intestine, large intestine, anus'],
    ['Where is digested food absorbed into the blood?', 'In the small intestine'],
    ['What does the large intestine do?', 'Absorbs water from undigested food'],
    ['Where does digestion happen? (3 places)', 'Mouth, stomach, small intestine'],
    ['What does the gullet do?', 'Pushes food from the mouth to the stomach (no digestion)']
  ],
  mcq: [
    { lv: 1, q: 'Which is the correct path of food through the body?', o: ['mouth, stomach, gullet, small intestine, large intestine', 'mouth, gullet, stomach, small intestine, large intestine', 'mouth, gullet, stomach, large intestine, small intestine', 'mouth, gullet, small intestine, stomach, large intestine'], a: 1, hint: 'Gullet is the tube right after the mouth. Small comes before large.', why: 'Mouth, gullet, stomach, SMALL intestine, LARGE intestine, anus.', img: 'digest' },
    { lv: 1, q: 'Where is digested food absorbed into the blood?', o: ['Stomach', 'Gullet', 'Small intestine', 'Large intestine'], a: 2, hint: 'Digestion is COMPLETED here too.', why: 'Digestion is completed in the small intestine, and the digested food is absorbed into the blood there.', img: 'digest' },
    { lv: 1, q: 'What is the main job of the large intestine?', o: ['To digest food', 'To absorb water from undigested food', 'To absorb digested food', 'To chew food'], a: 1, hint: 'Not food. Something else is absorbed.', why: 'The large intestine absorbs water from the undigested food. The waste then leaves through the anus.', img: 'digest' },
    { lv: 1, q: 'Which body system takes in oxygen and gives out carbon dioxide?', o: ['Digestive', 'Respiratory', 'Skeletal', 'Muscular'], a: 1, hint: 'Breathing.', why: 'The respiratory system (nose, windpipe, lungs) takes in oxygen and gives out carbon dioxide.', img: 'systems' },
    { lv: 2, q: 'In which parts of the digestive system does digestion take place?', o: ['Mouth, gullet and stomach', 'Mouth, stomach and small intestine', 'Stomach, small intestine and large intestine', 'Gullet, stomach and large intestine'], a: 1, hint: 'The gullet only pushes. The large intestine only absorbs water.', why: 'Digestion happens in the mouth (saliva), stomach (digestive juices) and small intestine (completed). The gullet and large intestine do not digest food.', img: 'digest' },
    { lv: 2, q: 'Mei chews her food well. Ali swallows big pieces. Why does chewing help digestion?', o: ['Chewing adds oxygen to the food.', 'Smaller pieces let the digestive juices act on the food more easily.', 'Chewing makes the food heavier.', 'Chewing cleans the teeth.'], a: 1, hint: 'Small pieces vs big pieces.', why: 'Chewing breaks food into smaller pieces, so digestive juices can act on more of the food and digestion is faster.', img: 'digest' },
    { lv: 2, q: 'Which body system carries digested food and oxygen to all parts of the body?', o: ['Digestive system', 'Respiratory system', 'Circulatory system', 'Skeletal system'], a: 2, hint: 'Heart, blood, blood vessels.', why: 'The circulatory system (heart, blood, blood vessels) transports digested food and oxygen to every part of the body.', img: 'teamup' },
    { lv: 2, q: 'A man has a badly damaged small intestine. He eats normally but feels weak and is losing weight. Why?', o: ['He cannot chew properly.', 'Less digested food is absorbed into his blood, so his body gets less food for energy.', 'He cannot breathe properly.', 'His stomach is empty.'], a: 1, hint: 'What does the small intestine do?', why: 'The small intestine absorbs digested food into the blood. If it is damaged, less food is absorbed, so the body has less food for energy and growth.', img: 'digest' }
  ],
  oe: [
    { q: 'Explain why chewing food well helps digestion.', m: 2, img: 'digest', ans: ['Chewing breaks the food into smaller pieces.', 'The digestive juices can then act on the food more easily, so digestion is faster.'], decoy: ['Chewing adds oxygen to the food.', 'Chewing makes the food go straight into the blood.'], kw: ['small', 'juice|easier|faster'] },
    { q: 'A patient has a badly damaged small intestine. He feels weak and is losing weight even though he eats normally. Explain why.', m: 2, img: 'digest', ans: ['Digested food is absorbed into the blood in the small intestine.', 'With a damaged small intestine, less digested food is absorbed, so his body gets less food for energy and growth.'], decoy: ['He cannot chew his food properly.', 'His large intestine cannot absorb water.'], kw: ['absorb', 'less|energy'] },
    { q: 'Why must food be digested before the body can use it?', m: 2, img: 'digest', ans: ['Food is too big to pass into the blood.', 'Digestion breaks food into tiny pieces that can be absorbed into the blood and carried to all parts of the body.'], decoy: ['Digestion makes the food taste better.', 'Food goes into the blood from the stomach without digestion.'], kw: ['big|large|tiny|small', 'blood'] }
  ]
});

BLOCKS.push({
  id: 'b9', theme: 'sys', name: 'Breathing & blood', icon: '🫁', lvl: 'P5',
  learn: [
    { h: 'Air is a mixture', t: 'Air is made of gases: **nitrogen** (the most), **oxygen**, **carbon dioxide** and **water vapour**.\nOur body uses the **oxygen**.', img: 'air' },
    { h: 'Breathing in', t: 'Air goes in through the **nose**, down the **windpipe**, into the **lungs**.\nIn the lungs, **oxygen goes into the blood** and **carbon dioxide comes out** of the blood to be breathed out.', img: 'resp' },
    { h: 'Breathed-out air', t: 'Compared with the air we breathe in, the air we breathe out has **less oxygen**, **more carbon dioxide** and **more water vapour**.\nWhy? The body **uses oxygen** to release energy from food, and this **makes carbon dioxide**.', img: 'resp' },
    { h: 'The circulatory system', t: '**Heart**: pumps blood. **Blood vessels**: tubes that carry blood everywhere.\n**Blood** carries **oxygen and digested food** to all parts, and carries **carbon dioxide** away to the lungs.', img: 'circ' },
    { h: 'Exercise', t: 'When you run, your muscles need **more energy**. Energy is released from food **using oxygen**.\nSo you **breathe faster** (more oxygen in) and your **heart beats faster** (blood carries oxygen and food to the muscles faster, and carries carbon dioxide away faster).', img: 'teamup' },
    { h: 'Fish, plants, humans', t: 'All living things take in oxygen and give out carbon dioxide.\n- **Humans**: lungs, oxygen from the **air**.\n- **Fish**: **gills**, oxygen dissolved in **water**.\n- **Plants**: **tiny openings** in the leaves.', img: 'gills' }
  ],
  facts: [
    ['4 gases in air', 'Nitrogen, oxygen, carbon dioxide, water vapour'],
    ['Path of air into the body', 'Nose, windpipe, lungs'],
    ['Breathed-out air has...', 'Less oxygen, more carbon dioxide, more water vapour'],
    ['3 parts of the circulatory system', 'Heart (pumps), blood vessels (tubes), blood (carries)'],
    ['Why does the heart beat faster when you run?', 'Muscles need more oxygen and food to release more energy']
  ],
  mcq: [
    { lv: 1, q: 'Which gases are in the air we breathe in?', o: ['Oxygen only', 'Oxygen and nitrogen only', 'Nitrogen, oxygen, carbon dioxide and water vapour', 'Carbon dioxide only'], a: 2, hint: 'Air is a mixture of four things.', why: 'Air is a mixture of nitrogen (the most), oxygen, carbon dioxide and water vapour.', img: 'air' },
    { lv: 1, q: 'Compared with the air we breathe in, the air we breathe out has...', o: ['more oxygen and less carbon dioxide', 'less oxygen and more carbon dioxide', 'the same amount of oxygen', 'no carbon dioxide'], a: 1, hint: 'The body uses one gas and makes another.', why: 'The body uses oxygen to release energy from food and makes carbon dioxide. So breathed-out air has less oxygen and more carbon dioxide.', img: 'resp' },
    { lv: 1, q: 'Which is the correct path of air into the body?', o: ['nose, lungs, windpipe', 'windpipe, nose, lungs', 'nose, windpipe, lungs', 'lungs, windpipe, nose'], a: 2, hint: 'Start at the nose. The windpipe is a pipe TO the lungs.', why: 'Air enters through the nose, goes down the windpipe and reaches the lungs.', img: 'resp' },
    { lv: 1, q: 'What happens in the lungs?', o: ['Digested food is absorbed into the blood.', 'Oxygen goes into the blood and carbon dioxide comes out of the blood.', 'Blood is pumped to the body.', 'Food is digested.'], a: 1, hint: 'Gas swap.', why: 'In the lungs, oxygen passes from the air into the blood, and carbon dioxide passes from the blood into the air to be breathed out.', img: 'resp' },
    { lv: 2, q: 'Why does a boy\'s heart beat faster when he runs?', o: ['His muscles need more oxygen and digested food to release more energy.', 'His lungs stop working.', 'His blood becomes thicker.', 'His body needs less oxygen.'], a: 0, hint: 'More running = more energy needed.', why: 'Running muscles need more energy. Energy is released from food using oxygen, so the heart pumps faster to deliver more oxygen and food (and remove carbon dioxide faster).', img: 'teamup' },
    { lv: 2, q: 'How does a fish take in oxygen?', o: ['With lungs, from the air', 'Through its skin, from the air', 'With gills, oxygen dissolved in water', 'It does not need oxygen'], a: 2, hint: 'Fish live in water.', why: 'Fish use gills to take in oxygen that is dissolved in the water. Humans use lungs to take oxygen from the air.', img: 'gills' },
    { lv: 2, q: 'Which two systems work together to carry oxygen from the air to the muscles?', o: ['Digestive and circulatory', 'Respiratory and circulatory', 'Skeletal and muscular', 'Respiratory and digestive'], a: 1, hint: 'One takes oxygen in. One delivers it.', why: 'The respiratory system takes oxygen into the blood (lungs). The circulatory system carries the blood with oxygen to the muscles.', img: 'teamup' },
    { lv: 2, q: 'Which of these does the blood carry AWAY from the muscles to the lungs?', o: ['Oxygen', 'Digested food', 'Carbon dioxide', 'Water vapour only'], a: 2, hint: 'The waste gas.', why: 'Blood carries carbon dioxide (made when energy is released) from the muscles to the lungs, where it is breathed out.', img: 'circ' }
  ],
  oe: [
    { q: 'Ali\'s heart rate was 70 beats per minute at rest and 140 beats per minute after running. Explain why his heart rate increased.', m: 2, img: 'teamup', ans: ['His muscles needed more oxygen and digested food to release more energy for running.', 'So the heart pumped blood faster to carry more oxygen and digested food to the muscles.'], decoy: ['His lungs became smaller when he ran.', 'His blood needed less oxygen when running.'], kw: ['energy|oxygen', 'faster|pump'] },
    { q: 'Compare how a fish and a human take in oxygen.', m: 2, img: 'gills', ans: ['A fish uses its gills to take in oxygen dissolved in water.', 'A human uses lungs to take in oxygen from the air.'], decoy: ['A fish does not need oxygen.', 'A human takes in oxygen through the skin.'], kw: ['gill', 'lung'] },
    { q: 'Explain how the digestive, respiratory and circulatory systems work together to give the body energy.', m: 3, img: 'teamup', ans: ['The digestive system breaks down food into digested food.', 'The respiratory system takes in oxygen into the blood.', 'The circulatory system carries the digested food and oxygen to all parts of the body, where energy is released.'], decoy: ['The digestive system takes in oxygen.', 'The respiratory system digests food.'], kw: ['digest', 'oxygen', 'blood|carr|transport'] }
  ]
});

BLOCKS.push({
  id: 'b10', theme: 'sys', name: 'Electricity', icon: '💡', lvl: 'P5',
  learn: [
    { h: 'A circuit is a loop', t: 'An electrical system needs an energy source (**battery**) and parts: **wires, bulb, switch**.\n**Closed circuit** = complete loop. **Current flows**, the bulb lights.\n**Open circuit** = there is a **gap**. No current, the bulb is off.', img: 'circuit' },
    { h: 'Circuit symbols', t: 'Exam questions use symbols. **Battery**: long line and short line. **Bulb**: circle with a cross.\n**Switch**: open (gap) or closed (joined). **Wires**: straight lines.', img: 'symbols' },
    { h: 'Conductors and insulators', t: '**Electrical conductors** let current pass: **metals** like copper, iron, steel, aluminium.\n**Insulators** do NOT let current pass: **plastic, rubber, wood, glass, paper**.\nPut an insulator in the gap: the bulb stays off.', img: 'conduct' },
    { h: 'Series: one path', t: 'In a **series** circuit there is **only one path**.\n- **More bulbs** in series (same battery) = each bulb **dimmer**.\n- If **one bulb blows**, the loop is broken: **ALL bulbs go off**.\n- **More batteries** in series = **brighter** bulbs (more current).', img: 'seriespar' },
    { h: 'Parallel: own path each', t: 'In a **parallel** circuit each bulb has its **own loop** with the battery.\n- Each bulb is as **bright** as if it were alone.\n- If one bulb blows, the **others stay on**.\n- A switch only controls the bulbs on **its own loop**. Houses use parallel circuits.', img: 'seriespar' }
  ],
  facts: [
    ['A closed circuit is...', 'A complete loop with no gaps, so current can flow'],
    ['Name 3 electrical conductors', 'Copper, iron, steel (all metals)'],
    ['Name 3 electrical insulators', 'Plastic, rubber, wood (also glass, paper)'],
    ['In a SERIES circuit, if one bulb blows...', 'All the bulbs go off (only one path)'],
    ['In a PARALLEL circuit, if one bulb blows...', 'The other bulbs stay on (each has its own loop)']
  ],
  mcq: [
    { lv: 1, q: 'A circuit has a battery, wires, a bulb and a switch. The switch is open. Why does the bulb NOT light up?', o: ['The battery has no energy.', 'The circuit is open, so no current flows.', 'The bulb is an insulator.', 'The wires are too long.'], a: 1, hint: 'Open switch = gap.', why: 'An open switch leaves a gap in the circuit. Current can only flow in a closed (complete) circuit.', img: 'circuit' },
    { lv: 1, q: 'Which object, placed in the gap of a circuit, will make the bulb light up?', o: ['A plastic ruler', 'A rubber band', 'An iron nail', 'A wooden stick'], a: 2, hint: 'Which one is a metal?', why: 'Iron is a metal, so it is an electrical conductor. It completes the circuit. Plastic, rubber and wood are insulators.', img: 'conduct' },
    { lv: 1, q: 'A second battery is added in series to a circuit with one bulb. What happens to the bulb?', o: ['It becomes dimmer.', 'It becomes brighter.', 'It goes off.', 'No change.'], a: 1, hint: 'More batteries = more push.', why: 'More batteries in series make a larger current flow, so the bulb is brighter.', img: 'seriespar' },
    { lv: 1, q: 'Which material is an electrical insulator?', o: ['Copper', 'Steel', 'Rubber', 'Aluminium'], a: 2, hint: 'Not a metal.', why: 'Rubber does not let current pass, so it is an insulator. Copper, steel and aluminium are metals and conductors.', img: 'conduct' },
    { lv: 2, q: 'Two bulbs are connected in SERIES to a battery. One bulb blows. What happens to the other bulb?', o: ['It becomes brighter.', 'It stays the same.', 'It goes off.', 'It becomes dimmer but stays on.'], a: 2, hint: 'Series = one path only.', why: 'In a series circuit there is only one path. A blown bulb breaks the loop, so the circuit is open and no current reaches the other bulb.', img: 'seriespar' },
    { lv: 2, q: 'Two bulbs are connected in PARALLEL to a battery. One bulb blows. What happens to the other bulb?', o: ['It goes off.', 'It stays on with the same brightness.', 'It becomes much dimmer.', 'It flashes.'], a: 1, hint: 'Parallel = each bulb has its own loop.', why: 'Each bulb in parallel is in its own complete loop with the battery. Breaking one loop does not affect the other.', img: 'seriespar' },
    { lv: 2, q: 'Three bulbs are in series with one battery. One bulb is removed and the gap is closed with a wire. What happens to the other two bulbs?', o: ['They go off.', 'They become dimmer.', 'They become brighter.', 'No change.'], a: 2, hint: 'Fewer bulbs sharing the same battery.', why: 'Fewer bulbs in series with the same battery means more current flows through each bulb, so they are brighter.', img: 'seriespar' },
    { lv: 2, q: 'Which set-up is used in a house so that each lamp can be switched on and off separately, and the other lamps stay on if one blows?', o: ['All lamps in series', 'All lamps in parallel, each with its own switch', 'One lamp only', 'No switches'], a: 1, hint: 'Own loop, own switch.', why: 'In a parallel circuit each lamp has its own loop and its own switch, so it works on its own. If one blows, the others stay on.', img: 'seriespar' }
  ],
  oe: [
    { q: 'Ravi connected a battery, a bulb and wires, with a plastic ruler in the gap. The bulb did not light up. Explain why.', m: 2, img: 'conduct', ans: ['Plastic is an electrical insulator, so it does not allow current to flow through it.', 'The circuit is not complete (open), so the bulb does not light up.'], decoy: ['The battery is too weak to light the bulb.', 'Plastic is a conductor but the ruler is too long.'], kw: ['insulator', 'open|not complete|no current|cannot flow'] },
    { q: 'Two bulbs P and Q are connected in parallel to a battery. Bulb P blows. Will bulb Q still light up? Explain.', m: 2, img: 'seriespar', ans: ['Yes, bulb Q will still light up.', 'Bulb Q is in its own closed circuit with the battery, so current can still flow through it.'], decoy: ['No, because the circuit is broken when P blows.', 'No, because Q needs P to work.'], kw: ['yes', 'own|closed|complete|still flow'] },
    { q: 'A bulb was connected to one battery. Ali added a second battery in series. Describe what happened to the bulb and explain why.', m: 2, img: 'seriespar', ans: ['The bulb became brighter.', 'With two batteries in series, a larger current flows through the bulb.'], decoy: ['The bulb became dimmer.', 'The wires became shorter, so the bulb was brighter.'], kw: ['bright', 'current|larger|more'] }
  ]
});

BLOCKS.push({
  id: 'b11', theme: 'int', name: 'Magnets', icon: '🧲', lvl: 'P3',
  learn: [
    { h: 'What a magnet does', t: 'A magnet can **push** (repel) or **pull** (attract) **without touching**.\nMagnets are made of **iron or steel**. They have **two poles**: **North** and **South**.\nA magnet hanging freely comes to rest pointing **North-South**. That is how a compass works.', img: 'poles' },
    { h: 'Attract or repel?', t: '**Unlike poles attract**: N and S pull together.\n**Like poles repel**: N and N (or S and S) push apart.\nOnly a magnet can repel. So **repel = proof it is a magnet**. Attract is NOT proof (iron also attracts).', img: 'poles' },
    { h: 'Magnetic materials', t: 'Magnets attract **magnetic materials**: **iron and steel**.\nNOT attracted: copper, aluminium, gold (metals, but not magnetic), plastic, wood, rubber, glass.\nThe magnetic force is **strongest at the poles**.', img: 'magnetmat' },
    { h: 'Making a magnet', t: '**Stroke method**: stroke a steel bar with **one pole**, in **one direction**, **many times**.\n**Electrical method**: coil wire around an **iron nail** and connect a battery. It is a magnet only while current flows. More coils or batteries = stronger.', img: 'makemag' },
    { h: 'Magnets around us', t: 'Compass needle, fridge door strip, magnetic cranes that lift scrap iron, maglev trains, magnetic pencil boxes.', img: 'uses_mag' }
  ],
  facts: [
    ['Unlike poles (N and S)...', 'Attract'],
    ['Like poles (N and N)...', 'Repel'],
    ['A freely hanging magnet rests pointing...', 'North-South'],
    ['2 magnetic materials', 'Iron and steel'],
    ['The only sure test that something is a magnet', 'It can repel (only magnets repel)']
  ],
  mcq: [
    { lv: 1, q: 'The north pole of magnet X is brought near the north pole of magnet Y. What happens?', o: ['They attract each other.', 'They repel each other.', 'Nothing happens.', 'Magnet Y stops being a magnet.'], a: 1, hint: 'N and N are LIKE poles.', why: 'Like poles (N-N or S-S) repel. Unlike poles (N-S) attract.', img: 'poles' },
    { lv: 1, q: 'A bar magnet is hung freely by a string. When it stops moving, which direction does its north pole point?', o: ['East', 'West', 'North', 'Down'], a: 2, hint: 'This is how a compass works.', why: 'A freely hanging magnet rests in a North-South direction, with its north pole pointing north.', img: 'poles' },
    { lv: 1, q: 'Which object will be attracted to a magnet?', o: ['A copper wire', 'A steel paper clip', 'An aluminium can', 'A plastic ruler'], a: 1, hint: 'Iron and steel only.', why: 'Steel and iron are magnetic materials. Copper and aluminium are metals but are NOT magnetic. Plastic is not magnetic.', img: 'magnetmat' },
    { lv: 1, q: 'Where is the magnetic force of a bar magnet the strongest?', o: ['In the middle', 'At the two poles', 'Everywhere the same', 'Only at the north pole'], a: 1, hint: 'Paper clips stick most at the ends.', why: 'The magnetic force is strongest at the two poles (the ends). The middle attracts the fewest paper clips.', img: 'magnet' },
    { lv: 2, q: 'Bar P attracts BOTH ends of a magnet. Bar Q attracts one end and repels the other end. Which is correct?', o: ['P is a magnet, Q is not.', 'Q is a magnet. P is a magnetic material but not a magnet.', 'Both are magnets.', 'Neither is a magnet.'], a: 1, hint: 'Only a magnet can repel.', why: 'Only a magnet can repel. Q repels one end, so Q is a magnet. P only attracts, so P is just a magnetic material like iron.', img: 'poles' },
    { lv: 2, q: 'Which is the correct way to make a steel bar into a magnet by the stroke method?', o: ['Stroke it back and forth with both poles.', 'Stroke it with one pole, in the same direction, many times.', 'Heat the bar.', 'Wrap the bar in paper.'], a: 1, hint: 'One pole, one direction, many times.', why: 'Stroke method: use ONE pole, stroke in ONE direction, lift, and repeat many times.', img: 'makemag' },
    { lv: 2, q: 'A wire is coiled around an iron nail and connected to a battery. The nail picks up paper clips. When the battery is removed, the clips drop. Why?', o: ['The nail became a permanent magnet.', 'The nail is a magnet only while current flows.', 'The paper clips are not magnetic.', 'The wire is an insulator.'], a: 1, hint: 'Electrical method = temporary.', why: 'With the electrical method, the iron nail is a magnet only while current flows in the coil. Remove the battery and it loses its magnetism.', img: 'makemag' },
    { lv: 2, q: 'How can you make the electromagnet (coil around an iron nail) STRONGER?', o: ['Use fewer coils of wire', 'Use more coils of wire or more batteries', 'Use a plastic rod instead of the nail', 'Remove the battery'], a: 1, hint: 'More of the things that make it work.', why: 'More coils of wire or more batteries make the electromagnet stronger, so it can pick up more clips.', img: 'makemag' }
  ],
  oe: [
    { q: 'Mei has a bar magnet and an unknown metal bar X. Describe how she can find out whether X is a magnet.', m: 3, img: 'poles', ans: ['Bring one pole of the bar magnet near one end of X, then near the other end of X.', 'If one end of X is repelled, X is a magnet.', 'This is because only a magnet can repel.'], decoy: ['If X is attracted to the magnet, X must be a magnet.', 'Heat X to see if it melts.'], kw: ['end|pole|near', 'repel', 'only'] },
    { q: 'Ali strokes a steel bar with a magnet to make it a magnet. State two things Ali must do for the stroke method to work.', m: 2, img: 'makemag', ans: ['Use only ONE pole of the magnet.', 'Stroke in the same direction many times.'], decoy: ['Stroke back and forth quickly.', 'Use both poles one after the other.'], kw: ['one pole|same pole', 'same direction|one direction|many'] },
    { q: 'A crane uses an electromagnet to lift scrap iron. Explain why an electromagnet is better than a permanent magnet for this job.', m: 2, img: 'uses_mag', ans: ['The electromagnet can be switched off, so the scrap iron drops where it is wanted.', 'A permanent magnet cannot be switched off, so the iron would stay stuck to it.'], decoy: ['An electromagnet is always weaker than a permanent magnet.', 'A permanent magnet cannot attract iron.'], kw: ['switch|off|drop', 'permanent|stuck|cannot'] }
  ]
});

BLOCKS.push({
  id: 'b12', theme: 'int', name: 'Forces', icon: '🏋️', lvl: 'P6',
  learn: [
    { h: 'A force is a push or a pull', t: 'You cannot see a force. You see **what it does**.\nA force can: make a still object **move**, make a moving object **speed up**, **slow down**, **change direction** or **stop**, and it can **change the shape** of an object.', img: 'effects' },
    { h: 'The 4 forces', t: '- **Magnetic force**: push or pull between magnets, or a magnet and iron/steel.\n- **Gravitational force**: pulls everything **towards the Earth**.\n- **Elastic spring force**: a stretched or squashed spring pushes or pulls **back**.\n- **Frictional force**: between **two touching surfaces**, slows things down.', img: 'forces4' },
    { h: 'Friction', t: 'Friction acts **against** the motion and **slows things down**. It also makes **heat**.\n**Rough** surface = **more** friction. **Smooth** surface or **oil** = **less** friction.\nUseful friction: shoes grip the floor, brakes stop a bike. Unwanted friction: a rusty chain, so we oil it.', img: 'friction' },
    { h: 'Gravity and weight', t: '**Gravitational force** pulls objects towards the ground. That is why things fall **down**.\n**Weight** = how hard gravity pulls on an object. **Mass** = the amount of matter, and it never changes.\nOn the **Moon**, gravity is weaker: **weight is less**, mass is the **same**.', img: 'gravity' },
    { h: 'Springs', t: 'A **stretched** spring **pulls back**. A **squashed** spring **pushes back**.\nThe **more** you stretch it (bigger load), the **bigger** the extension and the bigger the force. Then it goes back to its shape.', img: 'spring' }
  ],
  facts: [
    ['A force is...', 'A push or a pull'],
    ['5 things a force can do', 'Start, speed up, slow down or stop, change direction, change shape'],
    ['4 types of forces', 'Magnetic, gravitational, elastic spring, frictional'],
    ['Rough surface means...', 'More friction, so things slow down faster'],
    ['On the Moon, your mass and weight...', 'Mass stays the same, weight is less (weaker gravity)']
  ],
  mcq: [
    { lv: 1, q: 'A ball is rolling to the right. A boy kicks it and it moves to the left. Which effect of a force is this?', o: ['The force changes the shape of the ball.', 'The force changes the direction of the ball.', 'The force makes a still object move.', 'The force has no effect.'], a: 1, hint: 'The ball was already moving.', why: 'The ball was already moving. The kick changed its direction. (If it had been still, the kick would have made a still object move.)', img: 'effects' },
    { lv: 1, q: 'Which force pulls a dropped ball towards the ground?', o: ['Frictional force', 'Magnetic force', 'Gravitational force', 'Elastic spring force'], a: 2, hint: 'It works on everything, everywhere on Earth.', why: 'Gravitational force pulls all objects towards the Earth. It gives objects their weight.', img: 'gravity' },
    { lv: 1, q: 'A spring is stretched and then let go. What does the spring do?', o: ['It stays stretched.', 'It pulls back to its original shape.', 'It becomes a magnet.', 'It gets heavier.'], a: 1, hint: 'Elastic spring force.', why: 'A stretched spring pulls back to its original shape because of the elastic spring force.', img: 'spring' },
    { lv: 1, q: 'Which action REDUCES friction?', o: ['Wearing rubber-soled shoes on a wet floor', 'Putting oil on a bicycle chain', 'Adding grooves to car tyres', 'Putting a rough mat under a rug'], a: 1, hint: 'Which one makes surfaces smoother?', why: 'Oil makes the surfaces smoother, so there is less friction and the chain moves easily. Rubber soles, tyre grooves and rough mats INCREASE friction to stop slipping.', img: 'friction' },
    { lv: 2, q: 'A toy car was pushed with the same force on three surfaces.<table class="q"><tr><th>Surface</th><th>Distance travelled</th></tr><tr><td>Carpet</td><td>40 cm</td></tr><tr><td>Wood</td><td>90 cm</td></tr><tr><td>Tiles</td><td>150 cm</td></tr></table>Which surface has the MOST friction?', o: ['Carpet', 'Wood', 'Tiles', 'All the same'], a: 0, hint: 'More friction = stops sooner = SHORTER distance.', why: 'More friction slows the car down faster, so it travels a shorter distance. Carpet (40 cm) has the most friction.', img: 'friction' },
    { lv: 2, q: 'An astronaut has a mass of 60 kg on Earth. Which is true when he is on the Moon?', o: ['His mass is less and his weight is less.', 'His mass is the same and his weight is less.', 'His mass and weight are the same.', 'His mass is less and his weight is the same.'], a: 1, hint: 'Mass = amount of matter. Weight = pull of gravity.', why: 'Mass is the amount of matter in him and never changes. Weight is the pull of gravity, which is weaker on the Moon, so his weight is less.', img: 'gravity' },
    { lv: 2, q: 'A spring stretches 2 cm with a 100 g load and 4 cm with a 200 g load. How much will it stretch with a 300 g load?', o: ['4 cm', '5 cm', '6 cm', '8 cm'], a: 2, hint: 'Every 100 g adds 2 cm.', why: 'Every 100 g adds 2 cm of stretch. 300 g gives 2 + 2 + 2 = 6 cm. More load = more extension.', img: 'spring' },
    { lv: 2, q: 'A parachute makes a skydiver fall more slowly. Why?', o: ['The parachute makes the skydiver lighter.', 'There is a large frictional force between the air and the parachute, which acts against the fall.', 'Gravity stops acting on the skydiver.', 'The parachute pushes the air down.'], a: 1, hint: 'Air rubbing against a big cloth.', why: 'The large parachute has a lot of friction with the air. This frictional force acts upwards, against the motion, so the fall is slower.', img: 'friction' }
  ],
  oe: [
    { q: 'A toy car was pushed with the same force on a carpet and on a tiled floor. It travelled 40 cm on the carpet and 150 cm on the tiles. Explain why it travelled a shorter distance on the carpet.', m: 2, img: 'friction', ans: ['The carpet is rougher, so there is more friction between the wheels and the carpet.', 'Friction acts against the motion and slows the car down faster, so it travels a shorter distance.'], decoy: ['The carpet pushes the car backwards.', 'The car was heavier on the carpet.'], kw: ['rough|more friction|greater friction', 'slow|against'] },
    { q: 'Ali hung loads on a spring. 100 g: 3 cm. 200 g: 6 cm. 300 g: 9 cm. (a) What is the relationship between the load and the extension? (b) Predict the extension for 500 g.', m: 2, img: 'spring', ans: ['(a) As the load increases, the extension of the spring increases.', '(b) With 500 g the extension will be 15 cm.'], decoy: ['(a) As the load increases, the extension decreases.', '(b) With 500 g the extension will be 12 cm.'], kw: ['increase', '15'] },
    { q: 'A rock weighs 60 N on Earth but only 10 N on the Moon. Explain why the rock weighs less on the Moon.', m: 2, img: 'gravity', ans: ['Weight is the gravitational force acting on the rock.', 'The gravitational force on the Moon is weaker than on Earth, so the rock weighs less. Its mass stays the same.'], decoy: ['The rock has less mass on the Moon.', 'There is no gravity on the Moon.'], kw: ['gravit', 'weaker|less|smaller'] }
  ]
});

// ---------- Content: blocks 13-18 ----------

BLOCKS.push({
  id: 'b13', theme: 'int', name: 'Food chains', icon: '🐸', lvl: 'P6',
  learn: [
    { h: 'A food chain', t: 'grass &rarr; grasshopper &rarr; frog &rarr; snake\nThe **arrow means "is eaten by"**. It shows **energy** flowing from the Sun to the plant to the animals.\n**Producer** = plant, makes its own food. Always first. **Consumers** = animals, eat other living things.', img: 'foodchain' },
    { h: 'Predator and prey', t: '**Predator** = hunts and eats another animal. **Prey** = is eaten.\nAn animal can be **both**: the frog eats the grasshopper (predator) and is eaten by the snake (prey).', img: 'foodchain' },
    { h: 'A food web', t: 'A **food web** = many food chains **joined together**, because most animals eat more than one kind of food.\nIf one animal disappears, follow the arrows to see who loses food (goes **down**) and who loses a predator (goes **up**).', img: 'foodweb' },
    { h: 'When numbers change', t: 'If the **frogs die**:\n- **Grasshoppers increase**: fewer frogs eat them.\n- **Snakes decrease**: less food for them.\nAlways give the **reason**: fewer predators, or less food.', img: 'foodchain' },
    { h: 'Organism, population, community', t: '**Organism** = one living thing.\n**Population** = a group of the **same kind**, living in the same place at the same time (all the frogs in a pond).\n**Community** = **many populations** living together (the frogs + the fish + the water plants).\n**Habitat** = the place where they live (garden, field, pond, seashore, tree, mangrove swamp).', img: 'opc' },
    { h: 'What affects survival', t: 'Living things need the right **temperature, light, water**, enough **food**, and they are affected by **other organisms** (producers, consumers, decomposers).\nWhen the environment becomes bad, organisms **adapt and survive**, **move away**, or **die**.', img: 'survive' }
  ],
  facts: [
    ['What does the arrow in a food chain mean?', 'Is eaten by (energy flows this way)'],
    ['A producer is...', 'A plant, it makes its own food, always first in the chain'],
    ['A population is...', 'A group of the same kind of organism living in the same place'],
    ['A community is...', 'Many different populations living together in one place'],
    ['If the environment becomes unfavourable, organisms...', 'Adapt and survive, move away, or die']
  ],
  mcq: [
    { lv: 1, q: 'grass &rarr; grasshopper &rarr; frog &rarr; snake<br>Which organism is the producer?', o: ['Grass', 'Grasshopper', 'Frog', 'Snake'], a: 0, hint: 'The one that makes its own food.', why: 'The producer makes its own food using light from the Sun. It is always first in the food chain. The others are consumers.', img: 'foodchain' },
    { lv: 1, q: 'What do the arrows in a food chain show?', o: ['Which animal is bigger', 'Energy flowing from the organism being eaten to the eater', 'Where the animals live', 'Which animal is faster'], a: 1, hint: 'Arrow = "is eaten by".', why: 'The arrow points from the food to the eater. Energy flows along the arrow.', img: 'foodchain' },
    { lv: 1, q: 'All the frogs living in one pond are called a...', o: ['Community', 'Habitat', 'Population', 'Food web'], a: 2, hint: 'Same kind, same place.', why: 'A population is a group of the SAME kind of organism in one place. A community is ALL the different populations together.', img: 'opc' },
    { lv: 1, q: 'grass &rarr; grasshopper &rarr; frog &rarr; snake<br>Which animal is both a predator and a prey?', o: ['Grass', 'Grasshopper', 'Frog', 'Snake'], a: 2, hint: 'It eats something AND gets eaten.', why: 'The frog eats the grasshopper (predator) and is eaten by the snake (prey). The grasshopper is only prey here; the snake is only a predator.', img: 'foodchain' },
    { lv: 2, q: 'grass &rarr; grasshopper &rarr; frog &rarr; snake<br>If all the frogs die, what happens to the grasshoppers and snakes at first?', o: ['Grasshoppers increase, snakes decrease', 'Grasshoppers decrease, snakes increase', 'Both increase', 'Both decrease'], a: 0, hint: 'Who lost a predator? Who lost their food?', why: 'Grasshoppers lose their predator, so more survive (increase). Snakes lose their food, so they decrease.', img: 'foodchain' },
    { lv: 2, q: 'The pond, all the fish in it, all the frogs and all the water plants together are called a...', o: ['Population', 'Community', 'Organism', 'Food chain'], a: 1, hint: 'Many populations together.', why: 'Many different populations (fish, frogs, water plants) living together make a community.', img: 'opc' },
    { lv: 2, q: 'A pond dried up during a long hot season. What is most likely to happen to the fish living in it?', o: ['They will grow bigger.', 'They will die or, if they can, move to another pond.', 'They will turn into frogs.', 'Nothing will change.'], a: 1, hint: 'Unfavourable environment: adapt, move or die.', why: 'When the environment becomes unfavourable, organisms adapt and survive, move away, or die. Fish cannot live without water.', img: 'survive' },
    { lv: 2, q: 'Why are plants important in every food chain?', o: ['They are the biggest living things.', 'They make food using light from the Sun, and all the animals get their energy from this food.', 'They eat the animals.', 'They give the animals water.'], a: 1, hint: 'Where does the energy start?', why: 'Plants (producers) make food using light energy from the Sun. Animals get energy by eating plants or animals that ate plants.', img: 'foodchain' }
  ],
  oe: [
    { q: 'grass &rarr; grasshopper &rarr; frog &rarr; snake<br>A disease killed most of the frogs in a field. Explain what would happen to the number of grasshoppers and the number of snakes.', m: 2, img: 'foodchain', ans: ['The number of grasshoppers would increase because there are fewer frogs to eat them.', 'The number of snakes would decrease because there are fewer frogs for them to eat.'], decoy: ['The number of grass plants would increase because there are fewer frogs.', 'The number of snakes would increase because they can eat the grasshoppers.'], kw: ['grasshopper', 'snake'] },
    { q: 'All the grass in a field was removed. Explain why the snakes in the field would eventually decrease in number.', m: 2, img: 'foodchain', ans: ['Without grass, the grasshoppers have no food and die, so the frogs have less food and die.', 'The snakes then have fewer frogs to eat, so their number decreases.'], decoy: ['The snakes eat grass, so they starve.', 'The snakes would increase because there is more space.'], kw: ['grasshopper|frog', 'less food|fewer|no food'] },
    { q: 'A pond dried up during a hot, dry season. State two things that could happen to the organisms living there.', m: 2, img: 'survive', ans: ['Some organisms may move away to another place with water.', 'Some organisms may die, or those that can adapt will survive.'], decoy: ['All the organisms will grow bigger.', 'The fish will learn to live on land.'], kw: ['move', 'die|adapt|survive'] }
  ]
});

BLOCKS.push({
  id: 'b14', theme: 'int', name: 'Adaptations', icon: '🦎', lvl: 'P6',
  learn: [
    { h: 'What is an adaptation?', t: 'An **adaptation** = a feature or a habit that helps a living thing **survive** in its habitat.\n**Structural** = a **body part** (webbed feet, thick fur, spines).\n**Behavioural** = something it **does** (hunting at night, huddling together, hibernating).', img: 'adapt' },
    { h: 'What adaptations are for', t: 'Every adaptation helps with one of these:\n- **cope with physical factors** (thick fur for cold, thick stem to store water)\n- **obtain food** (long beak, sharp claws)\n- **escape predators** (camouflage, spines, playing dead)\n- **reproduce** (bright feathers to attract a mate, seeds with wings to disperse).', img: 'adapt' },
    { h: 'Plant adaptations', t: '**Cactus**: leaves are **spines** (small surface area, less water lost by evaporation), thick stem **stores water**.\n**Water lily**: broad flat leaves **float** to get light.\n**Mangrove**: **breathing roots** stick out of the mud to get air.', img: 'plantadapt' },
    { h: 'Seeds are adapted too', t: 'The features of fruits and seeds are **structural adaptations** for dispersal.\nWings or hairs = wind. Fibrous husk that floats = water. Juicy or hooked = animals. Pod that bursts = splitting.', img: 'dispersal' },
    { h: 'Man\'s negative impact', t: '- **Deforestation** (cutting forests): animals lose their habitat and food, so they die or move away.\n- **Pollution** of land, water and air: harms living things.\n- **Global warming**: Earth gets hotter, ice melts, habitats change.\n- **Depleting resources**: using up fuels, trees, fish faster than they are replaced.', img: 'impact' },
    { h: 'Man\'s positive impact', t: '**Conservation**: protect habitats, nature reserves, reduce-reuse-recycle, save water and energy.\n**Reforestation**: plant new trees where forests were cut.', img: 'impact' }
  ],
  facts: [
    ['A structural adaptation is...', 'A body part that helps survival (webbed feet, thick fur)'],
    ['A behavioural adaptation is...', 'Something the animal does to survive (hunts at night, huddles)'],
    ['How do cactus spines help?', 'Small surface area, so less water is lost by evaporation'],
    ['3 negative impacts of man', 'Deforestation, pollution, global warming (also depleting resources)'],
    ['2 positive impacts of man', 'Conservation and reforestation']
  ],
  mcq: [
    { lv: 1, q: 'A desert plant has a thick fleshy stem and tiny spine-like leaves. How do these help it survive?', o: ['They attract more insects.', 'The stem stores water and the tiny leaves lose less water.', 'They make more food.', 'They help it float.'], a: 1, hint: 'Deserts are hot and dry.', why: 'The thick stem stores water. Tiny spine-like leaves have a small surface area, so less water is lost by evaporation. These are structural adaptations.', img: 'plantadapt' },
    { lv: 1, q: 'Owls hunt at night. Penguins huddle together in the cold. These are examples of...', o: ['Structural adaptations', 'Behavioural adaptations', 'Habitats', 'Food chains'], a: 1, hint: 'Things they DO, not body parts.', why: 'Behavioural adaptations are things an animal does. Structural adaptations are body features like thick fur or webbed feet.', img: 'adapt' },
    { lv: 1, q: 'Which is a NEGATIVE impact of humans on the environment?', o: ['Planting trees in a cleared forest', 'Recycling paper and plastic', 'Clearing a forest to build a factory', 'Protecting an animal habitat'], a: 2, hint: 'Which one destroys a habitat?', why: 'Clearing a forest (deforestation) destroys habitats and food sources, so animals die or move away. The other three are positive.', img: 'impact' },
    { lv: 1, q: 'A polar bear has thick fur and a thick layer of fat. What does this adaptation help it to do?', o: ['Attract a mate', 'Cope with the cold', 'Escape predators', 'Find food'], a: 1, hint: 'The Arctic is freezing.', why: 'Thick fur and fat keep heat in, so the bear can cope with the cold (a physical factor).', img: 'adapt' },
    { lv: 2, q: 'A duck has webbed feet. How does this structural adaptation help it survive?', o: ['It helps the duck fly faster.', 'It helps the duck move through water to find food and escape predators.', 'It keeps the duck warm.', 'It helps the duck attract a mate.'], a: 1, hint: 'Webbed feet work like paddles.', why: 'Webbed feet push against more water, so the duck swims well to find food and escape predators.', img: 'adapt' },
    { lv: 2, q: 'The flowers of plant X are large, brightly coloured and sweet-smelling. This adaptation helps the plant to...', o: ['store water', 'escape predators', 'reproduce, by attracting insects that carry pollen', 'make more food'], a: 2, hint: 'Which purpose needs insects?', why: 'Bright colour and smell attract insects. Insects carry pollen from anther to stigma (pollination), which helps the plant reproduce.', img: 'adapt' },
    { lv: 2, q: 'A forest is cleared to build houses. What will most likely happen to the animals that lived there?', o: ['They will get more food from the houses.', 'They will lose their habitat and food, so many will die or move away.', 'They will become bigger.', 'Nothing will change.'], a: 1, hint: 'Deforestation = loss of habitat.', why: 'The animals lose their homes and their food sources. Many die or move away, so their numbers fall.', img: 'impact' },
    { lv: 2, q: 'A fruit has a fibrous husk and can float on water. Which is true?', o: ['It is dispersed by wind.', 'Its husk is a structural adaptation for dispersal by water.', 'It is dispersed by splitting.', 'It cannot be dispersed.'], a: 1, hint: 'Think of a coconut.', why: 'A fibrous husk that floats is a structural adaptation that lets the fruit be carried away by water (like a coconut).', img: 'dispersal' }
  ],
  oe: [
    { q: 'A cactus grows in a hot, dry desert. Its leaves are tiny spines. Explain how the tiny spine-like leaves help the cactus survive.', m: 2, img: 'plantadapt', ans: ['The spine-like leaves have a smaller surface area.', 'So less water is lost from the plant by evaporation.'], decoy: ['The spines absorb water from the air.', 'The spines make more food for the cactus.'], kw: ['surface', 'less water|evaporat'] },
    { q: 'A forest was cleared to build houses. State one effect of this on the animals living in the forest and explain why.', m: 2, img: 'impact', ans: ['The animals lose their habitat and their source of food.', 'So many of them will die or move away, and their numbers decrease.'], decoy: ['The animals will get more food because there are more people.', 'The animals will grow bigger.'], kw: ['habitat|home|food', 'die|move'] },
    { q: 'Some fruits have hooks on their outside. Explain how this feature helps the plant.', m: 2, img: 'dispersal', ans: ['The hooks catch on the fur of animals passing by, so the seeds are carried far away from the parent plant.', 'The young plants then do not compete with the parent plant for light, water and space.'], decoy: ['The hooks protect the fruit from the rain.', 'The hooks help the fruit float on water.'], kw: ['animal|fur', 'compete|overcrowd|far'] }
  ]
});

BLOCKS.push({
  id: 'b15', theme: 'ene', name: 'Light', icon: '🔦', lvl: 'P4',
  learn: [
    { h: 'How we see', t: 'We see something when **light from it enters our eyes**.\nA **light source** gives out its own light: Sun, torch, lit candle, lamp.\nOther things (a book, the Moon, a mirror) do NOT make light. They **reflect** light into our eyes.', img: 'see' },
    { h: 'No light, no seeing', t: 'In a room with **no light**, no light can **reflect** off the objects into your eyes. You see nothing.\nExam answer: "There is no light, so no light can be reflected from the object into his eyes."', img: 'see' },
    { h: 'Shadows', t: 'Light travels in **straight lines**. It cannot bend around corners.\nWhen an object **blocks** the light, the space behind it gets no light. That dark patch is the **shadow**.\nThe shadow has the **same shape** as the side of the object facing the light.', img: 'shadow' },
    { h: 'Bigger or smaller shadow?', t: 'Object **nearer the light** = it blocks **more** light = **bigger** shadow.\nObject **nearer the screen** = **smaller** shadow.', img: 'shadowsize' },
    { h: 'Dark or faint shadow?', t: 'A material that lets **no** light through (wood, metal) makes a **dark** shadow.\nA material that lets **some** light through (tracing paper, thin plastic) makes a **faint** shadow.\nA material that lets **most** light through (clear glass) makes almost **no** shadow.', img: 'shadow' }
  ],
  facts: [
    ['We see an object when...', 'Light from it (source or reflected) enters our eyes'],
    ['Name 3 light sources', 'Sun, torch, lit candle (not the Moon, not a mirror)'],
    ['Light travels in...', 'Straight lines'],
    ['A shadow forms when...', 'Light is blocked by an object'],
    ['To make a shadow bigger, move the object...', 'Nearer to the light source']
  ],
  mcq: [
    { lv: 1, q: 'Why can we see the Moon at night even though it is not a light source?', o: ['The Moon gives out its own light.', 'The Moon reflects light from the Sun into our eyes.', 'The Moon is very hot.', 'Our eyes give out light.'], a: 1, hint: 'Reflect.', why: 'The Moon reflects sunlight. That reflected light enters our eyes, so we see it.', img: 'see' },
    { lv: 1, q: 'Which of these is a light source?', o: ['The Moon', 'A mirror', 'A lit candle', 'A white wall'], a: 2, hint: 'Which one makes its own light?', why: 'A lit candle gives out its own light. The Moon, a mirror and a wall only reflect light.', img: 'see' },
    { lv: 1, q: 'Which object will form the DARKEST shadow when light shines on it?', o: ['A clear glass sheet', 'A piece of tracing paper', 'A wooden board', 'A thin plastic bag'], a: 2, hint: 'Darkest = blocks ALL the light.', why: 'Wood lets no light through, so no light reaches the screen behind it: darkest shadow. Clear glass lets most light through: almost no shadow.', img: 'shadow' },
    { lv: 1, q: 'Ali can see his face in a mirror because...', o: ['the mirror is a light source', 'light from his face is reflected by the mirror into his eyes', 'the mirror absorbs light', 'his eyes give out light'], a: 1, hint: 'A mirror does not make light.', why: 'Light bounces off his face, hits the mirror and is reflected into his eyes. A mirror is not a light source.', img: 'see' },
    { lv: 2, q: 'A torch shines on a block, making a shadow on a screen. How can the shadow be made BIGGER?', o: ['Move the block nearer to the screen.', 'Move the block nearer to the torch.', 'Use a smaller block.', 'Move the torch further away.'], a: 1, hint: 'Nearer the light = blocks more light.', why: 'Nearer to the torch, the block blocks a larger part of the light, so a bigger area of the screen gets no light: a bigger shadow.', img: 'shadowsize' },
    { lv: 2, q: 'A torch was shone through three cards with holes in a straight line, and the light reached the screen. When the middle card was moved, no light reached the screen. What does this show?', o: ['Light bends around corners.', 'Light travels in straight lines.', 'Light is blocked by air.', 'Light can pass through cardboard.'], a: 1, hint: 'It only worked when the holes lined up.', why: 'Light only reached the screen when the holes were in a straight line. Light travels in straight lines and cannot bend around the moved card.', img: 'shadow' },
    { lv: 2, q: 'Ravi went into a room with no windows and switched off the light. Why could he not see anything?', o: ['His eyes stopped working.', 'There was no light to be reflected from the objects into his eyes.', 'The objects disappeared.', 'The room was too small.'], a: 1, hint: 'Seeing needs light entering the eyes.', why: 'With no light in the room, no light can be reflected from the objects into his eyes, so he sees nothing.', img: 'see' },
    { lv: 2, q: 'A toy was moved from near the torch to near the screen. What happens to its shadow?', o: ['It becomes bigger.', 'It becomes smaller.', 'It disappears.', 'It changes colour.'], a: 1, hint: 'Nearer the screen = ?', why: 'Nearer the screen, the toy blocks a smaller part of the light, so the shadow is smaller.', img: 'shadowsize' }
  ],
  oe: [
    { q: 'Mei placed a toy between a torch and a screen. When she moved the toy closer to the torch, the shadow became bigger. Explain why.', m: 2, img: 'shadowsize', ans: ['When the toy is nearer the torch, it blocks more light.', 'So a larger area of the screen does not receive light, and the shadow is bigger.'], decoy: ['The toy becomes bigger when it is nearer the torch.', 'The torch becomes brighter.'], kw: ['block', 'larger|bigger|more'] },
    { q: 'Ravi walked into a room with no windows and switched off the light. He could not see anything. Explain why.', m: 2, img: 'see', ans: ['There was no light in the room.', 'So no light could be reflected from the objects into his eyes.'], decoy: ['His eyes stopped working in the dark.', 'The objects were too far away.'], kw: ['no light', 'reflect|eye'] },
    { q: 'The Moon is not a light source. Explain why we can still see the Moon at night.', m: 2, img: 'see', ans: ['The Moon reflects light from the Sun.', 'The reflected light enters our eyes, so we can see the Moon.'], decoy: ['The Moon gives out its own light.', 'Our eyes give out light that reaches the Moon.'], kw: ['reflect', 'eye'] }
  ]
});

BLOCKS.push({
  id: 'b16', theme: 'ene', name: 'Heat', icon: '🌡️', lvl: 'P4',
  learn: [
    { h: 'Heat and temperature are different', t: '**Heat** is a form of **energy**.\n**Temperature** tells us **how hot** something is. We measure it with a **thermometer** in **&deg;C**.\nSources of heat: Sun, fire, stove, appliances, rubbing (friction), our body.', img: 'heat' },
    { h: 'Heat flows hot to cold', t: 'Heat always flows from the **hotter** object to the **colder** object, **until both are the same temperature**.\nAn ice cube in warm water: heat flows **from the water to the ice**. The water loses heat and cools; the ice gains heat and melts.\nNever write "cold flows". Only heat flows.', img: 'heatflow' },
    { h: 'Gain heat, lose heat', t: '**Gains heat** = temperature goes **up**. **Loses heat** = temperature goes **down**.\nGain heat: **expand** (get bigger), or change state (melt, boil, evaporate).\nLose heat: **contract** (get smaller), or change state (freeze, condense).', img: 'expand' },
    { h: 'Expansion in real life', t: 'Solids, liquids AND gases expand when heated.\nRailway tracks and bridges have **gaps** so the metal can expand on hot days without bending.\nA tight metal lid loosens under hot water because it **expands**.', img: 'expand' },
    { h: 'Conductors of heat', t: '**Good conductors**: **metals** (iron, steel, copper, aluminium). Heat passes through **quickly**. A metal spoon in hot soup gets hot.\n**Poor conductors**: **wood, plastic, rubber, air, cloth, styrofoam**. Heat passes **slowly**. Good for handles and keeping drinks hot or cold.', img: 'conductheat' }
  ],
  facts: [
    ['Heat is...', 'A form of energy'],
    ['Temperature is...', 'How hot something is, measured in degrees Celsius with a thermometer'],
    ['Heat flows from... to...', 'From the hotter object to the colder object, until both are the same temperature'],
    ['Gain heat = ? Lose heat = ?', 'Gain heat = expand. Lose heat = contract'],
    ['Good conductors of heat / poor conductors', 'Metals / wood, plastic, rubber, air']
  ],
  mcq: [
    { lv: 1, q: 'An ice cube is put into a glass of warm water. Which statement is correct?', o: ['Cold flows from the ice to the water.', 'Heat flows from the water to the ice.', 'Heat flows from the ice to the water.', 'No heat flows.'], a: 1, hint: 'Heat flows from HOT to COLD.', why: 'Heat always flows from the hotter object (water) to the colder one (ice). The water loses heat and cools; the ice gains heat and melts.', img: 'heatflow' },
    { lv: 1, q: 'Which statement about heat and temperature is correct?', o: ['Heat and temperature are the same thing.', 'Temperature is a form of energy.', 'Heat is a form of energy. Temperature is how hot an object is.', 'Temperature is measured in grams.'], a: 2, hint: 'One is energy, one is a measurement.', why: 'Heat is energy. Temperature is a measure of hotness in degrees Celsius.', img: 'heat' },
    { lv: 1, q: 'Which material is the most suitable for the handle of a cooking pot?', o: ['Copper', 'Iron', 'Steel', 'Plastic'], a: 3, hint: 'You do not want the handle to get hot.', why: 'Plastic is a poor conductor of heat, so heat from the pot does not travel quickly to your hand. Metals are good conductors and would burn you.', img: 'conductheat' },
    { lv: 1, q: 'A metal bar is heated. What happens to it?', o: ['It gets smaller.', 'It expands and gets slightly bigger.', 'It becomes lighter.', 'It turns into a liquid immediately.'], a: 1, hint: 'Gain heat = ?', why: 'When a solid gains heat, it expands (gets slightly bigger). When it loses heat, it contracts.', img: 'expand' },
    { lv: 2, q: 'Small gaps are left between sections of a metal railway track. Why?', o: ['To save metal', 'To let the metal expand on hot days without bending', 'To let rain drain away', 'To make the train slower'], a: 1, hint: 'Metal + hot day = ?', why: 'Metal expands when it gains heat. The gaps give it space to expand so the track does not bend.', img: 'expand' },
    { lv: 2, q: 'Three rods (copper, wood, plastic) of the same size had wax at one end. The other ends were heated at the same time. The wax on the copper rod melted first. Why?', o: ['Copper is the heaviest.', 'Copper is a good conductor of heat, so heat travelled along it the fastest.', 'Copper is the hottest material.', 'Wax sticks less to copper.'], a: 1, hint: 'Metal = good conductor.', why: 'Heat travels quickly through good conductors (metals). It reached the wax on the copper rod first.', img: 'conductheat' },
    { lv: 2, q: 'A cup of hot soup was left on a table. Its temperature dropped and then stayed at 30 &deg;C, the room temperature. Why did it stop cooling?', o: ['The soup ran out of heat.', 'The soup and the surroundings reached the same temperature, so heat stopped flowing out.', 'The room became hotter than the soup.', 'The cup is a conductor.'], a: 1, hint: 'Heat flows only when there is a difference.', why: 'Heat flows only while there is a temperature difference. Once the soup is at room temperature, it stops losing heat.', img: 'heatflow' },
    { lv: 2, q: 'A tight metal lid on a glass jar is loosened by running hot water over the lid. Why does this work?', o: ['The lid gains heat and expands, becoming slightly bigger.', 'The lid loses heat and contracts.', 'The water makes the lid slippery.', 'The glass jar expands more than the lid.'], a: 0, hint: 'Hot water on metal.', why: 'The metal lid gains heat and expands, so it becomes a little bigger and loosens.', img: 'expand' }
  ],
  oe: [
    { q: 'Ali left a metal spoon in a bowl of hot soup. After a minute, the handle of the spoon felt hot. Explain why.', m: 2, img: 'conductheat', ans: ['Metal is a good conductor of heat.', 'Heat from the hot soup was conducted quickly through the spoon to the handle.'], decoy: ['The handle produced its own heat.', 'Metal is a poor conductor of heat.'], kw: ['good conductor|conductor', 'conducted|soup|through|travel'] },
    { q: 'Ice cubes were added to a glass of orange juice. The juice became colder. Explain, in terms of heat, why the juice became colder.', m: 2, img: 'heatflow', ans: ['Heat flowed from the warmer juice to the colder ice.', 'The juice lost heat, so its temperature decreased.'], decoy: ['Cold flowed from the ice into the juice.', 'The ice gave heat to the juice.'], kw: ['juice to|to the ice|from the juice|warmer', 'lost heat|loses heat|temperature'] },
    { q: 'A metal ball can pass through a metal ring. After the ball is heated, it cannot pass through the ring. Explain why.', m: 2, img: 'expand', ans: ['The metal ball gained heat and expanded.', 'So it became bigger than the hole in the ring and could not pass through.'], decoy: ['The ring contracted when the ball was heated.', 'The ball melted and changed shape.'], kw: ['gain|expand', 'bigger|larger'] }
  ]
});

BLOCKS.push({
  id: 'b17', theme: 'ene', name: 'Photosynthesis', icon: '🌞', lvl: 'P6',
  learn: [
    { h: 'The Sun starts everything', t: 'The **Sun** is our **primary source** of energy (light and heat).\nPlants trap **light energy** to make food. Animals eat plants or other animals. So almost all energy in living things can be traced back to the Sun.', img: 'energysun' },
    { h: 'Photosynthesis: 3 in, 2 out', t: 'In the **green leaves**, plants make food.\n**IN**: light energy + **water** (from roots) + **carbon dioxide** (from air).\n**OUT**: **sugar** (food, stored as starch) + **oxygen** (into the air).\nIt only happens in **light**. More light = more food and more oxygen.', img: 'photo' },
    { h: 'Plants make food, animals eat food', t: '**Plants** make their own food by photosynthesis.\n**Animals** cannot make food. They get energy by **eating** plants or other animals.\nOnly the **green** parts of a leaf make food (they have the green substance that traps light).', img: 'photo2' },
    { h: 'Respiration: energy from food', t: '**Respiration** releases **energy** from food, using **oxygen**. Carbon dioxide is given out.\n**ALL living things** respire, **all the time**, day and night. Plants too!\nThe energy is used for life processes: moving, growing, staying warm.', img: 'resp2' },
    { h: 'Do not mix them up', t: '**Photosynthesis**: only in light, makes food, gives out oxygen. Plants only.\n**Respiration**: all the time, releases energy from food, gives out carbon dioxide. All living things.\nA plant in the dark still respires, but it cannot make food, so it becomes weak.', img: 'resp2' }
  ],
  facts: [
    ['3 things a plant needs to make food', 'Light, water, carbon dioxide'],
    ['2 things photosynthesis makes', 'Sugar (food) and oxygen'],
    ['Respiration is...', 'Releasing energy from food using oxygen (gives out carbon dioxide)'],
    ['Which living things respire, and when?', 'ALL living things, ALL the time (plants too)'],
    ['Our primary source of energy', 'The Sun']
  ],
  mcq: [
    { lv: 1, q: 'Which of these is NOT needed by a plant to make food?', o: ['Light', 'Water', 'Carbon dioxide', 'Oxygen'], a: 3, hint: 'One of these is made, not used.', why: 'Photosynthesis needs light, water and carbon dioxide. Oxygen is PRODUCED by photosynthesis.', img: 'photo' },
    { lv: 1, q: 'Which living things carry out respiration?', o: ['Animals only', 'Plants only', 'Plants and animals only', 'All living things, including fungi and bacteria'], a: 3, hint: 'Every living thing needs energy.', why: 'Every living thing needs energy, so every living thing respires (releases energy from food using oxygen), all the time.', img: 'resp2' },
    { lv: 1, q: 'A water plant in bright light gives out bubbles of gas. Which gas is it?', o: ['Carbon dioxide', 'Nitrogen', 'Oxygen', 'Water vapour'], a: 2, hint: 'Photosynthesis OUT.', why: 'In light, the plant photosynthesises and gives out oxygen.', img: 'photo2' },
    { lv: 1, q: 'A caterpillar eats a leaf. Where did the energy in the leaf originally come from?', o: ['The soil', 'Water', 'Light energy from the Sun', 'The caterpillar'], a: 2, hint: 'Trace it back.', why: 'The plant trapped light energy from the Sun and stored it in food. Eating the leaf passes this energy to the caterpillar.', img: 'energysun' },
    { lv: 2, q: 'A leaf with green and white patches was kept in sunlight, then tested for starch (food). Only the green parts had starch. Why?', o: ['The white parts had no water.', 'Only the green parts can trap light to make food.', 'The white parts made food but lost it.', 'The white parts had no roots.'], a: 1, hint: 'Which colour traps light?', why: 'Only the green parts of the leaf have the green substance that traps light energy for photosynthesis. White parts cannot make food.', img: 'photo2' },
    { lv: 2, q: 'A water plant in a beaker gave out 5 bubbles per minute in dim light and 20 bubbles per minute in bright light. Why?', o: ['The plant respired faster in bright light.', 'In bright light the plant made food faster, so it gave out more oxygen.', 'The water became hotter.', 'The plant received less carbon dioxide.'], a: 1, hint: 'More light = faster photosynthesis.', why: 'More light means faster photosynthesis, so more oxygen bubbles are given out.', img: 'photo' },
    { lv: 2, q: 'Which statement is correct?', o: ['Photosynthesis happens all the time; respiration only in the day.', 'Photosynthesis happens only in light; respiration happens all the time.', 'Plants do not respire because they make food.', 'Respiration makes food for the plant.'], a: 1, hint: 'Which one needs light?', why: 'Photosynthesis needs light. Respiration (releasing energy from food) never stops. Plants do both.', img: 'resp2' },
    { lv: 2, q: 'A potted plant was kept in a dark cupboard for two weeks and watered daily. Its leaves turned yellow and it became weak. Why?', o: ['It had too much water.', 'It could not make food without light, so it had no energy.', 'It could not take in oxygen.', 'It was too cold.'], a: 1, hint: 'No light = no ?', why: 'No light means no photosynthesis, so no food is made. Without food there is no energy for growth, and the plant becomes weak.', img: 'photo' }
  ],
  oe: [
    { q: 'Mei kept a healthy potted plant in a dark cupboard for two weeks. It was watered every day. After two weeks the plant was weak and its leaves were yellow. Explain why the plant became weak.', m: 2, img: 'photo', ans: ['Without light, the plant could not carry out photosynthesis to make food.', 'Without food, it could not release enough energy for its life processes, so it became weak.'], decoy: ['The plant did not have enough water.', 'The plant could not respire in the dark.'], kw: ['light|photosynthes|food', 'energy'] },
    { q: 'A water plant in a beaker gave out 20 bubbles per minute in bright light and 5 bubbles per minute in dim light. (a) Name the gas in the bubbles. (b) Explain the difference in the number of bubbles.', m: 2, img: 'photo', ans: ['(a) The gas is oxygen.', '(b) In bright light the plant photosynthesises faster, so it produces more oxygen.'], decoy: ['(a) The gas is carbon dioxide.', '(b) In bright light the plant respires more.'], kw: ['oxygen', 'photosynthes|faster|more light'] },
    { q: 'Plants make their own food, but they still respire. Explain why plants need to respire.', m: 2, img: 'resp2', ans: ['Respiration releases energy from the food.', 'Plants need this energy to carry out life processes such as growing.'], decoy: ['Respiration makes food for the plant.', 'Plants only respire at night.'], kw: ['energy', 'grow|life process|alive|move'] }
  ]
});

BLOCKS.push({
  id: 'b18', theme: 'ene', name: 'Energy', icon: '⚡', lvl: 'P6',
  learn: [
    { h: '6 forms of energy', t: '- **Kinetic**: moving things.\n- **Potential**: **stored** energy: a battery, food, a stretched spring or rubber band, an object held up high.\n- **Light**, **heat**, **sound**, **electrical**.', img: 'forms' },
    { h: 'Potential and kinetic', t: 'A ball at the **top** of a slide has the most **potential** energy (high up, not moving).\nAs it slides down, potential energy changes into **kinetic** energy. At the **bottom** it is fastest: most kinetic energy.\nA girl on a swing: highest point = most potential, lowest point = most kinetic.', img: 'kepe' },
    { h: 'Energy is converted', t: 'Energy changes from one form to another. Write it as a chain with arrows.\n- Torch: **potential** (battery) &rarr; **electrical** &rarr; **light + heat**.\n- Fan: electrical &rarr; kinetic (+ sound, heat).\n- Solar panel: **light** &rarr; **electrical**.\n- Running: potential (food) &rarr; kinetic + heat.', img: 'convert' },
    { h: 'Most energy comes from the Sun', t: 'Plants trap light from the Sun and store it in **food**. Animals eat plants. We eat both.\nCoal and oil formed from living things long ago. Wind is made by the Sun heating the air.\nSo most of our energy can be traced back to the **Sun**.', img: 'energysun' },
    { h: 'Conserve energy', t: 'Fuels like coal, oil and gas can be **used up** (depleted). Burning them causes **pollution**.\nSo: **switch off** appliances not in use, use energy-saving bulbs, use **renewable** energy (solar, wind, water).', img: 'conserve' }
  ],
  facts: [
    ['6 forms of energy', 'Kinetic, potential, light, heat, sound, electrical'],
    ['Potential energy is stored in...', 'A battery, food, a stretched spring, an object held up high'],
    ['Energy conversion in a torch', 'Potential (battery) to electrical to light and heat'],
    ['Where does most of our energy come from?', 'The Sun'],
    ['2 reasons to conserve energy', 'Fuels can be used up; burning fuels causes pollution']
  ],
  mcq: [
    { lv: 1, q: 'A stretched rubber band is held still. What form of energy does it have?', o: ['Kinetic energy', 'Potential energy', 'Sound energy', 'Electrical energy'], a: 1, hint: 'Stored, ready to go.', why: 'A stretched (or squashed) object stores potential energy. When let go, it changes to kinetic energy as it moves.', img: 'forms' },
    { lv: 1, q: 'Which energy conversion takes place in a torch when it is switched on?', o: ['light, electrical, potential', 'potential (battery), electrical, light and heat', 'heat, light, electrical', 'kinetic, light'], a: 1, hint: 'Start with the battery.', why: 'The battery stores potential energy. It becomes electrical energy in the wires, then light (and some heat) in the bulb.', img: 'convert' },
    { lv: 1, q: 'A girl on a swing is at the highest point. Which is true?', o: ['She has the most kinetic energy.', 'She has the most potential energy.', 'She has no energy.', 'She has the most sound energy.'], a: 1, hint: 'High up and (for a moment) not moving.', why: 'At the top she is high up and momentarily still: most potential energy. At the bottom she is fastest: most kinetic energy.', img: 'kepe' },
    { lv: 1, q: 'Which energy conversion takes place in a solar panel?', o: ['heat to electrical', 'light to electrical', 'electrical to light', 'kinetic to electrical'], a: 1, hint: 'Solar = Sun light.', why: 'Solar panels convert light energy from the Sun into electrical energy.', img: 'convert' },
    { lv: 2, q: 'Which statement about the Sun is correct?', o: ['The Sun gives energy only to plants.', 'Most of our energy, including the energy in food and in coal, comes from the Sun.', 'The Sun is not needed for wind energy.', 'Batteries get energy from the Sun directly.'], a: 1, hint: 'Trace food and coal back.', why: 'Plants trap the Sun\'s light to make food; animals eat plants; coal and oil formed from living things long ago; wind is made by the Sun heating the air.', img: 'energysun' },
    { lv: 2, q: 'Which action helps to conserve energy?', o: ['Leaving the lights on when leaving a room', 'Switching off the fan when nobody is in the room', 'Opening the fridge door for a long time', 'Leaving the TV on all night'], a: 1, hint: 'Use less electricity.', why: 'Switching off appliances not in use reduces the electricity used, so less fuel is burnt. Fuels can be used up and burning them pollutes.', img: 'conserve' },
    { lv: 2, q: 'A boy eats breakfast and then runs a race. Which energy conversion takes place in his body?', o: ['kinetic to potential', 'potential (in food) to kinetic and heat', 'light to kinetic', 'electrical to kinetic'], a: 1, hint: 'Food stores energy.', why: 'Food stores potential energy. Respiration releases it, and the boy converts it to kinetic energy (movement) and heat (he feels hot).', img: 'convert' },
    { lv: 2, q: 'An electric fan is switched on. It turns and makes a humming sound. Which conversion is correct?', o: ['kinetic to electrical', 'electrical to kinetic and sound', 'sound to electrical', 'light to kinetic'], a: 1, hint: 'What goes IN? What comes OUT?', why: 'Electrical energy goes in. It is converted to kinetic energy (the blades turn) and sound energy (the hum), plus some heat.', img: 'convert' }
  ],
  oe: [
    { q: 'A wind turbine turns when the wind blows and produces electricity. Describe the energy conversion that takes place.', m: 2, img: 'convert', ans: ['Kinetic energy of the moving air (wind) is converted to kinetic energy of the turning turbine.', 'This is then converted to electrical energy.'], decoy: ['Electrical energy is converted to kinetic energy of the wind.', 'Light energy is converted to electrical energy.'], kw: ['kinetic', 'electrical'] },
    { q: 'A boy eats rice and then runs. Trace the energy from the Sun to the running boy.', m: 3, img: 'energysun', ans: ['Light energy from the Sun is trapped by the rice plant.', 'The energy is stored as potential energy in the food.', 'The boy eats the food and converts the potential energy into kinetic energy when he runs.'], decoy: ['The boy absorbs light energy from the Sun directly.', 'The rice gets its energy from the soil.'], kw: ['light|sun', 'potential|stored|food', 'kinetic'] },
    { q: 'Most electricity in Singapore is made by burning natural gas, a fossil fuel. Give two reasons why we should conserve electricity.', m: 2, img: 'conserve', ans: ['Fossil fuels can be used up (depleted) and cannot be replaced quickly.', 'Burning fossil fuels causes air pollution and global warming.'], decoy: ['Electricity makes the air cooler.', 'Electricity is made from sunlight, so it never runs out.'], kw: ['used up|deplet|run out', 'pollut|warming'] }
  ]
});

// ---------- Science Obby engine ----------
(function () {
  'use strict';
  var $ = function (s, r) { return (r || document).querySelector(s); };
  var $$ = function (s, r) { return Array.prototype.slice.call((r || document).querySelectorAll(s)); };
  function esc(s) { return String(s == null ? '' : s).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;').replace(/"/g, '&quot;'); }
  function shuffle(a) { a = a.slice(); for (var i = a.length - 1; i > 0; i--) { var j = Math.floor(Math.random() * (i + 1)); var t = a[i]; a[i] = a[j]; a[j] = t; } return a; }
  function pick(a, n) { return shuffle(a).slice(0, n); }
  function pad2(n) { return (n < 10 ? '0' : '') + n; }
  function mmss(s) { s = Math.max(0, Math.round(s)); return Math.floor(s / 60) + ':' + pad2(s % 60); }
  function md(t) {
    var lines = String(t).split('\n'), out = '', inList = false;
    lines.forEach(function (ln) {
      var isLi = /^- /.test(ln);
      if (isLi && !inList) { out += '<ul>'; inList = true; }
      if (!isLi && inList) { out += '</ul>'; inList = false; }
      var html = ln.replace(/^- /, '').replace(/\*\*(.+?)\*\*/g, '<b class="kw">$1</b>');
      out += isLi ? '<li>' + html + '</li>' : '<p>' + html + '</p>';
    });
    if (inList) out += '</ul>';
    return out;
  }
  function plain(html) { var d = document.createElement('div'); d.innerHTML = String(html).replace(/<\/?(td|th|tr|table|br|p|li|ul)[^>]*>/gi, ' '); return (d.textContent || '').replace(/\s+/g, ' ').trim(); }
  function pic(key, big) { return IMG[key] ? '<div class="pic' + (big ? ' big' : '') + '">' + IMG[key] + '</div>' : ''; }
  function shade(hex, amt) {
    var n = parseInt(hex.slice(1), 16), r = n >> 16, g = (n >> 8) & 255, b = n & 255;
    function f(c) { c = amt < 0 ? c * (1 + amt) : c + (255 - c) * amt; return Math.max(0, Math.min(255, Math.round(c))); }
    return '#' + ((1 << 24) + (f(r) << 16) + (f(g) << 8) + f(b)).toString(16).slice(1);
  }
  var REDUCED = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  // ---------- state ----------
  var KEY = 'sciobby.v1';
  var S = load() || {};
  var DEF = { av: 0, name: '', coins: 0, streak: 0, bestStreak: 0, mute: false, blocks: {}, fixit: [], arenaA: [], arenaB: [], started: false };
  Object.keys(DEF).forEach(function (k) { if (S[k] === undefined) S[k] = DEF[k]; });
  function save() { try { localStorage.setItem(KEY, JSON.stringify(S)); } catch (e) { } }
  function load() { try { var j = localStorage.getItem(KEY); return j ? JSON.parse(j) : null; } catch (e) { return null; } }
  function blockOf(id) { for (var i = 0; i < BLOCKS.length; i++) if (BLOCKS[i].id === id) return BLOCKS[i]; return null; }
  function prog(id) { if (!S.blocks[id]) S.blocks[id] = { stars: 0, first: 0, runs: 0, mcqC: 0, mcqT: 0, oeM: 0, oeT: 0 }; return S.blocks[id]; }
  function nextBlockId() { for (var i = 0; i < BLOCKS.length; i++) { var p = S.blocks[BLOCKS[i].id]; if (!p || !p.runs) return BLOCKS[i].id; } for (var j = 0; j < BLOCKS.length; j++) { if (S.blocks[BLOCKS[j].id].stars < 3) return BLOCKS[j].id; } return BLOCKS[0].id; }
  var ISLANDS = [
    { id: 'div', name: 'Diversity Island', e: '🌿', sub: 'Living things and materials' },
    { id: 'cyc', name: 'Cycles Island', e: '🔁', sub: 'Life cycles, matter, reproduction, water' },
    { id: 'sys', name: 'Systems Island', e: '⚙️', sub: 'Plants, digestion, breathing, circuits' },
    { id: 'int', name: 'Interactions Island', e: '🧲', sub: 'Magnets, forces, food chains, adaptations' },
    { id: 'ene', name: 'Energy Island', e: '⚡', sub: 'Light, heat, photosynthesis, energy' }
  ];
  var THEMECOL = { div: '#2E9E4F', cyc: '#2F7FD6', sys: '#EF8A2A', int: '#8A5CD6', ene: '#D9A400' };
  var AVS = [
    { n: 'Noob', skin: '#F5D06B', shirt: '#2F7FD6', pants: '#2E9E4F', hat: 'none' },
    { n: 'Ninja', skin: '#F0C9A0', shirt: '#2B2B2B', pants: '#2B2B2B', hat: 'band' },
    { n: 'Knight', skin: '#EAC9A5', skinDark: true, shirt: '#9AA5B8', pants: '#5E6884', hat: 'helmet' },
    { n: 'Astro', skin: '#F0C9A0', shirt: '#F4F4F4', pants: '#DDE3EA', hat: 'visor' },
    { n: 'Zombie', skin: '#8FD08A', shirt: '#6B4F9E', pants: '#3B2E5A', hat: 'cap' }
  ];

  // ---------- sounds ----------
  var AC = null;
  function ctx() { if (!AC) { try { AC = new (window.AudioContext || window.webkitAudioContext)(); } catch (e) { AC = null; } } if (AC && AC.state === 'suspended') { try { AC.resume(); } catch (e) { } } return AC; }
  function tone(f, t0, dur, type, vol, f2) {
    var c = ctx(); if (!c) return;
    var o = c.createOscillator(), g = c.createGain();
    o.type = type || 'square'; o.frequency.setValueAtTime(f, t0); if (f2) o.frequency.exponentialRampToValueAtTime(f2, t0 + dur);
    g.gain.setValueAtTime(0.0001, t0); g.gain.exponentialRampToValueAtTime(vol || 0.12, t0 + 0.01); g.gain.exponentialRampToValueAtTime(0.0001, t0 + dur);
    o.connect(g); g.connect(c.destination); o.start(t0); o.stop(t0 + dur + 0.02);
  }
  function snd(name) {
    if (S.mute) return; var c = ctx(); if (!c) return; var t = c.currentTime;
    if (name === 'coin') { tone(988, t, 0.08, 'square', 0.1); tone(1319, t + 0.08, 0.2, 'square', 0.1); }
    else if (name === 'jump') { tone(300, t, 0.18, 'square', 0.08, 700); }
    else if (name === 'fall') { tone(500, t, 0.45, 'sawtooth', 0.1, 120); }
    else if (name === 'wrong') { tone(220, t, 0.15, 'sawtooth', 0.08); tone(180, t + 0.15, 0.2, 'sawtooth', 0.08); }
    else if (name === 'tick') { tone(1500, t, 0.03, 'square', 0.04); }
    else if (name === 'fanfare') { [523, 659, 784, 1047].forEach(function (f, i) { tone(f, t + i * 0.12, 0.25, 'triangle', 0.14); }); tone(1319, t + 0.5, 0.5, 'triangle', 0.14); }
    else if (name === 'click') { tone(800, t, 0.04, 'square', 0.04); }
  }

  // ---------- read aloud ----------
  var VOICE = null;
  function pickVoice() {
    if (!('speechSynthesis' in window)) return;
    var vs = speechSynthesis.getVoices() || [];
    var pref = ['en-SG', 'en-GB', 'en-AU', 'en-US', 'en'];
    for (var i = 0; i < pref.length && !VOICE; i++) for (var j = 0; j < vs.length; j++) if (vs[j].lang && vs[j].lang.replace('_', '-').indexOf(pref[i]) === 0) { VOICE = vs[j]; break; }
  }
  if ('speechSynthesis' in window) { pickVoice(); speechSynthesis.onvoiceschanged = pickVoice; }
  function speak(text) {
    if (!('speechSynthesis' in window)) { toast('Read aloud is not available here'); return; }
    var u = new SpeechSynthesisUtterance(text); u.lang = 'en-GB'; u.rate = 0.9; if (VOICE) u.voice = VOICE;
    speechSynthesis.cancel(); speechSynthesis.speak(u);
  }
  function hush() { if ('speechSynthesis' in window) speechSynthesis.cancel(); }

  // ---------- timer ----------
  var TM = { iv: null, total: 0, left: 0, onEnd: null, lava: true };
  function startTimer(sec, onEnd, opts) {
    stopTimer(); opts = opts || {};
    TM.total = sec; TM.left = sec; TM.onEnd = onEnd; TM.lava = opts.lava !== false;
    paintTimer();
    TM.iv = setInterval(function () {
      TM.left--; paintTimer();
      if (TM.left <= 10 && TM.left > 0 && TM.total <= 300) snd('tick');
      if (TM.left <= 0) { stopTimer(); if (TM.onEnd) TM.onEnd(); }
    }, 1000);
  }
  function stopTimer() { if (TM.iv) clearInterval(TM.iv); TM.iv = null; }
  function paintTimer() {
    var bar = $('#tbar'), lab = $('#tlab'); var frac = TM.total ? TM.left / TM.total : 1;
    if (bar) { bar.style.width = Math.max(0, frac * 100) + '%'; bar.parentNode.classList.toggle('urgent', frac < 0.2); }
    if (lab) lab.textContent = mmss(TM.left);
    if (TM.lava) setLava(1 - frac);
  }

  // ---------- scene ----------
  var SC = { mode: 'map', n: 0, idx: 0, states: [], theme: 'cyc', label: '', icon: '', geom: null, lava: 0 };
  function scene(o) { for (var k in o) SC[k] = o[k]; drawScene(); }
  function cube(x, y, s, col, o) {
    o = o || {}; var d = s * 0.3, top = o.top || shade(col, 0.35), side = shade(col, -0.3);
    var str = '<polygon points="' + x + ',' + y + ' ' + (x + d) + ',' + (y - d) + ' ' + (x + s + d) + ',' + (y - d) + ' ' + (x + s) + ',' + y + '" fill="' + top + '"/>';
    str += '<polygon points="' + (x + s) + ',' + y + ' ' + (x + s + d) + ',' + (y - d) + ' ' + (x + s + d) + ',' + (y - d + s) + ' ' + (x + s) + ',' + (y + s) + '" fill="' + side + '"/>';
    str += '<rect x="' + x + '" y="' + y + '" width="' + s + '" height="' + s + '" fill="' + col + '"/>';
    if (o.crack) str += '<path d="M' + (x + s * 0.2) + ' ' + (y + s * 0.15) + ' l' + (s * 0.25) + ' ' + (s * 0.3) + ' l-' + (s * 0.15) + ' ' + (s * 0.2) + ' l' + (s * 0.3) + ' ' + (s * 0.3) + '" fill="none" stroke="#3a1a10" stroke-width="3"/>';
    if (o.glow) str += '<rect x="' + (x - 3) + '" y="' + (y - d - 3) + '" width="' + (s + d + 6) + '" height="' + (s + d + 6) + '" rx="6" fill="none" stroke="#FFF176" stroke-width="4" opacity=".9"/>';
    return str;
  }
  function avatarSVG(i, h) {
    var c = AVS[i] || AVS[0], u = h / 12, s = '';
    var hx = -2 * u, hy = -12 * u; // head 4u square
    s += '<rect x="' + (-1.6 * u) + '" y="' + (-8 * u) + '" width="' + (3.2 * u) + '" height="' + (4.4 * u) + '" fill="' + c.shirt + '"/>';
    s += '<rect x="' + (-2.6 * u) + '" y="' + (-7.8 * u) + '" width="' + u + '" height="' + (4 * u) + '" fill="' + c.skin + '"/><rect x="' + (1.6 * u) + '" y="' + (-7.8 * u) + '" width="' + u + '" height="' + (4 * u) + '" fill="' + c.skin + '"/>';
    s += '<rect x="' + (-1.6 * u) + '" y="' + (-3.6 * u) + '" width="' + (1.5 * u) + '" height="' + (3.6 * u) + '" fill="' + c.pants + '"/><rect x="' + (0.1 * u) + '" y="' + (-3.6 * u) + '" width="' + (1.5 * u) + '" height="' + (3.6 * u) + '" fill="' + c.pants + '"/>';
    s += '<rect x="' + hx + '" y="' + hy + '" width="' + (4 * u) + '" height="' + (4 * u) + '" rx="' + (0.4 * u) + '" fill="' + c.skin + '"/>';
    s += '<rect x="' + (-1.2 * u) + '" y="' + (-10.6 * u) + '" width="' + (0.7 * u) + '" height="' + (0.9 * u) + '" fill="#1E2A44"/><rect x="' + (0.5 * u) + '" y="' + (-10.6 * u) + '" width="' + (0.7 * u) + '" height="' + (0.9 * u) + '" fill="#1E2A44"/>';
    s += '<path d="M' + (-0.9 * u) + ' ' + (-9.1 * u) + ' q' + (0.9 * u) + ' ' + (0.8 * u) + ' ' + (1.8 * u) + ' 0" fill="none" stroke="#1E2A44" stroke-width="' + (0.3 * u) + '" stroke-linecap="round"/>';
    if (c.hat === 'band') s += '<rect x="' + hx + '" y="' + (-11.2 * u) + '" width="' + (4 * u) + '" height="' + (1.6 * u) + '" fill="#2B2B2B"/><rect x="' + (-1.2 * u) + '" y="' + (-10.6 * u) + '" width="' + (0.7 * u) + '" height="' + (0.9 * u) + '" fill="#fff"/><rect x="' + (0.5 * u) + '" y="' + (-10.6 * u) + '" width="' + (0.7 * u) + '" height="' + (0.9 * u) + '" fill="#fff"/>';
    if (c.hat === 'helmet') s += '<rect x="' + (hx - 0.3 * u) + '" y="' + (hy - 0.6 * u) + '" width="' + (4.6 * u) + '" height="' + (2.2 * u) + '" rx="' + (0.5 * u) + '" fill="#7C8AA3"/>';
    if (c.hat === 'visor') s += '<rect x="' + (hx - 0.4 * u) + '" y="' + (hy - 0.5 * u) + '" width="' + (4.8 * u) + '" height="' + (5 * u) + '" rx="' + (1.2 * u) + '" fill="none" stroke="#DDE3EA" stroke-width="' + (0.6 * u) + '"/>';
    if (c.hat === 'cap') s += '<rect x="' + (hx - 0.2 * u) + '" y="' + (hy - 0.8 * u) + '" width="' + (4.4 * u) + '" height="' + (1.4 * u) + '" rx="' + (0.3 * u) + '" fill="#E0503A"/><rect x="' + (hx + 2.4 * u) + '" y="' + (hy - 0.2 * u) + '" width="' + (2.6 * u) + '" height="' + (0.6 * u) + '" fill="#E0503A"/>';
    return s;
  }
  function avatarCard(i) { return '<svg viewBox="-30 -66 60 72">' + avatarSVG(i, 60) + '</svg>'; }
  function coinSVG(x, y, r) { return '<g class="coin"><circle cx="' + x + '" cy="' + y + '" r="' + r + '" fill="#FFC72C" stroke="#C8901A" stroke-width="3"/><text x="' + x + '" y="' + (y + r * 0.45) + '" text-anchor="middle" font-size="' + (r * 1.3) + '" font-weight="700" fill="#8A5A00">$</text></g>'; }
  function layout(W, H, n) {
    var pad = 22, per = Math.min(n, 8), rows = Math.ceil(n / per), yG = H * 0.8;
    var s = Math.min(70, (W - 2 * pad) / (per + 1.6), (yG - 24) / ((rows - 1) * 1.95 + 2.7));
    var rowH = s * 1.95, xs = per > 1 ? (W - 2 * pad - s * 1.3) / (per - 1) : 0, pos = [];
    var climb = rows === 1 && n > 1 ? Math.max(0, Math.min(s * 0.6, (yG - s - 2.2 * s - 14) / (n - 1))) : 0;
    for (var i = 0; i < n; i++) {
      var r = Math.floor(i / per), c = i % per; if (r % 2 === 1) c = per - 1 - c;
      var x = per > 1 ? pad + c * xs : (W - s) / 2, y = yG - s - r * rowH - i * climb;
      pos.push({ x: x, y: y });
    }
    return { s: s, pos: pos, yG: yG, rows: rows, per: per };
  }
  function drawScene() {
    var el = $('#scene'); if (!el) return;
    var W = Math.max(200, el.clientWidth), H = Math.max(120, el.clientHeight), mob = H < 220;
    var col = THEMECOL[SC.theme] || '#2F7FD6', str = '';
    str += '<defs><linearGradient id="lg" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#FFB300"/><stop offset=".35" stop-color="#FF6A2C"/><stop offset="1" stop-color="#B71C1C"/></linearGradient></defs>';
    str += '<circle cx="' + (W - 50) + '" cy="46" r="26" fill="#FFE066" opacity=".9"/>';
    [[0.12, 0.12, 1], [0.55, 0.06, 0.8], [0.8, 0.22, 0.6]].forEach(function (c, i) {
      var cx = W * c[0], cy = H * c[1] + 10, k = 26 * c[2] * (mob ? 0.6 : 1);
      str += '<g class="cloud c' + i + '"><ellipse cx="' + cx + '" cy="' + cy + '" rx="' + (k * 1.8) + '" ry="' + k + '" fill="var(--cloud)"/><ellipse cx="' + (cx + k * 1.2) + '" cy="' + (cy - k * 0.3) + '" rx="' + (k * 1.3) + '" ry="' + (k * 0.9) + '" fill="var(--cloud)"/><ellipse cx="' + (cx - k * 1.1) + '" cy="' + (cy + k * 0.1) + '" rx="' + (k * 1.1) + '" ry="' + (k * 0.8) + '" fill="var(--cloud)"/></g>';
    });
    var av = { x: W / 2, y: H * 0.7, h: 60 }, geom = null;
    if (SC.mode === 'map' || SC.mode === 'flash' || SC.mode === 'report') {
      var n = ISLANDS.length, s = Math.min(64, (W - 40) / (n + 1.2)), gap = (W - 40 - s * 1.3) / (n - 1), y = H * 0.72;
      var doneIsland = 0; ISLANDS.forEach(function (isl, i) { var ok = BLOCKS.filter(function (b) { return b.theme === isl.id && S.blocks[b.id] && S.blocks[b.id].runs; }).length === BLOCKS.filter(function (b) { return b.theme === isl.id; }).length; if (ok) doneIsland = i + 1; });
      var cur = Math.min(doneIsland, n - 1); var nb = blockOf(nextBlockId()); ISLANDS.forEach(function (isl, i) { if (isl.id === nb.theme) cur = i; });
      ISLANDS.forEach(function (isl, i) { var x = 20 + i * gap; str += cube(x, y, s, THEMECOL[isl.id], { glow: i === cur }); str += '<text x="' + (x + s / 2) + '" y="' + (y + s * 0.68) + '" text-anchor="middle" font-size="' + (s * 0.5) + '">' + isl.e + '</text>'; });
      av = { x: 20 + cur * gap + s / 2, y: y - s * 0.15, h: Math.min(s * 1.4, H * 0.5) };
      SC.lava = 0;
    } else if (SC.mode === 'learn' || SC.mode === 'win' || SC.mode === 'break') {
      var bs = Math.min(110, H * 0.34, W * 0.3), bx = W / 2 - bs / 2, by = H * 0.78 - bs;
      str += cube(bx, by, bs, col, { glow: SC.mode === 'win' });
      str += '<text x="' + (bx + bs / 2) + '" y="' + (by + bs * 0.7) + '" text-anchor="middle" font-size="' + (bs * 0.55) + '">' + (SC.icon || '') + '</text>';
      if (SC.mode === 'win') { str += '<line x1="' + (bx + bs + 30) + '" y1="' + (by - bs * 0.3) + '" x2="' + (bx + bs + 30) + '" y2="' + (by + bs) + '" stroke="#5D4037" stroke-width="5"/><polygon points="' + (bx + bs + 33) + ',' + (by - bs * 0.3) + ' ' + (bx + bs + 78) + ',' + (by - bs * 0.15) + ' ' + (bx + bs + 33) + ',' + (by) + '" fill="#2E9E4F"/>'; }
      av = { x: bx + bs / 2, y: by - bs * 0.15, h: Math.min(90, bs * 1.1) };
      SC.lava = 0;
    } else {
      var total = SC.n, win = Math.min(8, total), start = total > 8 ? Math.max(0, Math.min(SC.idx - 3, total - 8)) : 0;
      geom = layout(W, H, win); geom.start = start; var sz = geom.s;
      geom.pos.forEach(function (p, i) {
        var qn = start + i, stt = SC.states[qn] || 'todo', c2 = stt === 'ok' ? '#2E9E4F' : stt === 'bad' ? '#B0483A' : col;
        str += cube(p.x, p.y, sz, c2, { crack: stt === 'bad', glow: qn === SC.idx });
        str += '<text x="' + (p.x + sz / 2) + '" y="' + (p.y + sz * 0.66) + '" text-anchor="middle" font-size="' + (sz * 0.42) + '" font-weight="700" fill="#fff" opacity=".85">' + (qn + 1) + '</text>';
        if (stt === 'todo' && qn !== SC.idx) str += coinSVG(p.x + sz / 2 + sz * 0.15, p.y - sz * 0.3 - sz * 0.5, sz * 0.2);
        if (stt === 'ok') str += '<text x="' + (p.x + sz / 2 + sz * 0.15) + '" y="' + (p.y - sz * 0.3 - sz * 0.35) + '" text-anchor="middle" font-size="' + (sz * 0.45) + '">⭐</text>';
      });
      if (start + win === total) {
        var last = geom.pos[geom.pos.length - 1], fx = last.x + sz + sz * 0.3 + 14, fy = last.y - sz * 0.3;
        if (fx > W - 20) { fx = last.x + sz * 0.5; fy = last.y - sz * 0.3 - sz * 0.9; }
        str += '<line x1="' + fx + '" y1="' + (fy - sz * 0.9) + '" x2="' + fx + '" y2="' + (fy + sz * 0.3) + '" stroke="#5D4037" stroke-width="4"/><polygon points="' + (fx + 2) + ',' + (fy - sz * 0.9) + ' ' + (fx + sz * 0.6) + ',' + (fy - sz * 0.7) + ' ' + (fx + 2) + ',' + (fy - sz * 0.5) + '" fill="#E0503A"/>';
      } else if (!mob) str += '<text class="lbl" x="' + (W - 14) + '" y="' + (geom.pos[geom.pos.length - 1].y - sz * 0.5) + '" text-anchor="end" font-size="15" font-weight="700" opacity=".9">' + (total - start - win) + ' more →</text>';
      var cp = geom.pos[Math.min(Math.max(0, SC.idx - start), geom.pos.length - 1)] || geom.pos[0];
      av = { x: cp.x + sz / 2, y: cp.y - sz * 0.15, h: Math.min(80, sz * 1.25) };
    }
    if (SC.label && !mob) str += '<text class="lbl" x="' + (W / 2) + '" y="30" text-anchor="middle" font-size="16" font-weight="700" opacity=".85">' + esc(SC.label) + '</text>';
    // lava
    var lavaH = H, wave = 'M0 0';
    for (var x = 0; x <= W + 40; x += 40) wave += ' q20 -14 40 0';
    wave += ' L' + (W + 40) + ' ' + lavaH + ' L0 ' + lavaH + ' Z';
    str += '<g id="lava" class="lava" style="transform:translateY(' + lavaY(H, geom) + 'px)"><path d="' + wave + '" fill="url(#lg)"/><path d="' + wave + '" fill="none" stroke="#FFE082" stroke-width="3" opacity=".7"/></g>';
    var cls = SC.mode === 'break' ? ' bounce' : '';
    str += '<g id="av" class="av' + cls + '" style="--ax:' + av.x.toFixed(1) + 'px;--ay:' + av.y.toFixed(1) + 'px;transform:translate(' + av.x.toFixed(1) + 'px,' + av.y.toFixed(1) + 'px)"><g class="body">' + avatarSVG(S.av, av.h) + '</g></g>';
    el.innerHTML = '<svg viewBox="0 0 ' + W + ' ' + H + '" width="' + W + '" height="' + H + '" font-family="Lexend,Verdana,Arial,sans-serif">' + str + '</svg><div id="toast"></div>';
    SC.geom = geom; SC.W = W; SC.H = H;
  }
  function lavaY(H, geom) { var top0 = H - 16, top1 = geom ? geom.yG + 6 : H * 0.8; return top0 - (SC.lava || 0) * (top0 - top1); }
  function setLava(frac) { SC.lava = Math.max(0, Math.min(1, frac)); var g = $('#lava'); if (g) g.style.transform = 'translateY(' + lavaY(SC.H, SC.geom) + 'px)'; }
  function moveAvatar(idx, opts) {
    SC.idx = idx; var g = $('#av'); if (!g || !SC.geom) { drawScene(); return; }
    var local = idx - (SC.geom.start || 0);
    if (local < 0 || local >= SC.geom.pos.length) { drawScene(); return; }
    var p = SC.geom.pos[local], sz = SC.geom.s; if (!p) { drawScene(); return; }
    var x = p.x + sz / 2, y = p.y - sz * 0.15;
    g.style.setProperty('--ax', x.toFixed(1) + 'px'); g.style.setProperty('--ay', y.toFixed(1) + 'px');
    g.classList.remove('falling'); g.style.transform = 'translate(' + x.toFixed(1) + 'px,' + y.toFixed(1) + 'px)';
    if (opts && opts.hop) { g.classList.remove('hop'); void g.getBoundingClientRect(); g.classList.add('hop'); }
  }
  function fallAvatar() { var g = $('#av'); if (!g) return; g.classList.remove('hop'); void g.getBoundingClientRect(); g.classList.add('falling'); setTimeout(function () { if (g.parentNode) { g.classList.remove('falling'); } }, 1400); }
  var rsz; window.addEventListener('resize', function () { clearTimeout(rsz); rsz = setTimeout(drawScene, 150); });

  // ---------- HUD / toast / confetti ----------
  function hud() {
    var done = BLOCKS.filter(function (b) { return S.blocks[b.id] && S.blocks[b.id].runs; }).length;
    $('#hud').innerHTML = '<span class="logo">🧱 Science Obby</span><span class="chip coin">🪙 <b>' + S.coins + '</b></span><span class="chip">🔥 ' + S.streak + '</span><span class="chip">🧱 ' + done + '/' + BLOCKS.length + '</span><span class="spacer"></span>' +
      (S.name ? '<span class="chip">' + esc(S.name) + '</span>' : '') +
      '<button class="icobtn" id="mute" title="Sound on/off" aria-label="Sound on or off">' + (S.mute ? '🔇' : '🔊') + '</button><button class="icobtn" id="home" title="Map" aria-label="Back to map">🗺️</button>';
    $('#mute').onclick = function () { S.mute = !S.mute; save(); hud(); if (!S.mute) snd('click'); };
    $('#home').onclick = function () { stopTimer(); hush(); if (RUN && RUN.live) { if (!confirm('Leave this run? Progress on this run will not be saved.')) return; } RUN = null; showMap(); };
  }
  function toast(msg, ms) { var t = $('#toast'); if (!t) return; t.textContent = msg; t.classList.add('on'); clearTimeout(t._t); t._t = setTimeout(function () { t.classList.remove('on'); }, ms || 1400); }
  function confetti() {
    if (REDUCED) return; var cv = $('#confetti'); if (!cv) return; var c = cv.getContext('2d');
    cv.width = window.innerWidth; cv.height = window.innerHeight;
    var ps = [], cols = ['#FFC72C', '#2E9E4F', '#2F7FD6', '#EF8A2A', '#8A5CD6', '#E0503A', '#fff'];
    for (var i = 0; i < 140; i++) ps.push({ x: Math.random() * cv.width, y: -20 - Math.random() * cv.height * 0.5, vx: (Math.random() - 0.5) * 3, vy: 2 + Math.random() * 4, s: 6 + Math.random() * 8, c: cols[i % cols.length], r: Math.random() * 6.28, vr: (Math.random() - 0.5) * 0.3 });
    var t0 = Date.now();
    (function step() {
      c.clearRect(0, 0, cv.width, cv.height);
      ps.forEach(function (p) { p.x += p.vx; p.y += p.vy; p.r += p.vr; c.save(); c.translate(p.x, p.y); c.rotate(p.r); c.fillStyle = p.c; c.fillRect(-p.s / 2, -p.s / 2, p.s, p.s * 0.6); c.restore(); });
      if (Date.now() - t0 < 2800) requestAnimationFrame(step); else c.clearRect(0, 0, cv.width, cv.height);
    })();
  }
  function card(html, cls) { var c = $('#card'); c.className = cls || ''; c.innerHTML = '<div class="inner">' + html + '</div>'; c.scrollTop = 0; }
  function stars(n) { return '<span aria-label="' + n + ' stars">' + '★'.repeat(n) + '<span style="opacity:.3">' + '★'.repeat(3 - n) + '</span></span>'; }
  function themeVar(t) { return 'style="--tc:' + (THEMECOL[t] || '#2F7FD6') + '"'; }

  // ---------- screens ----------
  var RUN = null;
  function showStart() {
    stopTimer(); hush(); RUN = null; hud(); scene({ mode: 'map', label: '' });
    var back = S.started;
    var h = '<div class="centre"><div class="stage">PSLE Science 2026</div><h1 class="title">Science Obby 🧱</h1><p class="sub">' + (back ? 'Welcome back' + (S.name ? ', ' + esc(S.name) : '') + '! Pick your avatar and jump in.' : 'Learn one block, run it, collect coins. Every coin = 1 exam mark.') + '</p></div>';
    h += '<div class="avs">' + AVS.map(function (a, i) { return '<button class="av' + (i === S.av ? ' sel' : '') + '" data-av="' + i + '" aria-label="' + a.n + '">' + avatarCard(i) + '</button>'; }).join('') + '</div>';
    h += '<input class="nm" id="nm" maxlength="20" placeholder="Your name (optional)" value="' + esc(S.name) + '" aria-label="Your name">';
    h += '<div class="plan"><b>The AL5 plan:</b> Booklet A has 30 MCQ, <b>2 marks each = 60 marks</b>. That is the goldmine. Get <b>24 of 30 MCQ</b> right (48) and <b>20 of 40</b> in Booklet B and you have <b>68 = AL5</b>. Every block here has 8 MCQ and 3 Booklet B questions.</div>';
    h += '<div class="stack mt"><button class="btn big ok" id="go">' + (back ? 'Continue ▶' : 'Start ▶') + '</button></div>';
    card(h);
    $$('.av').forEach(function (b) { b.onclick = function () { S.av = +b.getAttribute('data-av'); $$('.av').forEach(function (x) { x.classList.remove('sel'); }); b.classList.add('sel'); snd('click'); save(); drawScene(); }; });
    $('#go').onclick = function () { S.name = $('#nm').value.trim(); S.started = true; save(); ctx(); snd('coin'); showMap(); };
  }
  function showMap() {
    stopTimer(); hush(); RUN = null; hud(); scene({ mode: 'map', label: 'Pick a block' });
    var nxt = nextBlockId(), h = '<h1 class="title">Choose your block</h1><p class="sub">Go in order: the glowing block is next. Learn → Run (8 MCQ) → Booklet B (3) → Checkpoint.</p><div class="map">';
    ISLANDS.forEach(function (isl) {
      h += '<div class="island" ' + themeVar(isl.id) + '><h3>' + isl.e + ' ' + isl.name + ' <span class="tag">' + isl.sub + '</span></h3><div class="blocks">';
      BLOCKS.filter(function (b) { return b.theme === isl.id; }).forEach(function (b) {
        var p = S.blocks[b.id], st = p && p.runs ? stars(p.stars) : '<span style="opacity:.35">★★★</span>';
        h += '<button class="blk' + (b.id === nxt ? ' next' : '') + (p && p.runs ? ' done' : '') + '" data-b="' + b.id + '"><span class="nm">' + b.icon + ' ' + esc(b.name) + '</span><span class="st">' + st + ' <span class="small">' + b.lvl + '</span></span></button>';
      });
      h += '</div></div>';
    });
    h += '</div>';
    var fixN = S.fixit.length;
    h += '<h2 class="title mt" style="font-size:1.2em">Arenas and tools</h2><div class="arena">' +
      '<button class="btn warn" id="arA">🏟️ Arena A: MCQ<small>30 questions · 50 min (or a 10-Q sprint)</small></button>' +
      '<button class="btn purple" id="arB">📝 Arena B: Booklet B<small>10 questions · 45 min (or a 4-Q sprint)</small></button>' +
      '<button class="btn grey" id="fix">🔧 Fix-it pile<small>' + (fixN ? fixN + ' question' + (fixN > 1 ? 's' : '') + ' to fix' : 'nothing to fix yet') + '</small></button>' +
      '<button class="btn" id="flash">⚡ Flash cards<small>fast facts, 5 per block</small></button>' +
      '<button class="btn ghost" id="rep">📊 Report for Mum</button>' +
      '<button class="btn ghost" id="reset">🔄 Change avatar</button></div>';
    card(h);
    $$('.blk').forEach(function (b) { b.onclick = function () { startBlock(b.getAttribute('data-b')); }; });
    $('#arA').onclick = arenaAMenu; $('#arB').onclick = arenaBMenu; $('#fix').onclick = showFixit; $('#flash').onclick = showFlash; $('#rep').onclick = showReport; $('#reset').onclick = showStart;
  }

  // ----- block: learn -----
  function startBlock(id) {
    var B = blockOf(id); RUN = { B: B, li: 0, qi: 0, first: 0, correct: 0, coins: 0, res: [], oe: [], oi: 0, live: false };
    hud(); scene({ mode: 'learn', theme: B.theme, icon: B.icon, label: B.name });
    showLearn();
  }
  function showLearn() {
    var B = RUN.B, i = RUN.li, L = B.learn[i], last = i === B.learn.length - 1, seen = S.blocks[B.id] && S.blocks[B.id].runs;
    var h = '<div ' + themeVar(B.theme) + '><span class="stage">Learn · ' + B.icon + ' ' + esc(B.name) + '</span><div class="dots">' + B.learn.map(function (_, k) { return '<i class="' + (k === i ? 'on' : '') + '"></i>'; }).join('') + '</div>';
    h += '<div class="learn"><h2>' + L.h + '</h2>' + md(L.t) + pic(L.img, true) + '</div>';
    h += '<div class="row between mt"><button class="btn ghost" id="say">🔊 Read to me</button><span class="row">' + (i > 0 ? '<button class="btn grey" id="prev">◀ Back</button>' : '') + '<button class="btn ' + (last ? 'ok' : '') + '" id="next">' + (last ? 'Start the run 🏃' : 'Next ▶') + '</button></span></div>';
    if (seen && !last) h += '<p class="small centre mt"><button class="btn ghost" id="skip" style="min-height:40px;font-size:.9em">Skip lesson, go to the run</button></p>';
    h += '</div>';
    card(h);
    $('#say').onclick = function () { speak(L.h + '. ' + plain(md(L.t))); };
    if ($('#prev')) $('#prev').onclick = function () { hush(); RUN.li--; showLearn(); };
    $('#next').onclick = function () { hush(); snd('click'); if (last) startRun(); else { RUN.li++; showLearn(); } };
    if ($('#skip')) $('#skip').onclick = function () { hush(); startRun(); };
  }

  // ----- MCQ question screen (block run, fix-it, arena A) -----
  function startRun() {
    var B = RUN.B; RUN.qs = B.mcq.map(function (q, i) { return { q: q, b: B.id, i: i }; }); RUN.qi = 0; RUN.mode = 'run'; RUN.live = true;
    scene({ mode: 'run', n: RUN.qs.length, idx: 0, states: [], theme: B.theme, label: 'Run: ' + B.name });
    showQ();
  }
  function showQ() {
    var item = RUN.qs[RUN.qi], q = item.q, n = RUN.qs.length, arena = RUN.mode === 'arenaA';
    RUN.tries = 0; RUN.answered = false;
    var fixed = q.o.every(function (o) { return plain(o).length <= 2; });
    RUN.perm = fixed ? [0, 1, 2, 3] : shuffle([0, 1, 2, 3]);
    var badge = arena ? 'Arena A · Question ' + (RUN.qi + 1) + ' of ' + n : RUN.mode === 'fix' ? 'Fix-it · ' + (RUN.qi + 1) + ' of ' + n : 'Booklet A · Question ' + (RUN.qi + 1) + ' of 8';
    var h = '<div ' + themeVar(blockOf(item.b).theme) + '><div class="row between"><span class="stage">' + badge + '</span><span class="small" id="tlab"></span></div>';
    h += '<div class="timer"><div id="tbar"></div></div>';
    h += '<div class="qtext" style="font-size:1.05em">' + q.q + '</div>';
    h += '<div class="opts">' + RUN.perm.map(function (oi, k) { return '<button class="opt" data-k="' + k + '"><span class="let">' + 'ABCD'[k] + '</span><span>' + q.o[oi] + '</span></button>'; }).join('') + '</div>';
    h += '<p class="small mt">' + (arena ? 'Exam mode: no hints. Answer and move on. Keys 1-4 also work.' : 'Tap the best answer. Wrong = you get one more try (for 1 coin). Keys 1-4 also work.') + '</p>';
    h += '<div id="fb"></div><div class="row end mt" id="nav"></div></div>';
    card(h);
    $$('.opt').forEach(function (b) { b.onclick = function () { answer(+b.getAttribute('data-k')); }; });
    if (arena) { paintTimer(); } else startTimer(RUN.mode === 'fix' ? 75 : 90, timeUp);
  }
  function rightK() { return RUN.perm.indexOf(RUN.qs[RUN.qi].q.a); }
  function markOpts(q, chosen) {
    var rk = rightK();
    $$('.opt').forEach(function (b) { var k = +b.getAttribute('data-k'); b.disabled = true; if (k === rk) b.classList.add('correct'); else if (k === chosen) b.classList.add('wrong'); else b.classList.add('dim'); });
  }
  function answer(k) {
    if (!RUN || RUN.answered) return; var item = RUN.qs[RUN.qi], q = item.q;
    var right = RUN.perm[k] === q.a;
    if (RUN.mode === 'arenaA') { RUN.answered = true; RUN.res.push({ item: item, chosen: k, chosenText: q.o[RUN.perm[k]], ok: right, rightLetter: 'ABCD'[rightK()] }); $$('.opt').forEach(function (b) { b.disabled = true; if (+b.getAttribute('data-k') === k) b.classList.add('sel'); }); SC.states[RUN.qi] = 'ok'; moveAvatar(RUN.qi + 1, { hop: true }); snd('jump'); toast('Saved'); setTimeout(nextQ, 350); return; }
    if (right) { correct(RUN.tries === 0 ? 2 : 1); return; }
    if (RUN.tries === 0) {
      RUN.tries = 1; snd('wrong'); var b = $$('.opt')[k]; b.disabled = true; b.classList.add('wrong', 'shake');
      $('#fb').innerHTML = '<div class="fb hint"><h3>Not that one. One more try 💪</h3><p><b>Hint:</b> ' + q.hint + '</p></div>';
      return;
    }
    fail('Not this time.');
  }
  function correct(pts) {
    stopTimer(); var item = RUN.qs[RUN.qi], q = item.q; RUN.answered = true;
    markOpts(q, q.a); if (RUN.mode === 'fix') pts = 1;
    S.coins += pts; RUN.coins += pts; RUN.correct++; if (pts === 2 && RUN.mode !== 'fix') RUN.first++;
    S.streak++; if (S.streak > S.bestStreak) S.bestStreak = S.streak;
    RUN.res.push({ item: item, ok: true, first: pts === 2 });
    if (RUN.mode === 'fix') { S.fixit = S.fixit.filter(function (f) { return !(f.b === item.b && f.i === item.i); }); }
    save(); hud(); snd('coin'); SC.states[RUN.qi] = 'ok'; moveAvatar(RUN.qi + 1, { hop: true }); setTimeout(function () { snd('jump'); }, 120); toast('+' + pts + ' coin' + (pts > 1 ? 's' : '') + '!');
    $('#fb').innerHTML = '<div class="fb good"><h3>Correct! +' + pts + ' 🪙' + (pts === 2 ? ' First try!' : '') + '</h3><p><b>Why:</b> ' + q.why + '</p>' + pic(q.img) + '</div>';
    navNext();
  }
  function fail(msg) {
    stopTimer(); var item = RUN.qs[RUN.qi], q = item.q; RUN.answered = true; markOpts(q, -1);
    S.streak = 0; RUN.res.push({ item: item, ok: false });
    if (!S.fixit.some(function (f) { return f.b === item.b && f.i === item.i; })) S.fixit.push({ b: item.b, i: item.i });
    if (RUN.mode === 'fix') { S.fixit = S.fixit.filter(function (f) { return !(f.b === item.b && f.i === item.i); }); S.fixit.push({ b: item.b, i: item.i }); }
    save(); hud(); snd('fall'); SC.states[RUN.qi] = 'bad'; fallAvatar(); (function (r, i) { setTimeout(function () { if (RUN === r) moveAvatar(i); }, 1400); })(RUN, RUN.qi + 1);
    $('#fb').innerHTML = '<div class="fb bad"><h3>' + msg + ' The answer is ' + 'ABCD'[rightK()] + '.</h3><p><b>Why:</b> ' + q.why + '</p>' + pic(q.img) + '<p class="small">This question goes into your Fix-it pile. You will beat it later.</p></div>';
    navNext();
  }
  function timeUp() { if (!RUN || RUN.answered) return; if (RUN.mode === 'arenaA') { finishArenaA(true); return; } fail('Time is up! The lava got you.'); }
  function navNext() {
    var last = RUN.qi === RUN.qs.length - 1;
    $('#nav').innerHTML = '<button class="btn ok" id="next">' + (last ? (RUN.mode === 'run' ? 'Booklet B ▶' : 'Finish ▶') : 'Next ▶') + '</button>';
    $('#next').onclick = nextQ; var fb = $('#fb'); if (fb) fb.scrollIntoView({ behavior: REDUCED ? 'auto' : 'smooth', block: 'nearest' });
  }
  function nextQ() {
    if (!RUN) return; hush(); RUN.qi++;
    if (RUN.qi < RUN.qs.length) { showQ(); return; }
    if (RUN.mode === 'run') startOE(); else if (RUN.mode === 'fix') finishFix(); else if (RUN.mode === 'arenaA') finishArenaA(false);
  }
  document.addEventListener('keydown', function (e) {
    if (!RUN || !$('.opt')) return; if (e.target && /INPUT|TEXTAREA/.test(e.target.tagName)) return;
    var k = { '1': 0, '2': 1, '3': 2, '4': 3, a: 0, b: 1, c: 2, d: 3 }[e.key.toLowerCase()];
    if (k !== undefined && !RUN.answered) { var b = $$('.opt')[k]; if (b && !b.disabled) b.click(); }
    if (e.key === 'Enter' && $('#next')) $('#next').click();
  });

  // ----- Booklet B (structured) -----
  function startOE() {
    var B = RUN.B; RUN.oeqs = B.oe.map(function (q, i) { return { q: q, b: B.id, i: i }; }); RUN.oi = 0; RUN.mode = 'oe'; RUN.oeMarks = 0; RUN.oeTotal = 0;
    scene({ mode: 'oe', n: RUN.oeqs.length, idx: 0, states: [], theme: B.theme, label: 'Booklet B: ' + B.name });
    showOE();
  }
  function showOE() {
    var item = RUN.oeqs[RUN.oi], q = item.q, n = RUN.oeqs.length, arena = RUN.mode === 'arenaB';
    RUN.sel = []; RUN.typed = false; RUN.answered = false;
    var chips = shuffle(q.ans.map(function (a, i) { return { t: a, id: 'a' + i, ok: true }; }).concat(q.decoy.map(function (d, i) { return { t: d, id: 'd' + i, ok: false }; })));
    RUN.chips = chips;
    var h = '<div ' + themeVar(blockOf(item.b).theme) + '><div class="row between"><span class="stage">' + (arena ? 'Arena B · ' : 'Booklet B · ') + 'Question ' + (RUN.oi + 1) + ' of ' + n + ' · [' + q.m + ' mark' + (q.m > 1 ? 's' : '') + ']</span><span class="small" id="tlab"></span></div>';
    h += '<div class="timer"><div id="tbar"></div></div>';
    h += '<div style="font-size:1.05em">' + q.q + '</div>' + pic(q.img);
    h += '<p class="small"><b>Build your answer:</b> tap the sentences you need, in order. Beware: some are traps. ' + q.m + ' mark' + (q.m > 1 ? 's' : '') + ' = ' + q.m + ' correct sentence' + (q.m > 1 ? 's' : '') + '.</p>';
    h += '<div class="chips" id="chips">' + chips.map(function (c) { return '<button class="chipbtn" data-id="' + c.id + '">' + c.t + '</button>'; }).join('') + '</div>';
    h += '<div class="answerbox" id="abox"><span class="empty">Your answer appears here…</span></div>';
    h += '<div id="typebox" class="hide"><textarea class="ans" id="ta" placeholder="Type your answer here. Use the science words."></textarea></div>';
    h += '<div class="row between mt"><span class="row"><button class="btn ghost" id="type" style="min-height:44px">⌨️ Type instead</button><button class="btn ghost" id="clr" style="min-height:44px">Clear</button></span><button class="btn ok" id="chk">Check my answer ✔</button></div>';
    h += '<div id="fb"></div><div class="row end mt" id="nav"></div></div>';
    card(h);
    $$('.chipbtn').forEach(function (b) { b.onclick = function () { toggleChip(b.getAttribute('data-id')); }; });
    $('#clr').onclick = function () { RUN.sel = []; paintChips(); if ($('#ta')) $('#ta').value = ''; };
    $('#type').onclick = function () { RUN.typed = !RUN.typed; $('#typebox').classList.toggle('hide', !RUN.typed); $('#chips').classList.toggle('hide', RUN.typed); $('#abox').classList.toggle('hide', RUN.typed); $('#type').textContent = RUN.typed ? '🧩 Use the sentence chips' : '⌨️ Type instead'; if (RUN.typed) $('#ta').focus(); };
    $('#chk').onclick = function () { checkOE(false); };
    if (arena) paintTimer(); else startTimer(q.m * 60, function () { checkOE(true); });
  }
  function toggleChip(id) { var i = RUN.sel.indexOf(id); if (i >= 0) RUN.sel.splice(i, 1); else RUN.sel.push(id); snd('click'); paintChips(); }
  function paintChips() {
    $$('.chipbtn').forEach(function (b) { b.classList.toggle('sel', RUN.sel.indexOf(b.getAttribute('data-id')) >= 0); });
    var box = $('#abox'); if (!box) return;
    box.innerHTML = RUN.sel.length ? RUN.sel.map(function (id) { var c = RUN.chips.filter(function (x) { return x.id === id; })[0]; return '<span class="piece">' + c.t + '</span>'; }).join(' ') : '<span class="empty">Your answer appears here…</span>';
  }
  function hiKw(text, kw) {
    var out = text; kw.forEach(function (g) { g.split('|').forEach(function (w) { if (!w) return; var re = new RegExp('(' + w.replace(/[.*+?^${}()|[\]\\]/g, '\\$&') + '[a-z]*)', 'i'); out = out.replace(re, '<span class="mk">$1</span>'); }); }); return out;
  }
  function checkOE(timed) {
    if (!RUN || RUN.answered) return; RUN.answered = true; stopTimer();
    var item = RUN.oeqs[RUN.oi], q = item.q, marks = 0, detail = '';
    if (RUN.typed) {
      var txt = ($('#ta') ? $('#ta').value : '').toLowerCase(), found = [], missing = [];
      q.kw.forEach(function (g) { var hit = g.split('|').some(function (w) { if (!w) return false; w = w.toLowerCase(); if (w.length <= 2) return new RegExp('(^|[^a-z0-9])' + w.replace(/[.*+?^${}()|[\]\\]/g, '\\$&') + '($|[^a-z0-9])', 'i').test(txt); return txt.indexOf(w) >= 0; }); if (hit) { marks++; found.push(g.split('|')[0]); } else missing.push(g.split('|')[0]); });
      if (!txt.trim()) marks = 0;
      detail = '<p><b>Keywords found:</b> ' + (found.length ? found.join(', ') : 'none') + (missing.length ? '. <b>Missing:</b> ' + missing.join(', ') : '') + '</p>';
    } else {
      var good = 0, bad = 0; RUN.sel.forEach(function (id) { var c = RUN.chips.filter(function (x) { return x.id === id; })[0]; if (c.ok) good++; else bad++; });
      marks = Math.max(0, Math.min(q.m, good - bad));
      $$('.chipbtn').forEach(function (b) { var c = RUN.chips.filter(function (x) { return x.id === b.getAttribute('data-id'); })[0]; b.disabled = true; if (RUN.sel.indexOf(c.id) >= 0) b.classList.add(c.ok ? 'yes' : 'no'); else if (c.ok) b.classList.add('yes'); else b.classList.add('used'); });
      detail = '<p><b>' + good + '</b> correct sentence' + (good !== 1 ? 's' : '') + ' chosen' + (bad ? ', <b>' + bad + '</b> trap' + (bad > 1 ? 's' : '') + ' (each trap costs 1 mark)' : '') + '. Green = should be in the answer. Red = a trap.</p>';
    }
    RUN.oeMarks += marks; RUN.oeTotal += q.m; S.coins += marks; RUN.coins += marks; save(); hud();
    RUN.oe.push({ item: item, marks: marks });
    var full = marks === q.m;
    if (full) { snd('coin'); SC.states[RUN.oi] = 'ok'; moveAvatar(RUN.oi + 1, { hop: true }); S.streak++; }
    else if (marks > 0) { snd('click'); SC.states[RUN.oi] = 'ok'; moveAvatar(RUN.oi + 1, { hop: true }); }
    else { snd('fall'); SC.states[RUN.oi] = 'bad'; fallAvatar(); S.streak = 0; (function (r, i) { setTimeout(function () { if (RUN === r) moveAvatar(i); }, 1400); })(RUN, RUN.oi + 1); }
    toast(marks ? '+' + marks + ' coin' + (marks > 1 ? 's' : '') : 'No marks');
    var model = q.ans.map(function (a, i) { return '<p style="margin:4px 0">' + hiKw(a, q.kw) + '</p>'; }).join('');
    $('#fb').innerHTML = '<div class="fb ' + (full ? 'good' : marks ? 'hint' : 'bad') + '"><h3>' + (timed ? 'Time is up! ' : '') + marks + ' / ' + q.m + ' mark' + (q.m > 1 ? 's' : '') + (full ? ' 🎉' : '') + '</h3>' + detail +
      '<div class="model"><b>Model answer</b> (highlighted = the keywords the marker looks for):' + model + '</div>' +
      '<div class="cer"><b>C</b><span>Claim: say what happens or what the answer is.</span><b>E</b><span>Evidence: the science fact (the keyword).</span><b>R</b><span>Reasoning: link it with "so" or "because".</span></div></div>';
    var last = RUN.oi === RUN.oeqs.length - 1;
    $('#nav').innerHTML = '<button class="btn ok" id="next">' + (last ? 'Checkpoint ▶' : 'Next ▶') + '</button>';
    $('#next').onclick = function () { hush(); RUN.oi++; if (RUN.oi < RUN.oeqs.length) showOE(); else if (RUN.mode === 'arenaB') finishArenaB(); else checkpoint(); };
    $('#fb').scrollIntoView({ behavior: REDUCED ? 'auto' : 'smooth', block: 'nearest' });
  }

  // ----- checkpoint & break -----
  function checkpoint() {
    var B = RUN.B, p = prog(B.id), st = RUN.first >= 7 ? 3 : RUN.first >= 5 ? 2 : 1;
    p.runs++; p.stars = Math.max(p.stars, st); p.first = Math.max(p.first, RUN.first); p.mcqC += RUN.correct; p.mcqT += RUN.qs.length; p.oeM += RUN.oeMarks; p.oeT += RUN.oeTotal; p.last = new Date().toISOString().slice(0, 10);
    RUN.live = false; save(); hud();
    scene({ mode: 'win', theme: B.theme, icon: B.icon, label: 'Checkpoint!' }); snd('fanfare'); confetti();
    var wrong = RUN.res.filter(function (r) { return !r.ok; });
    var nid = nextBlockId(), nb = blockOf(nid);
    var h = '<div class="centre" ' + themeVar(B.theme) + '><span class="stage">Checkpoint</span><h1 class="title">' + B.icon + ' ' + esc(B.name) + ' done!</h1><div class="stars">' + stars(st) + '</div>';
    h += '<div class="score">+' + RUN.coins + ' 🪙</div><p class="sub">MCQ: ' + RUN.first + ' of 8 first try (' + RUN.correct + ' of 8 correct) · Booklet B: ' + RUN.oeMarks + ' of ' + RUN.oeTotal + ' marks</p>';
    h += '<p>' + (st === 3 ? 'Superb. This block is exam-ready.' : st === 2 ? 'Good run. One more go later will make it 3 stars.' : 'You finished the block, and that is the hard part. Do the Fix-it pile, then run it again.') + '</p></div>';
    if (wrong.length) h += '<div class="plan"><b>Fix-it pile got ' + wrong.length + ' question' + (wrong.length > 1 ? 's' : '') + ':</b><ul style="margin:6px 0 0 18px">' + wrong.map(function (r) { return '<li class="small">' + plain(r.item.q.q).slice(0, 90) + (plain(r.item.q.q).length > 90 ? '…' : '') + '</li>'; }).join('') + '</ul></div>';
    h += '<div class="stack mt"><button class="btn big ok" id="brk">🏃 1-minute movement break</button><button class="btn big" id="nextb">Next block: ' + nb.icon + ' ' + esc(nb.name) + ' ▶</button><button class="btn big grey" id="map">🗺️ Back to map</button></div>';
    card(h);
    $('#brk').onclick = function () { showBreak(nid); }; $('#nextb').onclick = function () { startBlock(nid); }; $('#map').onclick = showMap;
  }
  function showBreak(nid) {
    RUN = null; scene({ mode: 'break', label: 'Break time' });
    var moves = ['Stand up. 10 star jumps! ⭐', 'Drink some water 💧', 'Shake out your arms and legs 🙆', 'Look out of the window, far away 👀', 'Stretch up to the ceiling 🙌', 'March on the spot 🥾'];
    var left = 60, mi = 0;
    function paint() { card('<div class="centre"><span class="stage">Break</span><h1 class="title">Move your body</h1><div class="score">' + mmss(left) + '</div><p style="font-size:1.3em;font-weight:700">' + moves[mi] + '</p><p class="sub">Brains learn better after moving. Back in a minute.</p><div class="row" style="justify-content:center"><button class="btn grey" id="skipb">Skip</button></div></div>'); $('#skipb').onclick = function () { clearInterval(iv); showMap(); }; }
    paint();
    var iv = setInterval(function () { left--; if (left % 15 === 0 && left > 0) { mi = (mi + 1) % moves.length; snd('click'); } if (left <= 0) { clearInterval(iv); snd('fanfare'); startBlock(nid); return; } var sc = $('.score'); if (sc) sc.textContent = mmss(left); var p = $('.centre p'); if (p) p.textContent = moves[mi]; }, 1000);
  }

  // ----- Arena A -----
  function arenaAMenu() {
    scene({ mode: 'map', label: 'Arena A' });
    var h = '<h1 class="title">🏟️ Arena A: Booklet A practice</h1><p class="sub">Exam pacing. One timer for the whole paper, the lava rises slowly, no hints. Marks show at the end with every answer explained. Aim: about 1.5 minutes per question.</p>';
    var hist = S.arenaA.slice(-3).map(function (a) { return '<li class="small">' + a.date + ': ' + a.score + ' / ' + a.n + ' (' + a.marks + ' marks of ' + a.n * 2 + ')</li>'; }).join('');
    h += '<div class="stack"><button class="btn big warn" id="full">Full paper: 30 MCQ · 50 minutes</button><button class="btn big" id="sprint">Sprint: 10 MCQ · 15 minutes</button><button class="btn big grey" id="back">◀ Back</button></div>' + (hist ? '<div class="plan"><b>Last results:</b><ul style="margin:4px 0 0 18px">' + hist + '</ul></div>' : '');
    card(h); $('#full').onclick = function () { startArenaA(30, 50 * 60); }; $('#sprint').onclick = function () { startArenaA(10, 15 * 60); }; $('#back').onclick = showMap;
  }
  function startArenaA(n, secs) {
    var qs = []; var bl = shuffle(BLOCKS); var per = Math.floor(n / bl.length), extra = n - per * bl.length;
    bl.forEach(function (B, k) { var take = per + (k < extra ? 1 : 0); pick(B.mcq.map(function (q, i) { return { q: q, b: B.id, i: i }; }), take).forEach(function (x) { qs.push(x); }); });
    qs = shuffle(qs).slice(0, n);
    RUN = { mode: 'arenaA', qs: qs, qi: 0, res: [], coins: 0, correct: 0, first: 0, live: true, secs: secs };
    scene({ mode: 'run', n: n, idx: 0, states: [], theme: 'int', label: 'Arena A' });
    startTimer(secs, function () { finishArenaA(true); });
    showQ();
  }
  function finishArenaA(timed) {
    stopTimer(); if (!RUN) return; RUN.live = false;
    var n = RUN.qs.length, score = RUN.res.filter(function (r) { return r.ok; }).length, marks = score * 2;
    RUN.res.forEach(function (r) { if (!r.ok && !S.fixit.some(function (f) { return f.b === r.item.b && f.i === r.item.i; })) S.fixit.push({ b: r.item.b, i: r.item.i }); });
    S.coins += marks; S.arenaA.push({ date: new Date().toISOString().slice(0, 10), n: n, score: score, marks: marks, secs: RUN.secs, used: RUN.secs - TM.left }); save(); hud();
    scene({ mode: 'win', theme: 'int', icon: '🏟️', label: 'Arena A result' }); if (score >= n * 0.7) { snd('fanfare'); confetti(); } else snd('coin');
    var pct = Math.round(score / n * 100), scaled = Math.round(score / n * 60);
    var h = '<div class="centre"><span class="stage">Arena A result</span><h1 class="title">' + (timed ? 'Time is up!' : 'Paper done!') + '</h1><div class="score">' + score + ' / ' + n + '</div><p class="sub">' + marks + ' marks · ' + pct + '% · that is about <b>' + scaled + ' / 60</b> on a real Booklet A' + (n < 30 ? ' (sprint estimate)' : '') + '</p></div>';
    h += '<p><b>Review every question.</b> Green = correct. Red = your Fix-it pile. Read the "why" for each one.</p>';
    RUN.qs.forEach(function (item, i) {
      var r = RUN.res[i], q = item.q, ok = r && r.ok, chosen = r ? r.chosen : -1;
      h += '<details style="margin:6px 0;border:3px solid ' + (ok ? 'var(--ok)' : 'var(--bad)') + ';border-radius:12px;padding:6px 10px;background:#fff"><summary style="cursor:pointer;font-weight:700">' + (ok ? '✅' : '❌') + ' Q' + (i + 1) + ' · ' + esc(blockOf(item.b).name) + '</summary><div class="small" style="margin-top:6px">' + q.q + '</div><p class="small">Your answer: <b>' + (chosen >= 0 ? 'ABCD'[chosen] + '. ' + r.chosenText : 'none') + '</b><br>Correct: <b>' + (r ? r.rightLetter + '. ' : '') + q.o[q.a] + '</b></p><p class="small"><b>Why:</b> ' + q.why + '</p>' + pic(q.img) + '</details>';
    });
    h += '<div class="stack mt"><button class="btn big" id="map">🗺️ Back to map</button></div>';
    card(h); $('#map').onclick = showMap; RUN = null;
  }

  // ----- Arena B -----
  function arenaBMenu() {
    scene({ mode: 'map', label: 'Arena B' });
    var h = '<h1 class="title">📝 Arena B: Booklet B practice</h1><p class="sub">Structured questions from different blocks, one timer for the whole set (about 1 minute per mark). Marks are shown after each question so you learn as you go.</p>';
    var hist = S.arenaB.slice(-3).map(function (a) { return '<li class="small">' + a.date + ': ' + a.raw + ' / ' + a.total + ' marks (about ' + a.scaled + ' / 40)</li>'; }).join('');
    h += '<div class="stack"><button class="btn big purple" id="full">Full set: 10 questions · 45 minutes</button><button class="btn big" id="sprint">Sprint: 4 questions · 15 minutes</button><button class="btn big grey" id="back">◀ Back</button></div>' + (hist ? '<div class="plan"><b>Last results:</b><ul style="margin:4px 0 0 18px">' + hist + '</ul></div>' : '');
    card(h); $('#full').onclick = function () { startArenaB(10, 45 * 60); }; $('#sprint').onclick = function () { startArenaB(4, 15 * 60); }; $('#back').onclick = showMap;
  }
  function startArenaB(n, secs) {
    var qs = []; pick(BLOCKS, n).forEach(function (B) { var i = Math.floor(Math.random() * B.oe.length); qs.push({ q: B.oe[i], b: B.id, i: i }); });
    RUN = { mode: 'arenaB', oeqs: qs, oi: 0, oe: [], coins: 0, oeMarks: 0, oeTotal: 0, live: true, secs: secs };
    scene({ mode: 'oe', n: n, idx: 0, states: [], theme: 'int', label: 'Arena B' });
    startTimer(secs, function () { if (RUN && !RUN.answered) checkOE(true); setTimeout(finishArenaB, 1500); });
    showOE();
  }
  function finishArenaB() {
    stopTimer(); if (!RUN) return; RUN.live = false;
    var raw = RUN.oeMarks, total = RUN.oeTotal || 1, scaled = Math.round(raw / total * 40);
    S.arenaB.push({ date: new Date().toISOString().slice(0, 10), n: RUN.oeqs.length, raw: raw, total: total, scaled: scaled }); save(); hud();
    scene({ mode: 'win', theme: 'int', icon: '📝', label: 'Arena B result' }); if (raw / total >= 0.5) { snd('fanfare'); confetti(); } else snd('coin');
    var h = '<div class="centre"><span class="stage">Arena B result</span><h1 class="title">Set done!</h1><div class="score">' + raw + ' / ' + total + '</div><p class="sub">That is about <b>' + scaled + ' / 40</b> on a real Booklet B.</p></div>';
    h += '<table class="rep"><tr><th>Q</th><th>Block</th><th>Marks</th></tr>' + RUN.oe.map(function (r, i) { return '<tr><td>' + (i + 1) + '</td><td>' + esc(blockOf(r.item.b).name) + '</td><td>' + r.marks + ' / ' + r.item.q.m + '</td></tr>'; }).join('') + '</table>';
    h += estimateHTML();
    h += '<div class="stack mt"><button class="btn big" id="map">🗺️ Back to map</button></div>';
    card(h); $('#map').onclick = showMap; RUN = null;
  }
  function alBand(m) { return m >= 90 ? 'AL1' : m >= 85 ? 'AL2' : m >= 80 ? 'AL3' : m >= 75 ? 'AL4' : m >= 65 ? 'AL5' : m >= 45 ? 'AL6' : m >= 20 ? 'AL7' : 'AL8'; }
  function estimateHTML() {
    var a = S.arenaA[S.arenaA.length - 1], b = S.arenaB[S.arenaB.length - 1]; if (!a || !b) return '';
    var ea = Math.round(a.score / a.n * 60), tot = ea + b.scaled;
    return '<div class="plan"><b>Rough estimate</b> (from your latest Arena A and Arena B): Booklet A about ' + ea + ' / 60 + Booklet B about ' + b.scaled + ' / 40 = <b>' + tot + ' / 100 = ' + alBand(tot) + '</b>. This is practice-bank data only, not a prediction of the real paper.</div>';
  }

  // ----- Fix-it pile -----
  function showFixit() {
    if (!S.fixit.length) { scene({ mode: 'map', label: 'Fix-it pile' }); card('<div class="centre"><span class="stage">Fix-it pile</span><h1 class="title">🔧 Nothing to fix!</h1><p class="sub">Questions you get wrong land here. Beat them on the first try to clear them.</p><button class="btn big" id="map">🗺️ Back to map</button></div>'); $('#map').onclick = showMap; return; }
    var qs = S.fixit.slice(0, 8).map(function (f) { var B = blockOf(f.b); return { q: B.mcq[f.i], b: f.b, i: f.i }; });
    RUN = { mode: 'fix', qs: qs, qi: 0, res: [], coins: 0, correct: 0, first: 0, live: true };
    scene({ mode: 'run', n: qs.length, idx: 0, states: [], theme: 'sys', label: 'Fix-it pile' });
    showQ();
  }
  function finishFix() {
    RUN.live = false; var fixed = RUN.res.filter(function (r) { return r.ok; }).length, n = RUN.qs.length;
    scene({ mode: 'win', theme: 'sys', icon: '🔧', label: 'Fix-it done' }); if (fixed === n) { snd('fanfare'); confetti(); } else snd('coin');
    card('<div class="centre"><span class="stage">Fix-it pile</span><h1 class="title">' + fixed + ' of ' + n + ' fixed 🔧</h1><p class="sub">' + (S.fixit.length ? S.fixit.length + ' still in the pile. The ones you missed come back later.' : 'Pile is empty. Nice.') + '</p><div class="stack"><button class="btn big ok" id="again">' + (S.fixit.length ? 'Fix more ▶' : 'Back to map') + '</button><button class="btn big grey" id="map">🗺️ Back to map</button></div></div>');
    $('#again').onclick = S.fixit.length ? showFixit : showMap; $('#map').onclick = showMap; RUN = null;
  }

  // ----- Flash cards -----
  function showFlash() {
    RUN = null; scene({ mode: 'flash', label: 'Flash cards' });
    var h = '<h1 class="title">⚡ Flash cards</h1><p class="sub">Say the answer out loud, then tap the card to check. Tuesday-morning tool: 10 minutes, all blocks.</p><div class="blocks">';
    h += '<button class="blk next" data-b="all"><span class="nm">⚡ All blocks</span><span class="st small">' + BLOCKS.reduce(function (a, b) { return a + b.facts.length; }, 0) + ' cards</span></button>';
    BLOCKS.forEach(function (b) { h += '<button class="blk" data-b="' + b.id + '"><span class="nm">' + b.icon + ' ' + esc(b.name) + '</span><span class="st small">' + b.facts.length + ' cards</span></button>'; });
    h += '</div><div class="stack mt"><button class="btn grey" id="map">🗺️ Back to map</button></div>';
    card(h); $('#map').onclick = showMap;
    $$('.blk').forEach(function (b) { b.onclick = function () { var id = b.getAttribute('data-b'); var deck = []; (id === 'all' ? BLOCKS : [blockOf(id)]).forEach(function (B) { B.facts.forEach(function (f) { deck.push({ q: f[0], a: f[1], t: B.theme, n: B.name }); }); }); runFlash(shuffle(deck), id === 'all' ? 'All blocks' : blockOf(id).name); }; });
  }
  function runFlash(deck, title) {
    var i = 0, got = 0, again = [], flipped = false, total = deck.length;
    function paint() {
      if (i >= deck.length) { if (again.length) { deck = shuffle(again); again = []; i = 0; toast('Round 2: the ones you missed'); } else { scene({ mode: 'win', theme: 'ene', icon: '⚡', label: 'Deck done' }); snd('fanfare'); confetti(); card('<div class="centre"><span class="stage">Flash cards</span><h1 class="title">Deck done! ⚡</h1><p class="sub">' + total + ' cards · ' + title + '</p><div class="stack"><button class="btn big" id="more">More decks</button><button class="btn big grey" id="map">🗺️ Back to map</button></div></div>'); $('#more').onclick = showFlash; $('#map').onclick = showMap; return; } }
      var c = deck[i]; flipped = false;
      card('<div ' + themeVar(c.t) + '><div class="row between"><span class="stage">' + esc(title) + '</span><span class="small">' + (i + 1) + ' / ' + deck.length + ' · ' + esc(c.n) + '</span></div><div class="flash"><div class="flashcard" id="fc">' + esc(c.q) + '</div></div><p class="small centre">Tap the card to flip it.</p><div class="row" style="justify-content:center" id="fbtn"><button class="btn ghost" id="say">🔊 Read</button></div></div>');
      $('#fc').onclick = flip; $('#say').onclick = function () { speak(flipped ? c.a : c.q); };
      function flip() { flipped = !flipped; var fc = $('#fc'); fc.classList.toggle('back', flipped); fc.textContent = flipped ? c.a : c.q; snd('click'); if (flipped) $('#fbtn').innerHTML = '<button class="btn ok" id="got">Got it ✅</button><button class="btn warn" id="not">Not yet 🔁</button><button class="btn ghost" id="say">🔊 Read</button>'; else $('#fbtn').innerHTML = '<button class="btn ghost" id="say">🔊 Read</button>'; $('#say').onclick = function () { speak(flipped ? c.a : c.q); }; if ($('#got')) { $('#got').onclick = function () { got++; S.coins += 1; save(); hud(); snd('coin'); i++; paint(); }; $('#not').onclick = function () { again.push(c); i++; paint(); }; } }
    }
    paint();
  }

  // ----- Report -----
  function showReport() {
    RUN = null; scene({ mode: 'report', label: 'Report' });
    var rows = BLOCKS.map(function (b) { var p = S.blocks[b.id]; return { b: b, p: p, acc: p && p.mcqT ? Math.round(p.mcqC / p.mcqT * 100) : null, oe: p && p.oeT ? Math.round(p.oeM / p.oeT * 100) : null }; });
    var done = rows.filter(function (r) { return r.p && r.p.runs; });
    var weak = done.slice().sort(function (x, y) { return (x.acc + (x.oe || 0)) - (y.acc + (y.oe || 0)); }).slice(0, 3);
    var h = '<h1 class="title">📊 Report</h1><p class="sub">' + (S.name ? esc(S.name) + ' · ' : '') + 'Coins: ' + S.coins + ' · Best streak: ' + S.bestStreak + ' · Blocks done: ' + done.length + ' of ' + BLOCKS.length + ' · Fix-it pile: ' + S.fixit.length + '</p>';
    h += '<table class="rep"><tr><th>Block</th><th>Stars</th><th>MCQ</th><th>Booklet B</th></tr>' + rows.map(function (r) { return '<tr><td>' + r.b.icon + ' ' + esc(r.b.name) + '</td><td>' + (r.p && r.p.runs ? stars(r.p.stars) : '—') + '</td><td>' + (r.acc === null ? '—' : r.acc + '%') + '</td><td>' + (r.oe === null ? '—' : r.oe + '%') + '</td></tr>'; }).join('') + '</table>';
    if (weak.length) h += '<div class="plan"><b>Weakest ' + weak.length + ' (do these again first):</b> ' + weak.map(function (r) { return r.b.icon + ' ' + esc(r.b.name); }).join(', ') + '</div>';
    if (S.arenaA.length) h += '<p class="small"><b>Arena A:</b> ' + S.arenaA.map(function (a) { return a.date + ' ' + a.score + '/' + a.n; }).join(' · ') + '</p>';
    if (S.arenaB.length) h += '<p class="small"><b>Arena B:</b> ' + S.arenaB.map(function (a) { return a.date + ' ' + a.raw + '/' + a.total; }).join(' · ') + '</p>';
    h += estimateHTML();
    h += '<div class="row mt"><button class="btn ok" id="copy">📋 Copy report for Mum</button><button class="btn grey" id="map">🗺️ Back to map</button></div><textarea class="ans hide" id="rtxt" readonly></textarea>';
    card(h);
    var txt = 'Science Obby report ' + new Date().toISOString().slice(0, 10) + (S.name ? ' for ' + S.name : '') + '\nCoins ' + S.coins + ', best streak ' + S.bestStreak + ', blocks done ' + done.length + '/' + BLOCKS.length + ', fix-it pile ' + S.fixit.length + '\n' +
      rows.map(function (r) { return r.b.name + ': ' + (r.p && r.p.runs ? r.p.stars + ' star(s), MCQ ' + r.acc + '%, Booklet B ' + (r.oe === null ? '-' : r.oe + '%') : 'not done'); }).join('\n') +
      (weak.length ? '\nWeakest: ' + weak.map(function (r) { return r.b.name; }).join(', ') : '') +
      (S.arenaA.length ? '\nArena A: ' + S.arenaA.map(function (a) { return a.date + ' ' + a.score + '/' + a.n; }).join(', ') : '') +
      (S.arenaB.length ? '\nArena B: ' + S.arenaB.map(function (a) { return a.date + ' ' + a.raw + '/' + a.total; }).join(', ') : '');
    $('#copy').onclick = function () {
      var ta = $('#rtxt'); ta.value = txt;
      if (navigator.clipboard && navigator.clipboard.writeText) navigator.clipboard.writeText(txt).then(function () { toast('Copied!'); }, function () { ta.classList.remove('hide'); ta.select(); toast('Select and copy the text'); });
      else { ta.classList.remove('hide'); ta.select(); try { document.execCommand('copy'); toast('Copied!'); } catch (e) { toast('Select and copy the text'); } }
    };
    $('#map').onclick = showMap;
  }

  // ---------- boot ----------
  window.addEventListener('beforeunload', function () { save(); });
  if (S.started) showMap(); else showStart();
  window.SCIOBBY = { state: S, blocks: BLOCKS, go: { start: showStart, map: showMap, block: startBlock, fix: showFixit, flash: showFlash, report: showReport, arenaA: startArenaA, arenaB: startArenaB }, _t: { timeUp: timeUp, stop: stopTimer } };
})();


</script>
</body>
</html>
