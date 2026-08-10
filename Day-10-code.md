<!DOCTYPE html>
<html lang="en" class="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Diya Jaiswal — Data Science Enthusiast | GenAI Builder</title>
<meta name="description" content="Portfolio of Diya Jaiswal — Computer Science student specializing in data visualization, Power BI, and GenAI-driven analytics. Based in Nagpur, India.">
<meta name="keywords" content="Diya Jaiswal, Data Science, Power BI, GenAI, Python, SQL, Portfolio, Nagpur">
<meta name="author" content="Diya Jaiswal">
<meta property="og:title" content="Diya Jaiswal — Data Science Enthusiast | GenAI Builder">
<meta property="og:description" content="Third-year B.Tech CS student building interactive dashboards and GenAI-powered analytics tools.">
<meta property="og:type" content="website">
<meta name="twitter:card" content="summary">
<link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><rect width=%22100%22 height=%22100%22 rx=%2220%22 fill=%22%230B0F14%22/><path d=%22M20 65 L38 45 L52 58 L80 30%22 stroke=%22%232DD4BF%22 stroke-width=%228%22 fill=%22none%22 stroke-linecap=%22round%22 stroke-linejoin=%22round%22/></svg>">

<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<script>
  tailwind.config = {
    darkMode: 'class',
    theme: {
      extend: {
        colors: {
          ink: { 950: '#0B0F14', 900: '#0F141B', 800: '#121821', 700: '#1A2230', 600: '#26303F', 400: '#8B95A1', 200: '#C7CFD8' },
          paper: { 50: '#F7F8FA', 100: '#EEF1F4', 200: '#E3E8EC' },
          teal: { DEFAULT: '#2DD4BF', 600: '#14B8A6', 300: '#7EEAE0' },
          violet: { DEFAULT: '#8B7CF6', 600: '#7C6AF0' },
          amber: { DEFAULT: '#F5A623' },
        },
        fontFamily: {
          display: ['"Space Grotesk"', 'sans-serif'],
          body: ['Inter', 'sans-serif'],
          mono: ['"JetBrains Mono"', 'monospace'],
        },
      }
    }
  }
</script>

