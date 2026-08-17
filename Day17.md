DAY 17

Learnings:

Claude can act as a data analyst capable of processing CSV datasets, calculating business metrics, generating visualizations, and building complete HTML dashboards. This workflow mirrors real-world analytics projects used in consulting, finance, operations, and business intelligence.

CSV Analysis: Analyze structured datasets without writing code.

Dashboard Creation: Generate complete HTML dashboards from raw data.

Business Metrics: Calculate meaningful KPIs and insights.

Visualization: Create charts and dashboards using SVG graphics.

Prompt I use:

## Details
- Vehicle : [YOUR VEHICLE MODEL]
- Fuel    : [Petrol/Diesel/CNG/E85/EV]
- Usage   : [City/Highway/Mixed/Fleet]
- KM/month: [e.g. 1000]
- Car Age : [e.g. 3 yrs]

## Role
Data analyst. Read attached CSV → compute metrics → output one HTML dashboard. HTML only, no explanation.

## Compute (group by Fuel_Type)
1. Avg Cost/km        = Fuel_Cost_INR ÷ Distance_km
2. Avg CO₂/km         = CO2_emitted_kg ÷ Distance_km
3. Avg Maintenance/km = Maintenance_Cost_INR ÷ Distance_km
4. Avg Refuel time    = Refuel_Recharge_time_min
5. Age buckets: New(0-2y) Mid-life(3-5y) Aged(6-9y) Old(10+y)
   → show Cost/km and Maint/km per bucket. Mark [CAR AGE] yrs.
6. E85 Paradox:
   - Pump saving    = ((Petrol_price−E85_price)/Petrol_price)×100
   - Running penalty= ((E85_cpkm−Petrol_cpkm)/Petrol_cpkm)×100
   - Break-even     = (E85_mileage÷Petrol_mileage)×Petrol_price
7. E85 Score/10: cost=4pt CO₂=3pt refuel=2pt maint=1pt

## Dashboard (no CDN, pure SVG charts, CSS in <style>, JS in <script>)
Dark navy #0a0f1e, glassmorphism. Colours: E85=amber Petrol=blue Diesel=grey CNG=green EV=purple.

1. Header — '[YOUR VEHICLE] · [FUEL] · Age:[CAR AGE]y · [KM/month]km/mo'
2. KPI Cards (5) — your fuel cost/km | E85 cost/km | E85 premium vs Petrol | break-even price | your monthly cost
3. SVG bar chart: Cost/km per fuel | SVG doughnut: CO₂/km per fuel (hover tooltips)
4. SVG line chart: Cost/km vs age (0-12y) per fuel. Vertical line at [CAR AGE].
5. SVG gauge: E85 score/10 (CSS animated). One verdict sentence.
6. Fuel cards: highlight [FUEL] with glow. Each: 2 pros ✅ 2 cons ❌ best-for 🚗

Output: <!DOCTYPE html> only. All numbers from CSV. Responsive 375px–1440px.

