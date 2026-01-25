<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Awesome Connected Things Security - Beast Mode</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Noto Sans", Helvetica, Arial, sans-serif;
            background-color: #0d1117;
            color: #e6edf3;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        
        /* ASCII Art */
        .ascii-art {
            font-family: 'Courier New', monospace;
            font-size: 10px;
            line-height: 1.1;
            color: #58a6ff;
            white-space: pre;
            text-align: center;
            margin-bottom: 20px;
            text-shadow: 0 0 10px #58a6ff40;
        }
        
        @media (max-width: 768px) {
            .ascii-art {
                font-size: 6px;
            }
        }
        
        /* Banner */
        .banner-container {
            text-align: center;
            margin: 20px 0;
        }
        
        .banner {
            width: 100%;
            max-width: 800px;
            height: 200px;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 1px solid #30363d;
            margin: 0 auto;
        }
        
        .banner-icons {
            font-size: 60px;
            letter-spacing: 20px;
        }
        
        /* Tagline */
        .tagline {
            text-align: center;
            font-size: 18px;
            color: #8b949e;
            margin: 20px 0;
            font-style: italic;
        }
        
        .tagline-jp {
            color: #ff6b6b;
        }
        
        /* Badges Row */
        .badges {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 8px;
            margin: 20px 0;
        }
        
        .badge {
            height: 28px;
            border-radius: 4px;
            display: inline-flex;
            align-items: center;
            font-size: 12px;
            font-weight: 600;
            overflow: hidden;
        }
        
        .badge-label {
            background: #30363d;
            padding: 0 10px;
            height: 100%;
            display: flex;
            align-items: center;
        }
        
        .badge-value {
            padding: 0 10px;
            height: 100%;
            display: flex;
            align-items: center;
        }
        
        .badge-awesome { background: #fc60a8; color: white; padding: 0 12px; }
        .badge-stars .badge-value { background: #fbbf24; color: #000; }
        .badge-forks .badge-value { background: #3b82f6; color: white; }
        .badge-license .badge-value { background: #22c55e; color: white; }
        .badge-commit .badge-value { background: #ef4444; color: white; }
        
        /* Terminal Box */
        .terminal-box {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 15px 20px;
            margin: 25px auto;
            max-width: 700px;
            font-family: 'Courier New', monospace;
            text-align: center;
            font-size: 14px;
        }
        
        .terminal-box.wide {
            max-width: 800px;
        }
        
        .terminal-header {
            display: flex;
            gap: 6px;
            margin-bottom: 10px;
        }
        
        .terminal-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }
        
        .dot-red { background: #ff5f56; }
        .dot-yellow { background: #ffbd2e; }
        .dot-green { background: #27ca40; }
        
        /* Description */
        .description {
            text-align: center;
            margin: 20px 0;
        }
        
        .description-main {
            font-size: 18px;
            font-weight: 600;
            color: #e6edf3;
        }
        
        .description-sub {
            font-size: 14px;
            color: #8b949e;
            margin-top: 5px;
        }
        
        /* Category Buttons */
        .category-buttons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin: 25px 0;
        }
        
        .cat-btn {
            padding: 10px 20px;
            border-radius: 6px;
            font-size: 13px;
            font-weight: 600;
            text-decoration: none;
            color: white;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.2s, box-shadow 0.2s;
        }
        
        .cat-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.3);
        }
        
        .cat-btn.ics { background: linear-gradient(135deg, #ff6b6b, #ee5a5a); }
        .cat-btn.auto { background: linear-gradient(135deg, #4ecdc4, #44b3ab); }
        .cat-btn.awesome { background: linear-gradient(135deg, #a855f7, #9333ea); }
        .cat-btn.contrib { background: linear-gradient(135deg, #f59e0b, #d97706); }
        
        /* Flow */
        .flow {
            text-align: center;
            font-family: 'Courier New', monospace;
            color: #fbbf24;
            font-size: 14px;
            margin: 20px 0;
        }
        
        /* Attack Surfaces */
        .section-title {
            text-align: center;
            font-size: 20px;
            margin: 40px 0 20px 0;
            color: #e6edf3;
        }
        
        .attack-surfaces {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin: 20px 0;
        }
        
        .surface-card {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 20px;
            width: 150px;
            text-align: center;
            transition: transform 0.2s, border-color 0.2s;
        }
        
        .surface-card:hover {
            transform: translateY(-4px);
            border-color: #58a6ff;
        }
        
        .surface-icon {
            font-size: 36px;
            margin-bottom: 10px;
        }
        
        .surface-title {
            font-weight: 600;
            margin-bottom: 8px;
            color: #e6edf3;
        }
        
        .surface-sub {
            font-size: 11px;
            color: #8b949e;
            line-height: 1.4;
        }
        
        /* Why Section */
        .why-box {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            margin: 20px auto;
            max-width: 700px;
            font-family: 'Courier New', monospace;
        }
        
        .why-box pre {
            color: #7ee787;
            font-size: 13px;
            line-height: 1.8;
        }
        
        /* Difficulty Table */
        .diff-table {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 20px 0;
        }
        
        .diff-item {
            text-align: center;
        }
        
        .diff-badge {
            font-size: 24px;
            margin-bottom: 5px;
        }
        
        .diff-label {
            font-size: 14px;
            font-weight: 600;
        }
        
        .diff-desc {
            font-size: 12px;
            color: #8b949e;
        }
        
        /* Quick Access */
        .quick-access {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 8px;
            margin: 20px 0;
        }
        
        .quick-btn {
            background: #21262d;
            border: 1px solid #30363d;
            padding: 6px 12px;
            border-radius: 4px;
            font-size: 12px;
            color: #e6edf3;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }
        
        .quick-btn:hover {
            background: #30363d;
            border-color: #8b949e;
        }
        
        /* Community */
        .community {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        
        .social-btn {
            padding: 10px 20px;
            border-radius: 6px;
            font-size: 13px;
            font-weight: 600;
            text-decoration: none;
            color: white;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        
        .social-btn.telegram { background: #26A5E4; }
        .social-btn.discord { background: #5865F2; }
        .social-btn.reddit { background: #FF4500; }
        .social-btn.twitter { background: #1DA1F2; }
        
        /* Quote */
        .quote-box {
            text-align: center;
            margin: 40px 0;
            padding: 30px;
            border: 1px solid #30363d;
            border-radius: 12px;
            background: linear-gradient(135deg, #161b22 0%, #0d1117 100%);
        }
        
        .quote-text {
            font-size: 18px;
            font-style: italic;
            color: #8b949e;
            margin-bottom: 15px;
        }
        
        .quote-author {
            color: #58a6ff;
            font-weight: 600;
        }
        
        hr {
            border: none;
            border-top: 1px solid #30363d;
            margin: 30px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        
        <!-- ASCII Art Logo -->
        <div class="ascii-art">
   ██████╗ ██████╗ ███╗   ██╗███╗   ██╗███████╗ ██████╗████████╗███████╗██████╗ 
  ██╔════╝██╔═══██╗████╗  ██║████╗  ██║██╔════╝██╔════╝╚══██╔══╝██╔════╝██╔══██╗
  ██║     ██║   ██║██╔██╗ ██║██╔██╗ ██║█████╗  ██║        ██║   █████╗  ██║  ██║
  ██║     ██║   ██║██║╚██╗██║██║╚██╗██║██╔══╝  ██║        ██║   ██╔══╝  ██║  ██║
  ╚██████╗╚██████╔╝██║ ╚████║██║ ╚████║███████╗╚██████╗   ██║   ███████╗██████╔╝
   ╚═════╝ ╚═════╝ ╚═╝  ╚═══╝╚═╝  ╚═══╝╚══════╝ ╚═════╝   ╚═╝   ╚══════╝╚═════╝ 
  ████████╗██╗  ██╗██╗███╗   ██╗ ██████╗ ███████╗    ███████╗███████╗ ██████╗
  ╚══██╔══╝██║  ██║██║████╗  ██║██╔════╝ ██╔════╝    ██╔════╝██╔════╝██╔════╝
     ██║   ███████║██║██╔██╗ ██║██║  ███╗███████╗    ███████╗█████╗  ██║     
     ██║   ██╔══██║██║██║╚██╗██║██║   ██║╚════██║    ╚════██║██╔══╝  ██║     
     ██║   ██║  ██║██║██║ ╚████║╚██████╔╝███████║    ███████║███████╗╚██████╗
     ╚═╝   ╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝ ╚═════╝ ╚══════╝    ╚══════╝╚══════╝ ╚═════╝
        </div>
        
        <!-- Banner -->
        <div class="banner-container">
            <div class="banner">
                <span class="banner-icons">🔐 📡 🔧 💻 🎯</span>
            </div>
        </div>
        
        <!-- Tagline -->
        <div class="tagline">
            <span class="tagline-jp">「</span> <em>Hack the Planet, One Device at a Time</em> <span class="tagline-jp">」</span>
        </div>
        
        <!-- Main Badges -->
        <div class="badges">
            <span class="badge badge-awesome">★ Awesome</span>
            <span class="badge badge-stars">
                <span class="badge-label">⭐ Stars</span>
                <span class="badge-value">2.4k</span>
            </span>
            <span class="badge badge-forks">
                <span class="badge-label">🍴 Forks</span>
                <span class="badge-value">456</span>
            </span>
            <span class="badge badge-license">
                <span class="badge-label">📜 License</span>
                <span class="badge-value">MIT</span>
            </span>
            <span class="badge badge-commit">
                <span class="badge-label">🔄 Updated</span>
                <span class="badge-value">2 days ago</span>
            </span>
        </div>
        
        <!-- Terminal Categories -->
        <div class="terminal-box">
            🔓 FIRMWARE  │  📡 WIRELESS  │  🔧 HARDWARE  │  🌐 PROTOCOLS  │  ☁️ CLOUD
        </div>
        
        <!-- Description -->
        <div class="description">
            <div class="description-main">The Ultimate Arsenal for IoT Security Researchers, Hardware Hackers & Embedded Exploit Developers</div>
            <div class="description-sub"><em>900+ curated resources • Actively maintained • Community-driven</em></div>
        </div>
        
        <!-- Category Buttons -->
        <div class="category-buttons">
            <a href="#" class="cat-btn ics">🏭 ICS SECURITY — SCADA & OT</a>
            <a href="#" class="cat-btn auto">🚗 AUTOMOTIVE — CAN & ECU</a>
            <a href="#" class="cat-btn awesome">📚 AWESOME COLLECTION</a>
            <a href="#" class="cat-btn contrib">🤝 CONTRIBUTE — JOIN US</a>
        </div>
        
        <!-- Flow -->
        <div class="flow">
            ⚡ UART → JTAG → SWD → SPI → I2C → eMMC → FIRMWARE → EXPLOIT → ROOT ⚡
        </div>
        
        <hr>
        
        <!-- Attack Surfaces -->
        <div class="section-title">🎯 ATTACK SURFACES COVERED</div>
        
        <div class="attack-surfaces">
            <div class="surface-card">
                <div class="surface-icon">⚡</div>
                <div class="surface-title">Hardware</div>
                <div class="surface-sub">UART • JTAG • SWD<br/>SPI • I2C • Glitching</div>
            </div>
            <div class="surface-card">
                <div class="surface-icon">📡</div>
                <div class="surface-title">Wireless</div>
                <div class="surface-sub">BLE • ZigBee • LoRa<br/>WiFi • NFC • SDR</div>
            </div>
            <div class="surface-card">
                <div class="surface-icon">💾</div>
                <div class="surface-title">Firmware</div>
                <div class="surface-sub">Extraction • RE<br/>Emulation • Fuzzing</div>
            </div>
            <div class="surface-card">
                <div class="surface-icon">🌐</div>
                <div class="surface-title">Cloud/API</div>
                <div class="surface-sub">MQTT • CoAP<br/>AWS IoT • Firebase</div>
            </div>
            <div class="surface-card">
                <div class="surface-icon">🚗</div>
                <div class="surface-title">Automotive</div>
                <div class="surface-sub">CAN Bus • ECU<br/>EV Chargers • OBD</div>
            </div>
        </div>
        
        <hr>
        
        <!-- Why Section -->
        <div class="section-title">🔥 WHY THIS REPO?</div>
        
        <div class="why-box">
            <pre>
 ╔══════════════════════════════════════════════════════════════════════════╗
 ║                                                                          ║
 ║   [✓] 900+ Hand-Curated Resources      [✓] Zero Fluff, Pure Signal      ║
 ║   [✓] Beginner → Advanced Pathways     [✓] Real Exploit Techniques      ║
 ║   [✓] Active Community Support         [✓] Weekly Updates               ║
 ║   [✓] Conference Talks & Papers        [✓] Working Tools & PoCs         ║
 ║                                                                          ║
 ╚══════════════════════════════════════════════════════════════════════════╝
            </pre>
        </div>
        
        <!-- Difficulty -->
        <div class="diff-table">
            <div class="diff-item">
                <div class="diff-badge">🟢</div>
                <div class="diff-label">Beginner Friendly</div>
                <div class="diff-desc">Start your journey</div>
            </div>
            <div class="diff-item">
                <div class="diff-badge">🟡</div>
                <div class="diff-label">Intermediate</div>
                <div class="diff-desc">Level up your skills</div>
            </div>
            <div class="diff-item">
                <div class="diff-badge">🔴</div>
                <div class="diff-label">Advanced</div>
                <div class="diff-desc">Master the craft</div>
            </div>
        </div>
        
        <hr>
        
        <!-- Quick Access -->
        <div class="section-title">💀 QUICK ACCESS</div>
        
        <div class="quick-access">
            <a href="#" class="quick-btn">⚡ HARDWARE HACKING</a>
            <a href="#" class="quick-btn">📶 BLUETOOTH / BLE</a>
            <a href="#" class="quick-btn">💾 FIRMWARE ANALYSIS</a>
            <a href="#" class="quick-btn">📡 WIRELESS PROTOCOLS</a>
            <a href="#" class="quick-btn">🔧 TOOLS ARSENAL</a>
            <a href="#" class="quick-btn">🎮 LABS & CTFs</a>
        </div>
        
        <hr>
        
        <!-- Community -->
        <div class="section-title">📡 COMMUNITY</div>
        
        <div class="community">
            <a href="#" class="social-btn telegram">📱 Telegram</a>
            <a href="#" class="social-btn discord">💬 Discord</a>
            <a href="#" class="social-btn reddit">🔴 Reddit</a>
            <a href="#" class="social-btn twitter">🐦 Twitter</a>
        </div>
        
        <hr>
        
        <!-- Quote -->
        <div class="quote-box">
            <div class="quote-text">"In a world of connected devices,<br/>the curious become the powerful."</div>
            <div class="quote-author">— IoTSecurity101</div>
        </div>
        
    </div>
</body>
</html>
