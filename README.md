<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ruban.M | Profile Animation</title>
    <style>
        /* Import Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@700&display=swap');

        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #000;
            /* GitHub readme background preview fix */
            background-image: radial-gradient(circle at center, #0a0a12 0%, #000000 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            font-family: 'Share Tech Mono', monospace;
            overflow-x: hidden;
            padding: 20px;
        }

        /* Main Container for SVG */
        .profile-wrap {
            position: relative;
            width: 400px;
            height: 400px;
            margin: 0 auto;
            /* Ensure it scales down on smaller screens */
            max-width: 100%;
        }

        svg.profile {
            width: 100%;
            height: auto;
            display: block;
            /* Subtle drop shadow for the card */
            filter: drop-shadow(0 0 15px rgba(0, 255, 255, 0.1));
        }

        /* Clickable Cursor for the SVG Button Area */
        #launch-btn-group {
            cursor: pointer;
            transition: filter 0.3s ease;
        }

        #launch-btn-group:hover {
            filter: brightness(1.2);
        }

        /* Info Box Styling */
        .info-box {
            margin-top: 24px;
            background: rgba(10, 10, 18, 0.8);
            border: 1px solid rgba(0, 255, 255, 0.2);
            backdrop-filter: blur(5px);
            border-radius: 12px;
            padding: 20px 24px;
            width: 100%;
            max-width: 400px;
            color: #0ff;
            font-size: 12px;
            line-height: 1.9;
            letter-spacing: 1px;
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5);
        }

        .info-box h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 14px;
            color: #bd00ff;
            letter-spacing: 2px;
            margin-bottom: 12px;
            border-bottom: 1px solid rgba(189, 0, 255, 0.3);
            padding-bottom: 8px;
        }

        .bar-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 4px;
            font-weight: bold;
        }

        .bar-outer {
            height: 6px;
            background: rgba(0, 255, 255, 0.1);
            border-radius: 3px;
            margin-bottom: 12px;
            overflow: hidden;
            border: 1px solid rgba(0, 255, 255, 0.1);
        }

        .bar-inner {
            height: 100%;
            border-radius: 3px;
            /* Animation defined in CSS variables per element */
            animation: barGrow 2s cubic-bezier(.4, 0, .2, 1) forwards;
            transform-origin: left;
        }

        @keyframes barGrow {
            from { width: 0; }
            to { width: var(--w); }
        }

        /* Skill Bars Configuration */
        .skill-bar-1 { background: linear-gradient(90deg, #0ff, #bd00ff); --w: 92%; }
        .skill-bar-2 { background: linear-gradient(90deg, #ff00ff, #0ff); --w: 87%; }
        .skill-bar-3 { background: linear-gradient(90deg, #bd00ff, #ff0080); --w: 79%; }
        .skill-bar-4 { background: linear-gradient(90deg, #00ff88, #0ff); --w: 95%; }

        /* Badges */
        .badge-row {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            margin-top: 16px;
        }

        .badge {
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 10px;
            letter-spacing: 1px;
            animation: badgePop .5s ease both;
            font-weight: bold;
        }

        @keyframes badgePop {
            from { transform: scale(0); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .b1 { background: rgba(0, 255, 255, 0.1); border: 1px solid #0ff; color: #0ff; animation-delay: 0.2s; }
        .b2 { background: rgba(189, 0, 255, 0.1); border: 1px solid #bd00ff; color: #bd00ff; animation-delay: 0.35s; }
        .b3 { background: rgba(255, 0, 255, 0.1); border: 1px solid #ff00ff; color: #ff00ff; animation-delay: 0.5s; }
        .b4 { background: rgba(0, 255, 136, 0.1); border: 1px solid #00ff88; color: #00ff88; animation-delay: 0.65s; }
        .b5 { background: rgba(255, 0, 128, 0.1); border: 1px solid #ff0080; color: #ff0080; animation-delay: 0.8s; }

        /* Code Block Decoration */
        .code-block {
            margin-top: 16px;
            background: rgba(6, 6, 16, 0.9);
            border: 1px solid rgba(0, 255, 255, 0.15);
            border-radius: 6px;
            padding: 12px 16px;
            font-size: 11px;
            color: rgba(0, 255, 255, 0.8);
            line-height: 1.6;
            position: relative;
        }
        
        .code-block::before {
            content: "TERMINAL";
            position: absolute;
            top: -8px;
            left: 10px;
            background: #0a0a12;
            padding: 0 5px;
            font-size: 9px;
            color: #555;
        }

        .c-purple { color: #bd00ff; }
        .c-cyan { color: #0ff; }
        .c-green { color: #00ff88; }
        .c-pink { color: #ff00ff; }

    </style>
</head>
<body>

    <!-- Profile Animation Card -->
    <div class="profile-wrap">
        <!-- 
           I added an ID 'launch-btn-group' to the group containing the button.
           The JavaScript listens for clicks on this specific group.
        -->
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
                
                <!-- Radial gradient for core -->
                <radialGradient id="coreGrad" cx="50%" cy="50%" r="50%">
                    <stop offset="0%"><animate attributeName="stop-color" values="#ffffff;#bd00ff;#0ff;#ffffff" dur="2s" repeatCount="indefinite"/></stop>
                    <stop offset="60%"><animate attributeName="stop-color" values="#bd00ff;#0ff;#ff00ff;#bd00ff" dur="2s" repeatCount="indefinite"/></stop>
                    <stop offset="100%" stop-color="transparent"/>
                </radialGradient>
            </defs>

            <!-- BACKGROUND LAYER -->
            <rect width="400" height="400" rx="20" fill="#000913"/>
            <rect width="400" height="400" rx="20" fill="url(#matrix)" opacity="0.4"/>

            <!-- Hex grid bg (Simplified for performance) -->
            <g opacity="0.06" stroke="#0ff" stroke-width="0.5" fill="none">
                <path d="M40,20 L60,20 L70,37 L60,54 L40,54 L30,37 Z M80,20 L100,20 L110,37 L100,54 L80,54 L70,37 Z M120,20 L140,20 L150,37 L140,54 L120,54 L110,37 Z"/>
                <path d="M160,20 L180,20 L190,37 L180,54 L160,54 L150,37 Z M200,20 L220,20 L230,37 L220,54 L200,54 L190,37 Z"/>
                <path d="M240,20 L260,20 L270,37 L260,54 L240,54 L230,37 Z M280,20 L300,20 L310,37 L300,54 L280,54 L270,37 Z"/>
                <path d="M320,20 L340,20 L350,37 L340,54 L320,54 L310,37 Z M360,20 L380,20 L390,37 L380,54 L360,54 L350,37 Z"/>
                <!-- Just a representative sample of the grid to keep code clean -->
            </g>

            <!-- PARTICLE FIELD -->
            <g id="particles">
                <circle cx="20" cy="30" r="1.5" fill="#0ff"><animate attributeName="cy" values="30;370;30" dur="4.2s" repeatCount="indefinite"/><animate attributeName="opacity" values="1;0.2;1" dur="4.2s" repeatCount="indefinite"/></circle>
                <circle cx="380" cy="30" r="1" fill="#ff00ff"><animate attributeName="cy" values="30;370;30" dur="5.1s" repeatCount="indefinite"/></circle>
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
                <!-- Additional particles omitted for brevity, functionality remains -->
            </g>

            <!-- BORDER BOX -->
            <rect x="12" y="12" width="376" height="376" rx="22" fill="rgba(0,5,20,0.85)" stroke="url(#grad1)" stroke-width="3">
                <animate attributeName="stroke-opacity" values="0.6;1;0.6" dur="0.8s" repeatCount="indefinite"/>
            </rect>
            <rect x="18" y="18" width="364" height="364" rx="18" fill="none" stroke="url(#grad2)" stroke-width="1" stroke-dasharray="8 4">
                <animateTransform attributeName="transform" type="rotate" from="0 200 200" to="360 200 200" dur="20s" repeatCount="indefinite"/>
            </rect>

            <!-- CORNER DECORATIONS -->
            <path d="M12,42 L12,22 Q12,12 22,12 L42,12" fill="none" stroke="#0ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.2s" repeatCount="indefinite"/></path>
            <path d="M358,12 L378,12 Q388,12 388,22 L388,42" fill="none" stroke="#0ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.4s" repeatCount="indefinite"/></path>
            <path d="M12,358 L12,378 Q12,388 22,388 L42,388" fill="none" stroke="#bd00ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.1s" repeatCount="indefinite"/></path>
            <path d="M358,388 L378,388 Q388,388 388,378 L388,358" fill="none" stroke="#bd00ff" stroke-width="2" filter="url(#softglow)"><animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="1.6s" repeatCount="indefinite"/></path>

            <!-- SCANNING LINE -->
            <line x1="18" y1="80" x2="382" y2="80" stroke="#0ff" stroke-width="1" opacity="0.3">
                <animate attributeName="y1" values="18;382;18" dur="3s" repeatCount="indefinite"/>
                <animate attributeName="y2" values="18;382;18" dur="3s" repeatCount="indefinite"/>
                <animate attributeName="opacity" values="0.4;0;0.4" dur="3s" repeatCount="indefinite"/>
            </line>

            <!-- ORBITING RINGS -->
            <ellipse cx="200" cy="175" rx="130" ry="130" fill="none" stroke="#0ff" stroke-width="0.8" stroke-dasharray="15 8" opacity="0.5">
                <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="12s" repeatCount="indefinite"/>
            </ellipse>
            <ellipse cx="200" cy="175" rx="115" ry="115" fill="none" stroke="#ff00ff" stroke-width="1" stroke-dasharray="6 4" opacity="0.6">
                <animateTransform attributeName="transform" type="rotate" from="360 200 175" to="0 200 175" dur="9s" repeatCount="indefinite"/>
            </ellipse>
            <ellipse cx="200" cy="175" rx="100" ry="100" fill="none" stroke="#bd00ff" stroke-width="1.5" stroke-dasharray="20 5" opacity="0.5">
                <animateTransform attributeName="transform" type="rotate" from="0 200 175" to="360 200 175" dur="7s" repeatCount="indefinite"/>
            </ellipse>
            <ellipse cx="200" cy="175" rx="40" ry="88" fill="none" stroke="#ffff00" stroke-width="0.8" stroke-dasharray="4 4" opacity="0.4">
                <animateTransform attributeName="transform" type="rotate" from="360 200 175" to="0 200 175" dur="6s" repeatCount="indefinite"/>
            </ellipse>

            <!-- AVATAR SECTION -->
            <circle cx="200" cy="175" r="60" fill="none" stroke="url(#grad1)" stroke-width="3" filter="url(#neon)">
                <animate attributeName="r" values="58;62;58" dur="2s" repeatCount="indefinite"/>
                <animate attributeName="stroke-opacity" values="0.7;1;0.7" dur="1.5s" repeatCount="indefinite"/>
            </circle>
            <circle cx="200" cy="175" r="52" fill="#0a0520"/>
            <text x="200" y="185" font-family="Orbitron,sans-serif" font-weight="700" font-size="28" fill="url(#grad1)" text-anchor="middle" filter="url(#neon)">R.M</text>

            <!-- TEXT INFO -->
            <text x="200" y="268" font-family="Orbitron,sans-serif" font-weight="700" font-size="22" fill="#fff" text-anchor="middle" filter="url(#neon)" letter-spacing="3">RUBAN.M</text>
            <line x1="120" y1="275" x2="280" y2="275" stroke="url(#grad1)" stroke-width="1">
                <animate attributeName="x1" values="120;160;120" dur="3s" repeatCount="indefinite"/>
                <animate attributeName="x2" values="280;240;280" dur="3s" repeatCount="indefinite"/>
            </line>
            <text x="200" y="295" font-family="'Share Tech Mono',monospace" font-size="12" fill="#bd00ff" text-anchor="middle" letter-spacing="4">
                ▸ AI PROMPTER ◂
                <animate attributeName="opacity" values="1;0.6;1" dur="1.5s" repeatCount="indefinite"/>
                <animate attributeName="fill" values="#bd00ff;#0ff;#ff00ff;#bd00ff" dur="3s" repeatCount="indefinite"/>
            </text>

            <!-- LAUNCH BUTTON (Wrapped in a group for click handling) -->
            <g id="launch-btn-group" role="button" aria-label="Launch Website">
                <rect id="btn" x="135" y="330" width="130" height="34" rx="17" fill="url(#grad1)" filter="url(#neon)">
                    <animate attributeName="width" values="130;140;130" dur="1.5s" repeatCount="indefinite"/>
                    <animate attributeName="x" values="135;130;135" dur="1.5s" repeatCount="indefinite"/>
                    <animate attributeName="opacity" values="0.85;1;0.85" dur="0.7s" repeatCount="indefinite"/>
                </rect>
                <text x="200" y="351" font-family="Orbitron,sans-serif" font-size="10" fill="#000" text-anchor="middle" font-weight="700" letter-spacing="2">LAUNCH ↗</text>
            </g>

            <!-- BOTTOM DATA READOUTS -->
            <text x="30" y="380" font-family="monospace" font-size="7" fill="#0ff4" letter-spacing="1">SYS:OK</text>
            <text x="380" y="380" font-family="monospace" font-size="7" fill="#0ff4" letter-spacing="1" text-anchor="end">99%</text>
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

    <div class="info-box code-block">
        <span class="c-purple">const</span> status = <span class="c-cyan">"Ready"</span>;<br>
        <span class="c-purple">if</span> (clicked) {<br>
        &nbsp;&nbsp;window.open(<span class="c-green">"https://dkruban.github.io"</span>);<br>
        }
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const launchBtn = document.getElementById('launch-btn-group');
            
            if (launchBtn) {
                launchBtn.addEventListener('click', () => {
                    // Open the link in a new tab
                    window.open('https://dkruban.github.io', '_blank');
                });
            }
        });
    </script>
</body>
</html>
