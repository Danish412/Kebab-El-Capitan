# Kebab-El-Capitan
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Menú Digital — Kebab El Capitan</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #121212;
    --bg-raised: #1a1a1a;
    --line: #333333;
    --ink: #F5F4F0;
    --ink-dim: #9a9a95;
    --amber: #8a5a20;
    --amber-bright: #d99a3f;
    --emerald: #0e9e6d;
    --emerald-dark: #087a53;
    --mono: 'JetBrains Mono', monospace;
    --display: 'Space Grotesk', sans-serif;
    --banner-h: 58px;
  }
  *{ box-sizing: border-box; }
  html{ -webkit-tap-highlight-color: transparent; }
  body{
    margin:0;
    background: var(--bg);
    color: var(--ink);
    font-family: var(--display);
    padding-bottom: 128px;
    -webkit-font-smoothing: antialiased;
  }
  a{ color: inherit; }

  /* ---------- TOP WARNING BANNER ---------- */
  .takeaway-banner{
    position: sticky;
    top:0;
    z-index: 50;
    background: linear-gradient(180deg, var(--amber) 0%, #6e4517 100%);
    border-bottom: 2px solid var(--amber-bright);
    color: #fff;
    text-align:center;
    padding: 10px 14px;
    min-height: calc(var(--banner-h) - 2px);
    display:flex;
    flex-direction:column;
    justify-content:center;
    font-family: var(--mono);
    font-weight: 700;
    letter-spacing: 0.03em;
    font-size: 0.82rem;
    box-shadow: 0 4px 14px rgba(0,0,0,0.35);
  }
  .takeaway-banner .line2{
    display:block;
    font-weight:400;
    font-size:0.7rem;
    opacity:0.85;
    margin-top:2px;
    letter-spacing: 0.08em;
  }

  /* ---------- HEADER ---------- */
  header.hero{
    padding: 34px 20px 22px;
    text-align:center;
    border-bottom: 1px dashed var(--line);
  }
  .ticket-tag{
    display:inline-block;
    font-family: var(--mono);
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    color: var(--ink-dim);
    border: 1px solid var(--line);
    padding: 4px 10px;
    border-radius: 2px;
    margin-bottom: 14px;
  }
  h1.brand{
    font-size: clamp(1.9rem, 7vw, 3rem);
    margin: 0;
    letter-spacing: -0.02em;
    font-weight: 700;
  }
  .brand-sub{
    font-family: var(--mono);
    color: var(--ink-dim);
    font-size: 0.85rem;
    margin-top: 10px;
    line-height:1.6;
  }
  .brand-sub b{ color: var(--ink); }

  /* ---------- NAV (category jump) ---------- */
  nav.catnav{
    display:flex;
    gap:8px;
    overflow-x:auto;
    padding: 14px 16px;
    border-bottom: 1px solid var(--line);
    position: sticky;
    top: var(--banner-h);
    background: rgba(18,18,18,0.96);
    backdrop-filter: blur(6px);
    z-index: 40;
    scrollbar-width: none;
  }
  nav.catnav::-webkit-scrollbar{ display:none; }
  nav.catnav a{
    flex: 0 0 auto;
    font-family: var(--mono);
    font-size: 0.72rem;
    letter-spacing: 0.05em;
    text-decoration:none;
    color: var(--ink-dim);
    border: 1px solid var(--line);
    padding: 7px 12px;
    border-radius: 3px;
    white-space:nowrap;
  }
  nav.catnav a:hover{ color: var(--ink); border-color: var(--ink-dim); }

  /* ---------- SAUCE STRIP ---------- */
  .sauce-strip{
    margin: 22px 16px;
    border: 1px solid var(--line);
    background: var(--bg-raised);
    border-radius: 4px;
    padding: 14px 16px;
    font-family: var(--mono);
    font-size: 0.78rem;
    color: var(--ink-dim);
  }
  .sauce-strip .label{
    color: var(--ink);
    font-weight:700;
    letter-spacing: 0.08em;
    display:block;
    margin-bottom:6px;
    font-size: 0.72rem;
  }
  .sauce-strip .chips{ display:flex; flex-wrap:wrap; gap:8px; margin-top:8px; }
  .sauce-strip .chip{
    border:1px solid var(--line);
    padding: 4px 10px;
    border-radius: 20px;
    color: var(--ink);
  }

  /* ---------- SECTIONS ---------- */
  main{ max-width: 760px; margin: 0 auto; padding: 6px 16px 10px; }
  section.category{ margin-top: 40px; scroll-margin-top: 110px; }
  .cat-head{
    display:flex;
    align-items:center;
    justify-content: space-between;
    gap:10px;
    margin-bottom: 14px;
  }
  .cat-head .bracket{
    font-family: var(--mono);
    font-weight:700;
    font-size: clamp(1.1rem, 4.5vw, 1.5rem);
    letter-spacing: 0.01em;
  }
  .cat-head .count{
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--ink-dim);
  }
  .cat-note{
    font-family: var(--mono);
    font-size: 0.74rem;
    color: var(--ink-dim);
    border-left: 2px solid var(--emerald);
    padding: 6px 10px;
    margin-bottom: 16px;
    background: rgba(14,158,109,0.06);
  }
  .cat-note b{ color: var(--ink); }

  /* item ticket row */
  .item{
    border: 1px solid var(--line);
    border-radius: 4px;
    padding: 14px 16px;
    margin-bottom: 10px;
    background: var(--bg-raised);
  }
  .item-top{
    display:flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
  }
  .item-name{
    font-weight: 600;
    font-size: 1rem;
    letter-spacing: 0.01em;
    line-height: 1.3;
  }
  .item-price{
    font-family: var(--mono);
    font-weight: 700;
    color: var(--emerald);
    font-size: 1rem;
    line-height: 1.3;
    white-space: nowrap;
  }
  .leader{
    flex: 1;
    align-self: center;
    border-bottom: 1px dotted var(--line);
    margin: 0 8px;
    min-width: 16px;
  }
  .item-desc{
    font-family: var(--mono);
    font-size: 0.74rem;
    color: var(--ink-dim);
    margin-top: 6px;
    line-height: 1.5;
  }

  /* combo/menu items (no description, simpler) */
  .item.menu-item .item-desc{ display:none; }

  /* menu sub-group headings (e.g. "MENÚS KEBAB") */
  .menu-subhead{
    display:block;
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--ink-dim);
    letter-spacing: 0.08em;
    margin: 22px 0 10px;
    padding-bottom: 4px;
    border-bottom: 1px dashed var(--line);
  }
  .menu-subhead:first-of-type{ margin-top: 4px; }

  /* ---------- FOOTER INFO ---------- */
  footer.info{
    max-width: 760px;
    margin: 40px auto 0;
    padding: 20px 16px 10px;
    border-top: 1px dashed var(--line);
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--ink-dim);
    text-align:center;
    line-height: 1.8;
  }

  /* ---------- STICKY CALL BAR ---------- */
  .call-bar{
    position: fixed;
    left:0; right:0; bottom:0;
    z-index: 60;
    background: linear-gradient(180deg, rgba(18,18,18,0) 0%, var(--bg) 22%);
    padding: 14px 16px calc(14px + env(safe-area-inset-bottom));
  }
  .call-bar-inner{
    max-width: 760px;
    margin: 0 auto;
  }
  .call-btn{
    display:flex;
    align-items:center;
    justify-content:center;
    gap: 10px;
    width: 100%;
    background: linear-gradient(180deg, var(--emerald) 0%, var(--emerald-dark) 100%);
    color: #fff;
    text-decoration:none;
    font-family: var(--display);
    font-weight: 700;
    font-size: 1.15rem;
    letter-spacing: 0.01em;
    padding: 18px 20px;
    border-radius: 10px;
    box-shadow: 0 8px 22px rgba(14,158,109,0.35), inset 0 1px 0 rgba(255,255,255,0.15);
    border: 1px solid rgba(255,255,255,0.15);
  }
  .call-btn:active{ transform: translateY(1px) scale(0.99); }
  .call-caption{
    text-align:center;
    font-family: var(--mono);
    font-size: 0.68rem;
    color: var(--ink-dim);
    margin-top: 8px;
    letter-spacing: 0.02em;
  }

  @media (min-width: 640px){
    .call-btn{ font-size: 1.25rem; }
  }
