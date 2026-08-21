DAY 21

Learnings:

Claude can analyze digital ecosystems, estimate privacy exposure, identify tracking risks, and generate interactive dashboards that help users better understand how their online activities contribute to their digital footprint.

Privacy Analysis: Understand how digital services contribute to your online footprint.

Risk Assessment: Identify potential privacy and tracking risks.

Digital Twin Modeling: Estimate what platforms might infer from your activity.

Actionable Security: Generate realistic privacy improvement plans.

Prompt I use:

### Sample User Dataset

Use the following dataset as the user's reported digital footprint.

Facts:

Applications : Instagram, Snapchat, TikTok, YouTube, Discord, WhatsApp, iMessage, Spotify, Roblox, PUBG Mobile, Amazon, Meesho, Google Search, Google Pay, Google Photos

Dataset Rules:
* Treat all listed services as Facts.
* Use these services to calculate all scores, exposure rankings, heatmaps, risk levels, ecosystem concentration, digital twin insights, data collection likelihood, and privacy recommendations.
* Infer parent companies from the services.
* Any behavioural, demographic, lifestyle, shopping, spending, entertainment, mobility, travel, communication, or technology-related conclusions must be labeled as Estimates.
* Never claim certainty.
* Never claim access to private databases.
* If information cannot reasonably be inferred, display: 'Not enough information provided.'

# Output Requirement

Generate a complete interactive HTML artifact starting with <style>.

Do not output markdown.

The artifact should feel like a premium cybersecurity dashboard.

Design Inspiration:

Notion, Stripe Dashboard, Linear, Google Privacy Checkup, Apple Privacy Reports, Modern SaaS Analytics Platforms.

### Dashboard Overview

Create a visually rich dashboard containing:

1. Digital Footprint Score (0-100)
2. Privacy Score (0-100)
3. Exposure Heatmap
4. Company Exposure Ranking
5. Data Collection Matrix
6. Risk Radar
7. Digital Twin Profile
8. Most Valuable Data Assets
9. Privacy Improvement Plan

Display:

Digital Footprint Score
🟢 0-30 = Minimal
🟡 31-60 = Moderate
🟠 61-80 = Significant
🔴 81-100 = Extensive

Privacy Score
🔴 0-30 = Weak
🟠 31-60 = Fair
🟡 61-80 = Good
🟢 81-100 = Strong

Include:
* Total Services Used
* Number of Parent Companies
* Ecosystem Concentration Score
* Estimated Tracking Surface

Create all sections exactly as specified including Digital Twin Profile, Exposure Heatmap, Company Exposure Ranking, Data Collection Matrix, Risk Radar, WOW Insights, Most Valuable Data Assets, Privacy Improvement Simulator, and Final Verdict.

Critical Rules:
* Never claim access to private databases.
* Never claim certainty about inferred traits.
* Separate Facts from Estimates.

CODE:

<style>
  :root{
    --bg:#0a0e14;
    --panel:#101720;
    --panel2:#0d1420;
    --line:#1e2a38;
    --ink:#dbe6ef;
    --ink-dim:#7c8ea3;
    --mono:'JetBrains Mono','SF Mono',Consolas,monospace;
    --sans:'Inter',-apple-system,BlinkMacSystemFont,sans-serif;
    --cyan:#3fd8e0;
    --cyan-dim:#3fd8e033;
    --amber:#f5a623;
    --red:#ef4a5f;
    --green:#3ecf8e;
    --violet:#8b7cf6;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  body{
    background:
      radial-gradient(ellipse at top left, #0f1a26 0%, transparent 55%),
      radial-gradient(ellipse at bottom right, #10151f 0%, transparent 55%),
      var(--bg);
    color:var(--ink);
    font-family:var(--sans);
    padding:32px 20px 80px;
    min-height:100vh;
  }
  .wrap{max-width:1180px;margin:0 auto;}

  /* header */
  .scanline{
    position:relative;overflow:hidden;
    border:1px solid var(--line);border-radius:14px;
    background:linear-gradient(180deg,#0d1620,#0a0f17);
    padding:26px 28px;margin-bottom:22px;
  }
  .scanline::after{
    content:"";position:absolute;left:0;right:0;height:2px;
    background:linear-gradient(90deg,transparent,var(--cyan),transparent);
    top:0;animation:scan 4.5s linear infinite;opacity:.6;
  }
  @keyframes scan{0%{top:0%}100%{top:100%}}
  .eyebrow{
    font-family:var(--mono);font-size:11px;letter-spacing:.14em;
    color:var(--cyan);text-transform:uppercase;display:flex;align-items:center;gap:8px;
  }
  .eyebrow .dot{width:6px;height:6px;border-radius:50%;background:var(--green);box-shadow:0 0 8px var(--green);animation:pulse 2s infinite;}
  @keyframes pulse{0%,100%{opacity:1}50%{opacity:.3}}
  h1{font-size:28px;margin-top:8px;font-weight:700;letter-spacing:-.01em;}
  .sub{color:var(--ink-dim);font-size:13.5px;margin-top:6px;max-width:640px;line-height:1.5;}

  /* disclaimer strip */
  .disclaimer{
    display:flex;gap:10px;align-items:flex-start;
    border:1px solid #2a2416;background:#1a160c;
    border-radius:10px;padding:12px 16px;margin-bottom:22px;
    font-size:12.5px;color:#e8c988;line-height:1.55;
  }
  .disclaimer b{color:var(--amber);}

  /* legend badges */
  .badge{
    font-family:var(--mono);font-size:10px;letter-spacing:.06em;
    padding:2px 7px;border-radius:5px;text-transform:uppercase;font-weight:700;
  }
  .b-fact{background:#12321f;color:var(--green);border:1px solid #1e4a30;}
  .b-est{background:#2a2211;color:var(--amber);border:1px solid #4a3a16;}

  /* score row */
  .scores{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px;}
  @media(max-width:720px){.scores{grid-template-columns:1fr;}}
  .score-card{
    border:1px solid var(--line);border-radius:14px;padding:22px;
    background:linear-gradient(160deg,var(--panel),var(--panel2));
    position:relative;
  }
  .score-top{display:flex;justify-content:space-between;align-items:flex-start;}
  .score-label{font-family:var(--mono);font-size:11px;color:var(--ink-dim);letter-spacing:.1em;text-transform:uppercase;}
  .score-num{font-size:50px;font-weight:800;font-family:var(--mono);line-height:1;margin-top:10px;}
  .score-tag{display:inline-block;margin-top:8px;padding:3px 10px;border-radius:20px;font-size:11.5px;font-weight:700;font-family:var(--mono);}
  .track{height:8px;border-radius:6px;background:#1a2330;margin-top:16px;overflow:hidden;}
  .track > div{height:100%;border-radius:6px;}

  .tag-sig{background:#3a2410;color:var(--amber);}
  .tag-fair{background:#3a2410;color:var(--amber);}

  /* stat strip */
  .stats{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:26px;}
  @media(max-width:820px){.stats{grid-template-columns:1fr 1fr;}}
  .stat{
    border:1px solid var(--line);border-radius:12px;padding:16px;background:var(--panel);
  }
  .stat .n{font-family:var(--mono);font-size:24px;font-weight:700;color:var(--cyan);}
  .stat .l{font-size:11.5px;color:var(--ink-dim);margin-top:4px;}

  section{margin-bottom:30px;}
  .section-head{display:flex;align-items:baseline;gap:10px;margin-bottom:14px;}
  .section-num{font-family:var(--mono);color:var(--ink-dim);font-size:12px;}
  h2{font-size:17px;font-weight:700;}
  .section-desc{color:var(--ink-dim);font-size:12.5px;margin:-6px 0 14px;max-width:600px;}

  .panel{border:1px solid var(--line);border-radius:14px;background:var(--panel);padding:20px;}

  /* heatmap */
  .heatgrid{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;}
  @media(max-width:700px){.heatgrid{grid-template-columns:repeat(3,1fr);}}
  @media(max-width:460px){.heatgrid{grid-template-columns:repeat(2,1fr);}}
  .heatcell{
    border-radius:10px;padding:12px;border:1px solid var(--line);
    display:flex;flex-direction:column;gap:6px;min-height:78px;justify-content:space-between;
  }
  .heatcell .app{font-weight:700;font-size:13px;}
  .heatcell .lvl{font-family:var(--mono);font-size:10px;letter-spacing:.05em;text-transform:uppercase;opacity:.9;}
  .h1lvl{background:#12321f;border-color:#1e4a30;}
  .h2lvl{background:#2a2c11;border-color:#484c16;}
  .h3lvl{background:#3a2410;border-color:#5a3c16;}
  .h4lvl{background:#3a1418;border-color:#5c1f26;}

  /* company ranking */
  .rank-row{
    display:grid;grid-template-columns:28px 1fr 120px 90px;align-items:center;gap:12px;
    padding:11px 4px;border-bottom:1px solid var(--line);font-size:13px;
  }
  .rank-row:last-child{border-bottom:none;}
  .rank-row .idx{font-family:var(--mono);color:var(--ink-dim);font-size:12px;}
  .rank-row .name{font-weight:600;}
  .rank-row .apps{color:var(--ink-dim);font-size:11.5px;margin-top:2px;}
  .bar-bg{height:7px;background:#1a2330;border-radius:5px;overflow:hidden;}
  .bar-fg{height:100%;background:linear-gradient(90deg,var(--cyan),var(--violet));}
  .rank-row .pct{font-family:var(--mono);font-size:12px;text-align:right;color:var(--ink-dim);}

  /* matrix */
  table{width:100%;border-collapse:collapse;font-size:12.5px;}
  th{
    text-align:left;font-family:var(--mono);font-size:10.5px;color:var(--ink-dim);
    text-transform:uppercase;letter-spacing:.05em;padding:8px 10px;border-bottom:1px solid var(--line);
  }
  td{padding:9px 10px;border-bottom:1px solid #141c27;}
  tr:hover td{background:#0d1520;}
  .dot-y{color:var(--red);font-weight:700;}
  .dot-n{color:var(--ink-dim);opacity:.35;}
  .company-chip{font-family:var(--mono);font-size:11px;color:var(--cyan);}

  /* risk radar */
  .radar-wrap{display:flex;gap:26px;align-items:center;flex-wrap:wrap;}
  .radar-legend{flex:1;min-width:220px;display:flex;flex-direction:column;gap:10px;}
  .radar-item{display:flex;justify-content:space-between;font-size:12.5px;padding:8px 10px;border:1px solid var(--line);border-radius:8px;}
  .radar-item .v{font-family:var(--mono);color:var(--amber);}

  /* twin */
  .twin-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
  @media(max-width:700px){.twin-grid{grid-template-columns:1fr;}}
  .twin-card{border:1px solid var(--line);border-radius:10px;padding:14px;background:var(--panel2);}
  .twin-card .k{font-family:var(--mono);font-size:10.5px;color:var(--ink-dim);text-transform:uppercase;letter-spacing:.05em;}
  .twin-card .v{font-size:13.5px;margin-top:6px;line-height:1.5;}

  /* assets */
  .asset-row{display:flex;justify-content:space-between;align-items:center;padding:13px 4px;border-bottom:1px solid var(--line);gap:14px;}
  .asset-row:last-child{border-bottom:none;}
  .asset-name{font-weight:600;font-size:13.5px;}
  .asset-desc{color:var(--ink-dim);font-size:11.5px;margin-top:3px;max-width:420px;}
  .asset-val{font-family:var(--mono);font-weight:700;color:var(--green);white-space:nowrap;font-size:13px;}

  /* simulator */
  .sim{display:flex;flex-direction:column;gap:14px;}
  .sim-row{display:flex;align-items:center;gap:14px;font-size:13px;}
  .sim-row label{width:190px;color:var(--ink-dim);flex-shrink:0;}
  input[type=range]{flex:1;accent-color:var(--cyan);}
  .sim-out{
    margin-top:6px;padding:16px;border-radius:10px;background:var(--panel2);border:1px solid var(--line);
    display:flex;justify-content:space-between;align-items:center;
  }
  .sim-out .big{font-family:var(--mono);font-size:30px;font-weight:800;color:var(--green);}

  /* verdict */
  .verdict{
    border:1px solid var(--line);border-radius:14px;padding:24px;
    background:linear-gradient(150deg,#101a24,#0a0f17);
  }
  .verdict p{font-size:13.5px;line-height:1.7;color:var(--ink);}
  .verdict p + p{margin-top:10px;}
  footer{margin-top:30px;text-align:center;color:var(--ink-dim);font-size:11px;font-family:var(--mono);}
</style>

<div class="wrap">

  <div class="scanline">
    <div class="eyebrow"><span class="dot"></span>DIGITAL FOOTPRINT AUDIT — LIVE SNAPSHOT</div>
    <h1>Your Digital Exposure Report</h1>
    <div class="sub">Built from 15 self-reported services. Scores and rankings below are derived only from which apps you use — not from any private data, leak, or account-level access.</div>
  </div>

  <div class="disclaimer">
    ⚠️ <div><b>How to read this dashboard:</b> Anything marked <span class="badge b-fact">FACT</span> is a service you told us you use. Anything marked <span class="badge b-est">ESTIMATE</span> is a plausible inference based on how that category of app typically behaves — never a certainty, never sourced from a real database, and never a claim about your actual accounts.</div>
  </div>

  <div class="scores">
    <div class="score-card">
      <div class="score-top">
        <div>
          <div class="score-label">Digital Footprint Score</div>
          <div class="score-num" style="color:var(--amber)">72</div>
          <span class="score-tag tag-sig">🟠 SIGNIFICANT</span>
        </div>
      </div>
      <div class="track"><div style="width:72%;background:linear-gradient(90deg,#f5a623,#ef4a5f)"></div></div>
      <div class="section-desc" style="margin-top:12px">Estimate — reflects breadth across social, messaging, gaming, payments, and shopping categories, not a real exposure measurement.</div>
    </div>
    <div class="score-card">
      <div class="score-top">
        <div>
          <div class="score-label">Privacy Score</div>
          <div class="score-num" style="color:var(--amber)">42</div>
          <span class="score-tag tag-fair">🟠 FAIR</span>
        </div>
      </div>
      <div class="track"><div style="width:42%;background:linear-gradient(90deg,#ef4a5f,#f5a623)"></div></div>
      <div class="section-desc" style="margin-top:12px">Estimate — lower scores suggest more room to reduce tracking, not a verified privacy audit of your accounts.</div>
    </div>
  </div>

  <div class="stats">
    <div class="stat"><div class="n">15</div><div class="l">Total Services Used <span class="badge b-fact">FACT</span></div></div>
    <div class="stat"><div class="n">11</div><div class="l">Parent Companies <span class="badge b-est">EST.</span></div></div>
    <div class="stat"><div class="n">27%</div><div class="l">Ecosystem Concentration (Google) <span class="badge b-est">EST.</span></div></div>
    <div class="stat"><div class="n">~34</div><div class="l">Estimated Tracking Surface Points <span class="badge b-est">EST.</span></div></div>
  </div>

  <section>
    <div class="section-head"><span class="section-num">01</span><h2>Exposure Heatmap</h2></div>
    <div class="section-desc">Estimated exposure intensity per app, based on typical data practices for that category of service.</div>
    <div class="panel">
      <div class="heatgrid">
        <div class="heatcell h4lvl"><div class="app">Instagram</div><div class="lvl">🔴 High</div></div>
        <div class="heatcell h4lvl"><div class="app">TikTok</div><div class="lvl">🔴 High</div></div>
        <div class="heatcell h3lvl"><div class="app">Snapchat</div><div class="lvl">🟠 Elevated</div></div>
        <div class="heatcell h3lvl"><div class="app">YouTube</div><div class="lvl">🟠 Elevated</div></div>
        <div class="heatcell h3lvl"><div class="app">Google Search</div><div class="lvl">🟠 Elevated</div></div>
        <div class="heatcell h3lvl"><div class="app">Google Pay</div><div class="lvl">🟠 Elevated</div></div>
        <div class="heatcell h3lvl"><div class="app">Amazon</div><div class="lvl">🟠 Elevated</div></div>
        <div class="heatcell h2lvl"><div class="app">Meesho</div><div class="lvl">🟡 Moderate</div></div>
        <div class="heatcell h2lvl"><div class="app">Discord</div><div class="lvl">🟡 Moderate</div></div>
        <div class="heatcell h2lvl"><div class="app">Roblox</div><div class="lvl">🟡 Moderate</div></div>
        <div class="heatcell h2lvl"><div class="app">PUBG Mobile</div><div class="lvl">🟡 Moderate</div></div>
        <div class="heatcell h2lvl"><div class="app">Google Photos</div><div class="lvl">🟡 Moderate</div></div>
        <div class="heatcell h1lvl"><div class="app">WhatsApp</div><div class="lvl">🟢 Lower</div></div>
        <div class="heatcell h1lvl"><div class="app">iMessage</div><div class="lvl">🟢 Lower</div></div>
        <div class="heatcell h1lvl"><div class="app">Spotify</div><div class="lvl">🟢 Lower</div></div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">02</span><h2>Company Exposure Ranking</h2></div>
    <div class="section-desc">Which inferred parent companies see the most of your activity, by share of your total services. <span class="badge b-est">ESTIMATE</span></div>
    <div class="panel">
      <div class="rank-row">
        <div class="idx">01</div>
        <div><div class="name">Alphabet / Google</div><div class="apps">YouTube · Search · Pay · Photos</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:27%"></div></div>
        <div class="pct">4/15</div>
      </div>
      <div class="rank-row">
        <div class="idx">02</div>
        <div><div class="name">Meta</div><div class="apps">Instagram · WhatsApp</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:13%"></div></div>
        <div class="pct">2/15</div>
      </div>
      <div class="rank-row">
        <div class="idx">03</div>
        <div><div class="name">ByteDance</div><div class="apps">TikTok</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:7%"></div></div>
        <div class="pct">1/15</div>
      </div>
      <div class="rank-row">
        <div class="idx">04</div>
        <div><div class="name">Snap Inc.</div><div class="apps">Snapchat</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:7%"></div></div>
        <div class="pct">1/15</div>
      </div>
      <div class="rank-row">
        <div class="idx">05</div>
        <div><div class="name">Amazon</div><div class="apps">Amazon Shopping</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:7%"></div></div>
        <div class="pct">1/15</div>
      </div>
      <div class="rank-row">
        <div class="idx">06</div>
        <div><div class="name">Apple</div><div class="apps">iMessage</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:7%"></div></div>
        <div class="pct">1/15</div>
      </div>
      <div class="rank-row">
        <div class="idx">07</div>
        <div><div class="name">Discord Inc. · Spotify · Roblox Corp · Krafton · Meesho</div><div class="apps">1 service each</div></div>
        <div class="bar-bg"><div class="bar-fg" style="width:7%"></div></div>
        <div class="pct">5×1/15</div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">03</span><h2>Data Collection Matrix</h2></div>
    <div class="section-desc">Likely categories of data each service *typically* collects for its category. <span class="badge b-est">ESTIMATE</span> — not confirmed permissions for your specific accounts.</div>
    <div class="panel" style="overflow-x:auto">
      <table>
        <tr><th>Service</th><th>Location</th><th>Contacts</th><th>Payment Info</th><th>Media/Photos</th><th>Behavioral</th></tr>
        <tr><td><span class="company-chip">Instagram</span></td><td class="dot-y">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Snapchat</span></td><td class="dot-y">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">TikTok</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">YouTube</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Discord</span></td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">WhatsApp</span></td><td class="dot-y">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-n">●</td></tr>
        <tr><td><span class="company-chip">iMessage</span></td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-n">●</td></tr>
        <tr><td><span class="company-chip">Spotify</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Roblox</span></td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">PUBG Mobile</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Amazon</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Meesho</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Google Search</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Google Pay</span></td><td class="dot-y">●</td><td class="dot-y">●</td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-y">●</td></tr>
        <tr><td><span class="company-chip">Google Photos</span></td><td class="dot-y">●</td><td class="dot-n">●</td><td class="dot-n">●</td><td class="dot-y">●</td><td class="dot-n">●</td></tr>
      </table>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">04</span><h2>Risk Radar</h2></div>
    <div class="section-desc">Relative risk pressure across categories, estimated from the mix of app types present. <span class="badge b-est">ESTIMATE</span></div>
    <div class="panel radar-wrap">
      <div class="radar-legend">
        <div class="radar-item"><span>Social / Behavioral Tracking</span><span class="v">High</span></div>
        <div class="radar-item"><span>Financial Exposure</span><span class="v">Moderate</span></div>
        <div class="radar-item"><span>Location Inference</span><span class="v">Moderate–High</span></div>
        <div class="radar-item"><span>Communication Metadata</span><span class="v">Moderate</span></div>
        <div class="radar-item"><span>Media / Photo Exposure</span><span class="v">Moderate</span></div>
        <div class="radar-item"><span>Minor-Adjacent App Usage (Roblox/PUBG)</span><span class="v">Watch</span></div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">05</span><h2>Digital Twin Profile</h2></div>
    <div class="section-desc">A speculative sketch of the "profile" an ad-tech system might build from this app mix. Entirely inferential. <span class="badge b-est">ESTIMATE</span></div>
    <div class="twin-grid">
      <div class="twin-card"><div class="k">Likely age band</div><div class="v">Teen–young adult (Roblox, PUBG Mobile, TikTok, Snapchat skew younger)</div></div>
      <div class="twin-card"><div class="k">Likely region signal</div><div class="v">India-leaning (Meesho, Google Pay usage pattern)</div></div>
      <div class="twin-card"><div class="k">Shopping behavior</div><div class="v">Mobile-first, value/discount-oriented (Meesho + Amazon combo)</div></div>
      <div class="twin-card"><div class="k">Entertainment style</div><div class="v">Short-form video + music + mobile gaming heavy</div></div>
      <div class="twin-card"><div class="k">Communication style</div><div class="v">Multi-platform — mixes closed (iMessage/WhatsApp) and open (Discord) circles</div></div>
      <div class="twin-card"><div class="k">Spending inference</div><div class="v">Not enough information provided.</div></div>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">06</span><h2>Most Valuable Data Assets</h2></div>
    <div class="section-desc">The data points advertisers/data brokers would value most from this specific app mix. <span class="badge b-est">ESTIMATE</span></div>
    <div class="panel">
      <div class="asset-row">
        <div><div class="asset-name">Payment behavior</div><div class="asset-desc">Google Pay transaction patterns — strong purchase-intent signal</div></div>
        <div class="asset-val">Very High</div>
      </div>
      <div class="asset-row">
        <div><div class="asset-name">Short-form video engagement</div><div class="asset-desc">TikTok + Instagram watch/interaction history</div></div>
        <div class="asset-val">High</div>
      </div>
      <div class="asset-row">
        <div><div class="asset-name">Search history</div><div class="asset-desc">Google Search intent data across daily life</div></div>
        <div class="asset-val">High</div>
      </div>
      <div class="asset-row">
        <div><div class="asset-name">Shopping cart / wishlist data</div><div class="asset-desc">Amazon + Meesho browsing and purchase signals</div></div>
        <div class="asset-val">Moderate</div>
      </div>
      <div class="asset-row">
        <div><div class="asset-name">Photo/media library metadata</div><div class="asset-desc">Google Photos — timestamps, locations if enabled</div></div>
        <div class="asset-val">Moderate</div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">07</span><h2>Privacy Improvement Simulator</h2></div>
    <div class="section-desc">Drag the sliders to see how reducing exposure changes your estimated privacy score.</div>
    <div class="panel sim">
      <div class="sim-row">
        <label>Limit ad tracking (Meta/Google)</label>
        <input type="range" min="0" max="20" value="0" id="s1" oninput="updateSim()">
      </div>
      <div class="sim-row">
        <label>Tighten social privacy settings</label>
        <input type="range" min="0" max="20" value="0" id="s2" oninput="updateSim()">
      </div>
      <div class="sim-row">
        <label>Disable location on shopping/photo apps</label>
        <input type="range" min="0" max="18" value="0" id="s3" oninput="updateSim()">
      </div>
      <div class="sim-out">
        <div>
          <div class="score-label">Simulated Privacy Score</div>
          <div class="section-desc" style="margin:4px 0 0">Illustrative only — not a real-time device scan.</div>
        </div>
        <div class="big" id="simScore">42</div>
      </div>
    </div>
  </section>

  <section>
    <div class="section-head"><span class="section-num">08</span><h2>Final Verdict</h2></div>
    <div class="verdict">
      <p><b>Facts:</b> You reported using 15 services spanning social media, messaging, gaming, payments, shopping, and media — inferred to sit under roughly 11 distinct parent companies, with Alphabet/Google holding the largest single share (4 of 15 services).</p>
      <p><b>Estimates:</b> This mix suggests a Significant digital footprint (🟠 72/100) and a Fair privacy posture (🟠 42/100), driven mainly by high-frequency social/video apps and a payments app sitting in the same ecosystem as your search and media history. None of this reflects actual account settings, real tracking logs, or private data — it's a pattern-based read of the services themselves.</p>
      <p><b>Suggested next step:</b> Reviewing ad personalization settings on Google and Meta accounts, and checking location permissions on Google Photos and shopping apps, are the two levers estimated to move the privacy score the most.</p>
    </div>
  </section>

  <footer>NO PRIVATE DATABASES ACCESSED · NO REAL-TIME SCAN PERFORMED · ALL INFERENCES ARE ESTIMATES</footer>
</div>

<script>
function updateSim(){
  const s1=+document.getElementById('s1').value;
  const s2=+document.getElementById('s2').value;
  const s3=+document.getElementById('s3').value;
  const score=Math.min(100,42+s1+s2+s3);
  document.getElementById('simScore').textContent=score;
}
</script>

