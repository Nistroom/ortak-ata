# ortak-ata
evrimle alakalı
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Ortak Ata</title>
<style>
:root{--bg:#ecfdf5;--bg2:#f0fdfa;--card:#fff;--card2:#f8fafc;--text:#0f172a;--muted:#64748b;--muted2:#94a3b8;--border:#d1fae5;--border2:#e2e8f0;--primary:#10b981;--primary2:#0d9488;--green-bg:#ecfdf5;--green-tx:#065f46;--red-bg:#fef2f2;--red-tx:#b91c1c;--chip:#d1fae5;--chip-tx:#065f46}
body.dark{--bg:#0f172a;--bg2:#0c1425;--card:#1e293b;--card2:#0f172a;--text:#f1f5f9;--muted:#94a3b8;--muted2:#64748b;--border:#334155;--border2:#475569;--primary:#34d399;--primary2:#14b8a6;--green-bg:#064e3b;--green-tx:#a7f3d0;--red-bg:#450a0a;--red-tx:#fca5a5;--chip:#065f46;--chip-tx:#a7f3d0}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;background:linear-gradient(135deg,var(--bg) 0%,var(--bg2) 50%,var(--bg) 100%);min-height:100vh;color:var(--text);padding-bottom:80px;transition:background .3s,color .3s}
.header{background:var(--card);border-bottom:1px solid var(--border);position:sticky;top:0;z-index:20}
.hdr{max-width:600px;margin:0 auto;padding:12px 16px;display:flex;justify-content:space-between;align-items:center;gap:8px}
.brand{display:flex;align-items:center;gap:10px}
.logo{width:40px;height:40px;background:linear-gradient(135deg,var(--primary),var(--primary2));border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:20px}
.title{font-size:17px;font-weight:700;line-height:1.2}
.sub{font-size:11px;color:var(--muted)}
.actions{display:flex;align-items:center;gap:6px}
.icon-btn{width:36px;height:36px;border-radius:10px;background:var(--card2);border:1px solid var(--border2);cursor:pointer;font-size:16px;display:flex;align-items:center;justify-content:center;color:var(--text)}
.icon-btn:hover{background:var(--green-bg)}
.lang-wrap{position:relative}
.lang-menu{position:absolute;right:0;top:100%;margin-top:6px;background:var(--card);border:1px solid var(--border2);border-radius:12px;box-shadow:0 4px 16px rgba(0,0,0,.15);width:170px;overflow:hidden;z-index:30;display:none}
.lang-menu.show{display:block}
.lang-item{width:100%;text-align:left;padding:9px 16px;background:none;border:none;border-bottom:1px solid var(--border2);font-size:14px;cursor:pointer;display:flex;align-items:center;gap:8px;color:var(--text)}
.lang-item:last-child{border-bottom:none}
.lang-item:hover{background:var(--green-bg)}
.main{max-width:600px;margin:0 auto;padding:16px}
.card{background:var(--card);border-radius:16px;padding:16px;box-shadow:0 1px 3px rgba(0,0,0,.04);border:1px solid var(--border);margin-bottom:14px}
.intro{font-size:13px;color:var(--muted);line-height:1.6}
.field{margin-bottom:12px}
.lbl{display:block;font-size:13px;font-weight:500;margin-bottom:6px}
.input-w{position:relative}
.inp{width:100%;padding:12px 14px;border:1px solid var(--border2);border-radius:10px;background:var(--card2);font-size:15px;transition:.2s;outline:none;color:var(--text);font-family:inherit}
.inp:focus{border-color:var(--primary);background:var(--card);box-shadow:0 0 0 3px rgba(16,185,129,.15)}
.sug{position:absolute;top:100%;left:0;right:0;margin-top:4px;background:var(--card);border:1px solid var(--border2);border-radius:10px;box-shadow:0 4px 16px rgba(0,0,0,.15);max-height:260px;overflow-y:auto;z-index:10;display:none}
.sug.show{display:block}
.sug-item{width:100%;text-align:left;padding:10px 14px;background:none;border:none;border-bottom:1px solid var(--border2);font-size:14px;cursor:pointer;display:flex;align-items:center;gap:10px;color:var(--text)}
.sug-item:last-child{border-bottom:none}
.sug-item:hover{background:var(--green-bg)}
.sug-em{font-size:20px}
.sug-name{font-weight:500}
.sug-meta{font-size:11px;color:var(--muted2);margin-top:1px}
.sug-empty{padding:12px 16px;font-size:13px;color:var(--muted2)}
.chip{display:inline-flex;align-items:center;gap:6px;background:var(--chip);color:var(--chip-tx);padding:6px 12px;border-radius:999px;font-size:14px;font-weight:500;margin-top:8px}
.chip button{background:none;border:none;color:var(--chip-tx);font-size:18px;cursor:pointer;padding:0;line-height:1}
.chip-actions{display:inline-flex;gap:4px;margin-left:6px}
.chip-actions button{font-size:13px}
.btn{width:100%;padding:14px;background:linear-gradient(135deg,var(--primary),var(--primary2));color:#fff;border:none;border-radius:10px;font-size:15px;font-weight:600;cursor:pointer;box-shadow:0 4px 12px rgba(16,185,129,.3);transition:.2s;font-family:inherit}
.btn:hover:not(:disabled){box-shadow:0 6px 16px rgba(16,185,129,.4);transform:translateY(-1px)}
.btn:active:not(:disabled){transform:scale(.98)}
.btn:disabled{opacity:.5;cursor:not-allowed}
.btn-sec{padding:10px 14px;background:var(--card2);color:var(--text);border:1px solid var(--border2);border-radius:10px;font-size:13px;font-weight:500;cursor:pointer;font-family:inherit;transition:.15s}
.btn-sec:hover{background:var(--green-bg);border-color:var(--primary)}
.err{background:var(--red-bg);border:1px solid var(--red-tx);color:var(--red-tx);padding:10px 14px;border-radius:10px;font-size:13px;margin-bottom:12px;display:none}
.err.show{display:block}
.sec-title{font-size:12px;font-weight:600;color:var(--muted);margin:0 0 8px 4px;text-transform:uppercase;letter-spacing:.5px}
.examples{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:14px}
.ex{background:var(--card);border:1px solid var(--border2);padding:6px 12px;border-radius:999px;font-size:12px;color:var(--text);cursor:pointer;transition:.15s;font-family:inherit}
.ex:hover{border-color:var(--primary);background:var(--green-bg)}
.result{background:var(--card);border-radius:16px;overflow:hidden;box-shadow:0 4px 20px rgba(0,0,0,.1);border:1px solid var(--border);animation:sl .4s ease-out;margin-bottom:14px}
@keyframes sl{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
.r-head{background:linear-gradient(135deg,var(--primary),var(--primary2));color:#fff;padding:16px 20px;position:relative}
.r-head-label{font-size:12px;opacity:.9}
.r-head-title{font-size:19px;font-weight:700;margin-top:4px}
.r-body{padding:16px}
.hero{display:flex;align-items:center;justify-content:center;gap:16px;padding:16px 0;border-bottom:1px solid var(--border);margin-bottom:16px}
.hero-sp{text-align:center;cursor:pointer;transition:.2s}
.hero-sp:hover{transform:scale(1.05)}
.hero-em{font-size:52px;line-height:1}
.hero-name{font-size:12px;font-weight:500;margin-top:4px;color:var(--text)}
.hero-x{font-size:24px;color:var(--muted2);font-weight:300}
.section{margin-bottom:16px}
.section-title{font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.5px;margin-bottom:10px;display:flex;align-items:center;gap:6px}
.score-wrap{display:flex;align-items:center;gap:16px;background:var(--green-bg);padding:16px;border-radius:12px}
.score-svg{width:90px;height:90px;flex-shrink:0}
.score-txt{flex:1}
.score-big{font-size:18px;font-weight:700;color:var(--green-tx)}
.score-desc{font-size:11px;color:var(--green-tx);opacity:.85;margin-top:4px;line-height:1.5}
.tl{margin-top:8px}
.tl-track{position:relative;height:8px;background:var(--border);border-radius:4px;margin:24px 0 8px}
.tl-marker{position:absolute;top:50%;transform:translate(-50%,-50%);width:16px;height:16px;background:var(--primary);border:3px solid var(--card);border-radius:50%;box-shadow:0 2px 6px rgba(0,0,0,.2);transition:.3s}
.tl-labels{display:flex;justify-content:space-between;font-size:10px;color:var(--muted2)}
.tl-info{font-size:12px;color:var(--muted);text-align:center;margin-top:8px;font-weight:500}
.tree{background:var(--card2);border-radius:12px;padding:12px;font-size:13px}
.tree-2col{display:grid;grid-template-columns:1fr 1px 1fr;gap:8px;align-items:start}
.tree-col{display:flex;flex-direction:column;gap:4px}
.tree-hdr{font-weight:600;font-size:12px;margin-bottom:6px;text-align:center;padding:4px;background:var(--card);border-radius:6px}
.tree-item{font-size:11px;padding:5px 8px;border-radius:6px;text-align:center;transition:.15s}
.tree-item.common{background:var(--green-bg);color:var(--green-tx);font-weight:500}
.tree-item.diff{background:var(--card2);color:var(--muted);border:1px solid var(--border2);opacity:.7}
.tree-lca{grid-column:1/-1;margin-top:8px;text-align:center;font-size:11px;color:var(--green-tx);font-weight:600;padding:6px;background:var(--green-bg);border-radius:6px}
.comment{background:var(--card2);border-radius:12px;padding:14px}
.comment-title{font-size:10px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px;display:flex;align-items:center;gap:6px}
.comment-txt{font-size:13px;line-height:1.6}
.latin{font-size:11px;color:var(--muted2);margin-top:10px;line-height:1.5}
.latin strong{color:var(--muted)}
.r-actions{display:flex;gap:8px;margin-top:14px}
.r-actions button{flex:1}
.interesting{background:var(--card);border-radius:16px;padding:16px;border:1px solid var(--border);margin-bottom:14px}
.int-list{display:flex;flex-direction:column;gap:8px;margin-top:10px}
.int-item{display:flex;align-items:center;gap:10px;padding:10px;background:var(--card2);border-radius:10px;cursor:pointer;transition:.15s;border:1px solid transparent}
.int-item:hover{background:var(--green-bg);border-color:var(--primary)}
.int-em{font-size:22px}
.int-info{flex:1;min-width:0}
.int-name{font-size:13px;font-weight:600}
.int-desc{font-size:11px;color:var(--muted);margin-top:1px}
.int-arrow{color:var(--muted2);font-size:16px}
.footer{text-align:center;font-size:11px;color:var(--muted2);margin-top:20px;line-height:1.6}
.hidden{display:none!important}
.modal{position:fixed;inset:0;z-index:100;display:none;align-items:center;justify-content:center;padding:16px}
.modal.show{display:flex}
.modal-bg{position:absolute;inset:0;background:rgba(0,0,0,.6);backdrop-filter:blur(4px)}
.modal-body{position:relative;background:var(--card);border-radius:20px;max-width:420px;width:100%;max-height:90vh;overflow-y:auto;padding:20px;box-shadow:0 20px 40px rgba(0,0,0,.3);animation:sl .3s}
.modal-close{position:absolute;top:12px;right:12px;width:32px;height:32px;border-radius:50%;background:var(--card2);border:none;cursor:pointer;font-size:18px;color:var(--text);display:flex;align-items:center;justify-content:center}
.modal-photo{text-align:center;margin-bottom:14px;min-height:120px;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:8px}
.modal-em{font-size:72px;line-height:1}
.modal-img{max-width:100%;max-height:200px;border-radius:12px;display:none;margin:0 auto}
.modal-title{font-size:20px;font-weight:700;text-align:center;margin-bottom:4px}
.modal-latin{font-size:12px;color:var(--muted);text-align:center;font-style:italic;margin-bottom:14px}
.modal-section{margin-bottom:12px;font-size:13px}
.modal-section-title{font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.5px;margin-bottom:6px}
.tax-list{display:flex;flex-wrap:wrap;gap:4px}
.tax-pill{background:var(--green-bg);color:var(--green-tx);padding:3px 8px;border-radius:6px;font-size:11px}
.modal-actions{display:flex;gap:8px;margin-top:16px}
.modal-actions button,.modal-actions a{flex:1;padding:10px;border-radius:10px;background:var(--card2);border:1px solid var(--border2);font-size:12px;text-align:center;cursor:pointer;text-decoration:none;color:var(--text);font-family:inherit;font-weight:500}
.modal-actions button:hover,.modal-actions a:hover{background:var(--green-bg);border-color:var(--primary)}
.toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(100px);background:#0f172a;color:#fff;padding:12px 20px;border-radius:999px;font-size:13px;font-weight:500;box-shadow:0 4px 16px rgba(0,0,0,.3);transition:transform .3s,opacity .3s;z-index:200;opacity:0;pointer-events:none}
.toast.show{transform:translateX(-50%) translateY(0);opacity:1}
.fab{position:fixed;bottom:20px;right:20px;z-index:50;width:56px;height:56px;border-radius:50%;background:linear-gradient(135deg,var(--primary),var(--primary2));color:#fff;border:none;cursor:pointer;font-size:24px;box-shadow:0 6px 20px rgba(16,185,129,.5);display:flex;align-items:center;justify-content:center;transition:.2s}
.fab:hover{transform:scale(1.1)}
.fab:active{transform:scale(.95)}
@media(max-width:380px){.hero-em{font-size:44px}.hero{gap:8px}}
</style>
</head>
<body>

<header class="header">
  <div class="hdr">
    <div class="brand">
      <div class="logo">🧬</div>
      <div>
        <div class="title" id="appTitle">Ortak Ata</div>
        <div class="sub" id="appSub">Evrimsel akrabalık keşfi</div>
      </div>
    </div>
    <div class="actions">
      <button class="icon-btn" id="themeBtn" onclick="toggleTheme()" title="Theme">🌙</button>
      <div class="lang-wrap">
        <button class="icon-btn" onclick="toggleLang(event)" title="Language">🌐</button>
        <div class="lang-menu" id="langMenu">
          <button class="lang-item" onclick="setLang('tr',event)">🇹🇷 Türkçe</button>
          <button class="lang-item" onclick="setLang('en',event)">🇬🇧 English</button>
          <button class="lang-item" onclick="setLang('de',event)">🇩🇪 Deutsch</button>
          <button class="lang-item" onclick="setLang('fr',event)">🇫🇷 Français</button>
          <button class="lang-item" onclick="setLang('es',event)">🇪🇸 Español</button>
          <button class="lang-item" onclick="setLang('ru',event)">🇷🇺 Русский</button>
        </div>
      </div>
    </div>
  </div>
</header>

<main class="main">
  <div class="card"><p class="intro" id="introText"></p></div>

  <div class="card">
    <div class="field">
      <label class="lbl" id="lbl1"></label>
      <div class="input-w">
        <input class="inp" id="in1" type="text" autocomplete="off">
        <div class="sug" id="sug1"></div>
      </div>
      <div class="chip hidden" id="chip1">
        <span id="chip1n"></span>
        <span class="chip-actions">
          <button onclick="openInfo(sel[1],event)" title="Info">ℹ️</button>
          <button onclick="clearSel(1)" title="Clear">×</button>
        </span>
      </div>
    </div>
    <div class="field">
      <label class="lbl" id="lbl2"></label>
      <div class="input-w">
        <input class="inp" id="in2" type="text" autocomplete="off">
        <div class="sug" id="sug2"></div>
      </div>
      <div class="chip hidden" id="chip2">
        <span id="chip2n"></span>
        <span class="chip-actions">
          <button onclick="openInfo(sel[2],event)" title="Info">ℹ️</button>
          <button onclick="clearSel(2)" title="Clear">×</button>
        </span>
      </div>
    </div>
    <div class="err" id="errBox"></div>
    <button class="btn" id="findBtn" onclick="findResult()" disabled></button>
  </div>

  <p class="sec-title" id="exLabel"></p>
  <div class="examples" id="examples"></div>
  <div id="resultBox" class="hidden"></div>
  <div class="interesting" id="interestingBox"></div>
  <p class="footer" id="footerNote"></p>
</main>

<div class="modal" id="infoModal">
  <div class="modal-bg" onclick="closeInfo()"></div>
  <div class="modal-body">
    <button class="modal-close" onclick="closeInfo()">×</button>
    <div id="modalContent"></div>
  </div>
</div>

<div class="toast" id="toast"></div>
<button class="fab" onclick="randomDiscover()" title="Random">🎲</button>

<script>
"use strict";

// ====== DİL SIRASI ======
var LO = ['tr','en','de','fr','es','ru'];

// ====== UI ======
var UI = {
  title:['Ortak Ata','Common Ancestor','Gemeinsamer Vorfahre','Ancêtre Commun','Ancestro Común','Общий Предок'],
  sub:['Evrimsel akrabalık keşfi','Discover evolutionary kinship','Evolutionäre Verwandtschaft entdecken','Découvrir la parenté évolutive','Descubriendo el parentesco evolutivo','Исследование эволюционного родства'],
  intro:['İki canlı seç, ortak atalarını, akrabalık skorunu, soy ağacını ve zaman çizelgesini gör. 32 hayvan ve 14 bitki arasından seçim yapabilirsin.','Pick two species, see their common ancestor, relatedness score, family tree, and timeline. Choose from 32 animals and 14 plants.','Wähle zwei Lebewesen und sieh ihren gemeinsamen Vorfahren, Verwandtschaftsgrad, Stammbaum und Zeitachse. Wähle aus 32 Tieren und 14 Pflanzen.','Choisis deux espèces, découvre leur ancêtre commun, score de parenté, arbre généalogique et chronologie. Choisis parmi 32 animaux et 14 plantes.','Elige dos seres vivos, descubre su ancestro común, puntuación de parentesco, árbol genealógico y línea de tiempo. Elige entre 32 animales y 14 plantas.','Выбери два организма и узнай их общего предка, оценку родства, родословное древо и хронологию. На выбор 32 животных и 14 растений.'],
  lbl1:['1. Canlı','1. Species','1. Lebewesen','1. Espèce','1. Ser vivo','1. Организм'],
  lbl2:['2. Canlı','2. Species','2. Lebewesen','2. Espèce','2. Ser vivo','2. Организм'],
  ph1:['Örn: İnsan, Aslan, Meşe...','e.g. Human, Lion, Oak...','z.B. Mensch, Löwe, Eiche...','ex. Humain, Lion, Chêne...','ej. Humano, León, Roble...','напр. Человек, Лев, Дуб...'],
  ph2:['Örn: Şempanze, Kaplan, Muz...','e.g. Chimpanzee, Tiger, Banana...','z.B. Schimpanse, Tiger, Banane...','ex. Chimpanzé, Tigre, Banane...','ej. Chimpancé, Tigre, Plátano...','напр. Шимпанзе, Тигр, Банан...'],
  find:['Ortak Atayı Bul','Find Common Ancestor','Gemeinsamen Vorfahren finden','Trouver l\'ancêtre commun','Encontrar Ancestro Común','Найти общего предка'],
  exLbl:['Hızlı örnekler:','Quick examples:','Schnelle Beispiele:','Exemples rapides :','Ejemplos rápidos:','Быстрые примеры:'],
  footer:['Bu bir demo sitedir. Veriler yaklaşık bilimsel tahminlere dayanır.','This is a demo site. Data is based on approximate scientific estimates.','Dies ist eine Demo-Seite. Die Daten basieren auf ungefähren wissenschaftlichen Schätzungen.','Ceci est un site de démonstration. Les données reposent sur des estimations scientifiques approximatives.','Este es un sitio de demostración. Los datos se basan en estimaciones científicas aproximadas.','Это демо-сайт. Данные основаны на приблизительных научных оценках.'],
  noRes:['Sonuç bulunamadı','No results found','Keine Ergebnisse gefunden','Aucun résultat trouvé','Sin resultados','Ничего не найдено'],
  sameErr:['Aynı canlıyı iki kez seçtin. Farklı iki canlı seç.','You picked the same species twice. Choose two different ones.','Du hast dasselbe Lebewesen zweimal gewählt. Wähle zwei verschiedene.','Tu as choisi la même espèce deux fois. Choisis deux espèces différentes.','Elegiste el mismo ser vivo dos veces. Elige dos diferentes.','Ты выбрал один и тот же организм дважды. Выбери два разных.'],
  resTitle:['Ortak Ata Sonucu','Common Ancestor Result','Ergebnis: Gemeinsamer Vorfahre','Résultat : Ancêtre commun','Resultado: Ancestro Común','Результат: Общий предок'],
  lcaLbl:['Ortak Ata','Common Ancestor','Gemeinsamer Vorfahre','Ancêtre commun','Ancestro común','Общий предок'],
  timeLbl:['Yaklaşık Ayrılma','Approx. Divergence','Ungefähre Trennung','Séparation approx.','Separación aprox.','Примерное разделение'],
  comment:['Yorum','Comment','Kommentar','Commentaire','Comentario','Комментарий'],
  animal:['hayvan','animal','Tier','animal','animal','животное'],
  plant:['bitki','plant','Pflanze','plante','planta','растение'],
  unknown:['yaklaşık birkaç milyon yıl','several million years ago','vor einigen Millionen Jahren','il y a plusieurs millions d\'années','hace varios millones de años','несколько миллионов лет назад'],
  genSame:['{s1} ile {s2} aynı büyük grupta yer alır ({lca}). Ortak ataları yaklaşık {time} önce yaşamış, o zamandan beri farklı evrim yolları izlemişlerdir.','{s1} and {s2} belong to the same major group ({lca}). Their common ancestor lived about {time} ago, and they have followed different evolutionary paths since.','{s1} und {s2} gehören zur selben großen Gruppe ({lca}). Ihr gemeinsamer Vorfahre lebte vor etwa {time}, seither haben sie unterschiedliche evolutionäre Wege eingeschlagen.','{s1} et {s2} appartiennent au même grand groupe ({lca}). Leur ancêtre commun vivait il y a environ {time}, et ils ont suivi des voies évolutives différentes depuis.','{s1} y {s2} pertenecen al mismo gran grupo ({lca}). Su ancestro común vivió hace aproximadamente {time}, y desde entonces han seguido caminos evolutivos diferentes.','{s1} и {s2} относятся к одной большой группе ({lca}). Их общий предок жил примерно {time} назад, и с тех пор они пошли разными эволюционными путями.'],
  genEuk:['{s1} ile {s2} çok uzak akrabadır. Ortak ataları, karmaşık hücreli tüm canlıların atası olan ökaryot bir organizmadır. O dönemde henüz bugünkü anlamda hayvan veya bitki yoktu.','{s1} and {s2} are very distant relatives. Their common ancestor was a eukaryotic organism, the ancestor of all complex-celled life. At that time there were no animals or plants as we know them.','{s1} und {s2} sind sehr entfernte Verwandte. Ihr gemeinsamer Vorfahre war ein eukaryotischer Organismus, der Vorfahre allen komplexen zellulären Lebens. Damals gab es weder Tiere noch Pflanzen im heutigen Sinne.','{s1} et {s2} sont des parents très éloignés. Leur ancêtre commun était un organisme eucaryote, l\'ancêtre de toute vie cellulaire complexe. À cette époque il n\'y avait ni animaux ni plantes au sens actuel.','{s1} y {s2} son parientes muy lejanos. Su ancestro común era un organismo eucariota, el ancestro de toda vida celular compleja. En ese entonces no existían animales ni plantas como los conocemos.','{s1} и {s2} — очень далёкие родственники. Их общий предок был эукариотическим организмом, предком всей сложной клеточной жизни. В то время ещё не было животных и растений в современном смысле.'],
  genKingdom:['{s1} ve {s2}, {kingdom} aleminin ortak atasına sahiptir. Bu ayrım yüzlerce milyon yıl önce gerçekleşmiştir.','{s1} and {s2} share a common ancestor of the {kingdom} kingdom. This divergence happened hundreds of millions of years ago.','{s1} und {s2} teilen einen gemeinsamen Vorfahren des Reichs {kingdom}. Diese Trennung geschah vor hunderten Millionen Jahren.','{s1} et {s2} partagent un ancêtre commun du règne {kingdom}. Cette séparation a eu lieu il y a des centaines de millions d\'années.','{s1} y {s2} comparten un ancestro común del reino {kingdom}. Esta separación ocurrió hace cientos de millones de años.','{s1} и {s2} имеют общего предка царства {kingdom}. Это разделение произошло сотни миллионов лет назад.'],
  genDiff:['{s1} ({t1}) ile {s2} ({t2}) ortak atası {lca} seviyesindedir. Bu, iki grubun da o ortak atadan türediği anlamına gelir.','{s1} ({t1}) and {s2} ({t2}) share a common ancestor at the {lca} level. Both groups descended from that ancestor.','{s1} ({t1}) und {s2} ({t2}) teilen einen gemeinsamen Vorfahren auf der Ebene {lca}. Beide Gruppen stammen von diesem Vorfahren ab.','{s1} ({t1}) et {s2} ({t2}) partagent un ancêtre commun au niveau {lca}. Les deux groupes descendent de cet ancêtre.','{s1} ({t1}) y {s2} ({t2}) comparten un ancestro común en el nivel {lca}. Ambos grupos descienden de ese ancestro.','{s1} ({t1}) и {s2} ({t2}) имеют общего предка на уровне {lca}. Обе группы произошли от этого предка.'],
  share:['Paylaş','Share','Teilen','Partager','Compartir','Поделиться'],
  copy:['Kopyala','Copy','Kopieren','Copier','Copiar','Копировать'],
  copied:['Panoya kopyalandı!','Copied to clipboard!','In Zwischenablage kopiert!','Copié dans le presse-papiers !','¡Copiado al portapapeles!','Скопировано в буфер обмена!'],
  copyFail:['Kopyalanamadı','Could not copy','Konnte nicht kopieren','Échec de la copie','No se pudo copiar','Не удалось скопировать'],
  scoreLbl:['Akrabalık Skoru','Relatedness Score','Verwandtschaftsgrad','Score de parenté','Puntuación de parentesco','Оценка родства'],
  scoreH:['Ne kadar yakın?','How close?','Wie nah?','À quel point proches ?','¿Qué tan cercanos?','Насколько близки?'],
  scoreVClose:['Çok yakın akraba','Very close relatives','Sehr nahe Verwandte','Parents très proches','Parientes muy cercanos','Очень близкие родственники'],
  scoreClose:['Yakın akraba','Close relatives','Nahe Verwandte','Parents proches','Parientes cercanos','Близкие родственники'],
  scoreMid:['Orta derece akraba','Moderate relatives','Mäßig verwandt','Parents modérés','Parientes moderados','Умеренно родственные'],
  scoreFar:['Uzak akraba','Distant relatives','Entfernte Verwandte','Parents éloignés','Parientes lejanos','Далёкие родственники'],
  scoreVFar:['Çok uzak akraba','Very distant relatives','Sehr entfernte Verwandte','Parents très éloignés','Parientes muy lejanos','Очень далёкие родственники'],
  treeLbl:['Soy Ağacı','Family Tree','Stammbaum','Arbre généalogique','Árbol genealógico','Родословное древо'],
  tlLbl:['Zaman Çizelgesi','Timeline','Zeitachse','Chronologie','Línea de tiempo','Хронология'],
  tlToday:['Bugün','Today','Heute','Aujourd\'hui','Hoy','Сегодня'],
  tlAgo:['4 milyar yıl önce','4 billion years ago','vor 4 Milliarden Jahren','il y a 4 milliards d\'années','hace 4 mil millones de años','4 миллиарда лет назад'],
  tlInfo:['Ortak ata yaklaşık {time} önce yaşadı','Common ancestor lived about {time} ago','Gemeinsamer Vorfahre lebte vor etwa {time}','L\'ancêtre commun vivait il y a environ {time}','El ancestro común vivió hace aproximadamente {time}','Общий предок жил примерно {time} назад'],
  infoLbl:['Bilgi Kartı','Info Card','Infokarte','Fiche d\'info','Ficha informativa','Инфокарта'],
  close:['Kapat','Close','Schließen','Fermer','Cerrar','Закрыть'],
  wiki:['Vikipedi\'de gör','View on Wikipedia','Auf Wikipedia ansehen','Voir sur Wikipédia','Ver en Wikipedia','Смотреть в Википедии'],
  loadPhoto:['Fotoğraf yükle','Load photo','Foto laden','Charger photo','Cargar foto','Загрузить фото'],
  photoErr:['Fotoğraf yüklenemedi','Photo failed to load','Foto konnte nicht geladen werden','Échec du chargement','Error al cargar foto','Не удалось загрузить фото'],
  taxonomy:['Taksonomi','Taxonomy','Taxonomie','Taxonomie','Taxonomía','Таксономия'],
  interestingLbl:['İlginç Çiftler','Interesting Pairs','Interessante Paare','Paires intéressantes','Parejas interesantes','Интересные пары']
};

// ====== TAXA ======
var TX = {
  Living:['Canlılar','Living things','Lebewesen','Êtres vivants','Seres vivos','Живые организмы'],
  Eukaryotes:['Ökaryotlar','Eukaryotes','Eukaryoten','Eucaryotes','Eucariotas','Эукариоты'],
  Animals:['Hayvanlar','Animals','Tiere','Animaux','Animales','Животные'],
  Plants:['Bitkiler','Plants','Pflanzen','Plantes','Plantas','Растения'],
  Chordates:['Kordalılar','Chordates','Chordatiere','Chordés','Cordados','Хордовые'],
  Vertebrates:['Omurgalılar','Vertebrates','Wirbeltiere','Vertébrés','Vertebrados','Позвоночные'],
  Arthropods:['Eklembacaklılar','Arthropods','Gliederfüßer','Arthropodes','Artrópodos','Членистоногие'],
  Mollusks:['Yumuşakçalar','Mollusks','Weichtiere','Mollusques','Moluscos','Моллюски'],
  Cnidarians:['Knidliler','Cnidarians','Nesseltiere','Cnidaires','Cnidarios','Стрекающие'],
  VascularPlants:['Damarlı Bitkiler','Vascular plants','Gefäßpflanzen','Plantes vasculaires','Plantas vasculares','Сосудистые растения'],
  Insects:['Böcekler','Insects','Insekten','Insectes','Insectos','Насекомые'],
  Mammals:['Memeliler','Mammals','Säugetiere','Mammifères','Mamíferos','Млекопитающие'],
  Birds:['Kuşlar','Birds','Vögel','Oiseaux','Aves','Птицы'],
  Reptiles:['Sürüngenler','Reptiles','Reptilien','Reptiles','Reptiles','Пресмыкающиеся'],
  Amphibians:['Amfibiler','Amphibians','Amphibien','Amphibiens','Anfibios','Земноводные'],
  Fish:['Balıklar','Fish','Fische','Poissons','Peces','Рыбы'],
  FloweringPlants:['Çiçekli Bitkiler','Flowering plants','Blütenpflanzen','Plantes à fleurs','Plantas con flores','Цветковые'],
  Gymnosperms:['Açık Tohumlular','Gymnosperms','Nacktsamer','Gymnospermes','Gimnospermas','Голосеменные'],
  Ferns:['Eğreltiler','Ferns','Farne','Fougères','Helechos','Папоротники'],
  Mosses:['Karayosunları','Mosses','Moose','Mousses','Musgos','Мхи'],
  Primates:['Primatlar','Primates','Primaten','Primates','Primates','Приматы'],
  Carnivora:['Etçiller','Carnivores','Raubtiere','Carnivores','Carnívoros','Хищные'],
  Perissodactyla:['Tektoynaklılar','Odd-toed ungulates','Unpaarhufer','Périssodactyles','Perisodáctilos','Непарнокопытные'],
  Artiodactyla:['Çifttoynaklılar','Even-toed ungulates','Paarhufer','Artiodactyles','Artiodáctilos','Парнокопытные'],
  Cetaceans:['Balinalar','Cetaceans','Wale','Cétacés','Cetáceos','Китообразные'],
  Bats:['Yarasalar','Bats','Fledertiere','Chauves-souris','Murciélagos','Рукокрылые'],
  Proboscidea:['Filler','Proboscideans','Rüsseltiere','Proboscidiens','Proboscídeos','Хоботные'],
  Rodents:['Kemirgenler','Rodents','Nagetiere','Rongeurs','Roedores','Грызуны'],
  Lagomorphs:['Tavşanlar','Lagomorphs','Hasenartige','Lagomorphes','Lagomorfos','Зайцеобразные'],
  Galliformes:['Tavuksular','Galliformes','Hühnervögel','Galliformes','Galliformes','Курообразные'],
  Accipitriformes:['Gündüz Yırtıcıları','Accipitriformes','Greifvögel','Accipitriformes','Accipitriformes','Ястребообразные'],
  Sphenisciformes:['Penguengiller','Penguins','Pinguine','Manchots','Pingüinos','Пингвинообразные'],
  Squamata:['Pullular','Squamates','Schuppenkriechtiere','Squamates','Escamosos','Чешуйчатые'],
  Crocodilia:['Timsahlar','Crocodilians','Krokodile','Crocodiliens','Cocodrilos','Крокодилы'],
  Anura:['Kuyruksuzlar','Anurans','Froschlurche','Anoures','Anuros','Бесхвостые'],
  Salmoniformes:['Alabalıklar','Salmonids','Lachsartige','Salmonidés','Salmónidos','Лососеобразные'],
  Hymenoptera:['Zar Kanatlılar','Hymenopterans','Hautflügler','Hyménoptères','Himenópteros','Перепончатокрылые'],
  Arachnids:['Örümceğimsiler','Arachnids','Spinnentiere','Arachnides','Arácnidos','Паукообразные'],
  Crustaceans:['Kabuklular','Crustaceans','Krebstiere','Crustacés','Crustáceos','Ракообразные'],
  Cephalopods:['Kafadanbacaklılar','Cephalopods','Kopffüßer','Céphalopodes','Cefalópodos','Головоногие'],
  Hominidae:['İnsangiller','Hominids','Hominiden','Hominidés','Homínidos','Гоминиды'],
  Felidae:['Kedigiller','Felids','Katzen','Félidés','Félidos','Кошачьи'],
  Canidae:['Köpekgiller','Canids','Hunde','Canidés','Cánidos','Псовые'],
  Ursidae:['Ayıgiller','Bears','Bären','Ursidés','Úrsidos','Медвежьи'],
  Equidae:['Atgiller','Equids','Pferde','Équidés','Équidos','Лошадиные'],
  Bovidae:['Boynuzlugiller','Bovids','Hornträger','Bovidés','Bóvidos','Полорогие'],
  Suidae:['Domuzgiller','Pigs','Schweine','Suidés','Súidos','Свиные'],
  Delphinidae:['Yunusgiller','Dolphins','Delfine','Delphinidés','Delfínidos','Дельфиновые'],
  Balaenopteridae:['Oluklu Balinagiller','Rorquals','Furchenwale','Rorquals','Rorcuales','Полосатиковые'],
  Pteropodidae:['Meyve Yarasagiller','Megabats','Flughunde','Roussettes','Zorros voladores','Крылановые'],
  Elephantidae:['Filgiller','Elephants','Elefanten','Éléphantidés','Elefántidos','Слоновые'],
  Muridae:['Sıçangiller','Mice and rats','Langschwanzmäuse','Muridés','Múridos','Мышиные'],
  Leporidae:['Tavşangiller','Hares and rabbits','Hasen','Léporidés','Lepóridos','Зайцевые'],
  Phasianidae:['Sülüngiller','Pheasants','Fasanenartige','Phasianidés','Fasiánidos','Фазановые'],
  Accipitridae:['Atmacağiller','Hawks and eagles','Habichtartige','Accipitridés','Accipítridos','Ястребиные'],
  Spheniscidae:['Penguengiller','Penguins','Pinguine','Manchots','Pingüinos','Пингвиновые'],
  Pythonidae:['Pitongiller','Pythons','Pythons','Pythonidés','Pitónidos','Питоны'],
  Crocodylidae:['Timsahgiller','Crocodiles','Echte Krokodile','Crocodylidés','Cocodrílidos','Настоящие крокодилы'],
  Ranidae:['Su Kurbağagiller','True frogs','Echte Frösche','Ranidés','Ránidos','Настоящие лягушки'],
  Salmonidae:['Alabalıkgiller','Salmonids','Lachsartige','Salmonidés','Salmónidos','Лососёвые'],
  Apidae:['Arıgiller','Bees','Bienen','Apidés','Ápidos','Пчёлы'],
  Formicidae:['Karıncagiller','Ants','Ameisen','Formicidés','Formícidos','Муравьи'],
  Theridiidae:['Örümcekgiller','Cobweb spiders','Kugelspinnen','Théridiidés','Terídidos','Тенётники'],
  Cancridae:['Yengeçgiller','Rock crabs','Taschenkrebse','Cancridés','Cáncridos','Канкриды'],
  Pelagiidae:['Denizanasıgiller','Sea nettles','Pelagiidae','Pélagiidés','Pelágidos','Пелагииды'],
  Octopodidae:['Ahtapotgiller','Octopuses','Echte Kraken','Octopodidés','Octopódidos','Осьминоги'],
  Fagaceae:['Kayıngiller','Beeches','Buchengewächse','Fagacées','Fagáceas','Буковые'],
  Pinaceae:['Çamgiller','Pines','Kieferngewächse','Pinacées','Pináceas','Сосновые'],
  Rosaceae:['Gülgiller','Roses','Rosengewächse','Rosacées','Rosáceas','Розовые'],
  Musaceae:['Muzgiller','Bananas','Bananengewächse','Musacées','Musáceas','Банановые'],
  Solanaceae:['Patlıcangiller','Nightshades','Nachtschattengewächse','Solanacées','Solanáceas','Паслёновые'],
  Poaceae:['Buğdaygiller','Grasses','Süßgräser','Poacées','Poáceas','Злаки'],
  Vitaceae:['Asmagiller','Grapevines','Weinrebengewächse','Vitacées','Vitáceas','Виноградовые'],
  Oleaceae:['Zeytingiller','Olives','Ölbaumgewächse','Oléacées','Oleáceas','Маслиновые'],
  Dennstaedtiaceae:['Eğreltigiller','Bracken ferns','Adlerfarngewächse','Dennstaedtiacées','Dennstaedtiáceas','Деннштедтиевые'],
  Bryaceae:['Karayosunugiller','Bryaceae','Bryaceae','Bryacées','Briáceas','Бриевые']
};

// ====== RANK YILLARI (yaklaşık, yıl) ======
var RY = {
  Living:3800000000,Eukaryotes:1750000000,Animals:600000000,Plants:470000000,Chordates:525000000,
  Vertebrates:510000000,Arthropods:525000000,Mollusks:525000000,Cnidarians:600000000,
  VascularPlants:425000000,Insects:375000000,Mammals:180000000,Birds:80000000,Reptiles:285000000,
  Amphibians:330000000,Fish:450000000,FloweringPlants:145000000,Gymnosperms:325000000,
  Ferns:375000000,Mosses:425000000,Primates:62500000,Carnivora:47500000,Perissodactyla:57500000,
  Artiodactyla:60000000,Cetaceans:52500000,Bats:55000000,Proboscidea:57500000,Rodents:65000000,
  Lagomorphs:65000000,Galliformes:70000000,Accipitriformes:55000000,Sphenisciformes:55000000,
  Squamata:225000000,Crocodilia:85000000,Anura:225000000,Salmoniformes:125000000,
  Hymenoptera:225000000,Arachnids:425000000,Crustaceans:525000000,Cephalopods:450000000,
  Hominidae:8000000,Felidae:15000000,Canidae:10000000,Panthera:3750000,Canis:1500000,
  Equidae:52500000,Bovidae:22500000,Suidae:25000000,Ursidae:25000000,Delphinidae:12000000,
  Balaenopteridae:15000000,Pteropodidae:25000000,Elephantidae:25000000,Muridae:20000000,
  Leporidae:40000000,Phasianidae:25000000,Accipitridae:35000000,Spheniscidae:40000000,
  Pythonidae:50000000,Crocodylidae:60000000,Ranidae:50000000,Salmonidae:100000000,
  Apidae:90000000,Formicidae:100000000,Theridiidae:100000000,Cancridae:50000000,
  Pelagiidae:400000000,Octopodidae:300000000,Fagaceae:60000000,Pinaceae:130000000,
  Rosaceae:60000000,Musaceae:70000000,Solanaceae:40000000,Poaceae:50000000,Vitaceae:100000000,
  Oleaceae:70000000,Dennstaedtiaceae:200000000,Bryaceae:400000000,
  Homo:1000000,Pan:1500000,Gorilla:9000000,Felis:10000000,Ursus:20000000,Equus:50000000,Bos:20000000,
  Ovis:20000000,Sus:25000000,Tursiops:12000000,Balaenoptera:15000000,Pteropus:25000000,
  Loxodonta:25000000,Mus:15000000,Oryctolagus:40000000,Gallus:25000000,Aquila:35000000,
  Aptenodytes:40000000,Python:50000000,Crocodylus:60000000,Rana:50000000,Salmo:100000000,
  Apis:90000000,Formica:100000000,Latrodectus:100000000,Cancer:50000000,Pelagia:400000000,
  Octopus:300000000,Quercus:60000000,Pinus:130000000,Rosa:60000000,Malus:60000000,
  Fragaria:60000000,Musa:70000000,Solanum:20000000,Triticum:50000000,Zea:50000000,
  Vitis:100000000,Olea:70000000,Pteridium:200000000,Bryum:400000000
};

// ====== ZAMAN ETİKETLERİ ======
var TM = {
  Living:['3,5–4 milyar yıl','3.5–4 billion years','3,5–4 Milliarden Jahre','3,5–4 milliards d\'années','3,5–4 mil millones de años','3,5–4 миллиарда лет'],
  Eukaryotes:['1,5–2 milyar yıl','1.5–2 billion years','1,5–2 Milliarden Jahre','1,5–2 milliards d\'années','1,5–2 mil millones de años','1,5–2 миллиарда лет'],
  Animals:['550–650 milyon yıl','550–650 million years','550–650 Millionen Jahre','550–650 millions d\'années','550–650 millones de años','550–650 миллионов лет'],
  Plants:['450–500 milyon yıl','450–500 million years','450–500 Millionen Jahre','450–500 millions d\'années','450–500 millones de años','450–500 миллионов лет'],
  Chordates:['500–550 milyon yıl','500–550 million years','500–550 Millionen Jahre','500–550 millions d\'années','500–550 millones de años','500–550 миллионов лет'],
  Vertebrates:['500–520 milyon yıl','500–520 million years','500–520 Millionen Jahre','500–520 millions d\'années','500–520 millones de años','500–520 миллионов лет'],
  Arthropods:['500–550 milyon yıl','500–550 million years','500–550 Millionen Jahre','500–550 millions d\'années','500–550 millones de años','500–550 миллионов лет'],
  Mollusks:['500–550 milyon yıl','500–550 million years','500–550 Millionen Jahre','500–550 millions d\'années','500–550 millones de años','500–550 миллионов лет'],
  Cnidarians:['550–650 milyon yıl','550–650 million years','550–650 Millionen Jahre','550–650 millions d\'années','550–650 millones de años','550–650 миллионов лет'],
  VascularPlants:['400–450 milyon yıl','400–450 million years','400–450 Millionen Jahre','400–450 millions d\'années','400–450 millones de años','400–450 миллионов лет'],
  Insects:['350–400 milyon yıl','350–400 million years','350–400 Millionen Jahre','350–400 millions d\'années','350–400 millones de años','350–400 миллионов лет'],
  Mammals:['160–200 milyon yıl','160–200 million years','160–200 Millionen Jahre','160–200 millions d\'années','160–200 millones de años','160–200 миллионов лет'],
  Birds:['60–100 milyon yıl','60–100 million years','60–100 Millionen Jahre','60–100 millions d\'années','60–100 millones de años','60–100 миллионов лет'],
  Reptiles:['250–320 milyon yıl','250–320 million years','250–320 Millionen Jahre','250–320 millions d\'années','250–320 millones de años','250–320 миллионов лет'],
  Amphibians:['300–360 milyon yıl','300–360 million years','300–360 Millionen Jahre','300–360 millions d\'années','300–360 millones de años','300–360 миллионов лет'],
  Fish:['400–500 milyon yıl','400–500 million years','400–500 Millionen Jahre','400–500 millions d\'années','400–500 millones de años','400–500 миллионов лет'],
  FloweringPlants:['130–160 milyon yıl','130–160 million years','130–160 Millionen Jahre','130–160 millions d\'années','130–160 millones de años','130–160 миллионов лет'],
  Gymnosperms:['300–350 milyon yıl','300–350 million years','300–350 Millionen Jahre','300–350 millions d\'années','300–350 millones de años','300–350 миллионов лет'],
  Ferns:['350–400 milyon yıl','350–400 million years','350–400 Millionen Jahre','350–400 millions d\'années','350–400 millones de años','350–400 миллионов лет'],
  Mosses:['400–450 milyon yıl','400–450 million years','400–450 Millionen Jahre','400–450 millions d\'années','400–450 millones de años','400–450 миллионов лет'],
  Primates:['55–70 milyon yıl','55–70 million years','55–70 Millionen Jahre','55–70 millions d\'années','55–70 millones de años','55–70 миллионов лет'],
  Carnivora:['40–55 milyon yıl','40–55 million years','40–55 Millionen Jahre','40–55 millions d\'années','40–55 millones de años','40–55 миллионов лет'],
  Perissodactyla:['55–60 milyon yıl','55–60 million years','55–60 Millionen Jahre','55–60 millions d\'années','55–60 millones de años','55–60 миллионов лет'],
  Artiodactyla:['55–65 milyon yıl','55–65 million years','55–65 Millionen Jahre','55–65 millions d\'années','55–65 millones de años','55–65 миллионов лет'],
  Cetaceans:['50–55 milyon yıl','50–55 million years','50–55 Millionen Jahre','50–55 millions d\'années','50–55 millones de años','50–55 миллионов лет'],
  Bats:['50–60 milyon yıl','50–60 million years','50–60 Millionen Jahre','50–60 millions d\'années','50–60 millones de años','50–60 миллионов лет'],
  Proboscidea:['55–60 milyon yıl','55–60 million years','55–60 Millionen Jahre','55–60 millions d\'années','55–60 millones de años','55–60 миллионов лет'],
  Rodents:['60–70 milyon yıl','60–70 million years','60–70 Millionen Jahre','60–70 millions d\'années','60–70 millones de años','60–70 миллионов лет'],
  Lagomorphs:['60–70 milyon yıl','60–70 million years','60–70 Millionen Jahre','60–70 millions d\'années','60–70 millones de años','60–70 миллионов лет'],
  Galliformes:['60–80 milyon yıl','60–80 million years','60–80 Millionen Jahre','60–80 millions d\'années','60–80 millones de años','60–80 миллионов лет'],
  Accipitriformes:['50–60 milyon yıl','50–60 million years','50–60 Millionen Jahre','50–60 millions d\'années','50–60 millones de años','50–60 миллионов лет'],
  Sphenisciformes:['50–60 milyon yıl','50–60 million years','50–60 Millionen Jahre','50–60 millions d\'années','50–60 millones de años','50–60 миллионов лет'],
  Squamata:['200–250 milyon yıl','200–250 million years','200–250 Millionen Jahre','200–250 millions d\'années','200–250 millones de años','200–250 миллионов лет'],
  Crocodilia:['80–90 milyon yıl','80–90 million years','80–90 Millionen Jahre','80–90 millions d\'années','80–90 millones de años','80–90 миллионов лет'],
  Anura:['200–250 milyon yıl','200–250 million years','200–250 Millionen Jahre','200–250 millions d\'années','200–250 millones de años','200–250 миллионов лет'],
  Salmoniformes:['100–150 milyon yıl','100–150 million years','100–150 Millionen Jahre','100–150 millions d\'années','100–150 millones de años','100–150 миллионов лет'],
  Hymenoptera:['200–250 milyon yıl','200–250 million years','200–250 Millionen Jahre','200–250 millions d\'années','200–250 millones de años','200–250 миллионов лет'],
  Arachnids:['400–450 milyon yıl','400–450 million years','400–450 Millionen Jahre','400–450 millions d\'années','400–450 millones de años','400–450 миллионов лет'],
  Crustaceans:['500–550 milyon yıl','500–550 million years','500–550 Millionen Jahre','500–550 millions d\'années','500–550 millones de años','500–550 миллионов лет'],
  Cephalopods:['400–500 milyon yıl','400–500 million years','400–500 Millionen Jahre','400–500 millions d\'années','400–500 millones de años','400–500 миллионов лет'],
  Hominidae:['6–10 milyon yıl','6–10 million years','6–10 Millionen Jahre','6–10 millions d\'années','6–10 millones de años','6–10 миллионов лет'],
  Felidae:['10–20 milyon yıl','10–20 million years','10–20 Millionen Jahre','10–20 millions d\'années','10–20 millones de años','10–20 миллионов лет'],
  Canidae:['5–15 milyon yıl','5–15 million years','5–15 Millionen Jahre','5–15 millions d\'années','5–15 millones de años','5–15 миллионов лет'],
  Ursidae:['20–25 milyon yıl','20–25 million years','20–25 Millionen Jahre','20–25 millions d\'années','20–25 millones de años','20–25 миллионов лет'],
  Equidae:['50–55 milyon yıl','50–55 million years','50–55 Millionen Jahre','50–55 millions d\'années','50–55 millones de años','50–55 миллионов лет'],
  Bovidae:['20–25 milyon yıl','20–25 million years','20–25 Millionen Jahre','20–25 millions d\'années','20–25 millones de años','20–25 миллионов лет'],
  Suidae:['25–30 milyon yıl','25–30 million years','25–30 Millionen Jahre','25–30 millions d\'années','25–30 millones de años','25–30 миллионов лет'],
  Delphinidae:['10–15 milyon yıl','10–15 million years','10–15 Millionen Jahre','10–15 millions d\'années','10–15 millones de años','10–15 миллионов лет'],
  Balaenopteridae:['15–20 milyon yıl','15–20 million years','15–20 Millionen Jahre','15–20 millions d\'années','15–20 millones de años','15–20 миллионов лет'],
  Pteropodidae:['25–30 milyon yıl','25–30 million years','25–30 Millionen Jahre','25–30 millions d\'années','25–30 millones de años','25–30 миллионов лет'],
  Elephantidae:['25–30 milyon yıl','25–30 million years','25–30 Millionen Jahre','25–30 millions d\'années','25–30 millones de años','25–30 миллионов лет'],
  Muridae:['20–25 milyon yıl','20–25 million years','20–25 Millionen Jahre','20–25 millions d\'années','20–25 millones de años','20–25 миллионов лет'],
  Leporidae:['40–45 milyon yıl','40–45 million years','40–45 Millionen Jahre','40–45 millions d\'années','40–45 millones de años','40–45 миллионов лет'],
  Phasianidae:['25–30 milyon yıl','25–30 million years','25–30 Millionen Jahre','25–30 millions d\'années','25–30 millones de años','25–30 миллионов лет'],
  Accipitridae:['35–40 milyon yıl','35–40 million years','35–40 Millionen Jahre','35–40 millions d\'années','35–40 millones de años','35–40 миллионов лет'],
  Spheniscidae:['40–45 milyon yıl','40–45 million years','40–45 Millionen Jahre','40–45 millions d\'années','40–45 millones de años','40–45 миллионов лет'],
  Pythonidae:['50–55 milyon yıl','50–55 million years','50–55 Millionen Jahre','50–55 millions d\'années','50–55 millones de años','50–55 миллионов лет'],
  Crocodylidae:['60–70 milyon yıl','60–70 million years','60–70 Millionen Jahre','60–70 millions d\'années','60–70 millones de años','60–70 миллионов лет'],
  Ranidae:['50–60 milyon yıl','50–60 million years','50–60 Millionen Jahre','50–60 millions d\'années','50–60 millones de años','50–60 миллионов лет'],
  Salmonidae:['100–120 milyon yıl','100–120 million years','100–120 Millionen Jahre','100–120 millions d\'années','100–120 millones de años','100–120 миллионов лет'],
  Apidae:['90–100 milyon yıl','90–100 million years','90–100 Millionen Jahre','90–100 millions d\'années','90–100 millones de años','90–100 миллионов лет'],
  Formicidae:['100–120 milyon yıl','100–120 million years','100–120 Millionen Jahre','100–120 millions d\'années','100–120 millones de años','100–120 миллионов лет'],
  Theridiidae:['100–120 milyon yıl','100–120 million years','100–120 Millionen Jahre','100–120 millions d\'années','100–120 millones de años','100–120 миллионов лет'],
  Cancridae:['50–60 milyon yıl','50–60 million years','50–60 Millionen Jahre','50–60 millions d\'années','50–60 millones de años','50–60 миллионов лет'],
  Pelagiidae:['400–450 milyon yıl','400–450 million years','400–450 Millionen Jahre','400–450 millions d\'années','400–450 millones de años','400–450 миллионов лет'],
  Octopodidae:['300–350 milyon yıl','300–350 million years','300–350 Millionen Jahre','300–350 millions d\'années','300–350 millones de años','300–350 миллионов лет'],
  Fagaceae:['60–70 milyon yıl','60–70 million years','60–70 Millionen Jahre','60–70 millions d\'années','60–70 millones de años','60–70 миллионов лет'],
  Pinaceae:['130–150 milyon yıl','130–150 million years','130–150 Millionen Jahre','130–150 millions d\'années','130–150 millones de años','130–150 миллионов лет'],
  Rosaceae:['60–70 milyon yıl','60–70 million years','60–70 Millionen Jahre','60–70 millions d\'années','60–70 millones de años','60–70 миллионов лет'],
  Musaceae:['70–80 milyon yıl','70–80 million years','70–80 Millionen Jahre','70–80 millions d\'années','70–80 millones de años','70–80 миллионов лет'],
  Solanaceae:['40–50 milyon yıl','40–50 million years','40–50 Millionen Jahre','40–50 millions d\'années','40–50 millones de años','40–50 миллионов лет'],
  Poaceae:['50–60 milyon yıl','50–60 million years','50–60 Millionen Jahre','50–60 millions d\'années','50–60 millones de años','50–60 миллионов лет'],
  Vitaceae:['100–110 milyon yıl','100–110 million years','100–110 Millionen Jahre','100–110 millions d\'années','100–110 millones de años','100–110 миллионов лет'],
  Oleaceae:['70–80 milyon yıl','70–80 million years','70–80 Millionen Jahre','70–80 millions d\'années','70–80 millones de años','70–80 миллионов лет'],
  Dennstaedtiaceae:['200–220 milyon yıl','200–220 million years','200–220 Millionen Jahre','200–220 millions d\'années','200–220 millones de años','200–220 миллионов лет'],
  Bryaceae:['400–420 milyon yıl','400–420 million years','400–420 Millionen Jahre','400–420 millions d\'années','400–420 millones de años','400–420 миллионов лет']
};

// ====== TÜRLER (46 tür) ======
var SP = {
  insan:{n:['İnsan','Human','Mensch','Humain','Humano','Человек'],la:'Homo sapiens',ty:'a',em:'🧑',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Primates','Hominidae','Homo']},
  sempanze:{n:['Şempanze','Chimpanzee','Schimpanse','Chimpanzé','Chimpancé','Шимпанзе'],la:'Pan troglodytes',ty:'a',em:'🐵',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Primates','Hominidae','Pan']},
  goril:{n:['Goril','Gorilla','Gorilla','Gorille','Gorila','Горилла'],la:'Gorilla gorilla',ty:'a',em:'🦍',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Primates','Hominidae','Gorilla']},
  kedi:{n:['Kedi','Cat','Katze','Chat','Gato','Кошка'],la:'Felis catus',ty:'a',em:'🐱',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Carnivora','Felidae','Felis']},
  kopek:{n:['Köpek','Dog','Hund','Chien','Perro','Собака'],la:'Canis lupus familiaris',ty:'a',em:'🐶',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Carnivora','Canidae','Canis']},
  aslan:{n:['Aslan','Lion','Löwe','Lion','León','Лев'],la:'Panthera leo',ty:'a',em:'🦁',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Carnivora','Felidae','Panthera']},
  kaplan:{n:['Kaplan','Tiger','Tiger','Tigre','Tigre','Тигр'],la:'Panthera tigris',ty:'a',em:'🐯',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Carnivora','Felidae','Panthera']},
  kurt:{n:['Kurt','Wolf','Wolf','Loup','Lobo','Волк'],la:'Canis lupus',ty:'a',em:'🐺',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Carnivora','Canidae','Canis']},
  ayi:{n:['Ayı','Bear','Bär','Ours','Oso','Медведь'],la:'Ursus arctos',ty:'a',em:'🐻',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Carnivora','Ursidae','Ursus']},
  at:{n:['At','Horse','Pferd','Cheval','Caballo','Лошадь'],la:'Equus caballus',ty:'a',em:'🐴',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Perissodactyla','Equidae','Equus']},
  inek:{n:['İnek','Cow','Kuh','Vache','Vaca','Корова'],la:'Bos taurus',ty:'a',em:'🐄',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Artiodactyla','Bovidae','Bos']},
  koyun:{n:['Koyun','Sheep','Schaf','Mouton','Oveja','Овца'],la:'Ovis aries',ty:'a',em:'🐑',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Artiodactyla','Bovidae','Ovis']},
  domuz:{n:['Domuz','Pig','Schwein','Cochon','Cerdo','Свинья'],la:'Sus scrofa',ty:'a',em:'🐷',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Artiodactyla','Suidae','Sus']},
  yunus:{n:['Yunus','Dolphin','Delfin','Dauphin','Delfín','Дельфин'],la:'Tursiops truncatus',ty:'a',em:'🐬',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Cetaceans','Delphinidae','Tursiops']},
  balina:{n:['Balina','Whale','Wal','Baleine','Ballena','Кит'],la:'Balaenoptera musculus',ty:'a',em:'🐋',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Cetaceans','Balaenopteridae','Balaenoptera']},
  yarasa:{n:['Yarasa','Bat','Fledermaus','Chauve-souris','Murciélago','Летучая мышь'],la:'Pteropus vampyrus',ty:'a',em:'🦇',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Bats','Pteropodidae','Pteropus']},
  fil:{n:['Fil','Elephant','Elefant','Éléphant','Elefante','Слон'],la:'Loxodonta africana',ty:'a',em:'🐘',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Proboscidea','Elephantidae','Loxodonta']},
  fare:{n:['Fare','Mouse','Maus','Souris','Ratón','Мышь'],la:'Mus musculus',ty:'a',em:'🐭',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Rodents','Muridae','Mus']},
  tavsan:{n:['Tavşan','Rabbit','Kaninchen','Lapin','Conejo','Кролик'],la:'Oryctolagus cuniculus',ty:'a',em:'🐰',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Mammals','Lagomorphs','Leporidae','Oryctolagus']},
  tavuk:{n:['Tavuk','Chicken','Huhn','Poulet','Gallina','Курица'],la:'Gallus gallus',ty:'a',em:'🐔',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Birds','Galliformes','Phasianidae','Gallus']},
  kartal:{n:['Kartal','Eagle','Adler','Aigle','Águila','Орёл'],la:'Aquila chrysaetos',ty:'a',em:'🦅',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Birds','Accipitriformes','Accipitridae','Aquila']},
  penguen:{n:['Penguen','Penguin','Pinguin','Manchot','Pingüino','Пингвин'],la:'Aptenodytes forsteri',ty:'a',em:'🐧',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Birds','Sphenisciformes','Spheniscidae','Aptenodytes']},
  yilan:{n:['Yılan','Snake','Schlange','Serpent','Serpiente','Змея'],la:'Python molurus',ty:'a',em:'🐍',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Reptiles','Squamata','Pythonidae','Python']},
  timsah:{n:['Timsah','Crocodile','Krokodil','Crocodile','Cocodrilo','Крокодил'],la:'Crocodylus niloticus',ty:'a',em:'🐊',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Reptiles','Crocodilia','Crocodylidae','Crocodylus']},
  kurbaga:{n:['Kurbağa','Frog','Frosch','Grenouille','Rana','Лягушка'],la:'Rana temporaria',ty:'a',em:'🐸',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Amphibians','Anura','Ranidae','Rana']},
  somon:{n:['Somon','Salmon','Lachs','Saumon','Salmón','Лосось'],la:'Salmo salar',ty:'a',em:'🐟',tx:['Living','Eukaryotes','Animals','Chordates','Vertebrates','Fish','Salmoniformes','Salmonidae','Salmo']},
  ahtapot:{n:['Ahtapot','Octopus','Oktopus','Poulpe','Pulpo','Осьминог'],la:'Octopus vulgaris',ty:'a',em:'🐙',tx:['Living','Eukaryotes','Animals','Mollusks','Cephalopods','Octopodidae','Octopus']},
  ari:{n:['Bal Arısı','Honey Bee','Honigbiene','Abeille','Abeja','Пчела'],la:'Apis mellifera',ty:'a',em:'🐝',tx:['Living','Eukaryotes','Animals','Arthropods','Insects','Hymenoptera','Apidae','Apis']},
  karinca:{n:['Karınca','Ant','Ameise','Fourmi','Hormiga','Муравей'],la:'Formica rufa',ty:'a',em:'🐜',tx:['Living','Eukaryotes','Animals','Arthropods','Insects','Hymenoptera','Formicidae','Formica']},
  orumcek:{n:['Örümcek','Spider','Spinne','Araignée','Araña','Паук'],la:'Latrodectus mactans',ty:'a',em:'🕷️',tx:['Living','Eukaryotes','Animals','Arthropods','Arachnids','Theridiidae','Latrodectus']},
  yengec:{n:['Yengeç','Crab','Krabbe','Crabe','Cangrejo','Краб'],la:'Cancer pagurus',ty:'a',em:'🦀',tx:['Living','Eukaryotes','Animals','Arthropods','Crustaceans','Cancridae','Cancer']},
  denizanasi:{n:['Deniz Anası','Jellyfish','Qualle','Méduse','Medusa','Медуза'],la:'Pelagia noctiluca',ty:'a',em:'🪼',tx:['Living','Eukaryotes','Animals','Cnidarians','Pelagiidae','Pelagia']},
  mese:{n:['Meşe','Oak','Eiche','Chêne','Roble','Дуб'],la:'Quercus robur',ty:'p',em:'🌳',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Fagaceae','Quercus']},
  cam:{n:['Çam','Pine','Kiefer','Pin','Pino','Сосна'],la:'Pinus sylvestris',ty:'p',em:'🌲',tx:['Living','Eukaryotes','Plants','VascularPlants','Gymnosperms','Pinaceae','Pinus']},
  gul:{n:['Gül','Rose','Rose','Rose','Rosa','Роза'],la:'Rosa gallica',ty:'p',em:'🌹',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Rosaceae','Rosa']},
  elma:{n:['Elma','Apple','Apfel','Pomme','Manzana','Яблоко'],la:'Malus domestica',ty:'p',em:'🍎',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Rosaceae','Malus']},
  cilek:{n:['Çilek','Strawberry','Erdbeere','Fraise','Fresa','Земляника'],la:'Fragaria vesca',ty:'p',em:'🍓',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Rosaceae','Fragaria']},
  muz:{n:['Muz','Banana','Banane','Banane','Plátano','Банан'],la:'Musa paradisiaca',ty:'p',em:'🍌',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Musaceae','Musa']},
  domates:{n:['Domates','Tomato','Tomate','Tomate','Tomate','Помидор'],la:'Solanum lycopersicum',ty:'p',em:'🍅',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Solanaceae','Solanum']},
  patates:{n:['Patates','Potato','Kartoffel','Pomme de terre','Patata','Картофель'],la:'Solanum tuberosum',ty:'p',em:'🥔',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Solanaceae','Solanum']},
  bugday:{n:['Buğday','Wheat','Weizen','Blé','Trigo','Пшеница'],la:'Triticum aestivum',ty:'p',em:'🌾',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Poaceae','Triticum']},
  misir:{n:['Mısır','Corn','Mais','Maïs','Maíz','Кукуруза'],la:'Zea mays',ty:'p',em:'🌽',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Poaceae','Zea']},
  uzum:{n:['Üzüm','Grape','Weintraube','Raisin','Uva','Виноград'],la:'Vitis vinifera',ty:'p',em:'🍇',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Vitaceae','Vitis']},
  zeytin:{n:['Zeytin','Olive','Olive','Olive','Oliva','Олива'],la:'Olea europaea',ty:'p',em:'🫒',tx:['Living','Eukaryotes','Plants','VascularPlants','FloweringPlants','Oleaceae','Olea']},
  egrelti:{n:['Eğrelti Otu','Fern','Farn','Fougère','Helecho','Папоротник'],la:'Pteridium aquilinum',ty:'p',em:'🌿',tx:['Living','Eukaryotes','Plants','VascularPlants','Ferns','Dennstaedtiaceae','Pteridium']},
  yosun:{n:['Yosun','Moss','Moos','Mousse','Musgo','Мох'],la:'Bryum argenteum',ty:'p',em:'🪴',tx:['Living','Eukaryotes','Plants','Mosses','Bryaceae','Bryum']}
};

// ====== ÖZEL YORUMLAR ======
var SC = {
  'insan-sempanze':['İnsan ile şempanze yaşayan en yakın akrabalarımızdır. DNA\'larımız %98,7 benzer. Ortak ataları yaklaşık 6–7 milyon yıl önce Afrika\'da yaşamış bir maymundu.','Humans and chimpanzees are our closest living relatives. Our DNA is ~98.7% similar. Their common ancestor was an African ape that lived ~6–7 million years ago.','Mensch und Schimpanse sind unsere nächsten lebenden Verwandten. Unsere DNA ist zu ~98,7 % ähnlich. Ihr gemeinsamer Vorfahre war ein afrikanischer Menschenaffe vor ~6–7 Millionen Jahren.','L\'humain et le chimpanzé sont nos plus proches parents vivants. Notre ADN est similaire à ~98,7 %. Leur ancêtre commun était un grand singe africain il y a ~6–7 millions d\'années.','Los humanos y los chimpancés son nuestros parientes vivos más cercanos. Nuestro ADN es ~98,7 % similar. Su ancestro común fue un simio africano de hace ~6–7 millones de años.','Человек и шимпанзе — наши ближайшие живые родственники. Наша ДНК совпадает на ~98,7 %. Их общий предок — африканская человекообразная обезьяна, жившая ~6–7 млн лет назад.'],
  'insan-goril':['Goriller de büyük maymunlardandır. İnsan-şempanze hattından biraz daha erken ayrıldılar. Ortak ataları güçlü, ormanlık alanlarda yaşayan bir canlıydı.','Gorillas are also great apes. They diverged a bit earlier than the human-chimp line. Their common ancestor was a powerful forest-dwelling creature.','Gorillas sind ebenfalls Menschenaffen. Sie trennten sich etwas früher als die Mensch-Schimpanse-Linie. Ihr gemeinsamer Vorfahre war ein kräftiges Waldlebewesen.','Les gorilles sont aussi des grands singes. Ils se sont séparés un peu plus tôt que la lignée humain-chimpanzé. Leur ancêtre commun était une puissante créature forestière.','Los gorilas también son grandes simios. Se separaron un poco antes que la línea humano-chimpancé. Su ancestro común era una criatura poderosa que vivía en bosques.','Гориллы также относятся к человекообразным обезьянам. Они отделились чуть раньше линии человек-шимпанзе. Их общий предок был мощным лесным существом.'],
  'aslan-kaplan':['Aslan ve kaplan aynı cinse (Panthera) aittir — yakın kuzenlerdir. Ortak ataları ~3,5–4 milyon yıl önce Asya veya Afrika\'da yaşamış büyük bir kedidir.','Lions and tigers belong to the same genus (Panthera) — close cousins. Their common ancestor was a large cat that lived in Asia or Africa ~3.5–4 million years ago.','Löwen und Tiger gehören zur selben Gattung (Panthera) — nahe Cousins. Ihr gemeinsamer Vorfahre war eine große Katze aus Asien oder Afrika vor ~3,5–4 Millionen Jahren.','Les lions et les tigres appartiennent au même genre (Panthera) — proches cousins. Leur ancêtre commun était un grand félin d\'Asie ou d\'Afrique il y a ~3,5–4 millions d\'années.','Los leones y los tigres pertenecen al mismo género (Panthera) — primos cercanos. Su ancestro común fue un gran felino de Asia o África hace ~3,5–4 millones de años.','Львы и тигры относятся к одному роду (Panthera) — близкие кузены. Их общий предок — крупная кошка из Азии или Африки ~3,5–4 млн лет назад.'],
  'kedi-kopek':['Kedi ve köpek, etçiller takımının iki farklı ailesine aittir. Ortak ataları Paleosen-Eosen döneminde yaşamış genel bir etçil memeliydi.','Cats and dogs belong to two different families within the order Carnivora. Their common ancestor was a generalized carnivorous mammal from the Paleocene-Eocene.','Katzen und Hunde gehören zu zwei verschiedenen Familien innerhalb der Carnivora. Ihr gemeinsamer Vorfahre war ein generalisiertes fleischfressendes Säugetier aus dem Paläozän-Eozän.','Les chats et les chiens appartiennent à deux familles différentes de l\'ordre des Carnivores. Leur ancêtre commun était un mammifère carnivore généralisé du Paléocène-Éocène.','Los gatos y los perros pertenecen a dos familias diferentes del orden Carnivora. Su ancestro común era un mamífero carnívoro generalizado del Paleoceno-Eoceno.','Кошки и собаки принадлежат к двум разным семействам отряда хищных. Их общий предок — обобщённое хищное млекопитающее из палеоцена-эоцена.'],
  'insan-muz':['İnsan ile muz, hayvan-bitki ayrımından çok önce ortak bir ataya sahiptir: son ökaryot ortak ata (LECA). O dönemde henüz hayvan veya bitki yoktu.','Humans and bananas share a common ancestor long before the animal-plant split: the Last Eukaryotic Common Ancestor (LECA). At that time there were no animals or plants yet.','Mensch und Banane haben einen gemeinsamen Vorfahren lange vor der Tier-Pflanze-Trennung: den letzten gemeinsamen Vorfahren der Eukaryoten (LECA). Damals gab es noch keine Tiere oder Pflanzen.','L\'humain et la banane partagent un ancêtre commun bien avant la séparation animal-plante : le dernier ancêtre commun eucaryote (LECA). À cette époque il n\'y avait ni animaux ni plantes.','Los humanos y los plátanos comparten un ancestro común mucho antes de la separación animal-planta: el último ancestro común eucariota (LECA). En ese entonces no había animales ni plantas.','Человек и банан имеют общего предка задолго до разделения животных и растений: последний общий предок эукариот (LECA). В то время не было ни животных, ни растений.'],
  'cam-mese':['Meşe çiçekli, çam ise açık tohumlu bir bitkidir. Ortak ataları Karbonifer-Permiyen döneminde yaşamış, tohum üreten ilk bitki gruplarından birine aitti.','The oak is a flowering plant while the pine is a gymnosperm. Their common ancestor lived in the Carboniferous-Permian and was among the first seed-bearing plants.','Die Eiche ist eine Blütenpflanze, die Kiefer ein Nacktsamer. Ihr gemeinsamer Vorfahre lebte im Karbon-Perm und gehörte zu den ersten Samenpflanzen.','Le chêne est une plante à fleurs, tandis que le pin est un gymnosperme. Leur ancêtre commun vivait au Carbonifère-Permien et faisait partie des premières plantes à graines.','El roble es una planta con flores, mientras que el pino es una gimnosperma. Su ancestro común vivió en el Carbonífero-Pérmico y fue una de las primeras plantas con semillas.','Дуб — цветковое растение, а сосна — голосеменное. Их общий предок жил в карбоне-перми и был одним из первых семенных растений.'],
  'elma-gul':['Gül ve elma aynı familyadadır (Gülgiller / Rosaceae). Ortak ataları çiçekli ve meyve veren bir bitkiydi. Bu yüzden çiçek yapıları benzerdir.','The rose and the apple belong to the same family (Rosaceae). Their common ancestor was a flowering and fruiting plant. That\'s why their flower structures are similar.','Rose und Apfel gehören zur selben Familie (Rosaceae). Ihr gemeinsamer Vorfahre war eine blühende und fruchttragende Pflanze. Deshalb sind ihre Blütenstrukturen ähnlich.','La rose et la pomme appartiennent à la même famille (Rosaceae). Leur ancêtre commun était une plante à fleurs et à fruits. C\'est pourquoi leurs structures florales sont similaires.','La rosa y la manzana pertenecen a la misma familia (Rosaceae). Su ancestro común era una planta con flores y frutos. Por eso sus estructuras florales son similares.','Роза и яблоко относятся к одному семейству (Rosaceae). Их общий предок был цветущим и плодоносящим растением. Поэтому строение их цветков схоже.'],
  'bugday-misir':['Buğday ve mısır aynı familyaya (buğdaygiller / Poaceae) aittir. Ortak ataları ot benzeri bir bitkiydi. İnsanlar ikisini de tarımla büyük ölçüde değiştirmiştir.','Wheat and corn belong to the same family (Poaceae / grasses). Their common ancestor was a grass-like plant. Humans have greatly modified both through agriculture.','Weizen und Mais gehören zur selben Familie (Poaceae / Gräser). Ihr gemeinsamer Vorfahre war eine grasartige Pflanze. Der Mensch hat beide durch Landwirtschaft stark verändert.','Le blé et le maïs appartiennent à la même famille (Poaceae / graminées). Leur ancêtre commun était une plante ressemblant à de l\'herbe. Les humains ont largement modifié les deux par l\'agriculture.','El trigo y el maíz pertenecen a la misma familia (Poaceae / gramíneas). Su ancestro común era una planta parecida a la hierba. Los humanos han modificado enormemente ambos mediante la agricultura.','Пшеница и кукуруза относятся к одному семейству (Poaceae / злаки). Их общий предок был травянистым растением. Человек сильно изменил оба вида через сельское хозяйство.'],
  'insan-tavuk':['İnsan (memeli) ile tavuk (kuş) ortak atası, yumurtayla çoğalan karasal bir amniyottu. Bu ayrım ~300 milyon yıl önce, dinozorlardan önce gerçekleşti.','The common ancestor of humans (mammals) and chickens (birds) was a land-dwelling, egg-laying amniote. This split happened ~300 million years ago, before the dinosaurs.','Der gemeinsame Vorfahre von Mensch (Säugetier) und Huhn (Vogel) war ein landbewohnender, eierlegender Amniot. Diese Trennung geschah vor ~300 Millionen Jahren, vor den Dinosauriern.','L\'ancêtre commun de l\'humain (mammifère) et du poulet (oiseau) était un amniote terrestre pondeur d\'œufs. Cette séparation a eu lieu il y a ~300 millions d\'années, avant les dinosaures.','El ancestro común del humano (mamífero) y la gallina (ave) era un amniota terrestre que ponía huevos. Esta separación ocurrió hace ~300 millones de años, antes de los dinosaurios.','Общий предок человека (млекопитающего) и курицы (птицы) был наземным яйцекладущим амниотом. Это разделение произошло ~300 млн лет назад, до динозавров.'],
  'insan-yilan':['İnsan ve yılan da amniyot ortak atadan gelir. Yılanlar sürüngenler içinde özel bir gruptur; bacaklarını sonradan kaybetmişlerdir.','Humans and snakes descend from an amniote common ancestor. Snakes are a special group of reptiles that later lost their legs.','Mensch und Schlange stammen von einem amnioten Vorfahren ab. Schlangen sind eine besondere Reptiliengruppe, die später ihre Beine verlor.','L\'humain et le serpent descendent d\'un ancêtre commun amniote. Les serpents sont un groupe particulier de reptiles qui a perdu ses pattes plus tard.','Los humanos y las serpientes descienden de un ancestro común amniota. Las serpientes son un grupo especial de reptiles que perdieron sus patas más tarde.','Человек и змея происходят от общего предка-амниота. Змеи — особая группа рептилий, позже утратившая ноги.'],
  'kopek-kurt':['Köpek ve kurt aynı cinse (Canis) aittir. Köpek aslında evcilleştirilmiş bir kurttur. Ayrılma ~15.000–40.000 yıl önce insanların evcilleştirmesiyle başladı.','Dogs and wolves belong to the same genus (Canis). Dogs are essentially domesticated wolves. Divergence began ~15,000–40,000 years ago through human domestication.','Hund und Wolf gehören zur selben Gattung (Canis). Hunde sind im Grunde domestizierte Wölfe. Die Trennung begann vor ~15.000–40.000 Jahren durch Domestizierung.','Le chien et le loup appartiennent au même genre (Canis). Les chiens sont essentiellement des loups domestiqués. La divergence a commencé il y a ~15 000–40 000 ans.','Los perros y los lobos pertenecen al mismo género (Canis). Los perros son esencialmente lobos domesticados. La divergencia comenzó hace ~15.000–40.000 años.','Собака и волк относятся к одному роду (Canis). Собаки — это по сути одомашненные волки. Разделение началось ~15 000–40 000 лет назад.'],
  'yunus-balina':['Yunus ve balina aynı gruba (Cetacea) aittir. İkisi de karada yaşayan atalardan evrimleşmiş deniz memelileridir.','Dolphins and whales both belong to the Cetacea group. Both evolved from land-dwelling ancestors into marine mammals.','Delfine und Wale gehören beide zu den Cetacea. Beide entwickelten sich aus landlebenden Vorfahren zu Meeressäugern.','Les dauphins et les baleines appartiennent tous deux aux Cétacés. Tous deux ont évolué à partir d\'ancêtres terrestres vers des mammifères marins.','Los delfines y las ballenas pertenecen al grupo Cetacea. Ambos evolucionaron de ancestros terrestres a mamíferos marinos.','Дельфины и киты относятся к группе китообразных. Оба произошли от наземных предков и стали морскими млекопитающими.'],
  'yilan-timsah':['Yılan ve timsah, sürüngenler sınıfının farklı gruplarına aittir. Ortak ataları ~250–320 milyon yıl önce yaşamış sürüngen benzeri bir canlıydı.','Snakes and crocodiles belong to different groups within Reptilia. Their common ancestor was a reptile-like creature that lived ~250–320 million years ago.','Schlangen und Krokodile gehören zu verschiedenen Gruppen der Reptilien. Ihr gemeinsamer Vorfahre war ein reptilienartiges Lebewesen vor ~250–320 Millionen Jahren.','Les serpents et les crocodiles appartiennent à différents groupes de reptiles. Leur ancêtre commun était une créature reptilienne il y a ~250–320 millions d\'années.','Las serpientes y los cocodrilos pertenecen a diferentes grupos dentro de Reptilia. Su ancestro común era una criatura reptiliana de hace ~250–320 millones de años.','Змеи и крокодилы относятся к разным группам рептилий. Их общий предок был рептилиеподобным существом ~250–320 млн лет назад.'],
  'ari-karinca':['Arı ve karınca aynı takıma (Zar Kanatlılar / Hymenoptera) aittir. İkisi de sosyal böceklerdir ve karmaşık koloniler kurar.','Bees and ants belong to the same order (Hymenoptera). Both are social insects that build complex colonies.','Bienen und Ameisen gehören zur selben Ordnung (Hymenoptera). Beide sind soziale Insekten, die komplexe Kolonien bilden.','Les abeilles et les fourmis appartiennent au même ordre (Hymenoptera). Toutes deux sont des insectes sociaux qui forment des colonies complexes.','Las abejas y las hormigas pertenecen al mismo orden (Hymenoptera). Ambas son insectos sociales que forman colonias complejas.','Пчёлы и муравьи относятся к одному отряду (Hymenoptera). Оба — социальные насекомые, строящие сложные колонии.'],
  'patates-domates':['Patates ve domates aynı cinse (Solanum) aittir — Patlıcangiller familyasından. İkisi de insanlar için önemli tarım bitkileridir.','Potatoes and tomatoes belong to the same genus (Solanum) in the nightshade family. Both are important agricultural plants for humans.','Kartoffeln und Tomaten gehören zur selben Gattung (Solanum) in der Familie der Nachtschattengewächse. Beide sind wichtige Nutzpflanzen.','Les pommes de terre et les tomates appartiennent au même genre (Solanum), famille des Solanacées. Toutes deux sont des plantes agricoles importantes.','Las patatas y los tomates pertenecen al mismo género (Solanum) de la familia Solanaceae. Ambos son plantas agrícolas importantes.','Картофель и помидор относятся к одному роду (Solanum) семейства паслёновых. Оба — важные сельскохозяйственные растения.'],
  'kedi-aslan':['Ev kedisi ile aslan aynı familyaya (Kedigiller) aittir. Ortak ataları Miosen döneminde yaşamış küçük, çevik bir kediydi. Aslanlar sonradan devleşti.','The domestic cat and the lion belong to the same family (Felidae). Their common ancestor was a small, agile cat from the Miocene. Lions later became enormous.','Hauskatze und Löwe gehören zur selben Familie (Felidae). Ihr gemeinsamer Vorfahre war eine kleine, wendige Katze aus dem Miozän. Löwen wurden später riesig.','Le chat domestique et le lion appartiennent à la même famille (Felidae). Leur ancêtre commun était un petit chat agile du Miocène. Les lions sont devenus énormes plus tard.','El gato doméstico y el león pertenecen a la misma familia (Felidae). Su ancestro común era un gato pequeño y ágil del Mioceno. Los leones se hicieron enormes después.','Домашняя кошка и лев относятся к одному семейству (Felidae). Их общий предок — маленькая ловкая кошка из миоцена. Позже львы стали огромными.'],
  'insan-ahtapot':['İnsan (omurgalı) ile ahtapot (yumuşakça) çok uzak akrabadır. Ortak ataları, tüm iki yanlı simetrik hayvanların atası olan ~600 milyon yıllık bir canlıdır.','Humans (vertebrates) and octopuses (mollusks) are very distant relatives. Their common ancestor was a ~600-million-year-old creature, the ancestor of all bilaterally symmetric animals.','Mensch (Wirbeltier) und Oktopus (Weichtier) sind sehr entfernte Verwandte. Ihr gemeinsamer Vorfahre war ein ~600 Millionen Jahre altes Lebewesen, der Vorfahre aller bilateral symmetrischen Tiere.','L\'humain (vertébré) et le poulpe (mollusque) sont des parents très éloignés. Leur ancêtre commun était une créature d\'environ 600 millions d\'années, l\'ancêtre de tous les animaux à symétrie bilatérale.','Los humanos (vertebrados) y los pulpos (moluscos) son parientes muy lejanos. Su ancestro común era una criatura de ~600 millones de años, el ancestro de todos los animales con simetría bilateral.','Человек (позвоночное) и осьминог (моллюск) — очень далёкие родственники. Их общий предок — существо возрастом ~600 млн лет, предок всех двусторонне-симметричных животных.']
};

// ====== STATE ======
var lang='tr';
var sel={1:null,2:null};
var darkMode=false;
var currentInfoKey=null;

// ====== HELPERS ======
function $(id){return document.getElementById(id);}
function byLang(arr){if(!arr)return '';var i=LO.indexOf(lang);return(i>=0&&arr[i]!=null)?arr[i]:arr[0];}
function tUI(k){return byLang(UI[k])||k;}
function tTX(k){return TX[k]?byLang(TX[k]):k;}
function tTM(k){return TM[k]?byLang(TM[k]):tUI('unknown');}
function tSP(k){return SP[k]?byLang(SP[k].n):k;}
function typeLabel(ty){return ty==='a'?tUI('animal'):tUI('plant');}
function norm(s){return(s||'').toLowerCase().replace(/ı/g,'i').replace(/ğ/g,'g').replace(/ü/g,'u').replace(/ş/g,'s').replace(/ö/g,'o').replace(/ç/g,'c').replace(/ä/g,'a').replace(/ë/g,'e').replace(/ï/g,'i').replace(/ÿ/g,'y').trim();}

// ====== TOAST ======
function toast(msg){
  var el=$('toast');
  el.textContent=msg;
  el.classList.add('show');
  setTimeout(function(){el.classList.remove('show');},2000);
}

// ====== TEMA ======
function toggleTheme(){
  darkMode=!darkMode;
  document.body.classList.toggle('dark',darkMode);
  $('themeBtn').textContent=darkMode?'☀️':'🌙';
  try{localStorage.setItem('ortakAtaDark',darkMode?'1':'0');}catch(_){}
}

// ====== DİL ======
function toggleLang(e){if(e)e.stopPropagation();$('langMenu').classList.toggle('show');}
function setLang(l,e){
  if(e)e.stopPropagation();
  lang=l;
  try{localStorage.setItem('ortakAtaLang',l);}catch(_){}
  $('langMenu').classList.remove('show');
  render();renderExamples();renderInteresting();
  if(sel[1]&&sel[2]&&!$('resultBox').classList.contains('hidden'))findResult();
}

function render(){
  $('appTitle').textContent=tUI('title');
  $('appSub').textContent=tUI('sub');
  $('introText').textContent=tUI('intro');
  $('lbl1').textContent=tUI('lbl1');
  $('lbl2').textContent=tUI('lbl2');
  $('in1').placeholder=tUI('ph1');
  $('in2').placeholder=tUI('ph2');
  $('findBtn').textContent=tUI('find');
  $('exLabel').textContent=tUI('exLbl');
  $('footerNote').textContent=tUI('footer');
  document.documentElement.lang=lang;
  document.title=tUI('title');
  if(sel[1])$('chip1n').textContent=SP[sel[1]].em+' '+tSP(sel[1]);
  if(sel[2])$('chip2n').textContent=SP[sel[2]].em+' '+tSP(sel[2]);
}

// ====== ÖRNEKLER ======
var exList=[['insan','sempanze'],['aslan','kaplan'],['kedi','kopek'],['insan','muz'],['mese','cam'],['kopek','domates'],['insan','goril'],['at','inek'],['yunus','balina'],['yilan','timsah'],['ari','karinca'],['elma','gul'],['bugday','misir'],['insan','tavuk'],['kedi','aslan'],['patates','domates'],['insan','ahtapot'],['kopek','kurt']];
function renderExamples(){
  var html='';
  for(var i=0;i<exList.length;i++){
    var a=exList[i][0],b=exList[i][1];
    html+='<button class="ex" onclick="setExample(\''+a+'\',\''+b+'\')">'+tSP(a)+' × '+tSP(b)+'</button>';
  }
  $('examples').innerHTML=html;
}

// ====== İLGİNÇ ÇİFTLER ======
var intList=[
  {a:'insan',b:'ahtapot',desc:['hayvanlar aleminin en uzak akrabalarından','from the most distant relatives in the animal kingdom','von den entferntesten Verwandten im Tierreich','parmi les parents les plus éloignés du règne animal','entre los parientes más lejanos del reino animal','среди самых далёких родственников в животном мире']},
  {a:'insan',b:'muz',desc:['hayvan-bitki ayrımının kökeni','origin of the animal-plant split','Ursprung der Tier-Pflanze-Trennung','origine de la séparation animal-plante','origen de la separación animal-planta','происхождение разделения животных и растений']},
  {a:'kedi',b:'aslan',desc:['evcil kediden aslana','from domestic cat to lion','von der Hauskatze zum Löwen','du chat domestique au lion','del gato doméstico al león','от домашней кошки ко льву']},
  {a:'yilan',b:'timsah',desc:['aynı sınıfın çok farklı üyeleri','very different members of the same class','sehr unterschiedliche Mitglieder derselben Klasse','membres très différents de la même classe','miembros muy diferentes de la misma clase','совсем разные члены одного класса']},
  {a:'yunus',b:'balina',desc:['deniz memelileri','marine mammals','Meeressäuger','mammifères marins','mamíferos marinos','морские млекопитающие']},
  {a:'patates',b:'domates',desc:['aynı cins, çok farklı görünüm','same genus, very different look','selbe Gattung, sehr unterschiedlich','même genre, très différent','mismo género, muy diferente','один род, совсем разный вид']}
];
function renderInteresting(){
  var html='<p class="sec-title">'+tUI('interestingLbl')+'</p><div class="int-list">';
  for(var i=0;i<intList.length;i++){
    var it=intList[i];
    html+='<div class="int-item" onclick="setExample(\''+it.a+'\',\''+it.b+'\')">';
    html+='<span class="int-em">'+SP[it.a].em+SP[it.b].em+'</span>';
    html+='<div class="int-info"><div class="int-name">'+tSP(it.a)+' × '+tSP(it.b)+'</div>';
    html+='<div class="int-desc">'+byLang(it.desc)+'</div></div>';
    html+='<span class="int-arrow">→</span></div>';
  }
  html+='</div>';
  $('interestingBox').innerHTML=html;
}

// ====== ÖNERİLER ======
function showSug(n){
  var box=$('sug'+n);
  var q=norm($('in'+n).value);
  var list;
  if(q.length===0)list=['insan','sempanze','kedi','kopek','aslan','at','tavuk','mese','gul','elma'];
  else{
    list=[];
    var keys=Object.keys(SP);
    for(var i=0;i<keys.length;i++){
      var k=keys[i];
      if(norm(tSP(k)).indexOf(q)!==-1||norm(SP[k].la).indexOf(q)!==-1||k.indexOf(q)!==-1){
        list.push(k);
        if(list.length>=10)break;
      }
    }
  }
  if(list.length===0)box.innerHTML='<div class="sug-empty">'+tUI('noRes')+'</div>';
  else{
    var html='';
    for(var i=0;i<list.length;i++){
      var k=list[i],s=SP[k];
      html+='<button class="sug-item" onclick="pickSpecies('+n+',\''+k+'\')">';
      html+='<span class="sug-em">'+s.em+'</span>';
      html+='<div><div class="sug-name">'+tSP(k)+'</div>';
      html+='<div class="sug-meta">'+s.la+' · '+typeLabel(s.ty)+'</div></div>';
      html+='</button>';
    }
    box.innerHTML=html;
  }
  box.classList.add('show');
}
function hideSug(){$('sug1').classList.remove('show');$('sug2').classList.remove('show');}

function pickSpecies(n,key){
  sel[n]=key;
  $('in'+n).value='';
  $('in'+n).classList.add('hidden');
  $('chip'+n).classList.remove('hidden');
  $('chip'+n+'n').textContent=SP[key].em+' '+tSP(key);
  hideSug();
  $('errBox').classList.remove('show');
  updateBtn();
}
function clearSel(n){
  sel[n]=null;
  $('in'+n).value='';
  $('in'+n).classList.remove('hidden');
  $('chip'+n).classList.add('hidden');
  $('resultBox').classList.add('hidden');
  $('errBox').classList.remove('show');
  updateBtn();
  try{history.replaceState(null,'',location.pathname);}catch(_){}
}
function updateBtn(){$('findBtn').disabled=!(sel[1]&&sel[2]);}

function setExample(a,b){
  pickSpecies(1,a);pickSpecies(2,b);findResult();
}

// ====== ÇEKİRDEK ======
function findLCA(t1,t2){
  var i=0;
  while(i<t1.length&&i<t2.length&&t1[i]===t2[i])i++;
  return{rank:t1[i-1]||'Living',depth:i};
}
function getSpecial(a,b){
  var k1=[a,b].sort().join('-');
  var k2=[b,a].sort().join('-');
  return SC[k1]||SC[k2]||null;
}

function genericComment(a,b,lcaRank,timeText){
  var s1n=tSP(a),s2n=tSP(b);
  var t1=SP[a].ty,t2=SP[b].ty;
  var str;
  if(lcaRank==='Eukaryotes'||lcaRank==='Living')str=tUI('genEuk');
  else if(lcaRank==='Animals'||lcaRank==='Plants'){
    str=tUI('genKingdom');
    str=str.replace(/\{kingdom\}/g,lcaRank==='Animals'?tUI('animal'):tUI('plant'));
  }
  else if(t1===t2){
    str=tUI('genSame');
    str=str.replace(/\{lca\}/g,tTX(lcaRank)).replace(/\{time\}/g,timeText);
  }
  else{
    str=tUI('genDiff');
    str=str.replace(/\{t1\}/g,typeLabel(t1)).replace(/\{t2\}/g,typeLabel(t2)).replace(/\{lca\}/g,tTX(lcaRank));
  }
  str=str.replace(/\{s1\}/g,s1n).replace(/\{s2\}/g,s2n);
  return str;
}

function getScore(depth){return Math.round(depth/9*100);}
function scoreLabel(score){
  if(score>=80)return tUI('scoreVClose');
  if(score>=60)return tUI('scoreClose');
  if(score>=40)return tUI('scoreMid');
  if(score>=20)return tUI('scoreFar');
  return tUI('scoreVFar');
}

// Logaritmik pozisyon: 4 myö = sol, bugün = sağ
function logPos(years){
  var maxY=4e9,minY=1;
  var lmin=Math.log10(minY),lmax=Math.log10(maxY);
  var pos=(Math.log10(Math.max(years,1))-lmin)/(lmax-lmin);
  return 100*(1-pos);
}

function treeHTML(a,b,lcaDepth){
  var ta=SP[a].tx,tb=SP[b].tx;
  var leftItems='',rightItems='';
  var maxLen=Math.max(ta.length,tb.length);
  for(var i=0;i<maxLen;i++){
    var ca=ta[i]||'',cb=tb[i]||'';
    var common=i<lcaDepth;
    if(ca)leftItems+='<div class="tree-item '+(common?'common':'diff')+'">'+tTX(ca)+'</div>';
    if(cb)rightItems+='<div class="tree-item '+(common?'common':'diff')+'">'+tTX(cb)+'</div>';
  }
  return '<div class="tree"><div class="tree-2col">'+
    '<div class="tree-col"><div class="tree-hdr">'+SP[a].em+' '+tSP(a)+'</div>'+leftItems+'</div>'+
    '<div style="width:1px;background:var(--border);"></div>'+
    '<div class="tree-col"><div class="tree-hdr">'+SP[b].em+' '+tSP(b)+'</div>'+rightItems+'</div>'+
    '<div class="tree-lca">🌟 '+tUI('lcaLbl')+': '+tTX(ta[lcaDepth-1]||'Living')+'</div>'+
    '</div></div>';
}

function findResult(){
  $('errBox').classList.remove('show');
  if(!sel[1]||!sel[2])return;
  if(sel[1]===sel[2]){$('errBox').textContent=tUI('sameErr');$('errBox').classList.add('show');return;}
  var a=sel[1],b=sel[2];
  var lca=findLCA(SP[a].tx,SP[b].tx);
  var timeText=tTM(lca.rank);
  var lcaText=tTX(lca.rank);
  var special=getSpecial(a,b);
  var comment=special?byLang(special):genericComment(a,b,lca.rank,timeText);
  var score=getScore(lca.depth);
  var years=RY[lca.rank]||5e6;
  var pos=logPos(years);
  var circumference=2*Math.PI*40;
  var offset=circumference*(1-score/100);

  try{history.replaceState(null,'','?a='+a+'&b='+b+'&lang='+lang+(darkMode?'&theme=dark':''));}catch(_){}

  var tree=treeHTML(a,b,lca.depth);

  var html='';
  html+='<div class="result">';
  html+='<div class="r-head"><div class="r-head-label">'+tUI('resTitle')+'</div>';
  html+='<div class="r-head-title">'+SP[a].em+' '+tSP(a)+' × '+SP[b].em+' '+tSP(b)+'</div></div>';
  html+='<div class="r-body">';
  // Hero
  html+='<div class="hero">';
  html+='<div class="hero-sp" onclick="openInfo(\''+a+'\',event)"><div class="hero-em">'+SP[a].em+'</div><div class="hero-name">'+tSP(a)+'</div></div>';
  html+='<div class="hero-x">×</div>';
  html+='<div class="hero-sp" onclick="openInfo(\''+b+'\',event)"><div class="hero-em">'+SP[b].em+'</div><div class="hero-name">'+tSP(b)+'</div></div>';
  html+='</div>';
  // Skor
  html+='<div class="section"><div class="section-title">📊 '+tUI('scoreH')+'</div>';
  html+='<div class="score-wrap">';
  html+='<svg class="score-svg" viewBox="0 0 100 100">';
  html+='<circle cx="50" cy="50" r="40" stroke="rgba(0,0,0,0.08)" stroke-width="8" fill="none"/>';
  html+='<circle cx="50" cy="50" r="40" stroke="var(--primary)" stroke-width="8" fill="none" stroke-dasharray="'+circumference+'" stroke-dashoffset="'+offset+'" stroke-linecap="round" transform="rotate(-90 50 50)"/>';
  html+='<text x="50" y="57" text-anchor="middle" font-size="22" font-weight="700" fill="var(--green-tx)">'+score+'</text>';
  html+='</svg>';
  html+='<div class="score-txt"><div class="score-big">'+scoreLabel(score)+'</div>';
  html+='<div class="score-desc">'+tUI('lcaLbl')+': '+lcaText+'<br>'+tUI('timeLbl')+': '+timeText+'</div></div>';
  html+='</div></div>';
  // Zaman çizelgesi
  html+='<div class="section"><div class="section-title">🕰️ '+tUI('tlLbl')+'</div>';
  html+='<div class="tl"><div class="tl-track">';
  html+='<div class="tl-marker" style="left:'+Math.min(99,Math.max(1,pos))+'%"></div>';
  html+='</div>';
  html+='<div class="tl-labels"><span>'+tUI('tlAgo')+'</span><span>'+tUI('tlToday')+'</span></div>';
  html+='<div class="tl-info">'+tUI('tlInfo').replace('{time}',timeText)+'</div>';
  html+='</div></div>';
  // Soy ağacı
  html+='<div class="section"><div class="section-title">🌳 '+tUI('treeLbl')+'</div>'+tree+'</div>';
  // Yorum
  html+='<div class="section"><div class="comment"><div class="comment-title">💡 '+tUI('comment')+'</div>';
  html+='<p class="comment-txt">'+comment+'</p></div>';
  html+='<div class="latin"><p><strong>'+tSP(a)+'</strong>: '+SP[a].la+'</p>';
  html+='<p><strong>'+tSP(b)+'</strong>: '+SP[b].la+'</p></div></div>';
  // Aksiyon
  html+='<div class="r-actions">';
  html+='<button class="btn-sec" onclick="shareResult()">📤 '+tUI('share')+'</button>';
  html+='<button class="btn-sec" onclick="copyResult()">📋 '+tUI('copy')+'</button>';
  html+='</div>';
  html+='</div></div>';

  $('resultBox').innerHTML=html;
  $('resultBox').classList.remove('hidden');
  $('resultBox').scrollIntoView({behavior:'smooth',block:'start'});
}

function buildShareText(){
  if(!sel[1]||!sel[2])return'';
  var a=sel[1],b=sel[2];
  var lca=findLCA(SP[a].tx,SP[b].tx);
  var timeText=tTM(lca.rank);
  var lcaText=tTX(lca.rank);
  var score=getScore(lca.depth);
  var url=location.href;
  return tUI('resTitle')+':\n'+SP[a].em+' '+tSP(a)+' × '+SP[b].em+' '+tSP(b)+'\n'+tUI('lcaLbl')+': '+lcaText+'\n'+tUI('timeLbl')+': '+timeText+'\n'+tUI('scoreLbl')+': '+score+'/100\n\n'+url;
}

function shareResult(){
  var txt=buildShareText();
  if(!txt)return;
  if(navigator.share){
    navigator.share({title:tUI('title'),text:txt,url:location.href}).catch(function(){});
  }else{
    copyResult();
  }
}

function copyResult(){
  var txt=buildShareText();
  if(!txt)return;
  var done=function(){toast(tUI('copied'));};
  var fail=function(){
    var ta=document.createElement('textarea');
    ta.value=txt;ta.style.position='fixed';ta.style.opacity='0';
    document.body.appendChild(ta);ta.select();
    try{document.execCommand('copy');done();}catch(_){toast(tUI('copyFail'));}
    document.body.removeChild(ta);
  };
  if(navigator.clipboard&&navigator.clipboard.writeText){
    navigator.clipboard.writeText(txt).then(done).catch(fail);
  }else fail();
}

// ====== RASTGELE ======
function randomDiscover(){
  var keys=Object.keys(SP);
  var a,b;
  do{a=keys[Math.floor(Math.random()*keys.length)];b=keys[Math.floor(Math.random()*keys.length)];}while(a===b);
  setExample(a,b);
}

// ====== BİLGİ KARTI ======
function openInfo(key,e){
  if(e)e.stopPropagation();
  if(!key)return;
  currentInfoKey=key;
  var s=SP[key];
  var taxHTML='';
  for(var i=0;i<s.tx.length;i++)taxHTML+='<span class="tax-pill">'+tTX(s.tx[i])+'</span>';
  var html='';
  html+='<div class="modal-photo"><div class="modal-em" id="modalEm">'+s.em+'</div>';
  html+='<img class="modal-img" id="modalImg" alt=""></div>';
  html+='<div class="modal-title">'+tSP(key)+'</div>';
  html+='<div class="modal-latin">'+s.la+'</div>';
  html+='<div class="modal-section"><div class="modal-section-title">🧬 '+tUI('infoLbl')+'</div>';
  html+='<p style="font-size:13px;color:var(--muted);line-height:1.6">'+tSP(key)+' — '+typeLabel(s.ty)+'.</p></div>';
  html+='<div class="modal-section"><div class="modal-section-title">'+tUI('taxonomy')+'</div>';
  html+='<div class="tax-list">'+taxHTML+'</div></div>';
  html+='<div class="modal-actions">';
  html+='<a href="https://tr.wikipedia.org/wiki/'+encodeURIComponent(s.la.replace(/ /g,'_'))+'" target="_blank" rel="noopener">🌐 '+tUI('wiki')+'</a>';
  html+='<button onclick="loadPhoto()">📷 '+tUI('loadPhoto')+'</button>';
  html+='</div>';
  $('modalContent').innerHTML=html;
  $('infoModal').classList.add('show');
}

function closeInfo(){
  $('infoModal').classList.remove('show');
  currentInfoKey=null;
}

function loadPhoto(){
  if(!currentInfoKey)return;
  var s=SP[currentInfoKey];
  var wiki=s.la.replace(/ /g,'_');
  var img=$('modalImg');
  var url='https://en.wikipedia.org/api/rest_v1/page/summary/'+encodeURIComponent(wiki);
  fetch(url,{headers:{'Accept':'application/json'}}).then(function(res){
    if(!res.ok)throw new Error('not ok');
    return res.json();
  }).then(function(data){
    if(data.thumbnail&&data.thumbnail.source){
      img.src=data.thumbnail.source;
      img.style.display='block';
      $('modalEm').style.display='none';
    }else throw new Error('no thumbnail');
  }).catch(function(){
    toast(tUI('photoErr'));
  });
}

// ====== PWA MANIFEST (güvenli, sadece http/https) ======
function setupPWA(){
  try{
    if(location.protocol!=='http:'&&location.protocol!=='https:')return;
    var manifest={
      name:tUI('title'),
      short_name:tUI('title'),
      start_url:'./',
      display:'standalone',
      background_color:'#ecfdf5',
      theme_color:'#10b981',
      icons:[]
    };
    var svg='<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><rect width="100" height="100" rx="22" fill="#10b981"/><text x="50" y="70" font-size="60" text-anchor="middle" fill="white">🧬</text></svg>';
    var encoded='data:image/svg+xml,'+encodeURIComponent(svg);
    manifest.icons=[{src:encoded,sizes:'192x192',type:'image/svg+xml'}];
    var blob=new Blob([JSON.stringify(manifest)],{type:'application/manifest+json'});
    var link=document.createElement('link');
    link.rel='manifest';
    link.href=URL.createObjectURL(blob);
    document.head.appendChild(link);
  }catch(_){/* sessizce geç */}
}

// ====== SERVICE WORKER (sadece http/https, güvenli) ======
function setupSW(){
  try{
    if(!('serviceWorker' in navigator))return;
    if(location.protocol!=='http:'&&location.protocol!=='https:')return;
    navigator.serviceWorker.register('sw.js').catch(function(){/* sessiz */});
  }catch(_){/* sessizce geç */}
}

// ====== INIT ======
function init(){
  // localStorage güvenli
  try{
    var savedLang=localStorage.getItem('ortakAtaLang');
    if(savedLang&&LO.indexOf(savedLang)!==-1)lang=savedLang;
    var savedDark=localStorage.getItem('ortakAtaDark');
    if(savedDark==='1'){darkMode=true;document.body.classList.add('dark');$('themeBtn').textContent='☀️';}
  }catch(_){}

  // URL parametreleri
  try{
    var p=new URLSearchParams(location.search);
    var la=p.get('lang');if(la&&LO.indexOf(la)!==-1)lang=la;
    if(p.get('theme')==='dark'){darkMode=true;document.body.classList.add('dark');$('themeBtn').textContent='☀️';}
    var pa=p.get('a'),pb=p.get('b');
    if(pa&&pb&&SP[pa]&&SP[pb]&&pa!==pb){
      sel[1]=pa;sel[2]=pb;
      $('in1').classList.add('hidden');$('in2').classList.add('hidden');
      $('chip1').classList.remove('hidden');$('chip2').classList.remove('hidden');
      $('chip1n').textContent=SP[pa].em+' '+tSP(pa);
      $('chip2n').textContent=SP[pb].em+' '+tSP(pb);
    }
  }catch(_){}

  render();
  renderExamples();
  renderInteresting();
  updateBtn();

  // URL'den gelen sonucu göster
  if(sel[1]&&sel[2]){
    setTimeout(function(){findResult();},100);
  }

  // Input olayları
  $('in1').addEventListener('input',function(){showSug(1);});
  $('in2').addEventListener('input',function(){showSug(2);});
  $('in1').addEventListener('focus',function(){showSug(1);});
  $('in2').addEventListener('focus',function(){showSug(2);});

  // Dış tıklama
  document.addEventListener('click',function(e){
    if(!e.target.closest('.input-w'))hideSug();
    if(!e.target.closest('.lang-wrap'))$('langMenu').classList.remove('show');
  });

  // Escape → modal kapat
  document.addEventListener('keydown',function(e){
    if(e.key==='Escape')closeInfo();
  });

  // PWA + SW güvenli
  setupPWA();
  setupSW();
}

// Hata yakalayıcı — sandbox/SW hatalarını yut
window.addEventListener('error',function(e){
  var msg=(e.message||'')+'';
  if(msg.indexOf('serviceWorker')!==-1||msg.indexOf('SecurityError')!==-1||msg.indexOf('sandboxed')!==-1||msg.indexOf('blob:')!==-1)return;
  var div=document.createElement('div');
  div.id='jsErr';
  div.style.cssText='position:fixed;top:0;left:0;right:0;background:#fee2e2;color:#991b1b;padding:10px;font-family:monospace;font-size:12px;z-index:9999;border-bottom:2px solid #dc2626;white-space:pre-wrap';
  div.textContent='⚠️ '+e.message+' ('+(e.filename||'')+':'+e.lineno+')';
  document.body.appendChild(div);
});

if(document.readyState==='loading')document.addEventListener('DOMContentLoaded',init);
else init();
</script>
</body>
</html>