CODE:

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fuel Economics Dashboard</title>
<style>
  :root{
    --bg:#0a0f1e;
    --glass:rgba(255,255,255,0.05);
    --glass-border:rgba(255,255,255,0.10);
    --text:#e7ecf5;
    --sub:#8b93a7;
    --petrol:#4d9fff;
    --diesel:#9aa4b2;
    --cng:#3ddc84;
    --e85:#ffb347;
    --ev:#b47cff;
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
    background:radial-gradient(circle at 20% 0%, #101a33 0%, var(--bg) 55%);
    color:var(--text);
    padding:20px;
    min-height:100vh;
  }
  .wrap{max-width:1320px;margin:0 auto;}
  header{
    padding:22px 26px;
    border-radius:18px;
    background:var(--glass);
    border:1px solid var(--glass-border);
    backdrop-filter:blur(14px);
    margin-bottom:22px;
    display:flex;flex-wrap:wrap;justify-content:space-between;align-items:center;gap:10px;
  }
  header h1{margin:0;font-size:1.35rem;font-weight:700;letter-spacing:.3px;}
  header .tag{color:var(--sub);font-size:.85rem;margin-top:4px;}
  header .badge{
    background:rgba(154,164,178,0.18);
    border:1px solid var(--diesel);
    color:var(--diesel);
    padding:6px 14px;border-radius:999px;font-size:.78rem;font-weight:600;
  }
  .kpis{display:grid;grid-template-columns:repeat(5,1fr);gap:14px;margin-bottom:22px;}
  .kpi{
    background:var(--glass);border:1px solid var(--glass-border);border-radius:16px;
    padding:16px 16px;backdrop-filter:blur(14px);
    transition:transform .2s ease;
  }
  .kpi:hover{transform:translateY(-3px);}
  .kpi .lbl{font-size:.72rem;color:var(--sub);text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px;}
  .kpi .val{font-size:1.5rem;font-weight:800;}
  .kpi .sub{font-size:.72rem;color:var(--sub);margin-top:4px;}
  .grid2{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-bottom:18px;}
  .card{
    background:var(--glass);border:1px solid var(--glass-border);border-radius:18px;
    padding:20px;backdrop-filter:blur(14px);position:relative;
  }
  .card h3{margin:0 0 14px 0;font-size:.95rem;color:var(--text);font-weight:700;}
  .card h3 span{color:var(--sub);font-weight:500;font-size:.78rem;}
  svg{width:100%;height:auto;overflow:visible;}
  .bar{transition:opacity .2s;cursor:pointer;}
  .bar:hover{opacity:.75;}
  .legend{display:flex;flex-wrap:wrap;gap:10px;margin-top:12px;font-size:.72rem;color:var(--sub);}
  .legend .dot{width:9px;height:9px;border-radius:50%;display:inline-block;margin-right:5px;}
  .tooltip{
    position:absolute;pointer-events:none;background:#131a2e;border:1px solid var(--glass-border);
    padding:6px 10px;border-radius:8px;font-size:.72rem;color:var(--text);opacity:0;transition:opacity .12s;
    white-space:nowrap;z-index:10;box-shadow:0 6px 18px rgba(0,0,0,.4);
  }
  .seg{cursor:pointer;transition:opacity .2s;}
  .seg:hover{opacity:.75;}
  .agebuckets{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-top:6px;}
  .ab{background:rgba(255,255,255,0.03);border:1px solid var(--glass-border);border-radius:12px;padding:10px;text-align:center;font-size:.75rem;}
  .ab.active{border-color:var(--diesel);box-shadow:0 0 14px rgba(154,164,178,.35);background:rgba(154,164,178,.10);}
  .ab .name{color:var(--sub);font-size:.68rem;margin-bottom:6px;text-transform:uppercase;letter-spacing:.4px;}
  .ab .row{display:flex;justify-content:space-between;margin-top:3px;}
  .gaugewrap{display:flex;flex-direction:column;align-items:center;}
  .needle{transform-origin:150px 150px;animation:sweep 1.4s cubic-bezier(.2,.9,.25,1) forwards;}
  @keyframes sweep{
    from{transform:rotate(-90deg);}
  }
  .scoretxt{font-size:2.1rem;font-weight:800;margin-top:-38px;}
  .verdict{color:var(--sub);font-size:.85rem;text-align:center;margin-top:6px;max-width:340px;}
  .fuelcards{display:grid;grid-template-columns:repeat(5,1fr);gap:14px;margin-top:6px;}
  .fc{
    background:rgba(255,255,255,0.03);border:1px solid var(--glass-border);border-radius:16px;
    padding:14px;font-size:.78rem;position:relative;overflow:hidden;
  }
  .fc.hl{border-color:var(--diesel);box-shadow:0 0 22px rgba(154,164,178,.45),inset 0 0 20px rgba(154,164,178,.08);}
  .fc .fname{font-weight:800;font-size:.95rem;margin-bottom:8px;display:flex;align-items:center;gap:6px;}
  .fc .fname .dot{width:10px;height:10px;border-radius:50%;}
  .fc ul{margin:6px 0;padding-left:0;list-style:none;}
  .fc li{margin:4px 0;line-height:1.35;}
  .fc .best{margin-top:8px;color:var(--sub);font-size:.72rem;}
  .fc .youtag{
    position:absolute;top:10px;right:10px;background:var(--diesel);color:#0a0f1e;
    font-size:.62rem;font-weight:800;padding:3px 8px;border-radius:999px;
  }
  .paradox{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:6px;}
  .px{background:rgba(255,179,71,.06);border:1px solid rgba(255,179,71,.3);border-radius:12px;padding:12px;text-align:center;}
  .px .v{font-size:1.3rem;font-weight:800;color:var(--e85);}
  .px .l{font-size:.7rem;color:var(--sub);margin-top:4px;}
  @media(max-width:900px){
    .kpis{grid-template-columns:repeat(2,1fr);}
    .grid2{grid-template-columns:1fr;}
    .fuelcards{grid-template-columns:repeat(2,1fr);}
    .agebuckets{grid-template-columns:repeat(2,1fr);}
    .paradox{grid-template-columns:1fr;}
  }
  @media(max-width:480px){
    .kpis{grid-template-columns:1fr;}
    .fuelcards{grid-template-columns:1fr;}
  }
</style>
</head>
<body>
<div class="wrap">

  <header>
    <div>
      <h1>Your Diesel Vehicle · Diesel · Age: 6&ndash;9 y (Aged) · ~1,479 km/mo</h1>
      <div class="tag">Fuel economics dashboard — computed from 53-row trip dataset (5 fuel types)</div>
    </div>
    <div class="badge">DIESEL · AGED BUCKET</div>
  </header>

  <div class="kpis">
    <div class="kpi">
      <div class="lbl">Your Fuel Cost / km</div>
      <div class="val" style="color:var(--diesel)">₹4.69</div>
      <div class="sub">Diesel, Aged (6–9y) avg</div>
    </div>
    <div class="kpi">
      <div class="lbl">E85 Cost / km</div>
      <div class="val" style="color:var(--e85)">₹6.37</div>
      <div class="sub">Flex-fuel average</div>
    </div>
    <div class="kpi">
      <div class="lbl">E85 Premium vs Petrol</div>
      <div class="val" style="color:var(--e85)">+3.6%</div>
      <div class="sub">Running cost penalty despite cheaper pump price</div>
    </div>
    <div class="kpi">
      <div class="lbl">E85 Break-even Price</div>
      <div class="val" style="color:var(--e85)">₹79.1</div>
      <div class="sub">Price/L needed to match petrol cpkm</div>
    </div>
    <div class="kpi">
      <div class="lbl">Your Monthly Cost</div>
      <div class="val" style="color:var(--diesel)">₹6,938</div>
      <div class="sub">4.69 × 1,479 km/mo (Diesel avg)</div>
    </div>
  </div>

  <div class="grid2">
    <div class="card">
      <h3>Cost per km <span>by fuel type (₹)</span></h3>
      <svg viewBox="0 0 540 210" id="barChart">
        <line x1="30" y1="190" x2="520" y2="190" stroke="rgba(255,255,255,.15)" stroke-width="1"/>
        <!-- bars -->
        <g>
          <rect class="bar" x="40" y="101.3" width="70" height="88.7" rx="6" fill="#3ddc84"/>
          <text x="75" y="94" text-anchor="middle" font-size="12" fill="#e7ecf5" font-weight="700">₹3.32</text>
          <text x="75" y="205" text-anchor="middle" font-size="11" fill="#8b93a7">CNG</text>

          <rect class="bar" x="140" y="65.3" width="70" height="124.7" rx="6" fill="#9aa4b2"/>
          <text x="175" y="58" text-anchor="middle" font-size="12" fill="#e7ecf5" font-weight="700">₹4.67</text>
          <text x="175" y="205" text-anchor="middle" font-size="11" fill="#8b93a7">Diesel</text>

          <rect class="bar" x="240" y="20" width="70" height="170" rx="6" fill="#ffb347"/>
          <text x="275" y="14" text-anchor="middle" font-size="12" fill="#e7ecf5" font-weight="700">₹6.37</text>
          <text x="275" y="205" text-anchor="middle" font-size="11" fill="#8b93a7">E85</text>

          <rect class="bar" x="340" y="143.3" width="70" height="46.7" rx="6" fill="#b47cff"/>
          <text x="375" y="136" text-anchor="middle" font-size="12" fill="#e7ecf5" font-weight="700">₹1.75</text>
          <text x="375" y="205" text-anchor="middle" font-size="11" fill="#8b93a7">EV</text>

          <rect class="bar" x="440" y="25.9" width="70" height="164.1" rx="6" fill="#4d9fff"/>
          <text x="475" y="19" text-anchor="middle" font-size="12" fill="#e7ecf5" font-weight="700">₹6.15</text>
          <text x="475" y="205" text-anchor="middle" font-size="11" fill="#8b93a7">Petrol</text>
        </g>
      </svg>
    </div>

    <div class="card">
      <h3>CO₂ emitted per km <span>share by fuel type</span></h3>
      <svg viewBox="0 0 300 260" id="donutChart">
        <g transform="translate(150,130) rotate(-90)">
          <circle r="70" fill="none" stroke="rgba(255,255,255,.06)" stroke-width="34"/>
          <circle class="seg" r="70" fill="none" stroke="#3ddc84" stroke-width="34"
            stroke-dasharray="86.7 439.8" stroke-dashoffset="0" data-t="CNG · 0.125 kg/km · 19.7%"/>
          <circle class="seg" r="70" fill="none" stroke="#9aa4b2" stroke-width="34"
            stroke-dasharray="123.7 439.8" stroke-dashoffset="-86.7" data-t="Diesel · 0.179 kg/km · 28.1%"/>
          <circle class="seg" r="70" fill="none" stroke="#ffb347" stroke-width="34"
            stroke-dasharray="48.3 439.8" stroke-dashoffset="-210.4" data-t="E85 · 0.070 kg/km · 11.0%"/>
          <circle class="seg" r="70" fill="none" stroke="#b47cff" stroke-width="34"
            stroke-dasharray="63.1 439.8" stroke-dashoffset="-258.7" data-t="EV · 0.091 kg/km · 14.4%"/>
          <circle class="seg" r="70" fill="none" stroke="#4d9fff" stroke-width="34"
            stroke-dasharray="118.0 439.8" stroke-dashoffset="-321.8" data-t="Petrol · 0.171 kg/km · 26.8%"/>
        </g>
        <text x="150" y="124" text-anchor="middle" font-size="22" font-weight="800" fill="#e7ecf5">0.636</text>
        <text x="150" y="144" text-anchor="middle" font-size="11" fill="#8b93a7">kg CO₂ total /km (all fuels)</text>
      </svg>
      <div class="legend">
        <span><i class="dot" style="background:#3ddc84"></i>CNG</span>
        <span><i class="dot" style="background:#9aa4b2"></i>Diesel</span>
        <span><i class="dot" style="background:#ffb347"></i>E85</span>
        <span><i class="dot" style="background:#b47cff"></i>EV</span>
        <span><i class="dot" style="background:#4d9fff"></i>Petrol</span>
      </div>
    </div>
  </div>

  <div class="card" style="margin-bottom:18px;">
    <h3>Cost per km vs vehicle age <span>0–12 years · dashed line = your car's age (7y midpoint)</span></h3>
    <svg viewBox="0 0 640 200" id="lineChart">
      <g stroke="rgba(255,255,255,.08)">
        <line x1="40" y1="20" x2="40" y2="180"/>
        <line x1="40" y1="180" x2="600" y2="180"/>
      </g>
      <line x1="366.7" y1="20" x2="366.7" y2="180" stroke="#9aa4b2" stroke-width="1.5" stroke-dasharray="4 4"/>
      <text x="366.7" y="14" text-anchor="middle" font-size="10" fill="#9aa4b2">your car (7y)</text>

      <polyline fill="none" stroke="#3ddc84" stroke-width="2.5" points="40.0,121.4 86.7,121.4 133.3,121.4 180.0,116.9 226.7,116.9 273.3,116.9 320.0,109.8 366.7,109.7 413.3,109.7 460.0,109.7 506.7,109.7 553.3,109.7 600.0,109.7"/>
      <polyline fill="none" stroke="#9aa4b2" stroke-width="3" points="40.0,85.4 86.7,85.4 133.3,85.4 180.0,85.4 226.7,85.4 273.3,80.6 320.0,75.9 366.7,75.9 413.3,75.9 460.0,75.9 506.7,67.4 553.3,59.0 600.0,58.9"/>
      <polyline fill="none" stroke="#ffb347" stroke-width="2.5" points="40.0,30.1 86.7,30.1 133.3,30.1 180.0,20.0 226.7,20.0 273.3,20.0 320.0,20.0 366.7,20.0 413.3,20.0 460.0,20.0 506.7,20.0 553.3,20.0 600.0,20.0"/>
      <polyline fill="none" stroke="#b47cff" stroke-width="2.5" points="40.0,160.0 86.7,160.0 133.3,160.0 180.0,157.1 226.7,157.1 273.3,157.1 320.0,157.1 366.7,157.1 413.3,157.1 460.0,157.1 506.7,157.1 553.3,157.1 600.0,157.1"/>
      <polyline fill="none" stroke="#4d9fff" stroke-width="2.5" points="40.0,43.1 86.7,43.1 133.3,43.1 180.0,43.1 226.7,43.1 273.3,43.1 320.0,29.6 366.7,29.6 413.3,29.5 460.0,29.5 506.7,29.5 553.3,29.5 600.0,29.5"/>

      <text x="40" y="196" font-size="10" fill="#8b93a7">0y</text>
      <text x="600" y="196" text-anchor="end" font-size="10" fill="#8b93a7">12y</text>
    </svg>
    <div class="legend">
      <span><i class="dot" style="background:#3ddc84"></i>CNG</span>
      <span><i class="dot" style="background:#9aa4b2"></i>Diesel (yours)</span>
      <span><i class="dot" style="background:#ffb347"></i>E85</span>
      <span><i class="dot" style="background:#b47cff"></i>EV</span>
      <span><i class="dot" style="background:#4d9fff"></i>Petrol</span>
    </div>

    <div class="agebuckets">
      <div class="ab"><div class="name">New 0–2y</div><div class="row"><span>Diesel n/a</span></div></div>
      <div class="ab"><div class="name">Mid-life 3–5y</div><div class="row"><span>₹4.35/km</span><span>maint ₹0.70</span></div></div>
      <div class="ab active"><div class="name">Aged 6–9y ← you</div><div class="row"><span>₹4.69/km</span><span>maint ₹1.14</span></div></div>
      <div class="ab"><div class="name">Old 10y+</div><div class="row"><span>₹5.29/km</span><span>maint ₹1.41</span></div></div>
    </div>
  </div>

  <div class="grid2">
    <div class="card">
      <h3>E85 Score <span>cost 4pt · CO₂ 3pt · refuel 2pt · maint 1pt</span></h3>
      <div class="gaugewrap">
        <svg viewBox="0 0 300 170" width="280">
          <path d="M 30 150 A 120 120 0 0 1 270 150" fill="none" stroke="rgba(255,255,255,.08)" stroke-width="22"/>
          <path d="M 30 150 A 120 120 0 0 1 270 150" fill="none" stroke="#ffb347" stroke-width="22"
                stroke-dasharray="376.99" stroke-dashoffset="94.25" stroke-linecap="round"
                style="animation:fillGauge 1.4s cubic-bezier(.2,.9,.25,1) forwards; stroke-dashoffset:376.99;"/>
          <g class="needle">
            <line x1="150" y1="150" x2="150" y2="45" stroke="#e7ecf5" stroke-width="3"/>
            <circle cx="150" cy="150" r="6" fill="#e7ecf5"/>
          </g>
        </svg>
        <div class="scoretxt">5.71<span style="font-size:1rem;color:var(--sub);font-weight:500">/10</span></div>
        <div class="verdict">E85 wins hard on emissions and maintenance, but its running cost penalty (+3.6% vs petrol) and short mileage keep the overall score mid-pack — worth it mainly where CO₂ or engine longevity matter more than ₹/km.</div>
      </div>
    </div>

    <div class="card">
      <h3>The E85 Paradox <span>cheaper at the pump, pricier per km</span></h3>
      <div class="paradox">
        <div class="px">
          <div class="v">18.0%</div>
          <div class="l">Pump price saving vs Petrol</div>
        </div>
        <div class="px">
          <div class="v">+3.6%</div>
          <div class="l">Running cost penalty per km</div>
        </div>
        <div class="px">
          <div class="v">₹79.1</div>
          <div class="l">Break-even price / L</div>
        </div>
      </div>
      <p style="font-size:.8rem;color:var(--sub);line-height:1.5;margin-top:14px;">
        E85 sells for 18% less than petrol at the pump, but its lower energy density drags mileage down to
        ~12.9 km/L vs petrol's ~16.3 km/L. Net effect: you actually pay 3.6% more per km driven. E85 only
        beats petrol on cost if its price drops below ≈₹79.1/L.
      </p>
    </div>
  </div>

  <div class="card">
    <h3>Fuel type comparison</h3>
    <div class="fuelcards">
      <div class="fc">
        <div class="fname"><span class="dot" style="background:#3ddc84"></span>CNG</div>
        <ul>
          <li>✅ Lowest running penalty after EV (₹3.32/km)</li>
          <li>✅ Low CO₂ output (0.125 kg/km)</li>
          <li>❌ Slower refuel (~8 min)</li>
          <li>❌ Limited station coverage</li>
        </ul>
        <div class="best">🚗 Best for: high-mileage city fleets</div>
      </div>

      <div class="fc hl">
        <div class="youtag">YOUR FUEL</div>
        <div class="fname"><span class="dot" style="background:#9aa4b2"></span>Diesel</div>
        <ul>
          <li>✅ Strong mileage (~19.6 km/L)</li>
          <li>✅ Fast refuel (~5 min)</li>
          <li>❌ Highest maintenance/km (₹1.01)</li>
          <li>❌ Higher CO₂ than CNG/E85/EV</li>
        </ul>
        <div class="best">🚗 Best for: highway & long-distance mixed use</div>
      </div>

      <div class="fc">
        <div class="fname"><span class="dot" style="background:#ffb347"></span>E85</div>
        <ul>
          <li>✅ Lowest CO₂/km (0.070 kg)</li>
          <li>✅ Low maintenance (₹0.46/km)</li>
          <li>❌ Highest cost/km (₹6.37) — the paradox</li>
          <li>❌ Weak mileage (~12.9 km/L)</li>
        </ul>
        <div class="best">🚗 Best for: emissions-first short commutes</div>
      </div>

      <div class="fc">
        <div class="fname"><span class="dot" style="background:#b47cff"></span>EV</div>
        <ul>
          <li>✅ Cheapest running cost (₹1.75/km)</li>
          <li>✅ Lowest maintenance (₹0.23/km)</li>
          <li>❌ Slowest recharge (~45 min)</li>
          <li>❌ Needs charging infra planning</li>
        </ul>
        <div class="best">🚗 Best for: daily city driving with home charging</div>
      </div>

      <div class="fc">
        <div class="fname"><span class="dot" style="background:#4d9fff"></span>Petrol</div>
        <ul>
          <li>✅ Widely available, fast refuel (~5 min)</li>
          <li>✅ Decent mileage (~16.3 km/L)</li>
          <li>❌ 2nd-highest cost/km (₹6.15)</li>
          <li>❌ High CO₂ (0.171 kg/km)</li>
        </ul>
        <div class="best">🚗 Best for: low-mileage occasional drivers</div>
      </div>
    </div>
  </div>

</div>

<div class="tooltip" id="tt"></div>

<script>
  const tt = document.getElementById('tt');

  document.querySelectorAll('.seg').forEach(el=>{
    el.addEventListener('mousemove', e=>{
      tt.textContent = el.getAttribute('data-t');
      tt.style.left = (e.pageX+14)+'px';
      tt.style.top = (e.pageY-10)+'px';
      tt.style.opacity = 1;
    });
    el.addEventListener('mouseleave', ()=> tt.style.opacity = 0);
  });

  document.querySelectorAll('.bar').forEach(el=>{
    el.addEventListener('mousemove', e=>{
      const h = el.getAttribute('height');
      tt.textContent = el.previousElementSibling ? '' : '';
      tt.style.left = (e.pageX+14)+'px';
      tt.style.top = (e.pageY-10)+'px';
      tt.style.opacity = 1;
    });
    el.addEventListener('mouseleave', ()=> tt.style.opacity = 0);
  });

  // gauge sweep: rotate needle from -90deg to target angle
  const needle = document.querySelector('.needle');
  const targetAngle = -90 + 102.8; // gauge_angle degrees across 180deg semicircle
  needle.style.setProperty('transform', 'rotate(-90deg)');
  requestAnimationFrame(()=>{
    needle.style.transition = 'transform 1.4s cubic-bezier(.2,.9,.25,1)';
    needle.style.transform = `rotate(${targetAngle}deg)`;
  });
</script>
<style>
  @keyframes fillGauge{
    from{ stroke-dashoffset:376.99; }
    to{ stroke-dashoffset:94.25; }
  }
</style>
</body>
</html>