<style>
  :root { scroll-behavior: smooth; }
  body { background-color: #0B0F14; }
  html.light body { background-color: #F7F8FA; }

  .grid-bg {
    background-image:
      linear-gradient(to right, rgba(45,212,191,0.06) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(45,212,191,0.06) 1px, transparent 1px);
    background-size: 42px 42px;
  }
  html.light .grid-bg {
    background-image:
      linear-gradient(to right, rgba(20,184,166,0.08) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(20,184,166,0.08) 1px, transparent 1px);
  }

  .panel { background-color: #121821; border: 1px solid #1A2230; }
  html.light .panel { background-color: #FFFFFF; border: 1px solid #E3E8EC; }

  .text-main { color: #E7ECF1; }
  html.light .text-main { color: #10161D; }

  .text-sub { color: #8B95A1; }
  html.light .text-sub { color: #5B6673; }

  .bg-app { background-color: #0B0F14; }
  html.light .bg-app { background-color: #F7F8FA; }

  .bg-nav { background-color: rgba(11,15,20,0.75); backdrop-filter: blur(10px); border-bottom: 1px solid #1A2230; }
  html.light .bg-nav { background-color: rgba(247,248,250,0.8); border-bottom: 1px solid #E3E8EC; }

  ::selection { background-color: #2DD4BF; color: #0B0F14; }

  .caret { border-right: 2px solid #2DD4BF; animation: blink 0.9s steps(1) infinite; }
  @keyframes blink { 50% { border-color: transparent; } }

  .reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.7s ease, transform 0.7s ease; }
  .reveal.in { opacity: 1; transform: translateY(0); }

  .bar-fill { width: 0%; transition: width 1.4s cubic-bezier(0.16, 1, 0.3, 1); }

  .navlink { position: relative; color: #8B95A1; transition: color 0.2s ease; }
  .navlink::after {
    content: ''; position: absolute; left: 0; bottom: -6px; height: 1px; width: 0;
    background: #2DD4BF; transition: width 0.25s ease;
  }
  .navlink.active, .navlink:hover { color: #E7ECF1; }
  html.light .navlink.active, html.light .navlink:hover { color: #10161D; }
  .navlink.active::after, .navlink:hover::after { width: 100%; }

  .chip {
    font-family: 'JetBrains Mono', monospace; font-size: 0.72rem; letter-spacing: 0.02em;
  }

  .glow-teal { box-shadow: 0 0 0 1px rgba(45,212,191,0.25), 0 8px 30px -8px rgba(45,212,191,0.25); }

  .card-hover { transition: transform 0.35s cubic-bezier(0.16,1,0.3,1), border-color 0.35s ease, box-shadow 0.35s ease; }
  .card-hover:hover { transform: translateY(-6px); border-color: rgba(45,212,191,0.45); box-shadow: 0 20px 40px -20px rgba(45,212,191,0.25); }

  .sparkline path { stroke-dasharray: 500; stroke-dashoffset: 500; animation: draw 2.4s ease forwards 0.4s; }
  @keyframes draw { to { stroke-dashoffset: 0; } }

  .status-dot { box-shadow: 0 0 0 0 rgba(45,212,191,0.6); animation: pulse 2s infinite; }
  @keyframes pulse {
    0% { box-shadow: 0 0 0 0 rgba(45,212,191,0.5); }
    70% { box-shadow: 0 0 0 8px rgba(45,212,191,0); }
    100% { box-shadow: 0 0 0 0 rgba(45,212,191,0); }
  }

  input:focus-visible, textarea:focus-visible, button:focus-visible, a:focus-visible {
    outline: 2px solid #2DD4BF; outline-offset: 2px;
  }

  @media (prefers-reduced-motion: reduce) {
    .reveal, .bar-fill, .sparkline path, .status-dot { animation: none !important; transition: none !important; opacity: 1 !important; transform: none !important; width: var(--target, 100%) !important; }
  }

  .scrollbar-thin::-webkit-scrollbar { height: 6px; width: 6px; }
  .scrollbar-thin::-webkit-scrollbar-thumb { background: #26303F; border-radius: 999px; }
</style>
</head>

<body class="bg-app text-main font-body antialiased selection:bg-teal transition-colors duration-300">

<!-- ============ NAV ============ -->
<nav class="fixed top-0 inset-x-0 z-50 bg-nav">
  <div class="max-w-6xl mx-auto px-6 lg:px-8 h-16 flex items-center justify-between">
    <a href="#home" class="flex items-center gap-2 font-display font-semibold text-lg tracking-tight">
      <span class="w-2.5 h-2.5 rounded-full bg-teal status-dot"></span>
      DJ<span class="text-teal">.</span>dev
    </a>
    <div class="hidden md:flex items-center gap-8 chip uppercase" id="nav-links">
      <a href="#home" class="navlink active">Home</a>
      <a href="#about" class="navlink">About</a>
      <a href="#skills" class="navlink">Skills</a>
      <a href="#projects" class="navlink">Projects</a>
      <a href="#achievements" class="navlink">Achievements</a>
      <a href="#contact" class="navlink">Contact</a>
    </div>
    <div class="flex items-center gap-3">
      <button id="theme-toggle" aria-label="Toggle dark and light mode" class="w-9 h-9 rounded-full panel flex items-center justify-center hover:border-teal/60 transition-colors">
        <svg id="icon-sun" class="w-4 h-4 text-amber hidden" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M12 3v1.5M12 19.5V21M4.22 4.22l1.06 1.06M18.72 18.72l1.06 1.06M3 12h1.5M19.5 12H21M4.22 19.78l1.06-1.06M18.72 5.28l1.06-1.06M12 7.5a4.5 4.5 0 100 9 4.5 4.5 0 000-9z"/></svg>
        <svg id="icon-moon" class="w-4 h-4 text-teal" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M21 12.79A9 9 0 1111.21 3 7 7 0 0021 12.79z"/></svg>
      </button>
      <button id="mobile-toggle" aria-label="Open menu" class="md:hidden w-9 h-9 rounded-full panel flex items-center justify-center">
        <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16"/></svg>
      </button>
    </div>
  </div>
  <div id="mobile-menu" class="hidden md:hidden panel border-t chip uppercase">
    <div class="flex flex-col px-6 py-4 gap-4">
      <a href="#home" class="navlink">Home</a>
      <a href="#about" class="navlink">About</a>
      <a href="#skills" class="navlink">Skills</a>
      <a href="#projects" class="navlink">Projects</a>
      <a href="#achievements" class="navlink">Achievements</a>
      <a href="#contact" class="navlink">Contact</a>
    </div>
  </div>
</nav>

<!-- ============ HERO ============ -->
<header id="home" class="relative pt-32 pb-24 overflow-hidden grid-bg">
  <div class="absolute inset-0 pointer-events-none">
    <div class="absolute -top-24 -right-24 w-96 h-96 rounded-full bg-teal/10 blur-3xl"></div>
    <div class="absolute top-40 -left-24 w-72 h-72 rounded-full bg-violet/10 blur-3xl"></div>
  </div>

  <div class="relative max-w-6xl mx-auto px-6 lg:px-8">
    <div class="grid lg:grid-cols-[1.15fr,0.85fr] gap-14 items-center">

      <div>
        <div class="inline-flex items-center gap-2 chip uppercase text-teal panel px-3 py-1.5 rounded-full mb-6">
          <span class="w-1.5 h-1.5 rounded-full bg-teal status-dot"></span>
          Open to Internships &amp; Research Roles
        </div>

        <h1 class="font-display font-semibold leading-[1.05] tracking-tight text-4xl sm:text-5xl lg:text-6xl text-main">
          Diya Jaiswal
        </h1>

        <p class="mt-4 font-mono text-teal text-lg sm:text-xl h-8" id="typing-target"><span class="caret">&nbsp;</span></p>

        <p class="mt-6 text-sub text-base sm:text-lg max-w-xl leading-relaxed">
          I turn raw datasets into dashboards people actually understand — and I'm now
          building that same instinct into GenAI-powered tools. Currently a third-year
          B.Tech Computer Science student in Nagpur.
        </p>

        <div class="mt-8 flex flex-wrap items-center gap-4">
          <a href="#projects" class="px-6 py-3 rounded-lg bg-teal text-ink-950 font-semibold text-sm hover:bg-teal-300 transition-colors glow-teal">
            View Projects
          </a>
          <a href="#contact" class="px-6 py-3 rounded-lg panel text-main font-semibold text-sm hover:border-teal/50 transition-colors">
            Get in Touch
          </a>
        </div>

        <div class="mt-10 flex items-center gap-5">
          <a href="https://www.linkedin.com/in/diya-jaiswal-512b12250" target="_blank" rel="noopener" aria-label="LinkedIn" class="text-sub hover:text-teal transition-colors">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M20.45 20.45h-3.55v-5.57c0-1.33-.02-3.04-1.85-3.04-1.85 0-2.14 1.45-2.14 2.94v5.67H9.36V9h3.41v1.56h.05c.47-.9 1.63-1.85 3.36-1.85 3.6 0 4.27 2.37 4.27 5.45v6.29zM5.34 7.43a2.06 2.06 0 11.02-4.12 2.06 2.06 0 01-.02 4.12zM7.11 20.45H3.56V9h3.55v11.45zM22.22 0H1.77C.79 0 0 .77 0 1.73v20.54C0 23.23.79 24 1.77 24h20.45c.98 0 1.78-.77 1.78-1.73V1.73C24 .77 23.2 0 22.22 0z"/></svg>
          </a>
          <a href="https://github.com/DiYa174" target="_blank" rel="noopener" aria-label="GitHub" class="text-sub hover:text-teal transition-colors">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 .5C5.73.5.5 5.74.5 12.02c0 5.1 3.3 9.42 7.88 10.95.58.1.79-.25.79-.56 0-.28-.01-1.02-.02-2-3.2.7-3.88-1.54-3.88-1.54-.53-1.33-1.28-1.69-1.28-1.69-1.04-.71.08-.7.08-.7 1.15.08 1.76 1.18 1.76 1.18 1.02 1.75 2.68 1.24 3.34.95.1-.74.4-1.24.72-1.53-2.55-.29-5.24-1.28-5.24-5.7 0-1.26.45-2.29 1.18-3.09-.12-.29-.51-1.46.11-3.05 0 0 .97-.31 3.17 1.18a11 11 0 015.78 0c2.2-1.49 3.17-1.18 3.17-1.18.62 1.59.23 2.76.11 3.05.74.8 1.18 1.83 1.18 3.09 0 4.43-2.7 5.4-5.27 5.69.42.36.78 1.08.78 2.18 0 1.57-.01 2.84-.01 3.23 0 .31.21.67.8.56A10.53 10.53 0 0023.5 12.02C23.5 5.74 18.27.5 12 .5z"/></svg>
          </a>
          <a href="mailto:jaiswaldiya520@gmail.com" aria-label="Email" class="text-sub hover:text-teal transition-colors">
            <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.8"><path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
          </a>
          <span class="text-sub chip flex items-center gap-1.5">
            <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.8"><path stroke-linecap="round" stroke-linejoin="round" d="M17.66 17.66A8 8 0 106.34 6.34a8 8 0 0011.32 11.32z"/><path stroke-linecap="round" stroke-linejoin="round" d="M12 8v4l3 3"/></svg>
            Nagpur, India
          </span>
        </div>
      </div>

      <!-- Dashboard-style hero card -->
      <div class="reveal in">
        <div class="panel rounded-2xl p-5 sm:p-6 shadow-2xl">
          <div class="flex items-center justify-between mb-5">
            <span class="chip uppercase text-sub">profile.dashboard</span>
            <div class="flex gap-1.5">
              <span class="w-2.5 h-2.5 rounded-full bg-[#F5A623]/70"></span>
              <span class="w-2.5 h-2.5 rounded-full bg-teal/70"></span>
              <span class="w-2.5 h-2.5 rounded-full bg-violet/70"></span>
            </div>
          </div>

          <div class="flex items-center gap-4 mb-6">
            <img src="data:image/jpeg;base64,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"
                 alt="Portrait of Diya Jaiswal" class="w-16 h-16 rounded-xl object-cover border border-ink-600" />
            <div>
              <p class="font-display font-semibold text-main">Diya Jaiswal</p>
              <p class="text-sub text-sm">B.Tech CS · Class of 2028</p>
            </div>
          </div>

          <div class="grid grid-cols-2 gap-3 mb-5">
            <div class="rounded-lg bg-ink-700/40 border border-ink-600/60 p-3">
              <p class="chip text-sub uppercase mb-1">Certifications</p>
              <p class="font-display text-2xl font-semibold text-teal"><span data-counter="2">0</span></p>
            </div>
            <div class="rounded-lg bg-ink-700/40 border border-ink-600/60 p-3">
              <p class="chip text-sub uppercase mb-1">Core Languages</p>
              <p class="font-display text-2xl font-semibold text-violet"><span data-counter="4">0</span></p>
            </div>
            <div class="rounded-lg bg-ink-700/40 border border-ink-600/60 p-3">
              <p class="chip text-sub uppercase mb-1">Dashboards Built</p>
              <p class="font-display text-2xl font-semibold text-amber"><span data-counter="6">0</span>+</p>
            </div>
            <div class="rounded-lg bg-ink-700/40 border border-ink-600/60 p-3">
              <p class="chip text-sub uppercase mb-1">Grad Year</p>
              <p class="font-display text-2xl font-semibold text-main">20<span data-counter="28">00</span></p>
            </div>
          </div>

          <div class="rounded-lg bg-ink-700/30 border border-ink-600/60 p-3">
            <p class="chip text-sub uppercase mb-2">Learning trend</p>
            <svg class="sparkline w-full h-14" viewBox="0 0 300 60" fill="none">
              <path d="M0 45 L40 40 L80 42 L120 28 L160 30 L200 15 L240 18 L300 5" stroke="#2DD4BF" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
        </div>
      </div>

    </div>
  </div>
</header>

<!-- ============ ABOUT ============ -->
<section id="about" class="py-24 border-t border-ink-700/60">
  <div class="max-w-6xl mx-auto px-6 lg:px-8">
    <div class="grid lg:grid-cols-[0.4fr,0.6fr] gap-12">
      <div class="reveal">
        <p class="chip uppercase text-teal mb-3">01 · About</p>
        <h2 class="font-display text-3xl sm:text-4xl font-semibold tracking-tight">The person behind the panels</h2>
      </div>
      <div class="reveal space-y-5 text-sub text-base sm:text-lg leading-relaxed">
        <p>
          I'm a third-year Computer Science student at S. B. Jain Institute of Technology,
          Management &amp; Research in Nagpur, expected to graduate in 2028. My interest in
          software took a sharper shape during a data visualization internship, where I
          spent my time turning spreadsheets no one wanted to open into Power BI dashboards
          people actually used to make decisions.
        </p>
        <p>
          That experience left me with a simple belief: good engineering is really about
          making information legible. I'm now extending that belief from dashboards into
          GenAI — exploring how large language models can be wired into the same kind of
          practical, decision-ready tools, built on a foundation of C, C++, Java, Python
          and SQL.
        </p>
        <p>
          Outside of coursework, I've competed at hackathons, earned an advanced
          certification in data science, and I'm always looking for the next dataset,
          team, or problem worth digging into.
        </p>

        <div class="flex flex-wrap gap-2 pt-2">
          <span class="chip panel px-3 py-1.5 rounded-full text-sub">📍 Nagpur, India</span>
          <span class="chip panel px-3 py-1.5 rounded-full text-sub">🎓 B.Tech CS, Exp. 2028</span>
          <span class="chip panel px-3 py-1.5 rounded-full text-sub">💼 Ex-Intern, Codemate IT Services</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SKILLS ============ -->
<section id="skills" class="py-24 bg-ink-900/40 border-t border-ink-700/60">
  <div class="max-w-6xl mx-auto px-6 lg:px-8">
    <p class="chip uppercase text-teal mb-3 reveal">02 · Skills</p>
    <h2 class="font-display text-3xl sm:text-4xl font-semibold tracking-tight mb-12 reveal">Skill matrix</h2>

    <div class="grid lg:grid-cols-2 gap-10 mb-14">
      <div class="reveal panel rounded-2xl p-6 sm:p-8">
        <h3 class="font-display font-semibold text-lg mb-6 flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-teal"></span> Technical Proficiency
        </h3>
        <div class="space-y-5" id="bars-technical">
          <!-- filled by JS-driven markup below (static for no-js fallback) -->
          <div class="skill-row" data-level="88">
            <div class="flex justify-between chip mb-1.5"><span>Python</span><span class="text-sub">88%</span></div>
            <div class="h-1.5 rounded-full bg-ink-700 overflow-hidden"><div class="bar-fill h-full rounded-full bg-teal"></div></div>
          </div>
          <div class="skill-row" data-level="85">
            <div class="flex justify-between chip mb-1.5"><span>SQL</span><span class="text-sub">85%</span></div>
            <div class="h-1.5 rounded-full bg-ink-700 overflow-hidden"><div class="bar-fill h-full rounded-full bg-teal"></div></div>
          </div>
          <div class="skill-row" data-level="82">
            <div class="flex justify-between chip mb-1.5"><span>Power BI</span><span class="text-sub">82%</span></div>
            <div class="h-1.5 rounded-full bg-ink-700 overflow-hidden"><div class="bar-fill h-full rounded-full bg-violet"></div></div>
          </div>
          <div class="skill-row" data-level="72">
            <div class="flex justify-between chip mb-1.5"><span>Java / C++</span><span class="text-sub">72%</span></div>
            <div class="h-1.5 rounded-full bg-ink-700 overflow-hidden"><div class="bar-fill h-full rounded-full bg-violet"></div></div>
          </div>
          <div class="skill-row" data-level="65">
            <div class="flex justify-between chip mb-1.5"><span>Machine Learning (Basics)</span><span class="text-sub">65%</span></div>
            <div class="h-1.5 rounded-full bg-ink-700 overflow-hidden"><div class="bar-fill h-full rounded-full bg-amber"></div></div>
          </div>
        </div>
      </div>

      <div class="reveal panel rounded-2xl p-6 sm:p-8">
        <h3 class="font-display font-semibold text-lg mb-6 flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-violet"></span> Tools &amp; Platforms
        </h3>
        <div class="flex flex-wrap gap-2.5 mb-8">
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Microsoft Power BI</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">MS Excel</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">VS Code</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Jupyter Notebook</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">MS Office</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Git / GitHub</span>
        </div>

        <h3 class="font-display font-semibold text-lg mb-6 flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-amber"></span> Soft Skills
        </h3>
        <div class="flex flex-wrap gap-2.5">
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Analytical Thinking</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Leadership</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Communication</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Time Management</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Adaptability</span>
          <span class="chip px-3 py-2 rounded-lg bg-ink-700/50 border border-ink-600">Critical Thinking</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ PROJECTS ============ -->
<section id="projects" class="py-24 border-t border-ink-700/60">
  <div class="max-w-6xl mx-auto px-6 lg:px-8">
    <div class="flex items-end justify-between flex-wrap gap-4 mb-12">
      <div class="reveal">
        <p class="chip uppercase text-teal mb-3">03 · Projects</p>
        <h2 class="font-display text-3xl sm:text-4xl font-semibold tracking-tight">Selected work</h2>
      </div>
      <p class="reveal text-sub chip uppercase max-w-xs text-right hidden sm:block">Starter concepts — swap in your own repos anytime</p>
    </div>

    <div class="grid md:grid-cols-3 gap-6">

      <div class="reveal card-hover panel rounded-2xl p-6 flex flex-col">
        <div class="flex items-center justify-between mb-4">
          <span class="chip uppercase text-teal">Dashboard</span>
          <svg class="w-4 h-4 text-sub" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.8"><path stroke-linecap="round" stroke-linejoin="round" d="M13 7h6m0 0v6m0-6L10 17l-4-4-6 6"/></svg>
        </div>
        <h3 class="font-display font-semibold text-lg mb-2">Retail Sales Intelligence Dashboard</h3>
        <p class="text-sub text-sm leading-relaxed mb-5 flex-1">
          An interactive Power BI dashboard that consolidates regional sales data into
          drill-down views for revenue, returns, and store performance — built on the
          same modeling workflow used during my internship.
        </p>
        <div class="flex flex-wrap gap-2">
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-teal">Power BI</span>
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-teal">SQL</span>
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-teal">Excel</span>
        </div>
      </div>

      <div class="reveal card-hover panel rounded-2xl p-6 flex flex-col">
        <div class="flex items-center justify-between mb-4">
          <span class="chip uppercase text-violet">GenAI</span>
          <svg class="w-4 h-4 text-sub" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.8"><path stroke-linecap="round" stroke-linejoin="round" d="M13 7h6m0 0v6m0-6L10 17l-4-4-6 6"/></svg>
        </div>
        <h3 class="font-display font-semibold text-lg mb-2">Dataset-to-Insight Chat Assistant</h3>
        <p class="text-sub text-sm leading-relaxed mb-5 flex-1">
          A Python prototype that lets a user upload a CSV and ask plain-language
          questions about it, returning summary stats and quick charts — an early step
          toward combining GenAI with data analysis.
        </p>
        <div class="flex flex-wrap gap-2">
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-violet">Python</span>
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-violet">Pandas</span>
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-violet">LLM API</span>
        </div>
      </div>

      <div class="reveal card-hover panel rounded-2xl p-6 flex flex-col">
        <div class="flex items-center justify-between mb-4">
          <span class="chip uppercase text-amber">Database</span>
          <svg class="w-4 h-4 text-sub" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.8"><path stroke-linecap="round" stroke-linejoin="round" d="M13 7h6m0 0v6m0-6L10 17l-4-4-6 6"/></svg>
        </div>
        <h3 class="font-display font-semibold text-lg mb-2">Campus Event Management System</h3>
        <p class="text-sub text-sm leading-relaxed mb-5 flex-1">
          A SQL-backed application for scheduling and tracking college events and
          registrations, with a simple Java interface for organizers to manage
          attendance in real time.
        </p>
        <div class="flex flex-wrap gap-2">
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-amber">Java</span>
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-amber">SQL</span>
          <span class="chip px-2.5 py-1 rounded-md bg-ink-700/60 text-amber">C++</span>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ============ ACHIEVEMENTS ============ -->
<section id="achievements" class="py-24 bg-ink-900/40 border-t border-ink-700/60">
  <div class="max-w-6xl mx-auto px-6 lg:px-8">
    <p class="chip uppercase text-teal mb-3 reveal">04 · Achievements</p>
    <h2 class="font-display text-3xl sm:text-4xl font-semibold tracking-tight mb-12 reveal">Experience &amp; certifications</h2>

    <div class="relative pl-8 sm:pl-10 border-l border-ink-600 space-y-10">

      <div class="reveal relative">
        <span class="absolute -left-[41px] sm:-left-[49px] top-1 w-4 h-4 rounded-full bg-teal border-4 border-ink-950"></span>
        <p class="chip uppercase text-teal mb-1">June 2024</p>
        <h3 class="font-display font-semibold text-lg">Data Visualization Intern — Power BI</h3>
        <p class="text-sub text-sm mb-2">Codemate IT Services Pvt. Ltd., Nagpur</p>
        <p class="text-sub text-sm leading-relaxed max-w-2xl">
          Built interactive Power BI dashboards and reports, translated raw datasets into
          decision-ready visual insights, and applied data modeling best practices
          alongside a live reporting team.
        </p>
      </div>

      <div class="reveal relative">
        <span class="absolute -left-[41px] sm:-left-[49px] top-1 w-4 h-4 rounded-full bg-violet border-4 border-ink-950"></span>
        <p class="chip uppercase text-violet mb-1">Certification</p>
        <h3 class="font-display font-semibold text-lg">Advanced Certification in Data Science</h3>
        <p class="text-sub text-sm leading-relaxed max-w-2xl">
          Coursework covering statistics, data modeling, and visualization fundamentals.
        </p>
      </div>

      <div class="reveal relative">
        <span class="absolute -left-[41px] sm:-left-[49px] top-1 w-4 h-4 rounded-full bg-amber border-4 border-ink-950"></span>
        <p class="chip uppercase text-amber mb-1">Hackathon</p>
        <h3 class="font-display font-semibold text-lg">Women Who Master Hackathon — Logitech</h3>
        <p class="text-sub text-sm leading-relaxed max-w-2xl">
          Participation certificate from a hackathon focused on building and presenting
          technical solutions under time constraints.
        </p>
      </div>

      <div class="reveal relative">
        <span class="absolute -left-[41px] sm:-left-[49px] top-1 w-4 h-4 rounded-full bg-main bg-ink-200 border-4 border-ink-950"></span>
        <p class="chip uppercase text-sub mb-1">Expected 2028</p>
        <h3 class="font-display font-semibold text-lg">B.Tech, Computer Science</h3>
        <p class="text-sub text-sm leading-relaxed max-w-2xl">
          S. B. Jain Institute of Technology, Management &amp; Research, Nagpur.
        </p>
      </div>

    </div>
  </div>
</section>

<!-- ============ CONTACT ============ -->
<section id="contact" class="py-24 border-t border-ink-700/60">
  <div class="max-w-6xl mx-auto px-6 lg:px-8">
    <div class="grid lg:grid-cols-[0.45fr,0.55fr] gap-12">
      <div class="reveal">
        <p class="chip uppercase text-teal mb-3">05 · Contact</p>
        <h2 class="font-display text-3xl sm:text-4xl font-semibold tracking-tight mb-5">Let's build something</h2>
        <p class="text-sub leading-relaxed mb-8 max-w-sm">
          Open to internships, research collaborations, and interesting data problems.
          The fastest way to reach me is email.
        </p>

        <div class="space-y-4">
          <a href="mailto:jaiswaldiya520@gmail.com" class="flex items-center gap-3 panel rounded-xl p-4 hover:border-teal/50 transition-colors">
            <span class="w-9 h-9 rounded-lg bg-teal/10 flex items-center justify-center text-teal">
              <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.8"><path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
            </span>
            <span class="text-sm break-all">jaiswaldiya520@gmail.com</span>
          </a>
          <a href="https://www.linkedin.com/in/diya-jaiswal-512b12250" target="_blank" rel="noopener" class="flex items-center gap-3 panel rounded-xl p-4 hover:border-teal/50 transition-colors">
            <span class="w-9 h-9 rounded-lg bg-violet/10 flex items-center justify-center text-violet">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M20.45 20.45h-3.55v-5.57c0-1.33-.02-3.04-1.85-3.04-1.85 0-2.14 1.45-2.14 2.94v5.67H9.36V9h3.41v1.56h.05c.47-.9 1.63-1.85 3.36-1.85 3.6 0 4.27 2.37 4.27 5.45v6.29zM5.34 7.43a2.06 2.06 0 11.02-4.12 2.06 2.06 0 01-.02 4.12zM7.11 20.45H3.56V9h3.55v11.45zM22.22 0H1.77C.79 0 0 .77 0 1.73v20.54C0 23.23.79 24 1.77 24h20.45c.98 0 1.78-.77 1.78-1.73V1.73C24 .77 23.2 0 22.22 0z"/></svg>
            </span>
            <span class="text-sm">linkedin.com/in/diya-jaiswal</span>
          </a>
          <a href="https://github.com/DiYa174" target="_blank" rel="noopener" class="flex items-center gap-3 panel rounded-xl p-4 hover:border-teal/50 transition-colors">
            <span class="w-9 h-9 rounded-lg bg-amber/10 flex items-center justify-center text-amber">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 .5C5.73.5.5 5.74.5 12.02c0 5.1 3.3 9.42 7.88 10.95.58.1.79-.25.79-.56 0-.28-.01-1.02-.02-2-3.2.7-3.88-1.54-3.88-1.54-.53-1.33-1.28-1.69-1.28-1.69-1.04-.71.08-.7.08-.7 1.15.08 1.76 1.18 1.76 1.18 1.02 1.75 2.68 1.24 3.34.95.1-.74.4-1.24.72-1.53-2.55-.29-5.24-1.28-5.24-5.7 0-1.26.45-2.29 1.18-3.09-.12-.29-.51-1.46.11-3.05 0 0 .97-.31 3.17 1.18a11 11 0 015.78 0c2.2-1.49 3.17-1.18 3.17-1.18.62 1.59.23 2.76.11 3.05.74.8 1.18 1.83 1.18 3.09 0 4.43-2.7 5.4-5.27 5.69.42.36.78 1.08.78 2.18 0 1.57-.01 2.84-.01 3.23 0 .31.21.67.8.56A10.53 10.53 0 0023.5 12.02C23.5 5.74 18.27.5 12 .5z"/></svg>
            </span>
            <span class="text-sm">github.com/DiYa174</span>
          </a>
        </div>
      </div>

      <form id="contact-form" class="reveal panel rounded-2xl p-6 sm:p-8 space-y-5" onsubmit="return handleSubmit(event)">
        <div>
          <label for="name" class="chip uppercase text-sub block mb-2">Name</label>
          <input id="name" name="name" type="text" required placeholder="Your name"
            class="w-full bg-ink-700/40 border border-ink-600 rounded-lg px-4 py-3 text-sm text-main placeholder:text-ink-400 focus:border-teal outline-none transition-colors" />
        </div>
        <div>
          <label for="email" class="chip uppercase text-sub block mb-2">Email</label>
          <input id="email" name="email" type="email" required placeholder="you@example.com"
            class="w-full bg-ink-700/40 border border-ink-600 rounded-lg px-4 py-3 text-sm text-main placeholder:text-ink-400 focus:border-teal outline-none transition-colors" />
        </div>
        <div>
          <label for="message" class="chip uppercase text-sub block mb-2">Message</label>
          <textarea id="message" name="message" rows="4" required placeholder="What are you building?"
            class="w-full bg-ink-700/40 border border-ink-600 rounded-lg px-4 py-3 text-sm text-main placeholder:text-ink-400 focus:border-teal outline-none transition-colors resize-none"></textarea>
        </div>
        <button type="submit" class="w-full py-3 rounded-lg bg-teal text-ink-950 font-semibold text-sm hover:bg-teal-300 transition-colors">
          Send Message
        </button>
        <p id="form-status" class="chip text-sub text-center hidden"></p>
      </form>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer class="border-t border-ink-700/60 py-10">
  <div class="max-w-6xl mx-auto px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4">
    <p class="chip text-sub">© <span id="year"></span> Diya Jaiswal. Built with intent.</p>
    <div class="flex items-center gap-5">
      <a href="https://www.linkedin.com/in/diya-jaiswal-512b12250" target="_blank" rel="noopener" class="text-sub hover:text-teal transition-colors chip">LinkedIn</a>
      <a href="https://github.com/DiYa174" target="_blank" rel="noopener" class="text-sub hover:text-teal transition-colors chip">GitHub</a>
      <a href="mailto:jaiswaldiya520@gmail.com" class="text-sub hover:text-teal transition-colors chip">Email</a>
    </div>
  </div>
</footer>

<script>
  // Theme toggle (no persistence — in-memory only)
  const root = document.documentElement;
  const sunIcon = document.getElementById('icon-sun');
  const moonIcon = document.getElementById('icon-moon');

  function setTheme(mode) {
    if (mode === 'light') {
      root.classList.remove('dark'); root.classList.add('light');
      sunIcon.classList.remove('hidden'); moonIcon.classList.add('hidden');
    } else {
      root.classList.remove('light'); root.classList.add('dark');
      moonIcon.classList.remove('hidden'); sunIcon.classList.add('hidden');
    }
  }
  setTheme('dark');
  document.getElementById('theme-toggle').addEventListener('click', () => {
    setTheme(root.classList.contains('dark') ? 'light' : 'dark');
  });

  // Mobile menu
  const mobileToggle = document.getElementById('mobile-toggle');
  const mobileMenu = document.getElementById('mobile-menu');
  mobileToggle.addEventListener('click', () => mobileMenu.classList.toggle('hidden'));
  document.querySelectorAll('#mobile-menu a').forEach(a => a.addEventListener('click', () => mobileMenu.classList.add('hidden')));

  // Typing animation
  const roles = [
    'Data Science Enthusiast',
    'GenAI Builder',
    'Power BI Dashboard Developer',
    'Computer Science Student'
  ];
  const target = document.getElementById('typing-target');
  let roleIdx = 0, charIdx = 0, deleting = false;

  function typeLoop() {
    const current = roles[roleIdx];
    if (!deleting) {
      charIdx++;
      target.innerHTML = current.slice(0, charIdx) + '<span class="caret">&nbsp;</span>';
      if (charIdx === current.length) { deleting = true; setTimeout(typeLoop, 1600); return; }
    } else {
      charIdx--;
      target.innerHTML = current.slice(0, charIdx) + '<span class="caret">&nbsp;</span>';
      if (charIdx === 0) { deleting = false; roleIdx = (roleIdx + 1) % roles.length; }
    }
    setTimeout(typeLoop, deleting ? 45 : 85);
  }
  typeLoop();

  // Counter animation
  function animateCounters() {
    document.querySelectorAll('[data-counter]').forEach(el => {
      const target = parseInt(el.getAttribute('data-counter'), 10);
      const start = parseInt(el.textContent, 10) || 0;
      const duration = 1200;
      const startTime = performance.now();
      function step(now) {
        const progress = Math.min((now - startTime) / duration, 1);
        const eased = 1 - Math.pow(1 - progress, 3);
        el.textContent = Math.round(start + (target - start) * eased);
        if (progress < 1) requestAnimationFrame(step);
      }
      requestAnimationFrame(step);
    });
  }

  // Reveal on scroll + skill bars + counters trigger
  const revealEls = document.querySelectorAll('.reveal');
  const barsSection = document.getElementById('bars-technical');
  let barsAnimated = false, countersAnimated = false;

  const io = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('in');
        if (entry.target.contains(barsSection) || entry.target === barsSection) {
          if (!barsAnimated) {
            barsAnimated = true;
            document.querySelectorAll('.skill-row').forEach(row => {
              const level = row.getAttribute('data-level');
              const fill = row.querySelector('.bar-fill');
              requestAnimationFrame(() => { fill.style.width = level + '%'; });
            });
          }
        }
      }
    });
  }, { threshold: 0.25 });
  revealEls.forEach(el => io.observe(el));

  const heroIo = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting && !countersAnimated) {
        countersAnimated = true;
        animateCounters();
      }
    });
  }, { threshold: 0.3 });
  heroIo.observe(document.getElementById('home'));

  // Active nav highlighting
  const sections = document.querySelectorAll('section[id], header[id]');
  const navlinks = document.querySelectorAll('.navlink');
  const navIo = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        navlinks.forEach(link => {
          link.classList.toggle('active', link.getAttribute('href') === '#' + entry.target.id);
        });
      }
    });
  }, { rootMargin: '-45% 0px -50% 0px', threshold: 0 });
  sections.forEach(sec => navIo.observe(sec));

  // Contact form (no backend — front-end confirmation only)
  function handleSubmit(e) {
    e.preventDefault();
    const status = document.getElementById('form-status');
    status.textContent = 'Message ready — opening your email client…';
    status.classList.remove('hidden');
    const name = document.getElementById('name').value;
    const email = document.getElementById('email').value;
    const message = document.getElementById('message').value;
    const subject = encodeURIComponent('Portfolio contact from ' + name);
    const body = encodeURIComponent(message + '\n\n— ' + name + ' (' + email + ')');
    window.location.href = `mailto:jaiswaldiya520@gmail.com?subject=${subject}&body=${body}`;
    return false;
  }

  document.getElementById('year').textContent = new Date().getFullYear();
</script>

</body>
</html>
