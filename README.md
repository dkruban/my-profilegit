<a href="https://dkruban.github.io" target="_blank" title="Click to Launch Site">
  <svg width="450" height="650" viewBox="0 0 450 650" xmlns="http://www.w3.org/2000/svg" style="border-radius: 20px; background: #050508; font-family: 'Share Tech Mono', monospace; box-shadow: 0 0 20px rgba(0, 243, 255, 0.1);">

    <!-- DEFINITIONS & FILTERS -->
    <defs>
      <!-- Neon Cyan Gradient -->
      <linearGradient id="gradCyan" x1="0%" y1="0%" x2="100%" y2="0%">
        <stop offset="0%" style="stop-color:#00f3ff;stop-opacity:1">
          <animate attributeName="stop-color" values="#00f3ff;#00ff88;#00f3ff" dur="3s" repeatCount="indefinite"/>
        </stop>
        <stop offset="100%" style="stop-color:#0088ff;stop-opacity:1">
          <animate attributeName="stop-color" values="#0088ff;#00f3ff;#0088ff" dur="3s" repeatCount="indefinite"/>
        </stop>
      </linearGradient>

      <!-- Neon Pink Gradient -->
      <linearGradient id="gradPink" x1="0%" y1="0%" x2="100%" y2="0%">
        <stop offset="0%" style="stop-color:#ff00ff;stop-opacity:1">
          <animate attributeName="stop-color" values="#ff00ff;#bd00ff;#ff00ff" dur="4s" repeatCount="indefinite"/>
        </stop>
        <stop offset="100%" style="stop-color:#ff0080;stop-opacity:1"/>
      </linearGradient>

      <!-- Green Glow Gradient -->
      <linearGradient id="gradGreen" x1="0%" y1="0%" x2="100%" y2="0%">
        <stop offset="0%" style="stop-color:#0aff0a;stop-opacity:1"/>
        <stop offset="100%" style="stop-color:#00ff88;stop-opacity:1"/>
      </linearGradient>

      <!-- Holographic BG Gradient -->
      <radialGradient id="bgGrad" cx="50%" cy="50%" r="50%">
        <stop offset="0%" style="stop-color:#1a1a2e;stop-opacity:1"/>
        <stop offset="100%" style="stop-color:#050508;stop-opacity:1"/>
      </radialGradient>

      <!-- Glow Filter -->
      <filter id="glow">
        <feGaussianBlur stdDeviation="2.5" result="coloredBlur"/>
        <feMerge>
          <feMergeNode in="coloredBlur"/>
          <feMergeNode in="SourceGraphic"/>
        </feMerge>
      </filter>
      
      <!-- Strong Glow Filter -->
      <filter id="glowStrong">
        <feGaussianBlur stdDeviation="4" result="coloredBlur"/>
        <feMerge>
          <feMergeNode in="coloredBlur"/>
          <feMergeNode in="coloredBlur"/>
          <feMergeNode in="SourceGraphic"/>
        </feMerge>
      </filter>

      <!-- Clip Paths -->
      <clipPath id="cardClip">
        <rect x="0" y="0" width="450" height="650" rx="20" ry="20"/>
      </clipPath>
    </defs>

    <!-- BACKGROUND & BORDER -->
    <rect x="0" y="0" width="450" height="650" rx="20" fill="url(#bgGrad)" />
    <rect x="1" y="1" width="448" height="648" rx="20" fill="none" stroke="rgba(0, 243, 255, 0.3)" stroke-width="1" />

    <!-- SCANLINES (Animated) -->
    <g opacity="0.1">
      <line x1="0" y1="20" x2="450" y2="20" stroke="#fff" stroke-width="1"><animate attributeName="y1" values="0;650;0" dur="5s" repeatCount="indefinite"/><animate attributeName="y2" values="0;650;0" dur="5s" repeatCount="indefinite"/></line>
      <line x1="0" y1="100" x2="450" y2="100" stroke="#fff" stroke-width="1"><animate attributeName="y1" values="100;750;100" dur="7s" repeatCount="indefinite"/><animate attributeName="y2" values="100;750;100" dur="7s" repeatCount="indefinite"/></line>
      <line x1="0" y1="200" x2="450" y2="200" stroke="#fff" stroke-width="1"><animate attributeName="y1" values="200;850;200" dur="6s" repeatCount="indefinite"/><animate attributeName="y2" values="200;850;200" dur="6s" repeatCount="indefinite"/></line>
    </g>

    <!-- SCANNING BAR (Hero Effect) -->
    <rect x="0" y="0" width="450" height="5" fill="url(#gradCyan)" opacity="0.5" filter="url(#glow)">
      <animate attributeName="y" values="-10;660;660" dur="4s" repeatCount="indefinite" />
      <animate attributeName="opacity" values="0;0.8;0;0" dur="4s" repeatCount="indefinite" />
    </rect>

    <!-- PARTICLE SYSTEM (50+ Particles) -->
    <g id="particles" fill="#00f3ff">
      <!-- Random horizontal movers -->
      <circle cx="10" cy="50" r="1" opacity="0.6"><animate attributeName="cx" values="10;440;10" dur="15s" repeatCount="indefinite"/></circle>
      <circle cx="20" cy="150" r="1.5" fill="#ff00ff" opacity="0.5"><animate attributeName="cx" values="20;430;20" dur="12s" repeatCount="indefinite"/></circle>
      <circle cx="50" cy="300" r="1" opacity="0.7"><animate attributeName="cx" values="50;400;50" dur="18s" repeatCount="indefinite"/></circle>
      <circle cx="400" cy="100" r="2" fill="#0aff0a" opacity="0.4"><animate attributeName="cx" values="400;50;400" dur="20s" repeatCount="indefinite"/></circle>
      <circle cx="300" cy="500" r="1" opacity="0.8"><animate attributeName="cx" values="300;0;300" dur="14s" repeatCount="indefinite"/></circle>
      <circle cx="100" cy="600" r="1.5" fill="#bd00ff" opacity="0.5"><animate attributeName="cx" values="100;350;100" dur="16s" repeatCount="indefinite"/></circle>
      
      <!-- Vertical movers -->
      <circle cx="450" cy="20" r="1" opacity="0.6"><animate attributeName="cy" values="20;630;20" dur="10s" repeatCount="indefinite"/></circle>
      <circle cx="440" cy="100" r="1.5" fill="#ff00ff" opacity="0.5"><animate attributeName="cy" values="100;550;100" dur="13s" repeatCount="indefinite"/></circle>
      <circle cx="430" cy="300" r="1" opacity="0.7"><animate attributeName="cy" values="300;50;300" dur="19s" repeatCount="indefinite"/></circle>
      <circle cx="420" cy="500" r="2" fill="#0aff0a" opacity="0.4"><animate attributeName="cy" values="500;20;500" dur="11s" repeatCount="indefinite"/></circle>

      <!-- Diagonal Movers -->
      <circle cx="20" cy="20" r="1" opacity="0.8"><animate attributeName="cx" values="20;430;20" dur="25s" repeatCount="indefinite"/><animate attributeName="cy" values="20;630;20" dur="25s" repeatCount="indefinite"/></circle>
      <circle cx="430" cy="20" r="1" fill="#ff00ff" opacity="0.6"><animate attributeName="cx" values="430;20;430" dur="22s" repeatCount="indefinite"/><animate attributeName="cy" values="20;630;20" dur="22s" repeatCount="indefinite"/></circle>
      
      <!-- Tiny floating specs (Static flicker) -->
      <circle cx="225" cy="225" r="1.5" fill="#fff" filter="url(#glow)"><animate attributeName="opacity" values="0;1;0" dur="2s" repeatCount="indefinite"/></circle>
      <circle cx="100" cy="100" r="1" fill="#fff"><animate attributeName="opacity" values="0;0.8;0" dur="3s" repeatCount="indefinite"/></circle>
      <circle cx="350" cy="400" r="1" fill="#fff"><animate attributeName="opacity" values="0;0.8;0" dur="4s" repeatCount="indefinite"/></circle>
      <circle cx="50" cy="550" r="1.5" fill="#fff"><animate attributeName="opacity" values="0;1;0" dur="1.5s" repeatCount="indefinite"/></circle>
      <circle cx="400" cy="50" r="1" fill="#fff"><animate attributeName="opacity" values="0;0.8;0" dur="2.5s" repeatCount="indefinite"/></circle>
      <circle cx="250" cy="50" r="1" fill="#fff"><animate attributeName="opacity" values="0;1;0" dur="3.5s" repeatCount="indefinite"/></circle>
    </g>

    <!-- HEADER GRAPHIC -->
    <g transform="translate(0, 20)">
      <!-- Top decorative line -->
      <path d="M50,40 Q225,10 400,40" fill="none" stroke="url(#gradCyan)" stroke-width="2" filter="url(#glow)"/>
      <circle cx="225" cy="25" r="4" fill="#fff" filter="url(#glowStrong)">
        <animate attributeName="r" values="4;6;4" dur="1s" repeatCount="indefinite"/>
      </circle>
    </g>

    <!-- AVATAR SECTION -->
    <g transform="translate(225, 140)">
      <!-- Rotating Rings -->
      <circle r="80" fill="none" stroke="url(#gradCyan)" stroke-width="2" stroke-dasharray="10 5" opacity="0.5">
        <animateTransform attributeName="transform" type="rotate" from="0 0 0" to="360 0 0" dur="20s" repeatCount="indefinite"/>
      </circle>
      <circle r="70" fill="none" stroke="url(#gradPink)" stroke-width="1" stroke-dasharray="5 5" opacity="0.6">
        <animateTransform attributeName="transform" type="rotate" from="360 0 0" to="0 0 0" dur="15s" repeatCount="indefinite"/>
      </circle>
      <circle r="75" fill="none" stroke="#0aff0a" stroke-width="0.5" opacity="0.4">
        <animateTransform attributeName="transform" type="rotate" from="0 0 0" to="-360 0 0" dur="10s" repeatCount="indefinite"/>
      </circle>

      <!-- Avatar Circle (Glass) -->
      <circle r="55" fill="#000" stroke="#fff" stroke-width="2" filter="url(#glow)"/>
      
      <!-- Text Avatar (RM) -->
      <text x="0" y="15" font-family="Orbitron, sans-serif" font-weight="bold" font-size="35" fill="#fff" text-anchor="middle" filter="url(#glowStrong)">
        R.M
        <animate attributeName="opacity" values="1;0.8;1" dur="3s" repeatCount="indefinite"/>
      </text>
    </g>

    <!-- TEXT CONTENT -->
    <g transform="translate(225, 260)">
      <!-- Glitch Text Effect using two overlapping texts with clips -->
      <text x="0" y="0" font-family="Orbitron, sans-serif" font-weight="900" font-size="28" fill="#fff" text-anchor="middle" letter-spacing="3">RUBAN.M</text>
      
      <!-- Glitch Artifacts -->
      <text x="0" y="0" font-family="Orbitron, sans-serif" font-weight="900" font-size="28" fill="#00f3ff" text-anchor="middle" letter-spacing="3" opacity="0.7">
        RUBAN.M
        <animate attributeName="opacity" values="0;0;1;0" dur="5s" repeatCount="indefinite" keyTimes="0;0.9;0.92;1"/>
        <animateTransform attributeName="transform" type="translate" values="-2 0; 2 0; -2 0" dur="0.1s" repeatCount="indefinite"/>
      </text>
      <text x="0" y="0" font-family="Orbitron, sans-serif" font-weight="900" font-size="28" fill="#ff00ff" text-anchor="middle" letter-spacing="3" opacity="0.7">
        RUBAN.M
        <animate attributeName="opacity" values="0;0;1;0" dur="5s" repeatCount="indefinite" keyTimes="0;0.91;0.93;1"/>
        <animateTransform attributeName="transform" type="translate" values="2 0; -2 0; 2 0" dur="0.1s" repeatCount="indefinite"/>
      </text>

      <!-- Title -->
      <text x="0" y="25" font-family="monospace" font-size="12" fill="url(#gradCyan)" text-anchor="middle" letter-spacing="2">
        ▸ AI PROMPTER ◂
        <animate attributeName="fill" values="#00f3ff;#0aff0a;#00f3ff" dur="3s" repeatCount="indefinite"/>
      </text>
    </g>

    <!-- STATS SECTION -->
    <g transform="translate(40, 310)">
      
      <!-- Skill 1 -->
      <g transform="translate(0, 0)">
        <text x="0" y="10" font-size="10" fill="#aaa" letter-spacing="1">PROMPT ENGINEERING</text>
        <rect x="0" y="15" width="370" height="6" rx="3" fill="rgba(255,255,255,0.1)"/>
        <rect x="0" y="15" width="0" height="6" rx="3" fill="url(#gradCyan)" filter="url(#glow)">
          <animate attributeName="width" from="0" to="340" dur="1.5s" fill="freeze" calcMode="spline" keySplines="0.42 0 0.58 1"/>
        </rect>
        <text x="350" y="10" font-size="10" fill="#fff" text-anchor="end">92%</text>
      </g>

      <!-- Skill 2 -->
      <g transform="translate(0, 50)">
        <text x="0" y="10" font-size="10" fill="#aaa" letter-spacing="1">AI/ML WORKFLOWS</text>
        <rect x="0" y="15" width="370" height="6" rx="3" fill="rgba(255,255,255,0.1)"/>
        <rect x="0" y="15" width="0" height="6" rx="3" fill="url(#gradPink)" filter="url(#glow)">
          <animate attributeName="width" from="0" to="322" dur="1.5s" begin="0.2s" fill="freeze" calcMode="spline" keySplines="0.42 0 0.58 1"/>
        </rect>
        <text x="350" y="10" font-size="10" fill="#fff" text-anchor="end">87%</text>
      </g>

      <!-- Skill 3 -->
      <g transform="translate(0, 100)">
        <text x="0" y="10" font-size="10" fill="#aaa" letter-spacing="1">CREATIVE TECH</text>
        <rect x="0" y="15" width="370" height="6" rx="3" fill="rgba(255,255,255,0.1)"/>
        <rect x="0" y="15" width="0" height="6" rx="3" fill="url(#gradPink)" filter="url(#glow)">
          <animate attributeName="width" from="0" to="292" dur="1.5s" begin="0.4s" fill="freeze" calcMode="spline" keySplines="0.42 0 0.58 1"/>
        </rect>
        <text x="350" y="10" font-size="10" fill="#fff" text-anchor="end">79%</text>
      </g>

      <!-- Skill 4 -->
      <g transform="translate(0, 150)">
        <text x="0" y="10" font-size="10" fill="#aaa" letter-spacing="1">AUTOMATION</text>
        <rect x="0" y="15" width="370" height="6" rx="3" fill="rgba(255,255,255,0.1)"/>
        <rect x="0" y="15" width="0" height="6" rx="3" fill="url(#gradGreen)" filter="url(#glow)">
          <animate attributeName="width" from="0" to="351" dur="1.5s" begin="0.6s" fill="freeze" calcMode="spline" keySplines="0.42 0 0.58 1"/>
        </rect>
        <text x="350" y="10" font-size="10" fill="#fff" text-anchor="end">95%</text>
      </g>

    </g>

    <!-- BADGES -->
    <g transform="translate(225, 520)">
      <!-- Badge 1 -->
      <g transform="translate(-130, 0)">
        <rect x="-30" y="-10" width="60" height="20" rx="4" fill="rgba(0, 243, 255, 0.1)" stroke="#00f3ff" stroke-width="1"/>
        <text x="0" y="4" font-size="10" fill="#00f3ff" text-anchor="middle">Claude</text>
        <animateTransform attributeName="transform" type="translate" values="-130,0; -130,-3; -130,0" dur="3s" repeatCount="indefinite"/>
      </g>
      <!-- Badge 2 -->
      <g transform="translate(-60, 0)">
        <rect x="-30" y="-10" width="60" height="20" rx="4" fill="rgba(255, 0, 255, 0.1)" stroke="#ff00ff" stroke-width="1"/>
        <text x="0" y="4" font-size="10" fill="#ff00ff" text-anchor="middle">GPT-4</text>
        <animateTransform attributeName="transform" type="translate" values="-60,0; -60,-4; -60,0" dur="3.2s" repeatCount="indefinite"/>
      </g>
      <!-- Badge 3 -->
      <g transform="translate(10, 0)">
        <rect x="-30" y="-10" width="60" height="20" rx="4" fill="rgba(255, 0, 255, 0.1)" stroke="#ff00ff" stroke-width="1"/>
        <text x="0" y="4" font-size="10" fill="#ff00ff" text-anchor="middle">Gemini</text>
        <animateTransform attributeName="transform" type="translate" values="10,0; 10,-3; 10,0" dur="3.5s" repeatCount="indefinite"/>
      </g>
      <!-- Badge 4 -->
      <g transform="translate(80, 0)">
        <rect x="-35" y="-10" width="70" height="20" rx="4" fill="rgba(0, 255, 136, 0.1)" stroke="#00ff88" stroke-width="1"/>
        <text x="0" y="4" font-size="10" fill="#00ff88" text-anchor="middle">Open Source</text>
        <animateTransform attributeName="transform" type="translate" values="80,0; 80,-4; 80,0" dur="2.8s" repeatCount="indefinite"/>
      </g>
      <!-- Badge 5 -->
      <g transform="translate(160, 0)">
        <rect x="-30" y="-10" width="60" height="20" rx="4" fill="rgba(255, 0, 128, 0.1)" stroke="#ff0080" stroke-width="1"/>
        <text x="0" y="4" font-size="10" fill="#ff0080" text-anchor="middle">Automation</text>
        <animateTransform attributeName="transform" type="translate" values="160,0; 160,-3; 160,0" dur="3.1s" repeatCount="indefinite"/>
      </g>
    </g>

    <!-- FOOTER DATA -->
    <g transform="translate(225, 600)">
      <text x="-180" y="0" font-size="9" fill="#555" text-anchor="start">SYS.ID: <tspan fill="#00f3ff">8X-299</tspan></text>
      <text x="0" y="0" font-size="9" fill="#555" text-anchor="middle">STATUS: <tspan fill="#0aff0a">ONLINE</tspan></text>
      <text x="180" y="0" font-size="9" fill="#555" text-anchor="end">V:2.0.4</text>
    </g>

  </svg>
</a>
