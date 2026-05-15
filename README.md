# PSITINERARY26
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Palm Springs · June 18–21</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --sand: #F5EFE0;
    --sand-dark: #E8DEC8;
    --terracotta: #C4622D;
    --terracotta-light: #E8896A;
    --terracotta-pale: #F5E0D6;
    --sage: #6B8C6E;
    --sage-light: #A8C4A2;
    --sage-pale: #E4EDE4;
    --dusk: #2C3E50;
    --dusk-mid: #4A6278;
    --sky: #87CEEB;
    --gold: #C9943A;
    --text-primary: #1A1208;
    --text-secondary: #5C4A2A;
    --text-muted: #9A856A;
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--sand);
    color: var(--text-primary);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* HERO */
  .hero {
    background: var(--dusk);
    color: white;
    padding: 3rem 2rem 2rem;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 40px,
      rgba(255,255,255,0.015) 40px,
      rgba(255,255,255,0.015) 80px
    );
  }
  .hero-inner { position: relative; max-width: 800px; margin: 0 auto; }
  .hero-eyebrow {
    font-family: 'DM Sans', sans-serif;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--terracotta-light);
    margin-bottom: 12px;
  }
  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.4rem, 6vw, 3.6rem);
    font-weight: 400;
    line-height: 1.1;
    margin-bottom: 1rem;
  }
  .hero-title em { font-style: italic; color: var(--terracotta-light); }
  .hero-meta {
    display: flex;
    gap: 24px;
    flex-wrap: wrap;
    margin-top: 1.5rem;
  }
  .hero-pill {
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 100px;
    padding: 6px 16px;
    font-size: 13px;
    color: rgba(255,255,255,0.8);
  }

  /* WEATHER BAR */
  .weather-bar {
    background: var(--dusk-mid);
    padding: 1rem 2rem;
    display: flex;
    justify-content: center;
    gap: 0;
  }
  .weather-bar-inner {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    max-width: 800px;
    width: 100%;
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 10px;
    overflow: hidden;
  }
  .w-day-cell {
    padding: 12px 16px;
    text-align: center;
    border-right: 1px solid rgba(255,255,255,0.1);
  }
  .w-day-cell:last-child { border-right: none; }
  .w-label { font-size: 11px; color: rgba(255,255,255,0.5); letter-spacing: 0.06em; margin-bottom: 4px; }
  .w-temp { font-size: 20px; font-weight: 500; color: var(--terracotta-light); }
  .w-sky { font-size: 11px; color: rgba(255,255,255,0.4); margin-top: 2px; }

  /* NAV TABS */
  .nav-tabs {
    background: var(--sand-dark);
    border-bottom: 1px solid rgba(0,0,0,0.08);
    display: flex;
    justify-content: center;
    padding: 0 2rem;
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .tab-btn {
    background: none;
    border: none;
    border-bottom: 3px solid transparent;
    padding: 1rem 1.5rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    font-weight: 500;
    color: var(--text-muted);
    cursor: pointer;
    transition: all 0.2s;
    letter-spacing: 0.02em;
  }
  .tab-btn:hover { color: var(--text-secondary); }
  .tab-btn.active {
    color: var(--terracotta);
    border-bottom-color: var(--terracotta);
  }

  /* MAIN CONTENT */
  .main { max-width: 800px; margin: 0 auto; padding: 2rem; }
  .tab-panel { display: none; }
  .tab-panel.active { display: block; }

  /* DAY CARDS */
  .day-card {
    background: white;
    border-radius: 16px;
    margin-bottom: 16px;
    overflow: hidden;
    border: 1px solid rgba(0,0,0,0.06);
    animation: fadeUp 0.4s ease both;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .day-card:nth-child(1) { animation-delay: 0.05s; }
  .day-card:nth-child(2) { animation-delay: 0.1s; }
  .day-card:nth-child(3) { animation-delay: 0.15s; }
  .day-card:nth-child(4) { animation-delay: 0.2s; }

  .day-header {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 16px 20px;
    background: var(--sand);
    border-bottom: 1px solid rgba(0,0,0,0.06);
    cursor: pointer;
  }
  .day-badge {
    background: var(--terracotta);
    color: white;
    font-size: 11px;
    font-weight: 500;
    padding: 4px 12px;
    border-radius: 100px;
    letter-spacing: 0.04em;
    white-space: nowrap;
  }
  .day-name {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-weight: 400;
    color: var(--text-primary);
    flex: 1;
  }
  .day-chevron {
    font-size: 18px;
    color: var(--text-muted);
    transition: transform 0.2s;
  }
  .day-card.open .day-chevron { transform: rotate(180deg); }

  .day-body { padding: 0 20px 16px; display: none; }
  .day-card.open .day-body { display: block; }

  .event-block {
    display: flex;
    gap: 14px;
    padding: 14px 0;
    border-bottom: 1px solid rgba(0,0,0,0.05);
  }
  .event-block:last-child { border-bottom: none; }
  .event-time {
    font-size: 12px;
    color: var(--text-muted);
    width: 60px;
    flex-shrink: 0;
    padding-top: 2px;
    font-weight: 500;
  }
  .event-content { flex: 1; }
  .event-title { font-size: 15px; font-weight: 500; color: var(--text-primary); margin-bottom: 3px; }
  .event-detail { font-size: 13px; color: var(--text-secondary); line-height: 1.55; }
  .event-tag {
    display: inline-block;
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 100px;
    margin-top: 6px;
    font-weight: 500;
  }
  .tag-pool { background: #DDEEFF; color: #1A4A7A; }
  .tag-food { background: var(--terracotta-pale); color: #7A2A0A; }
  .tag-spa  { background: var(--sage-pale); color: #2A5C2E; }
  .tag-explore { background: #EEE8FF; color: #3A2A7A; }
  .tag-night { background: #E8E8F0; color: #2A2A4A; }

  /* TIP */
  .tip-box {
    background: var(--terracotta-pale);
    border-left: 3px solid var(--terracotta);
    border-radius: 10px;
    padding: 14px 16px;
    font-size: 13px;
    color: var(--text-secondary);
    line-height: 1.6;
    margin-top: 8px;
  }
  .tip-box strong { color: var(--terracotta); }

  /* GROCERY */
  .grocery-controls {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 1.25rem;
  }
  .grocery-progress { font-size: 13px; color: var(--text-muted); }
  .reset-btn {
    background: none;
    border: 1px solid rgba(0,0,0,0.15);
    border-radius: 8px;
    padding: 6px 14px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--text-secondary);
    cursor: pointer;
    transition: all 0.15s;
  }
  .reset-btn:hover { background: rgba(0,0,0,0.05); }

  .legend {
    display: flex;
    gap: 14px;
    margin-bottom: 1.25rem;
    flex-wrap: wrap;
  }
  .legend-item { display: flex; align-items: center; gap: 6px; font-size: 12px; color: var(--text-muted); }
  .legend-dot {
    width: 10px; height: 10px; border-radius: 50%;
  }
  .dot-fri { background: var(--terracotta); }
  .dot-sun { background: var(--sage); }
  .dot-all { background: var(--gold); }

  .grocery-section { margin-bottom: 1.5rem; animation: fadeUp 0.35s ease both; }
  .grocery-section:nth-child(3) { animation-delay: 0.05s; }
  .grocery-section:nth-child(4) { animation-delay: 0.1s; }
  .grocery-section:nth-child(5) { animation-delay: 0.15s; }
  .grocery-section:nth-child(6) { animation-delay: 0.2s; }
  .grocery-section:nth-child(7) { animation-delay: 0.25s; }
  .grocery-section:nth-child(8) { animation-delay: 0.3s; }

  .grocery-section-title {
    font-size: 11px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--text-muted);
    margin-bottom: 8px;
  }
  .grocery-card {
    background: white;
    border-radius: 14px;
    overflow: hidden;
    border: 1px solid rgba(0,0,0,0.06);
  }
  .grocery-row {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 11px 16px;
    border-bottom: 1px solid rgba(0,0,0,0.05);
    cursor: pointer;
    transition: background 0.15s;
    user-select: none;
  }
  .grocery-row:last-child { border-bottom: none; }
  .grocery-row:hover { background: rgba(0,0,0,0.02); }
  .grocery-row.checked { background: rgba(0,0,0,0.02); }
  .grocery-row.checked .grocery-name {
    color: var(--text-muted);
    text-decoration: line-through;
  }

  .check-circle {
    width: 20px; height: 20px;
    border-radius: 50%;
    border: 1.5px solid rgba(0,0,0,0.2);
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    transition: all 0.15s;
    color: white;
    font-size: 11px;
  }
  .grocery-row.checked .check-circle {
    background: var(--sage);
    border-color: var(--sage);
  }
  .grocery-name { font-size: 14px; color: var(--text-primary); flex: 1; }
  .grocery-note { font-size: 12px; color: var(--text-muted); }
  .grocery-cat {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }
  .cat-fri { background: var(--terracotta); }
  .cat-sun { background: var(--sage); }
  .cat-all { background: var(--gold); }

  /* PROGRESS BAR */
  .progress-bar-wrap {
    background: rgba(0,0,0,0.08);
    border-radius: 100px;
    height: 4px;
    margin-bottom: 1.25rem;
    overflow: hidden;
  }
  .progress-bar-fill {
    height: 100%;
    background: var(--sage);
    border-radius: 100px;
    transition: width 0.3s ease;
    width: 0%;
  }
</style>
</head>
<body>

<div class="hero">
  <div class="hero-inner">
    <p class="hero-eyebrow">Friends Trip · Chill & Relaxing</p>
    <h1 class="hero-title">Palm Springs,<br><em>June 18–21</em></h1>
    <div class="hero-meta">
      <span class="hero-pill">☀️ 4 Days</span>
      <span class="hero-pill">👥 5–6 People</span>
      <span class="hero-pill">🏠 Airbnb</span>
      <span class="hero-pill">🌡️ Pool weather</span>
    </div>
  </div>
</div>

<div class="weather-bar">
  <div class="weather-bar-inner">
    <div class="w-day-cell"><p class="w-label">Thu 6/18</p><p class="w-temp">104°</p><p class="w-sky">Sunny</p></div>
    <div class="w-day-cell"><p class="w-label">Fri 6/19</p><p class="w-temp">107°</p><p class="w-sky">Sunny</p></div>
    <div class="w-day-cell"><p class="w-label">Sat 6/20</p><p class="w-temp">108°</p><p class="w-sky">Sunny</p></div>
    <div class="w-day-cell"><p class="w-label">Sun 6/21</p><p class="w-temp">105°</p><p class="w-sky">Sunny</p></div>
  </div>
</div>

<nav class="nav-tabs">
  <button class="tab-btn active" onclick="switchTab('itinerary', this)">Itinerary</button>
  <button class="tab-btn" onclick="switchTab('grocery', this)">Grocery List</button>
</nav>

<div class="main">

  <!-- ITINERARY TAB -->
  <div id="tab-itinerary" class="tab-panel active">

    <div class="day-card open">
      <div class="day-header" onclick="toggleDay(this)">
        <span class="day-badge">Thu · Jun 18</span>
        <span class="day-name">Arrival & settle in</span>
        <span class="day-chevron">▾</span>
      </div>
      <div class="day-body">
        <div class="event-block">
          <span class="event-time">Afternoon</span>
          <div class="event-content">
            <p class="event-title">Check in & hit the pool immediately</p>
            <p class="event-detail">Drop bags, change, don't even think about anything else. June afternoons run 100°+ — the pool is mandatory, not optional.</p>
            <span class="event-tag tag-pool">Pool time</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">7 PM</span>
          <div class="event-content">
            <p class="event-title">Dinner at Birba</p>
            <p class="event-detail">Wood-fired pizza and natural wine on a great outdoor patio. Relaxed, no dress code, perfect group vibe. Book ahead — it fills up.</p>
            <span class="event-tag tag-food">Dinner</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">After</span>
          <div class="event-content">
            <p class="event-title">Nightcap at The Amigo Room</p>
            <p class="event-detail">Divey-cool cocktail bar inside Ace Hotel. Low-key crowd, good drinks — no need to go hard on night one.</p>
            <span class="event-tag tag-night">Nightcap</span>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card open">
      <div class="day-header" onclick="toggleDay(this)">
        <span class="day-badge">Fri · Jun 19</span>
        <span class="day-name">Spa day — full rest mode</span>
        <span class="day-chevron">▾</span>
      </div>
      <div class="day-body">
        <div class="event-block">
          <span class="event-time">9 AM</span>
          <div class="event-content">
            <p class="event-title">Breakfast at the Airbnb</p>
            <p class="event-detail">Eggs, bacon, hash browns, avocado toast — full spread. Leisurely morning before the spa, no rush.</p>
            <span class="event-tag tag-food">Breakfast at home</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">11 AM</span>
          <div class="event-content">
            <p class="event-title">Spa at Two Bunch Palms</p>
            <p class="event-detail">20 min north in Desert Hot Springs. Natural hot springs, grotto pools, full menu of treatments. Book 2–3 massages as a group in advance. Well Spa at Miramonte is a closer alternative if you'd rather stay in town.</p>
            <span class="event-tag tag-spa">Spa</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">4 PM</span>
          <div class="event-content">
            <p class="event-title">Back to the pool</p>
            <p class="event-detail">Float, nap, snacks, drinks. No agenda. This is peak desert living.</p>
            <span class="event-tag tag-pool">Pool time</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">7:30 PM</span>
          <div class="event-content">
            <p class="event-title">Dinner at Workshop Kitchen + Bar</p>
            <p class="event-detail">Industrial-chic space, excellent cocktail program, sharable plates. Great for groups — book ahead.</p>
            <span class="event-tag tag-food">Dinner</span>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card open">
      <div class="day-header" onclick="toggleDay(this)">
        <span class="day-badge">Sat · Jun 20</span>
        <span class="day-name">One outing, then chill</span>
        <span class="day-chevron">▾</span>
      </div>
      <div class="day-body">
        <div class="event-block">
          <span class="event-time">8 AM</span>
          <div class="event-content">
            <p class="event-title">Palm Springs Aerial Tramway — first tram</p>
            <p class="event-detail">The top station sits at 8,500 ft — 30°+ cooler than the desert floor. Stunning views, genuinely refreshing. Go first tram of the day before it gets crowded.</p>
            <span class="event-tag tag-explore">Activity</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">10 AM</span>
          <div class="event-content">
            <p class="event-title">Quick stroll on Palm Canyon Drive</p>
            <p class="event-detail">Vintage shops, galleries, coffee. Do it now before it gets too hot to be outside.</p>
            <span class="event-tag tag-explore">Explore</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">12 PM</span>
          <div class="event-content">
            <p class="event-title">Pool the rest of the afternoon</p>
            <p class="event-detail">Noon through 5 PM — stay horizontal. Order drinks, put on a playlist, do absolutely nothing productive.</p>
            <span class="event-tag tag-pool">Pool time</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">7 PM</span>
          <div class="event-content">
            <p class="event-title">Dinner at Tac/Quila or La Quinta Cliffhouse</p>
            <p class="event-detail">Tac/Quila for casual Mexican with great margaritas and a fun scene. La Quinta Cliffhouse for a nicer sit-down with mountain views — a short drive but worth it for a special group dinner.</p>
            <span class="event-tag tag-food">Dinner</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">After</span>
          <div class="event-content">
            <p class="event-title">The Rowan rooftop or Hunters</p>
            <p class="event-detail">Rowan Hotel rooftop for cocktails with a skyline view. Or Hunters for a high-energy dance bar if the group wants to go bigger on the last night out.</p>
            <span class="event-tag tag-night">Night out</span>
          </div>
        </div>
      </div>
    </div>

    <div class="day-card open">
      <div class="day-header" onclick="toggleDay(this)">
        <span class="day-badge">Sun · Jun 21</span>
        <span class="day-name">Slow morning & head out</span>
        <span class="day-chevron">▾</span>
      </div>
      <div class="day-body">
        <div class="event-block">
          <span class="event-time">9 AM</span>
          <div class="event-content">
            <p class="event-title">Continental breakfast at the Airbnb</p>
            <p class="event-detail">Bagels, croissants, fruit, yogurt, OJ. Easy, no cooking, everyone grazes on their own timeline.</p>
            <span class="event-tag tag-food">Breakfast at home</span>
          </div>
        </div>
        <div class="event-block">
          <span class="event-time">11 AM</span>
          <div class="event-content">
            <p class="event-title">Last dip before checkout</p>
            <p class="event-detail">One final hour in the pool. Pack, load up, hit the road before peak afternoon heat for the drive back.</p>
            <span class="event-tag tag-pool">Pool time</span>
          </div>
        </div>
      </div>
    </div>

    <div class="tip-box">
      <strong>June heat reminder:</strong> Plan all outdoor activity before 10 AM or after 7 PM. Stay very hydrated — the dry desert heat sneaks up on you. Sunscreen in every bag, every day.
    </div>

  </div>

  <!-- GROCERY TAB -->
  <div id="tab-grocery" class="tab-panel">

    <div class="grocery-controls">
      <span class="grocery-progress" id="progress-label">0 of 32 items checked</span>
      <button class="reset-btn" onclick="resetGrocery()">Reset all</button>
    </div>

    <div class="progress-bar-wrap">
      <div class="progress-bar-fill" id="progress-bar"></div>
    </div>

    <div class="legend">
      <div class="legend-item"><span class="legend-dot dot-fri"></span> Friday breakfast</div>
      <div class="legend-item"><span class="legend-dot dot-sun"></span> Sunday continental</div>
      <div class="legend-item"><span class="legend-dot dot-all"></span> General / drinks</div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Eggs & protein — Friday breakfast</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Eggs</span><span class="grocery-note">18-pack</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Bacon</span><span class="grocery-note">2 packs</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Breakfast sausage</span><span class="grocery-note">links or patties</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Shredded cheese</span><span class="grocery-note">cheddar or Mexican blend</span><span class="grocery-cat cat-fri"></span></div>
      </div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Sides — Friday breakfast</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Potatoes</span><span class="grocery-note">for home fries / hash</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Avocados</span><span class="grocery-note">3–4, ripe</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Salsa</span><span class="grocery-note">jar or fresh</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Sourdough bread</span><span class="grocery-note">for toast</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Butter</span><span class="grocery-cat cat-fri"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Hot sauce</span><span class="grocery-note">Cholula or Tapatio</span><span class="grocery-cat cat-fri"></span></div>
      </div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Continental spread — Sunday</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Bagels or croissants</span><span class="grocery-note">6-pack</span><span class="grocery-cat cat-sun"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Cream cheese</span><span class="grocery-cat cat-sun"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Jam / preserves</span><span class="grocery-cat cat-sun"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Mixed fruit</span><span class="grocery-note">grapes, berries, melon</span><span class="grocery-cat cat-sun"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Greek yogurt</span><span class="grocery-note">individual cups</span><span class="grocery-cat cat-sun"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Granola</span><span class="grocery-cat cat-sun"></span></div>
      </div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Coffee & morning drinks</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Ground coffee or pods</span><span class="grocery-note">check what the Airbnb has first</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">OJ</span><span class="grocery-note">large carton</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Creamer</span><span class="grocery-cat cat-all"></span></div>
      </div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Hydration — critical in June</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Sparkling water</span><span class="grocery-note">case of Topo Chico or La Croix</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Water / Gatorade</span><span class="grocery-note">stock the fridge on arrival</span><span class="grocery-cat cat-all"></span></div>
      </div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Pool snacks</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Tortilla chips</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Guacamole / salsa dip</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Watermelon</span><span class="grocery-note">half or whole</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Cheese & crackers</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Hummus & veggies</span><span class="grocery-cat cat-all"></span></div>
      </div>
    </div>

    <div class="grocery-section">
      <p class="grocery-section-title">Bar cart</p>
      <div class="grocery-card">
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Tequila</span><span class="grocery-note">1–2 bottles</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Triple sec / Cointreau</span><span class="grocery-note">for margs</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Fresh limes</span><span class="grocery-note">bag of them</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Beer</span><span class="grocery-note">12-pack, something light & cold</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Tajín</span><span class="grocery-note">for marg rims & fruit</span><span class="grocery-cat cat-all"></span></div>
        <div class="grocery-row" onclick="toggleItem(this)"><div class="check-circle">✓</div><span class="grocery-name">Ice</span><span class="grocery-note">grab 2 bags on the way in</span><span class="grocery-cat cat-all"></span></div>
      </div>
    </div>

  </div>

</div>

<script>
  function switchTab(name, btn) {
    document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('tab-' + name).classList.add('active');
    btn.classList.add('active');
  }

  function toggleDay(header) {
    header.parentElement.classList.toggle('open');
  }

  function toggleItem(row) {
    row.classList.toggle('checked');
    updateProgress();
  }

  function updateProgress() {
    const total = document.querySelectorAll('.grocery-row').length;
    const checked = document.querySelectorAll('.grocery-row.checked').length;
    document.getElementById('progress-label').textContent = checked + ' of ' + total + ' items checked';
    document.getElementById('progress-bar').style.width = Math.round((checked / total) * 100) + '%';
  }

  function resetGrocery() {
    document.querySelectorAll('.grocery-row.checked').forEach(r => r.classList.remove('checked'));
    updateProgress();
  }
</script>
</body>
</html>
