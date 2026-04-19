<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>QFT Interferenz – Interaktiver Erklärer</title>
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: system-ui, sans-serif;
  background: #ffffff;
  color: #3d3d3a;
  padding: 1.5rem;
  max-width: 720px;
  margin: 0 auto;
}
@media (prefers-color-scheme: dark) {
  body { background: #1a1a18; color: #c2c0b6; }
}
h1 { font-size: 18px; font-weight: 500; margin-bottom: 4px; }
.subtitle { font-size: 13px; color: #888780; margin-bottom: 1.5rem; }
canvas { display: block; }
.ctrl { display: flex; align-items: center; gap: 10px; margin: 8px 0; font-size: 13px; color: #888780; }
.ctrl label { min-width: 120px; }
.ctrl input[type=range] { flex: 1; }
.ctrl span { min-width: 32px; text-align: right; font-weight: 500; color: #3d3d3a; }
@media (prefers-color-scheme: dark) { .ctrl span { color: #c2c0b6; } }
.label-sm { font-size: 12px; color: #888780; margin-bottom: 4px; }
.grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 12px 0; }
#result-bar { height: 8px; border-radius: 4px; background: rgba(0,0,0,0.1); margin: 4px 0 12px; overflow: hidden; }
@media (prefers-color-scheme: dark) { #result-bar { background: rgba(255,255,255,0.1); } }
#result-fill { height: 100%; border-radius: 4px; background: #1D9E75; transition: width 0.1s; }
.note { font-size: 12px; color: #888780; line-height: 1.6; margin-top: 8px; }
.prob-row { font-size: 13px; color: #888780; margin-bottom: 4px; }
.prob-row strong { font-weight: 500; color: #3d3d3a; }
@media (prefers-color-scheme: dark) { .prob-row strong { color: #c2c0b6; } }
</style>
</head>
<body>

<h1>QFT Interferenz – Interaktiver Erklärer</h1>
<p class="subtitle">Wie die Quantum Fourier Transform eine periodische Welle in einen einzigen Messwert umwandelt</p>

<div class="ctrl">
  <label>Periode r</label>
  <input type="range" id="period" min="2" max="16" step="1" value="10">
  <span id="period-out">10</span>
</div>
<div class="ctrl">
  <label>Testfrequenz k</label>
  <input type="range" id="kval" min="0" max="31" step="1" value="3">
  <span id="k-out">3</span>
</div>

<div class="grid">
  <div>
    <div class="label-sm">Zeiger in der komplexen Ebene (je ein Strich pro |x⟩)</div>
    <canvas id="phasor" width="300" height="300"></canvas>
  </div>
  <div>
    <div class="label-sm">Summen-Zeiger (Resultierende)</div>
    <canvas id="result" width="300" height="300"></canvas>
  </div>
</div>

<div class="prob-row">
  Wahrscheinlichkeit bei k = <strong id="k-label">3</strong>:
  <strong id="prob-val" style="color:#1D9E75">0.000</strong>
</div>
<div id="result-bar"><div id="result-fill" style="width:0%"></div></div>

<p class="note">
  N=32 Basiszustände. Jeder Zeiger = e^(2πi·x/r) · e^(−2πi·kx/N).<br>
  Zeigen alle in dieselbe Richtung → konstruktive Interferenz → Messung liefert k.<br>
  Tipp: Setze r=10, k=3 für maximale Interferenz. Verändere k und beobachte den Kollaps.
</p>

<script>
const N = 32;
let r = 10, k = 3;

const isDark = matchMedia('(prefers-color-scheme: dark)').matches;
const col = {
  grid:    isDark ? 'rgba(255,255,255,0.07)' : 'rgba(0,0,0,0.07)',
  arrow:   isDark ? 'rgba(255,255,255,0.18)' : 'rgba(0,0,0,0.15)',
  sum:     '#1D9E75',
  sumFade: 'rgba(29,158,117,0.25)',
  dest:    '#534AB7',
  text:    isDark ? '#c2c0b6' : '#3d3d3a',
  axis:    isDark ? 'rgba(255,255,255,0.3)' : 'rgba(0,0,0,0.25)',
};

function phasors() {
  const arr = [];
  for (let x = 0; x < N; x++) {
    const phi = 2 * Math.PI * x / r - 2 * Math.PI * k * x / N;
    arr.push({ re: Math.cos(phi), im: Math.sin(phi) });
  }
  return arr;
}

function drawAxes(ctx, cx, cy, R) {
  ctx.strokeStyle = col.grid; ctx.lineWidth = 0.5;
  ctx.beginPath(); ctx.arc(cx, cy, R, 0, 2 * Math.PI); ctx.stroke();
  ctx.strokeStyle = col.axis; ctx.lineWidth = 0.5;
  ctx.beginPath(); ctx.moveTo(cx - R - 8, cy); ctx.lineTo(cx + R + 8, cy); ctx.stroke();
  ctx.beginPath(); ctx.moveTo(cx, cy - R - 8); ctx.lineTo(cx, cy + R + 8); ctx.stroke();
  ctx.font = '11px system-ui, sans-serif';
  ctx.fillStyle = col.text;
  ctx.textAlign = 'center';
  ctx.fillText('Im', cx + 4, cy - R - 12);
  ctx.textAlign = 'left';
  ctx.fillText('Re', cx + R + 10, cy + 4);
}

function drawPhasorPlot(ps) {
  const c = document.getElementById('phasor');
  const ctx = c.getContext('2d');
  const W = c.width, H = c.height, cx = W / 2, cy = H / 2, R = W * 0.42;
  ctx.clearRect(0, 0, W, H);
  drawAxes(ctx, cx, cy, R);
  ps.forEach(p => {
    const ex = cx + p.re * R, ey = cy - p.im * R;
    ctx.strokeStyle = col.arrow; ctx.lineWidth = 1;
    ctx.beginPath(); ctx.moveTo(cx, cy); ctx.lineTo(ex, ey); ctx.stroke();
    ctx.fillStyle = col.arrow;
    ctx.beginPath(); ctx.arc(ex, ey, 2.5, 0, 2 * Math.PI); ctx.fill();
  });
}

function drawResultPlot(ps) {
  const c = document.getElementById('result');
  const ctx = c.getContext('2d');
  const W = c.width, H = c.height, cx = W / 2, cy = H / 2, R = W * 0.42;
  ctx.clearRect(0, 0, W, H);
  drawAxes(ctx, cx, cy, R);

  const scale = R / N;
  let curRe = 0, curIm = 0;
  ps.forEach(p => {
    const nRe = curRe + p.re, nIm = curIm + p.im;
    const sx = cx + curRe * scale, sy = cy - curIm * scale;
    const ex = cx + nRe * scale, ey = cy - nIm * scale;
    ctx.strokeStyle = col.dest + 'aa'; ctx.lineWidth = 0.8;
    ctx.beginPath(); ctx.moveTo(sx, sy); ctx.lineTo(ex, ey); ctx.stroke();
    curRe = nRe; curIm = nIm;
  });

  const mag = Math.sqrt(curRe * curRe + curIm * curIm);
  const ex = cx + curRe * scale, ey = cy - curIm * scale;

  ctx.beginPath(); ctx.arc(cx, cy, mag * scale, 0, 2 * Math.PI);
  ctx.strokeStyle = col.sumFade; ctx.lineWidth = 1; ctx.stroke();

  ctx.strokeStyle = col.sum; ctx.lineWidth = 2.5;
  ctx.beginPath(); ctx.moveTo(cx, cy); ctx.lineTo(ex, ey); ctx.stroke();

  const angle = Math.atan2(ey - cy, ex - cx);
  const hs = 8;
  ctx.fillStyle = col.sum;
  ctx.beginPath();
  ctx.moveTo(ex, ey);
  ctx.lineTo(ex - hs * Math.cos(angle - 0.4), ey - hs * Math.sin(angle - 0.4));
  ctx.lineTo(ex - hs * Math.cos(angle + 0.4), ey - hs * Math.sin(angle + 0.4));
  ctx.closePath(); ctx.fill();

  const prob = (mag / N) * (mag / N);
  document.getElementById('prob-val').textContent = prob.toFixed(3);
  document.getElementById('result-fill').style.width = Math.min(100, prob * 100) + '%';
}

function update() {
  r = parseInt(document.getElementById('period').value);
  k = parseInt(document.getElementById('kval').value);
  document.getElementById('period-out').textContent = r;
  document.getElementById('k-out').textContent = k;
  document.getElementById('k-label').textContent = k;
  const ps = phasors();
  drawPhasorPlot(ps);
  drawResultPlot(ps);
}

document.getElementById('period').addEventListener('input', update);
document.getElementById('kval').addEventListener('input', update);
update();
</script>
</body>
</html>
