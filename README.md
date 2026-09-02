<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Lexend:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  * { box-sizing: border-box; }
  body {
    margin: 0; padding: 24px 14px 70px;
    background: #f1eadd; color: #332a21;
    font-family: "Lexend", ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
    text-align: left;
  }
  .wrap {
    max-width: 1140px; margin: 0 auto;
    background: linear-gradient(180deg, #fffdf8 0%, #faf4e8 100%);
    border: 1px solid #e2d6bf; border-radius: 26px;
    box-shadow: 0 12px 34px rgba(90, 62, 26, .09), 0 2px 6px rgba(90, 62, 26, .05);
    padding: 30px 34px 46px; position: relative; overflow: hidden;
  }
  .wrap::before {
    content: ""; position: absolute; top: 0; left: 0; right: 0; height: 7px;
    background: linear-gradient(90deg, #b96a3d, #d3a86a 38%, #c7b98f 70%, #6d8fb5);
  }
  .wrap::after {
    content: ""; position: absolute; inset: 10px; pointer-events: none;
    border: 1px dashed #e7dcc6; border-radius: 19px;
  }

  header { text-align: center; padding: 28px 0 4px; }
  .breedTag {
    display: inline-block; background: #e9dfcf; color: #6b5a44;
    font-size: 12px; letter-spacing: 1.5px; text-transform: uppercase;
    padding: 4px 12px; border-radius: 999px; margin-bottom: 12px;
  }
  h1 { font-family: "Lexend", sans-serif; font-weight: 700; font-size: 30px; margin: 0 0 8px; }
  header p { color: #857663; font-size: 14px; margin: 0 auto; max-width: 680px; line-height: 1.5; }

  .panel {
    background: #fff; border: 1px solid #e6ddcd; border-radius: 14px;
    padding: 16px 18px 18px; box-shadow: 0 1px 3px rgba(70,50,20,.06);
  }
  .parents { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-top: 22px; }
  @media (max-width: 820px){ .parents { grid-template-columns: 1fr; } }

  .parentHead { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
  .parentHead h2 { font-family: "Lexend", sans-serif; font-weight: 600; font-size: 19px; margin: 0; }
  .miniBtn {
    background: #f1e9db; border: 1px solid #dfd3be; color: #6b5a44; border-radius: 8px;
    padding: 4px 10px; font-size: 12px; cursor: pointer; font-family: inherit;
  }
  .miniBtn:hover { background: #e8ddc9; }

  .locusRow { display: flex; align-items: center; gap: 8px; padding: 5px 0; border-bottom: 1px dashed #efe7d9; }
  .locusRow:last-child { border-bottom: none; }
  .locusId {
    width: 26px; height: 26px; border-radius: 7px; flex: 0 0 26px;
    background: #efe6d4; color: #7a6546; font-size: 13px; font-weight: 700;
    display: flex; align-items: center; justify-content: center;
  }
  .locusName { flex: 1; font-size: 13px; color: #5d5040; }
  select {
    font-size: 13px; padding: 4px 6px; border-radius: 7px;
    border: 1px solid #d8cbb4; background: #fdfbf6; color: #332a21; font-family: inherit;
  }
  select:focus { outline: 2px solid #d3a86a; outline-offset: 1px; }

  .controls { display: flex; justify-content: center; margin: 22px 0 6px; }
  .bigBtn {
    background: #f1e9db; color: #fff; border: none; border-radius: 10px;
    font-size: 15px; font-weight: 600; padding: 12px 22px; cursor: pointer;
    font-family: inherit; letter-spacing: .3px;
  }
  .bigBtn:hover { background: #f1e7c0; }

  .results { margin-top: 20px; }
  .results h3 { font-family: "Lexend", sans-serif; font-weight: 600; font-size: 20px; margin: 0 0 4px; }
  .summary { font-size: 13px; color: #857663; margin: 0 0 14px; }
  .dot { display: inline-block; width: 13px; height: 13px; border-radius: 50%; border: 1px solid rgba(0,0,0,.15); vertical-align: -2px; margin: 0 4px 0 9px; }

  .litterGrid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 14px; }
  .puppy {
    background: #fff; border: 1px solid #e6ddcd; border-radius: 12px;
    padding: 14px 16px; box-shadow: 0 1px 3px rgba(70,50,20,.06);
  }
  .puppyTop { display: flex; align-items: center; gap: 10px; margin-bottom: 8px; flex-wrap: wrap; }
  .swatch { width: 30px; height: 30px; border-radius: 50%; border: 1px solid rgba(0,0,0,.18); flex: 0 0 30px; }
  .swatch.merle {
    background-image:
      radial-gradient(circle at 32% 30%, rgba(255,255,255,.85) 0 20%, transparent 42%),
      radial-gradient(circle at 72% 62%, rgba(255,255,255,.7) 0 24%, transparent 48%),
      radial-gradient(circle at 55% 22%, rgba(255,255,255,.55) 0 14%, transparent 36%),
      radial-gradient(circle at 40% 80%, rgba(255,255,255,.65) 0 16%, transparent 34%);
  }
  .puppyId { font-family: "Lexend", sans-serif; font-size: 17px; font-weight: 700; flex: 1; }
  .sex { font-size: 11px; letter-spacing: 1px; text-transform: uppercase; padding: 2px 8px; border-radius: 999px; color: #fff; }
  .sex.M { background: #6d8fb5; }
  .sex.F { background: #c77f9e; }
  .oosTag {
    font-size: 10.5px; font-weight: 700; letter-spacing: .7px; text-transform: uppercase;
    color: #fff; background: #a34a2a; border-radius: 999px; padding: 3px 9px;
  }
  .pheno { font-size: 13.5px; line-height: 1.45; color: #3a2f25; margin: 0 0 8px; }
  .genos {
    font-size: 11px; letter-spacing: -0.3px; color: #8a7860; font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
    background: #faf6ee; border: 1px solid #efe6d6; border-radius: 8px; padding: 6px 8px; line-height: 1.65;
  }
</style>

<div class="wrap">
  <header>
    <div class="breedTag">DiamondDoxie's</div>
    <h1>Chenille Litter Generator</h1>
    <p>Select the sire and dam's genotypes from the dropdowns and hit "roll litter" to reveal puppies.  Screenshot litter outcome and send to DiamondDoxies upon litter design approval request.</p>
  </header>

  <div class="parents">
    <section class="panel">
      <div class="parentHead">
        <h2>Sire</h2>
      </div>
      <div id="sireLoci"></div>
    </section>
    <section class="panel">
      <div class="parentHead">
        <h2>Dam</h2>
      </div>
      <div id="damLoci"></div>
    </section>
  </div>

  <div class="controls">
    <button class="bigBtn" onclick="produceLitter()">Roll Litter</button>
  </div>

  <div class="results" id="results"></div>
</div>

<script>
const LOCI = [
  { id: 'A', name: 'Agouti', order: 'Ay > asa > at > a', alleles: [
    { a: 'Ay', p: 'Sable — fawn with black-tipped hairs' },
    { a: 'asa', p: 'Black saddle — tan dog with a black saddle over the back' },
    { a: 'at', p: 'Tan points — body with tan markings on muzzle, brow, chest, legs' },
    { a: 'a',  p: 'Recessive black — solid black, no tan' },
  ]},
  { id: 'B', name: 'Brown', order: 'B > b', alleles: [
    { a: 'B', p: 'Black-based pigment (dominant)' },
    { a: 'b', p: 'Brown / chocolate pigment (recessive)' },
  ]},
  { id: 'C', name: 'Colorpoint', order: 'C > cs > c', alleles: [
    { a: 'C', p: 'Full color (dominant)' },
    { a: 'cs', p: 'Siamese colorpoint — pale body, dark points' },
    { a: 'c', p: 'Albino — white coat, pink eyes' },
  ]},
  { id: 'D', name: 'Dilution', order: 'D > d', alleles: [
    { a: 'D', p: 'Full pigment (dominant)' },
    { a: 'd', p: 'Dilute — black to blue, chocolate to isabella' },
  ]},
  { id: 'E', name: 'Extension', order: 'Em > E > e', alleles: [
    { a: 'Em', p: 'Melanistic mask — dark face/muzzle' },
    { a: 'E', p: 'Normal — allows black pigment' },
    { a: 'e', p: 'Red — no black on body' },
  ]},
  { id: 'I', name: 'Intensity', order: 'I > i', alleles: [
    { a: 'I', p: 'Full intensity (dominant)' },
    { a: 'i', p: 'Faded intensity — red washed out to cream' },
  ]},
  { id: 'K', name: 'Dominant black', order: 'K > kbr > ky', alleles: [
    { a: 'K', p: 'Dominant black — masks the A-locus' },
    { a: 'kbr', p: 'Brindle — dark stripes over the base pattern' },
    { a: 'ky', p: 'Recessive — the A-locus pattern shows' },
  ]},
  { id: 'M', name: 'Merle', order: 'M > m', alleles: [
    { a: 'M', p: 'Merle — mottled patches of diluted color' },
    { a: 'm', p: 'No merle (recessive)' },
  ]},
  { id: 'S', name: 'White spotting', order: 'S > sp > sc > si', alleles: [
    { a: 'S', p: 'Solid — no white (dominant)' },
    { a: 'sp', p: 'Piebald — white patches' },
    { a: 'sc', p: 'Caterpillar piebald — caterpillar-shaped white patches' },
    { a: 'si', p: 'Collared — white markings' },
  ]},
  { id: 'T', name: 'Ticking', order: 'T > t', alleles: [
    { a: 'T', p: 'Ticking — freckles/spots in the white areas' },
    { a: 't', p: 'No ticking (recessive)' },
  ]},
  { id: 'V', name: 'Ear type', order: 'V > v', alleles: [
    { a: 'V', p: 'Drop ears (dominant)' },
    { a: 'v', p: 'Butterfly ears (recessive)' },
  ]},
];

const DEFAULT_SIRE = { A: ['Ay','at'], B: ['B','b'], C: ['C','cs'], D: ['D','d'], E: ['Em','E'], I: ['I','i'], K: ['K','ky'], M: ['M','m'], S: ['S','sp'], T: ['T','T'], V: ['V','v'] };
const DEFAULT_DAM  = { A: ['at','a'], B: ['b','b'], C: ['C','cs'], D: ['d','d'], E: ['e','e'], I: ['i','i'], K: ['ky','ky'], M: ['m','m'], S: ['si','si'], T: ['T','t'], V: ['v','v'] };

function buildParentUI(parent) {
  const ctn = document.getElementById(parent + 'Loci');
  for (const L of LOCI) {
    const row = document.createElement('div');
    row.className = 'locusRow';
    const idEl = document.createElement('div');
    idEl.className = 'locusId';
    idEl.textContent = L.id;
    const nameEl = document.createElement('div');
    nameEl.className = 'locusName';
    nameEl.textContent = L.name;
    row.appendChild(idEl);
    row.appendChild(nameEl);
    for (const slot of ['a','b']) {
      const sel = document.createElement('select');
      sel.id = parent + '_' + L.id + slot;
      sel.title = L.id + ' locus — ' + L.name;
      for (const al of L.alleles) {
        const opt = document.createElement('option');
        opt.value = al.a;
        opt.textContent = al.a;
        opt.title = al.p;
        sel.appendChild(opt);
      }
      row.appendChild(sel);
    }
    ctn.appendChild(row);
  }
}

function setParent(parent, g) {
  for (const L of LOCI) {
    document.getElementById(parent + '_' + L.id + 'a').value = g[L.id][0];
    document.getElementById(parent + '_' + L.id + 'b').value = g[L.id][1];
  }
}

function readParentGenotype(parent) {
  const g = {};
  for (const L of LOCI) {
    g[L.id] = [
      document.getElementById(parent + '_' + L.id + 'a').value,
      document.getElementById(parent + '_' + L.id + 'b').value,
    ];
  }
  return g;
}

function pick(arr) { return arr[Math.floor(Math.random() * 2)]; }

function inheritPuppy(dam, sire) {
  const g = {};
  for (const L of LOCI) g[L.id] = [pick(dam[L.id]), pick(sire[L.id])];
  return g;
}

function has(g, id, a) { return g[id][0] === a || g[id][1] === a; }
function homo(g, id, a) { return g[id][0] === a && g[id][1] === a; }

function euColor(g) {
  const brown = homo(g, 'B', 'b');
  const dilute = homo(g, 'D', 'd');
  if (brown) return dilute ? 'isabella' : 'chocolate';
  return dilute ? 'blue' : 'black';
}

function cType(g) {
  if (has(g, 'C', 'C')) return 'full';
  if (homo(g, 'C', 'c')) return 'albino';
  return 'colorpoint';
}

function aPattern(g) {
  if (has(g, 'A', 'Ay')) return 'sable';
  if (has(g, 'A', 'asa')) return 'saddle';
  if (homo(g, 'A', 'a')) return 'black';
  return 'tanpoints';
}

function aDisplay(g) {
  const ap = aPattern(g);
  const eu = euColor(g);
  if (ap === 'sable') return eu + ' sable';
  if (ap === 'saddle') return eu + ' saddle';
  if (ap === 'tanpoints') return eu + '-and-tan';
  return 'recessive ' + eu;
}

function whiteType(g) {
  if (has(g, 'S', 'S')) return 'none';
  if (has(g, 'S', 'sp')) return 'piebald';
  if (has(g, 'S', 'sc')) return 'caterpillar';
  return 'irish';
}

function whitePhrase(g) {
  const w = whiteType(g);
  let s = '';
  if (w === 'piebald') s = 'piebald white';
  else if (w === 'caterpillar') s = 'caterpillar piebald';
  else if (w === 'irish') s = 'collared';
  if (s && has(g, 'T', 'T')) s += ' with ticking';
  return s;
}

function earPhrase(g) {
  return homo(g, 'V', 'v') ? 'butterfly ears' : 'drop ears';
}

function phenotype(g) {
  const ct = cType(g);
  const parts = [];
  if (ct === 'albino') {
    parts.push('albino — white coat, pink eyes');
  } else {
    if (homo(g, 'E', 'e')) {
      let b = homo(g, 'I', 'i') ? 'cream coat (faded intensity)' : 'red coat';
      if (homo(g, 'M', 'M')) b = 'double merle (lethal white) — mostly white coat';
      else if (has(g, 'M', 'M')) b += ' with ghost merle';
      parts.push(b);
    } else {
      const eu = euColor(g);
      let base;
      const kDominant = has(g, 'K', 'K');
      if (kDominant) base = 'solid ' + eu;
      else if (has(g, 'K', 'kbr')) base = aPattern(g) === 'black' ? 'solid ' + eu : 'brindle ' + aDisplay(g);
      else base = aDisplay(g);
      const patternExpr = !kDominant;
      if (homo(g, 'M', 'M')) {
        base = 'double merle (lethal white) — mostly white with small ' + eu + ' patches';
      } else if (has(g, 'M', 'M')) {
        const ap = aPattern(g);
        if (has(g, 'K', 'kbr')) base = eu + ' brindlemerle';
        else if (!patternExpr) base = eu + ' merle';
        else if (ap === 'tanpoints') base = eu + ' merle with tan points';
        else if (ap === 'black') base = eu + ' merle';
        else base = aDisplay(g) + ' merle';
      }
      parts.push(base);
      if (has(g, 'E', 'Em')) parts.push('dark ' + eu + ' mask');
    }
    const w = whitePhrase(g);
    if (w) parts.push(w);
    if (ct === 'colorpoint') parts.push('colorpoint');
  }
  parts.push(earPhrase(g));
  return parts.join(', ');
}

function outOfStandard(g) {
  if (homo(g, 'M', 'M')) return true;
  if (cType(g) === 'albino') return true;
  if (homo(g, 'E', 'e') && homo(g, 'I', 'i')) return true;
  if (!homo(g, 'E', 'e') && homo(g, 'D', 'd')) return true;
  return has(g, 'K', 'kbr') && has(g, 'M', 'M');
}

function swatchColor(g) {
  const ct = cType(g);
  if (ct === 'albino') return '#f4f1ec';
  if (homo(g, 'M', 'M')) return '#efe9e0';
  if (homo(g, 'E', 'e')) return homo(g, 'I', 'i') ? '#f0e0c4' : '#c4763a';
  const map = { black: '#3b3b45', blue: '#8b93a3', chocolate: '#6e4426', isabella: '#b59d96' };
  return map[euColor(g)];
}

function genoString(g) {
  return LOCI.map(L => {
    const a = g[L.id];
    const sorted = a.slice().sort((x, y) =>
      L.alleles.findIndex(al => al.a === x) - L.alleles.findIndex(al => al.a === y));
    return sorted.join('/');
  }).join(' ');
}

function produceLitter(scroll) {
  const sire = readParentGenotype('sire');
  const dam = readParentGenotype('dam');
  let n = 2 + Math.floor(Math.random() * 7);
  const pups = [];
  for (let i = 0; i < n; i++) {
    const g = inheritPuppy(dam, sire);
    pups.push({
      id: i + 1,
      sex: Math.random() < 0.5 ? 'F' : 'M',
      g,
      pheno: phenotype(g),
      color: swatchColor(g),
      merle: has(g, 'M', 'M') && !homo(g, 'M', 'M'),
    });
  }
  renderLitter(pups);
  if (scroll) {
    const top = document.getElementById('results').offsetTop - 12;
    window.scrollTo({ top, behavior: 'smooth' });
  }
}

function renderLitter(pups) {
  const ctn = document.getElementById('results');
  const f = pups.filter(p => p.sex === 'F').length;
  const m = pups.length - f;
  const colors = {};
  for (const p of pups) colors[p.color] = (colors[p.color] || 0) + 1;
  let html = '<h3>Litter of ' + pups.length + (pups.length === 1 ? ' Puppy' : ' Puppies') + '</h3>';
  html += '<p class="summary">' + f + ' female &middot; ' + m + ' male';
  for (const [c, count] of Object.entries(colors)) {
    html += '<span class="dot" style="background:' + c + '" title="' + count + '"></span>' + count;
  }
  html += '</p><div class="litterGrid">';
  for (const p of pups) {
    html += '<div class="puppy">';
    html += '<div class="puppyTop"><span class="swatch' + (p.merle ? ' merle' : '') + '" style="background:' + p.color + '"></span>';
    html += '<span class="puppyId">Puppy ' + p.id + '</span>';
    html += '<span class="sex ' + p.sex + '">' + (p.sex === 'F' ? 'Female' : 'Male') + '</span>';
    if (outOfStandard(p.g)) html += '<span class="oosTag">Out of standard</span>';
    html += '</div>';
    html += '<p class="pheno">' + p.pheno + '</p>';
    html += '<div class="genos">' + genoString(p.g) + '</div>';
    html += '</div>';
  }
  html += '</div>';
  ctn.innerHTML = html;
}

buildParentUI('sire');
buildParentUI('dam');
setParent('sire', DEFAULT_SIRE);
setParent('dam', DEFAULT_DAM);
produceLitter(false);

window.__gen = { inheritPuppy, phenotype, genoString, outOfStandard, cType, euColor, swatchColor, LOCI };
</script>
