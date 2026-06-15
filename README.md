<!-- ===== ORBITING DOTS on rings ===== -->
<!-- Dot on ring 1 -->
<circle r="4" fill="#0ff" filter="url(#softglow)">
  <animateMotion dur="12s" repeatCount="indefinite"><mpath href="#orbit1"/></animateMotion>
</circle>
<!-- Dot on ring 2 -->
<circle r="3" fill="#ff00ff" filter="url(#softglow)">
  <animateMotion dur="9s" repeatCount="indefinite" keyPoints="1;0" keyTimes="0;1" calcMode="linear"><mpath href="#orbit2"/></animateMotion>
</circle>
<!-- Dot on ring 3 -->
<circle r="5" fill="#bd00ff" filter="url(#pulseglow)">
  <animateMotion dur="7s" repeatCount="indefinite"><mpath href="#orbit3"/></animateMotion>
  <animate attributeName="r" values="5;7;5" dur="1s" repeatCount="indefinite"/>
</circle>
<!-- Dot on ring 6 -->
<circle r="2" fill="#ff0080" filter="url(#softglow)">
  <animateMotion dur="3s" repeatCount="indefinite"><mpath href="#orbit6"/></animateMotion>
</circle>

<defs>
  <path id="orbit1" d="M330,175 A130,130 0 1,1 329.99,175.01"/>
  <path id="orbit2" d="M315,175 A115,115 0 1,1 314.99,175.01"/>
  <path id="orbit3" d="M300,175 A100,100 0 1,1 299.99,175.01"/>
  <path id="orbit6" d="M270,175 A70,70 0 1,1 269.99,175.01"/>
</defs>

<!-- ===== AVATAR CIRCLE with animated border ===== -->
<!-- Outer glow ring -->
<circle cx="200" cy="175" r="60" fill="none" stroke="url(#grad1)" stroke-width="3" filter="url(#neon)">
  <animate attributeName="r" values="58;62;58" dur="2s" repeatCount="indefinite"/>
  <animate attributeName="stroke-opacity" values="0.7;1;0.7" dur="1.5s" repeatCount="indefinite"/>
</circle>
<!-- Inner avatar bg -->
<circle cx="200" cy="175" r="52" fill="url(#coreGrad)" opacity="0.3"/>
<!-- Avatar initials -->
<circle cx="200" cy="175" r="52" fill="#0a0520"/>
<text x="200" y="185" font-family="Orbitron,sans-serif" font-weight="700" font-size="28" fill="url(#grad1)" text-anchor="middle" filter="url(#neon)">R.M</text>

<!-- Rotating ring around avatar -->
<circle cx="200" cy="175" r="56" fill="none" stroke="#0ff" stroke-width="1" stroke-dasharray="4 4" opacity="0.6">
  <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="4s" repeatCount="indefinite"/>
</circle>
<circle cx="200" cy="175" r="58" fill="none" stroke="#ff00ff" stroke-width="0.5" stroke-dasharray="2 6" opacity="0.4">
  <animateTransform attributeName="transform" type="rotate" from="360 200 175" to="0 200 175" dur="6s" repeatCount="indefinite"/>
</circle>

<!-- ===== NAME & TITLE ===== -->
<!-- Name with typewriter-style flicker -->
<text x="200" y="268" font-family="Orbitron,sans-serif" font-weight="700" font-size="22" fill="#fff" text-anchor="middle" filter="url(#neon)" letter-spacing="3">
  RUBAN.M
  <animate attributeName="opacity" values="1;0.85;1;0.7;1;0.9;1" dur="0.3s" repeatCount="indefinite"/>
</text>
<!-- Underline animated -->
<line x1="120" y1="275" x2="280" y2="275" stroke="url(#grad1)" stroke-width="1">
  <animate attributeName="x1" values="120;160;120" dur="3s" repeatCount="indefinite"/>
  <animate attributeName="x2" values="280;240;280" dur="3s" repeatCount="indefinite"/>
</line>

<!-- Title -->
<text x="200" y="295" font-family="'Share Tech Mono',monospace" font-size="12" fill="#bd00ff" text-anchor="middle" letter-spacing="4">
  ▸ AI PROMPTER ◂
  <animate attributeName="opacity" values="1;0.6;1" dur="1.5s" repeatCount="indefinite"/>
  <animate attributeName="fill" values="#bd00ff;#0ff;#ff00ff;#bd00ff" dur="3s" repeatCount="indefinite"/>
</text>

<!-- Subtitle -->
<text x="200" y="316" font-family="'Share Tech Mono',monospace" font-size="9" fill="#0ff5" text-anchor="middle" letter-spacing="2">GITHUB.COM/RUBAN-M</text>

<!-- ===== STATUS INDICATORS ===== -->
<!-- Status dot left -->
<circle cx="90" cy="295" r="4" fill="#00ff88" filter="url(#softglow)">
  <animate attributeName="r" values="4;6;4" dur="1s" repeatCount="indefinite"/>
  <animate attributeName="fill" values="#00ff88;#ffff00;#00ff88" dur="2s" repeatCount="indefinite"/>