</style>
</head>
<body>

  <div class="takeaway-banner">
    ⚠️ SOLO PARA LLEVAR / TAKEAWAY ONLY
    <span class="line2">NO SERVICIO A DOMICILIO · NO SE SIRVE EN MESA · RECOGIDA EN LOCAL</span>
  </div>

  <header class="hero">
    <span class="ticket-tag">MENÚ · PEDIDO POR TELÉFONO</span>
    <h1 class="brand">KEBAB EL CAPITAN</h1>
    <div class="brand-sub">
      <b>Boulevard Juan Carlos I, nº 4</b> — Ponferrada (León)<br>
      Tel: 987 510 372 · 601 881 145
    </div>
  </header>

  <nav class="catnav">
    <a href="#kebab">KEBAB</a>
    <a href="#durum">DÜRUM</a>
    <a href="#lahmacun">LAHMACUN</a>
    <a href="#menus">MENÚS</a>
    <a href="#platos">PLATOS</a>
    <a href="#complementos">COMPLEMENTOS</a>
    <a href="#bebidas">BEBIDAS</a>
  </nav>

  <main>

    <div class="sauce-strip">
      <span class="label">🧂 SALSAS DISPONIBLES — indica tu elección al pedir</span>
      <div class="chips">
        <span class="chip">Blanca</span>
        <span class="chip">Picante</span>
        <span class="chip">Picante Fuerte</span>
        <span class="chip">Ketchup</span>
      </div>
    </div>

    <!-- ===================== KEBAB ===================== -->
    <section class="category" id="kebab">
      <div class="cat-head">
        <span class="bracket">[ KEBAB ]</span>
        <span class="count">7 opciones</span>
      </div>
      <div class="cat-note"><b>Tamaño Normal</b> incluido en el precio · <b>Tamaño XL</b> +3,00€ sobre cualquier kebab</div>

      <div class="item">
        <div class="item-top"><span class="item-name">Kebab Normal Ternera</span><span class="leader"></span><span class="item-price">5,00€</span></div>
        <div class="item-desc">Carne de ternera en pan turco, lechuga, tomate, cebolla y salsa</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Kebab de Pollo</span><span class="leader"></span><span class="item-price">5,50€</span></div>
        <div class="item-desc">Carne de pollo en pan turco, lechuga, tomate, cebolla y salsa</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Kebab Mixto</span><span class="leader"></span><span class="item-price">5,50€</span></div>
        <div class="item-desc">Carne de ternera y pollo en pan turco, lechuga, tomate, cebolla y salsa</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Kebab Carne con Queso</span><span class="leader"></span><span class="item-price">6,00€</span></div>
        <div class="item-desc">Carne de ternera y pollo en pan turco, lechuga, queso, cebolla y salsa</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Kebab Solo Carne</span><span class="leader"></span><span class="item-price">7,00€</span></div>
        <div class="item-desc">Carne de ternera o pollo en pan turco y salsa</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Kebab Vegetal</span><span class="leader"></span><span class="item-price">4,00€</span></div>
        <div class="item-desc">Pan turco, lechuga, tomate, cebolla y salsas</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Kebab con Falafel</span><span class="leader"></span><span class="item-price">5,00€</span></div>
        <div class="item-desc">Pan turco, puré de garbanzos (falafel), lechuga, tomate, cebolla y salsas</div>
      </div>
    </section>

    <!-- ===================== DÜRUM ===================== -->
    <section class="category" id="durum">
      <div class="cat-head">
        <span class="bracket">[ DÜRUM ]</span>
        <span class="count">7 opciones</span>
      </div>
      <div class="cat-note"><b>Tamaño Normal</b> incluido en el precio · <b>Tamaño XL</b> +3,00€ sobre cualquier dürum</div>

      <div class="item">
        <div class="item-top"><span class="item-name">Dürum de Ternera</span><span class="leader"></span><span class="item-price">6,00€</span></div>
        <div class="item-desc">Rollo de fina masa con carne de ternera, lechuga, tomate, cebolla y salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Dürum de Pollo</span><span class="leader"></span><span class="item-price">6,00€</span></div>
        <div class="item-desc">Rollo de fina masa con carne de pollo, lechuga, tomate, cebolla y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Dürum Mixto</span><span class="leader"></span><span class="item-price">6,00€</span></div>
        <div class="item-desc">Rollo de fina masa con carne de ternera y pollo, lechuga, tomate, cebolla y salsa griega tzatziki</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Dürum con Queso</span><span class="leader"></span><span class="item-price">6,50€</span></div>
        <div class="item-desc">Rollo de fina masa con carne de ternera o pollo, queso, lechuga, tomate, cebolla y salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Dürum Solo Carne</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Rollo de fina masa con carne de ternera o pollo y salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Dürum Vegetal</span><span class="leader"></span><span class="item-price">5,00€</span></div>
        <div class="item-desc">Rollo de fina masa con lechuga, tomate, cebolla y salsas</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Dürum con Falafel</span><span class="leader"></span><span class="item-price">5,50€</span></div>
        <div class="item-desc">Rollo de fina masa con puré de garbanzos (falafel) acompañado de lechuga, tomate, cebolla y salsas</div>
      </div>
    </section>

    <!-- ===================== LAHMACUN ===================== -->
    <section class="category" id="lahmacun">
      <div class="cat-head">
        <span class="bracket">[ LAHMACUN ]</span>
        <span class="count">7 opciones</span>
      </div>
      <div class="cat-note"><b>Tamaño Normal</b> incluido en el precio · <b>Tamaño XL</b> +3,00€ sobre cualquier lahmacun</div>

      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun de Ternera</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Masa especial enrollada rellena de fresca ensalada con carne de ternera y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun de Pollo</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Masa especial enrollada rellena de fresca ensalada con carne de pollo y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun Mixto</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Masa especial enrollada rellena de fresca ensalada con carne de ternera y pollo y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun Solo Carne</span><span class="leader"></span><span class="item-price">9,00€</span></div>
        <div class="item-desc">Masa especial enrollada rellena con carne de ternera o pollo y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun con Queso</span><span class="leader"></span><span class="item-price">8,50€</span></div>
        <div class="item-desc">Masa especial enrollada rellena de fresca ensalada con carne de ternera o pollo, queso y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun Vegetal</span><span class="leader"></span><span class="item-price">7,00€</span></div>
        <div class="item-desc">Masa especial enrollada rellena de fresca ensalada y salsas</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Lahmacun con Falafel</span><span class="leader"></span><span class="item-price">7,00€</span></div>
        <div class="item-desc">Masa especial enrollada rellena de fresca ensalada, puré de garbanzos (falafel) y salsas</div>
      </div>
    </section>

    <!-- ===================== MENÚS ===================== -->
    <section class="category" id="menus">
      <div class="cat-head">
        <span class="bracket">[ MENÚS ]</span>
        <span class="count">14 combinados</span>
      </div>
      <div class="cat-note">Todos los menús incluyen <b>bebida y patatas</b>. Precio único (sin distinción Normal/XL)</div>

      <span class="menu-subhead">— MENÚS KEBAB —</span>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Kebab de Ternera</span><span class="leader"></span><span class="item-price">8,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Kebab de Pollo</span><span class="leader"></span><span class="item-price">8,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Kebab Mixto</span><span class="leader"></span><span class="item-price">8,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Kebab con Queso</span><span class="leader"></span><span class="item-price">8,50€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Kebab Solo Carne</span><span class="leader"></span><span class="item-price">9,00€</span></div></div>

      <span class="menu-subhead">— MENÚS DÜRUM —</span>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Dürum de Ternera</span><span class="leader"></span><span class="item-price">9,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Dürum de Pollo</span><span class="leader"></span><span class="item-price">9,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Dürum Mixto</span><span class="leader"></span><span class="item-price">9,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Dürum con Queso</span><span class="leader"></span><span class="item-price">9,50€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Dürum Solo Carne</span><span class="leader"></span><span class="item-price">10,00€</span></div></div>

      <span class="menu-subhead">— MENÚS LAHMACUN —</span>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Lahmacun de Ternera</span><span class="leader"></span><span class="item-price">10,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Lahmacun de Pollo</span><span class="leader"></span><span class="item-price">10,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Lahmacun Mixto</span><span class="leader"></span><span class="item-price">10,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Menú Lahmacun Solo Carne</span><span class="leader"></span><span class="item-price">11,00€</span></div></div>
    </section>

    <!-- ===================== PLATOS ===================== -->
    <section class="category" id="platos">
      <div class="cat-head">
        <span class="bracket">[ PLATOS ]</span>
        <span class="count">7 opciones</span>
      </div>

      <div class="item">
        <div class="item-top"><span class="item-name">Plato de Ternera</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Carne de ternera, ensalada, patatas y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Plato de Pollo</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Carne de pollo, ensalada, patatas y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Plato Mixto</span><span class="leader"></span><span class="item-price">8,00€</span></div>
        <div class="item-desc">Carne de ternera y pollo, ensalada, patatas y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Plato de Carne y Patatas</span><span class="leader"></span><span class="item-price">9,00€</span></div>
        <div class="item-desc">Carne de ternera y pollo, patatas y nuestra sabrosa salsa griega (sin ensalada)</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Plato Falafel</span><span class="leader"></span><span class="item-price">7,00€</span></div>
        <div class="item-desc">Puré de garbanzos (falafel), ensalada, patatas y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Plato Solo Carne</span><span class="leader"></span><span class="item-price">13,00€</span></div>
        <div class="item-desc">Carne de ternera o pollo y nuestra sabrosa salsa griega</div>
      </div>
      <div class="item">
        <div class="item-top"><span class="item-name">Plato Gratinado</span><span class="leader"></span><span class="item-price">10,00€</span></div>
        <div class="item-desc">Carne de ternera o pollo con queso mozzarella y patatas</div>
      </div>
    </section>

    <!-- ===================== COMPLEMENTOS ===================== -->
    <section class="category" id="complementos">
      <div class="cat-head">
        <span class="bracket">[ COMPLEMENTOS ]</span>
        <span class="count">8 opciones</span>
      </div>
      <div class="cat-note"><b>Alitas y Nuggets</b> disponibles en dos raciones: 6 unidades o 12 unidades</div>

      <div class="item menu-item"><div class="item-top"><span class="item-name">Snacks Carne con Patatas</span><span class="leader"></span><span class="item-price">6,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Patatas Pequeña</span><span class="leader"></span><span class="item-price">3,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Patatas Grande</span><span class="leader"></span><span class="item-price">5,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Patatas Gratinadas</span><span class="leader"></span><span class="item-price">7,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Alitas de Pollo — 6 Unidades</span><span class="leader"></span><span class="item-price">5,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Alitas de Pollo — 12 Unidades</span><span class="leader"></span><span class="item-price">8,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Nuggets — 6 Unidades</span><span class="leader"></span><span class="item-price">5,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Nuggets — 12 Unidades</span><span class="leader"></span><span class="item-price">8,00€</span></div></div>
    </section>

    <!-- ===================== BEBIDAS ===================== -->
    <section class="category" id="bebidas">
      <div class="cat-head">
        <span class="bracket">[ BEBIDAS ]</span>
        <span class="count">2 opciones</span>
      </div>

      <div class="item menu-item"><div class="item-top"><span class="item-name">Agua</span><span class="leader"></span><span class="item-price">1,00€</span></div></div>
      <div class="item menu-item"><div class="item-top"><span class="item-name">Refrescos</span><span class="leader"></span><span class="item-price">1,50€</span></div></div>
    </section>

  </main>

  <footer class="info">
    BOULEVARD JUAN CARLOS I, Nº 4 · PONFERRADA (LEÓN)<br>
    987 510 372 · 601 881 145<br>
    SOLO RECOGIDA EN LOCAL — NO REPARTO A DOMICILIO
  </footer>

  <div class="call-bar">
    <div class="call-bar-inner">
      <a class="call-btn" href="tel:+34987510372">📞 LLAMAR Y PEDIR AHORA</a>
      <div class="call-caption">Haz tu pedido por teléfono • Recogida rápida exclusivamente en el local</div>
    </div>
  </div>

</body>
</html>
