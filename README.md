<!DOCTYPE html>
<html>
<head>
<style>
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@700&display=swap');
*{margin:0;padding:0;box-sizing:border-box}
body{background:#000;display:flex;flex-direction:column;align-items:center;justify-content:flex-start;min-height:100vh;font-family:'Share Tech Mono',monospace;overflow-x:hidden;padding:20px 0 40px}
canvas{display:block}
.profile-wrap{position:relative;width:400px;height:400px;margin:0 auto}
svg.profile{width:400px;height:400px}
.info-box{margin-top:18px;background:#0a0a12;border:1px solid #0ff3;border-radius:12px;padding:16px 24px;width:400px;color:#0ff;font-size:12px;line-height:1.9;letter-spacing:1px}
.info-box h3{font-family:'Orbitron',sans-serif;font-size:13px;color:#bd00ff;letter-spacing:3px;margin-bottom:8px}
.info-box .bar-label{display:flex;justify-content:space-between;margin-bottom:2px}
.bar-outer{height:5px;background:#0ff1;border-radius:3px;margin-bottom:8px;overflow:hidden}
.bar-inner{height:100%;border-radius:3px;animation:barGrow 2s cubic-bezier(.4,0,.2,1) forwards}
@keyframes barGrow{from{width:0}to{width:var(--w)}}
.skill-bar-1{background:linear-gradient(90deg,#0ff,#bd00ff);--w:92%}
.skill-bar-2{background:linear-gradient(90deg,#ff00ff,#0ff);--w:87%}
.skill-bar-3{background:linear-gradient(90deg,#bd00ff,#ff0080);--w:79%}
.skill-bar-4{background:linear-gradient(90deg,#00ff88,#0ff);--w:95%}
.badge-row{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px}
.badge{padding:3px 10px;border-radius:20px;font-size:10px;letter-spacing:1px;animation:badgePop .4s ease both}
@keyframes badgePop{from{transform:scale(0);opacity:0}to{transform:scale(1);opacity:1}}
.b1{background:#0ff2;border:1px solid #0ff;color:#0ff;animation-delay:.2s}
.b2{background:#bd00ff22;border:1px solid #bd00ff;color:#bd00ff;animation-delay:.35s}
.b3{background:#ff00ff22;border:1px solid #ff00ff;color:#ff00ff;animation-delay:.5s}
.b4{background:#00ff8822;border:1px solid #00ff88;color:#00ff88;animation-delay:.65s}
.b5{background:#ff008022;border:1px solid #ff0080;color:#ff0080;animation-delay:.8s}
.code-block{margin-top:16px;background:#060610;border:1px solid #0ff2;border-radius:8px;padding:12px 16px;font-size:11px;color:#0ff8;line-height:1.8}
.code-block .c-purple{color:#bd00ff}.code-block .c-cyan{color:#0ff}.code-block .c-green{color:#00ff88}.code-block .c-pink{color:#ff00ff}
</style>
</head>
<body>
<div class="profile-wrap">
<svg class="profile" viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg">
<defs>
  <!-- Matrix rain pattern -->
  <pattern id="matrix" x="0" y="0" width="20" height="400" patternUnits="userSpaceOnUse">
    <text x="2" y="20" font-size="10" fill="#00ff0022" font-family="monospace">0</text>
    <text x="2" y="40" font-size="10" fill="#00ff0015" font-family="monospace">1</text>
    <text x="2" y="60" font-size="10" fill="#00ff001a" font-family="monospace">0</text>
    <text x="2" y="80" font-size="10" fill="#00ff0012" font-family="monospace">1</text>
  </pattern>
  
  <!-- Animated gradient 1 -->
  <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="100%">
    <stop offset="0%"><animate attributeName="stop-color" values="#ff0000;#ff00ff;#0000ff;#00ffff;#00ff00;#ffff00;#ff0000" dur="3s" repeatCount="indefinite"/></stop>
    <stop offset="100%"><animate attributeName="stop-color" values="#00ffff;#00ff00;#ffff00;#ff0000;#ff00ff;#0000ff;#00ffff" dur="3s" repeatCount="indefinite"/></stop>
  </linearGradient>
  
  <!-- Animated gradient 2 -->
  <linearGradient id="grad2" x1="100%" y1="0%" x2="0%" y2="100%">
    <stop offset="0%"><animate attributeName="stop-color" values="#bd00ff;#0ff;#ff00ff;#bd00ff" dur="2s" repeatCount="indefinite"/></stop>
    <stop offset="100%"><animate attributeName="stop-color" values="#0ff;#ff00ff;#bd00ff;#0ff" dur="2s" repeatCount="indefinite"/></stop>
  </linearGradient>
  
  <!-- Neon glow filter -->
  <filter id="neon" x="-30%" y="-30%" width="160%" height="160%">
    <feGaussianBlur stdDeviation="3" result="blur"/>
    <feMerge><feMergeNode in="blur"/><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
  </filter>
  
  <!-- Soft glow -->
  <filter id="softglow" x="-20%" y="-20%" width="140%" height="140%">
    <feGaussianBlur stdDeviation="2" result="blur"/>
    <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
  </filter>
  
  <!-- Pulse glow -->
  <filter id="pulseglow" x="-40%" y="-40%" width="180%" height="180%">
    <feGaussianBlur stdDeviation="5" result="blur"/>
    <feMerge><feMergeNode in="blur"/><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
  </filter>
  
  <!-- Clip circle for avatar -->
  <clipPath id="avatarClip"><circle cx="200" cy="175" r="52"/></clipPath>
  
  <!-- Radial gradient for core -->
  <radialGradient id="coreGrad" cx="50%" cy="50%" r="50%">
    <stop offset="0%"><animate attributeName="stop-color" values="#ffffff;#bd00ff;#0ff;#ffffff" dur="2s" repeatCount="indefinite"/></stop>
    <stop offset="60%"><animate attributeName="stop-color" values="#bd00ff;#0ff;#ff00ff;#bd00ff" dur="2s" repeatCount="indefinite"/></stop>
    <stop offset="100%" stop-color="transparent"/>
  </radialGradient>
</defs>

<!-- ===== BACKGROUND LAYER ===== -->
<rect width="400" height="400" rx="20" fill="#000913"/>

<!-- Matrix-style background -->
<rect width="400" height="400" rx="20" fill="url(#matrix)" opacity="0.4"/>

<!-- Hex grid bg -->
<g opacity="0.06">
  <polygon points="40,20 60,20 70,37 60,54 40,54 30,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="80,20 100,20 110,37 100,54 80,54 70,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="120,20 140,20 150,37 140,54 120,54 110,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="160,20 180,20 190,37 180,54 160,54 150,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="200,20 220,20 230,37 220,54 200,54 190,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="240,20 260,20 270,37 260,54 240,54 230,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="280,20 300,20 310,37 300,54 280,54 270,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="320,20 340,20 350,37 340,54 320,54 310,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="360,20 380,20 390,37 380,54 360,54 350,37" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="60,54 80,54 90,71 80,88 60,88 50,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="100,54 120,54 130,71 120,88 100,88 90,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="140,54 160,54 170,71 160,88 140,88 130,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="180,54 200,54 210,71 200,88 180,88 170,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="220,54 240,54 250,71 240,88 220,88 210,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="260,54 280,54 290,71 280,88 260,88 250,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="300,54 320,54 330,71 320,88 300,88 290,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="340,54 360,54 370,71 360,88 340,88 330,71" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="40,88 60,88 70,105 60,122 40,122 30,105" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="80,88 100,88 110,105 100,122 80,122 70,105" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="120,88 140,88 150,105 140,122 120,122 110,105" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="340,88 360,88 370,105 360,122 340,122 330,105" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="320,88 340,88 350,105 340,122 320,122 310,105" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="60,122 80,122 90,139 80,156 60,156 50,139" fill="none" stroke="#ff00ff" stroke-width="0.5"/>
  <polygon points="300,122 320,122 330,139 320,156 300,156 290,139" fill="none" stroke="#ff00ff" stroke-width="0.5"/>
  <polygon points="40,156 60,156 70,173 60,190 40,190 30,173" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="340,156 360,156 370,173 360,190 340,190 330,173" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="40,190 60,190 70,207 60,224 40,224 30,207" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="340,190 360,190 370,207 360,224 340,224 330,207" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="40,224 60,224 70,241 60,258 40,258 30,241" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="340,224 360,224 370,241 360,258 340,258 330,241" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="60,258 80,258 90,275 80,292 60,292 50,275" fill="none" stroke="#ff00ff" stroke-width="0.5"/>
  <polygon points="300,258 320,258 330,275 320,292 300,292 290,275" fill="none" stroke="#ff00ff" stroke-width="0.5"/>
  <polygon points="80,292 100,292 110,309 100,326 80,326 70,309" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="120,292 140,292 150,309 140,326 120,326 110,309" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="260,292 280,292 290,309 280,326 260,326 250,309" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="280,292 300,292 310,309 300,326 280,326 270,309" fill="none" stroke="#0ff" stroke-width="0.5"/>
  <polygon points="100,326 120,326 130,343 120,360 100,360 90,343" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="140,326 160,326 170,343 160,360 140,360 130,343" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="180,326 200,326 210,343 200,360 180,360 170,343" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="220,326 240,326 250,343 240,360 220,360 210,343" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
  <polygon points="240,326 260,326 270,343 260,360 240,360 230,343" fill="none" stroke="#bd00ff" stroke-width="0.5"/>
</g>

<!-- ===== PARTICLE FIELD (40 particles) ===== -->
<g id="particles">
  <circle cx="20" cy="30" r="1.5" fill="#0ff"><animate attributeName="cy" values="30;370;30" dur="4.2s" repeatCount="indefinite"/><animate attributeName="opacity" values="1;0.2;1" dur="4.2s" repeatCount="indefinite"/></circle>
  <circle cx="380" cy="30" r="1" fill="#ff00ff"><animate attributeName="cy" values="30;370;30" dur="5.1s" repeatCount="indefinite"/><animate attributeName="opacity" values="0.8;0.1;0.8" dur="5.1s" repeatCount="indefinite"/></circle>
  <circle cx="60" cy="350" r="1.5" fill="#bd00ff"><animate attributeName="cy" values="350;10;350" dur="6.3s" repeatCount="indefinite"/><animate attributeName="cx" values="60;80;60" dur="6.3s" repeatCount="indefinite"/></circle>
  <circle cx="340" cy="350" r="1" fill="#00ff88"><animate attributeName="cy" values="350;10;350" dur="7.1s" repeatCount="indefinite"/></circle>
  <circle cx="100" cy="20" r="2" fill="#ffff00"><animate attributeName="cy" values="20;380;20" dur="3.8s" repeatCount="indefinite"/><animate attributeName="opacity" values="1;0;1" dur="3.8s" repeatCount="indefinite"/></circle>
  <circle cx="300" cy="380" r="1.5" fill="#ff0080"><animate attributeName="cy" values="380;20;380" dur="5.5s" repeatCount="indefinite"/></circle>
  <circle cx="150" cy="10" r="1" fill="#0ff"><animate attributeName="cy" values="10;390;10" dur="4.7s" repeatCount="indefinite"/><animate attributeName="cx" values="150;170;150" dur="9.4s" repeatCount="indefinite"/></circle>
  <circle cx="250" cy="390" r="1.5" fill="#ff00ff"><animate attributeName="cy" values="390;10;390" dur="6.1s" repeatCount="indefinite"/></circle>
  <circle cx="10" cy="200" r="1" fill="#00ff88"><animate attributeName="cx" values="10;390;10" dur="8s" repeatCount="indefinite"/></circle>
  <circle cx="390" cy="200" r="1" fill="#ffff00"><animate attributeName="cx" values="390;10;390" dur="9.2s" repeatCount="indefinite"/></circle>
  <circle cx="50" cy="100" r="1.5" fill="#bd00ff"><animate attributeName="cy" values="100;300;100" dur="4s" repeatCount="indefinite"/><animate attributeName="opacity" values="0.9;0.2;0.9" dur="4s" repeatCount="indefinite"/></circle>
  <circle cx="350" cy="300" r="1" fill="#0ff"><animate attributeName="cy" values="300;100;300" dur="5.3s" repeatCount="indefinite"/></circle>
  <circle cx="30" cy="150" r="2" fill="#ff0080"><animate attributeName="cy" values="150;250;150" dur="3s" repeatCount="indefinite"/><animate attributeName="cx" values="30;50;30" dur="6s" repeatCount="indefinite"/></circle>
  <circle cx="370" cy="250" r="1.5" fill="#00ff88"><animate attributeName="cy" values="250;150;250" dur="4.5s" repeatCount="indefinite"/></circle>
  <circle cx="180" cy="5" r="1" fill="#ffff00"><animate attributeName="cy" values="5;395;5" dur="7.2s" repeatCount="indefinite"/></circle>
  <circle cx="220" cy="395" r="1.5" fill="#ff00ff"><animate attributeName="cy" values="395;5;395" dur="6.8s" repeatCount="indefinite"/></circle>
  <circle cx="90" cy="280" r="1" fill="#0ff"><animate attributeName="cy" values="280;60;280" dur="5.7s" repeatCount="indefinite"/><animate attributeName="opacity" values="0.7;0.1;0.7" dur="5.7s" repeatCount="indefinite"/></circle>
  <circle cx="310" cy="120" r="1" fill="#bd00ff"><animate attributeName="cy" values="120;280;120" dur="4.9s" repeatCount="indefinite"/></circle>
  <circle cx="120" cy="340" r="2" fill="#ff0080"><animate attributeName="cy" values="340;40;340" dur="6.5s" repeatCount="indefinite"/></circle>
  <circle cx="280" cy="60" r="1" fill="#00ff88"><animate attributeName="cy" values="60;340;60" dur="5.2s" repeatCount="indefinite"/></circle>
  <!-- 20 more diagonal particles -->
  <circle cx="15" cy="15" r="1" fill="#0ff"><animate attributeName="cx" values="15;385;15" dur="10s" repeatCount="indefinite"/><animate attributeName="cy" values="15;385;15" dur="10s" repeatCount="indefinite"/><animate attributeName="opacity" values="1;0;1" dur="5s" repeatCount="indefinite"/></circle>
  <circle cx="385" cy="15" r="1" fill="#ff00ff"><animate attributeName="cx" values="385;15;385" dur="11s" repeatCount="indefinite"/><animate attributeName="cy" values="15;385;15" dur="11s" repeatCount="indefinite"/></circle>
  <circle cx="15" cy="385" r="1" fill="#bd00ff"><animate attributeName="cx" values="15;385;15" dur="8s" repeatCount="indefinite"/><animate attributeName="cy" values="385;15;385" dur="8s" repeatCount="indefinite"/></circle>
  <circle cx="385" cy="385" r="1.5" fill="#ffff00"><animate attributeName="cx" values="385;15;385" dur="9s" repeatCount="indefinite"/><animate attributeName="cy" values="385;15;385" dur="9s" repeatCount="indefinite"/></circle>
  <circle cx="200" cy="15" r="1" fill="#00ff88"><animate attributeName="cx" values="200;380;200" dur="12s" repeatCount="indefinite"/><animate attributeName="cy" values="15;100;15" dur="6s" repeatCount="indefinite"/></circle>
  <circle cx="40" cy="200" r="1" fill="#ff0080"><animate attributeName="cy" values="200;380;200;20;200" dur="8s" repeatCount="indefinite"/><animate attributeName="opacity" values="0.6;1;0.6" dur="4s" repeatCount="indefinite"/></circle>
  <circle cx="360" cy="180" r="1" fill="#0ff"><animate attributeName="cy" values="180;360;180;20;180" dur="9s" repeatCount="indefinite"/></circle>
  <circle cx="75" cy="375" r="1.5" fill="#ff00ff"><animate attributeName="cy" values="375;25;375" dur="7.4s" repeatCount="indefinite"/><animate attributeName="cx" values="75;110;75" dur="14.8s" repeatCount="indefinite"/></circle>
  <circle cx="325" cy="25" r="1" fill="#bd00ff"><animate attributeName="cy" values="25;375;25" dur="8.6s" repeatCount="indefinite"/></circle>
  <circle cx="170" cy="370" r="1" fill="#ffff00"><animate attributeName="cy" values="370;30;370" dur="5.9s" repeatCount="indefinite"/></circle>
  <circle cx="230" cy="30" r="2" fill="#00ff88"><animate attributeName="cy" values="30;370;30" dur="6.4s" repeatCount="indefinite"/><animate attributeName="opacity" values="1;0.3;1" dur="3.2s" repeatCount="indefinite"/></circle>
  <circle cx="130" cy="55" r="1" fill="#0ff"><animate attributeName="cy" values="55;345;55" dur="7.7s" repeatCount="indefinite"/></circle>
  <circle cx="270" cy="345" r="1.5" fill="#ff0080"><animate attributeName="cy" values="345;55;345" dur="6.9s" repeatCount="indefinite"/></circle>
  <circle cx="55" cy="260" r="1" fill="#bd00ff"><animate attributeName="cy" values="260;140;260" dur="4.4s" repeatCount="indefinite"/><animate attributeName="cx" values="55;30;55" dur="8.8s" repeatCount="indefinite"/></circle>
  <circle cx="345" cy="140" r="1" fill="#ff00ff"><animate attributeName="cy" values="140;260;140" dur="5.6s" repeatCount="indefinite"/></circle>
  <circle cx="160" cy="395" r="1.5" fill="#0ff"><animate attributeName="cy" values="395;5;395" dur="8.1s" repeatCount="indefinite"/></circle>
  <circle cx="240" cy="5" r="1" fill="#ffff00"><animate attributeName="cy" values="5;395;5" dur="7.3s" repeatCount="indefinite"/></circle>
  <circle cx="35" cy="335" r="1" fill="#00ff88"><animate attributeName="cy" values="335;65;335" dur="9.5s" repeatCount="indefinite"/></circle>
  <circle cx="365" cy="65" r="1.5" fill="#ff0080"><animate attributeName="cy" values="65;335;65" dur="8.3s" repeatCount="indefinite"/></circle>
  <circle cx="200" cy="200" r="1" fill="#ffffff"><animate attributeName="r" values="1;3;1" dur="2s" repeatCount="indefinite"/><animate attributeName="opacity" values="0.3;1;0.3" dur="2s" repeatCount="indefinite"/></circle>
</g>

<!-- ===== BORDER BOX with animated stroke ===== -->
<rect x="12" y="12" width="376" height="376" rx="22" fill="rgba(0,5,20,0.85)" stroke="url(#grad1)" stroke-width="3">
  <animate attributeName="stroke-opacity" values="0.6;1;0.6" dur="0.8s" repeatCount="indefinite"/>
</rect>
<!-- Secondary border -->
<rect x="18" y="18" width="364" height="364" rx="18" fill="none" stroke="url(#grad2)" stroke-width="1" stroke-dasharray="8 4">
  <animateTransform attributeName="transform" type="rotate" from="0 200 200" to="360 200 200" dur="20s" repeatCount="indefinite"/>
</rect>

<!-- ===== CORNER DECORATIONS ===== -->
<!-- TL corner -->
<path d="M12,42 L12,22 Q12,12 22,12 L42,12" fill="none" stroke="#0ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.2s" repeatCount="indefinite"/></path>
<!-- TR corner -->
<path d="M358,12 L378,12 Q388,12 388,22 L388,42" fill="none" stroke="#0ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.4s" repeatCount="indefinite"/></path>
<!-- BL corner -->
<path d="M12,358 L12,378 Q12,388 22,388 L42,388" fill="none" stroke="#bd00ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.1s" repeatCount="indefinite"/></path>
<!-- BR corner -->
<path d="M358,388 L378,388 Q388,388 388,378 L388,358" fill="none" stroke="#bd00ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.6s" repeatCount="indefinite"/></path>

<!-- Corner dots -->
<circle cx="12" cy="12" r="3" fill="#0ff" filter="url(#softglow)"><animate attributeName="r" values="3;5;3" dur="1s" repeatCount="indefinite"/></circle>
<circle cx="388" cy="12" r="3" fill="#ff00ff" filter="url(#softglow)"><animate attributeName="r" values="3;5;3" dur="1.3s" repeatCount="indefinite"/></circle>
<circle cx="12" cy="388" r="3" fill="#bd00ff" filter="url(#softglow)"><animate attributeName="r" values="3;5;3" dur="0.9s" repeatCount="indefinite"/></circle>
<circle cx="388" cy="388" r="3" fill="#00ff88" filter="url(#softglow)"><animate attributeName="r" values="3;5;3" dur="1.1s" repeatCount="indefinite"/></circle>

<!-- Mid-edge markers -->
<circle cx="200" cy="12" r="2" fill="#0ff"><animate attributeName="r" values="2;4;2" dur="1.5s" repeatCount="indefinite"/></circle>
<circle cx="200" cy="388" r="2" fill="#0ff"><animate attributeName="r" values="2;4;2" dur="1.7s" repeatCount="indefinite"/></circle>
<circle cx="12" cy="200" r="2" fill="#ff00ff"><animate attributeName="r" values="2;4;2" dur="1.3s" repeatCount="indefinite"/></circle>
<circle cx="388" cy="200" r="2" fill="#ff00ff"><animate attributeName="r" values="2;4;2" dur="1.9s" repeatCount="indefinite"/></circle>

<!-- ===== SCANNING LINE ===== -->
<line x1="18" y1="80" x2="382" y2="80" stroke="#0ff" stroke-width="1" opacity="0.3">
  <animate attributeName="y1" values="18;382;18" dur="3s" repeatCount="indefinite"/>
  <animate attributeName="y2" values="18;382;18" dur="3s" repeatCount="indefinite"/>
  <animate attributeName="opacity" values="0.4;0;0.4" dur="3s" repeatCount="indefinite"/>
</line>
<rect x="18" y="76" width="364" height="8" fill="url(#grad2)" opacity="0.04">
  <animate attributeName="y" values="18;378;18" dur="3s" repeatCount="indefinite"/>
  <animate attributeName="opacity" values="0.06;0;0.06" dur="3s" repeatCount="indefinite"/>
</rect>

<!-- ===== ORBITING RINGS (7 rings) ===== -->
<!-- Ring 1 -->
<ellipse cx="200" cy="175" rx="130" ry="130" fill="none" stroke="#0ff" stroke-width="0.8" stroke-dasharray="15 8" opacity="0.5">
  <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="12s" repeatCount="indefinite"/>
</ellipse>
<!-- Ring 2 -->
<ellipse cx="200" cy="175" rx="115" ry="115" fill="none" stroke="#ff00ff" stroke-width="1" stroke-dasharray="6 4" opacity="0.6">
  <animateTransform attributeName="transform" type="rotate" from="360 200 175" to="0 200 175" dur="9s" repeatCount="indefinite"/>
</ellipse>
<!-- Ring 3 -->
<ellipse cx="200" cy="175" rx="100" ry="100" fill="none" stroke="#bd00ff" stroke-width="1.5" stroke-dasharray="20 5" opacity="0.5">
  <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="7s" repeatCount="indefinite"/>
</ellipse>
<!-- Ring 4 - tilted ellipse -->
<ellipse cx="200" cy="175" rx="88" ry="40" fill="none" stroke="#00ff88" stroke-width="1" stroke-dasharray="8 6" opacity="0.5">
  <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="5s" repeatCount="indefinite"/>
</ellipse>
<!-- Ring 5 - tilted ellipse other axis -->
<ellipse cx="200" cy="175" rx="40" ry="88" fill="none" stroke="#ffff00" stroke-width="0.8" stroke-dasharray="4 4" opacity="0.4">
  <animateTransform attributeName="transform" type="rotate" from="360 200 175" to="0 200 175" dur="6s" repeatCount="indefinite"/>
</ellipse>
<!-- Ring 6 - fast small -->
<ellipse cx="200" cy="175" rx="70" ry="70" fill="none" stroke="#ff0080" stroke-width="0.8" stroke-dasharray="3 3" opacity="0.4">
  <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="3s" repeatCount="indefinite"/>
</ellipse>
<!-- Ring 7 - outer slow -->
<ellipse cx="200" cy="175" rx="140" ry="80" fill="none" stroke="#0ff" stroke-width="0.5" stroke-dasharray="30 10" opacity="0.3">
  <animateTransform attributeName="transform" type="rotate" from="45 200 175" to="405 200 175" dur="20s" repeatCount="indefinite"/>
</ellipse>

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