</circle>
<text x="100" y="299" font-family="monospace" font-size="8" fill="#00ff8899">ONLINE</text>

<!-- Status dot right -->
<circle cx="310" cy="295" r="4" fill="#ff0080" filter="url(#softglow)">
  <animate attributeName="r" values="4;6;4" dur="0.8s" repeatCount="indefinite"/>
  <animate attributeName="fill" values="#ff0080;#ff8800;#ff0080" dur="1.6s" repeatCount="indefinite"/>
</circle>
<text x="318" y="299" font-family="monospace" font-size="8" fill="#ff008099">ACTIVE</text>

<!-- ===== LAUNCH BUTTON ===== -->
<rect id="btn" x="135" y="330" width="130" height="34" rx="17" fill="url(#grad1)" filter="url(#neon)">
  <animate attributeName="width" values="130;140;130" dur="1.5s" repeatCount="indefinite"/>
  <animate attributeName="x" values="135;130;135" dur="1.5s" repeatCount="indefinite"/>
  <animate attributeName="opacity" values="0.85;1;0.85" dur="0.7s" repeatCount="indefinite"/>
</rect>
<text x="200" y="351" font-family="Orbitron,sans-serif" font-size="10" fill="#000" text-anchor="middle" font-weight="700" letter-spacing="2">LAUNCH ↗</text>

<!-- ===== BOTTOM DATA READOUTS ===== -->
<text x="30" y="380" font-family="monospace" font-size="7" fill="#0ff4" letter-spacing="1">SYS:OK</text>
<text x="80" y="380" font-family="monospace" font-size="7" fill="#ff00ff4" letter-spacing="1">AI:ON</text>
<text x="130" y="380" font-family="monospace" font-size="7" fill="#0ff4" letter-spacing="1">v2.5.1</text>
<text x="310" y="380" font-family="monospace" font-size="7" fill="#0ff4" letter-spacing="1" text-anchor="end">
  CPU:
  <animate attributeName="y" values="380;378;382;380" dur="0.5s" repeatCount="indefinite"/>
</text>
<text x="380" y="380" font-family="monospace" font-size="7" fill="#00ff884" letter-spacing="1" text-anchor="end">99%</text>

<!-- Animated binary readout bottom -->
<text x="200" y="378" font-family="monospace" font-size="6" fill="#0ff3" text-anchor="middle">
  <animate attributeName="textLength" values="0;120;0" dur="4s" repeatCount="indefinite"/>
  10110101 00110001 11001010
</text>
</svg>
</div>

<!-- INFO PANEL -->
<div class="info-box">
  <h3>// PROFILE_STATS.JSON</h3>
  
  <div class="bar-label"><span>Prompt Engineering</span><span style="color:#0ff">92%</span></div>
  <div class="bar-outer"><div class="bar-inner skill-bar-1"></div></div>
  
  <div class="bar-label"><span>AI/ML Workflows</span><span style="color:#ff00ff">87%</span></div>
  <div class="bar-outer"><div class="bar-inner skill-bar-2"></div></div>
  
  <div class="bar-label"><span>Creative Tech</span><span style="color:#bd00ff">79%</span></div>
  <div class="bar-outer"><div class="bar-inner skill-bar-3"></div></div>
  
  <div class="bar-label"><span>Automation</span><span style="color:#00ff88">95%</span></div>
  <div class="bar-outer"><div class="bar-inner skill-bar-4"></div></div>
  
  <div class="badge-row">
    <span class="badge b1">Claude</span>
    <span class="badge b2">GPT-4</span>
    <span class="badge b3">Gemini</span>
    <span class="badge b4">Open Source</span>
    <span class="badge b5">Automation</span>
  </div>
</div>

<!-- HOW TO SET THIS -->
<div class="info-box" style="margin-top:14px">
  <h3>// HOW_TO_ADD.MD</h3>
  <div class="code-block">
    <span class="c-purple">1.</span> Go to your GitHub profile → <span class="c-cyan">Create repo</span> named <span class="c-green">your-username</span><br>
    <span class="c-purple">2.</span> Add a <span class="c-cyan">README.md</span> file to the repo<br>
    <span class="c-purple">3.</span> Save this SVG as <span class="c-green">profile.svg</span><br>
    <span class="c-purple">4.</span> Upload SVG to the repo (or use GitHub Actions)<br>
    <span class="c-purple">5.</span> In README.md add:<br>
    <span class="c-pink">&lt;img src="profile.svg" width="400"/&gt;</span><br>
    <br>
    <span class="c-purple">TIP:</span> GitHub renders SVG animations <span class="c-green">natively ✓</span><br>
    <span class="c-purple">NOTE:</span> CSS animations need <span class="c-cyan">SMIL</span> (which this uses)<br>
    <span class="c-purple">TOOL:</span> Use <span class="c-pink">github-readme-stats</span> to add live stats
  </div>
</div>
</body>
</html>
