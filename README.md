<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Madhumitha Raj — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --surface2: #1c2128;
    --border: #30363d;
    --border-light: #21262d;
    --text: #e6edf3;
    --muted: #8b949e;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --accent3: #f78166;
    --accent4: #d2a8ff;
    --accent5: #ffa657;
    --badge-bg: #1f3250;
    --badge-text: #79c0ff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    line-height: 1.6;
  }

  .wrapper {
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px;
  }

  /* HEADER */
  .header {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-bottom: 40px;
    animation: fadeDown 0.7s ease both;
  }

  .avatar {
    width: 90px;
    height: 90px;
    border-radius: 50%;
    background: linear-gradient(135deg, #58a6ff 0%, #3fb950 50%, #d2a8ff 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 32px;
    font-weight: 700;
    font-family: 'Syne', sans-serif;
    margin-bottom: 16px;
    border: 3px solid var(--border);
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(28px, 6vw, 44px);
    font-weight: 800;
    letter-spacing: -1px;
    background: linear-gradient(90deg, #58a6ff, #3fb950, #d2a8ff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }

  .tagline {
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 0.5px;
    margin-bottom: 18px;
  }

  .typing-container {
    font-size: 13px;
    color: var(--accent2);
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 18px;
    display: inline-block;
    position: relative;
    margin-bottom: 20px;
  }
  .typing-container::before {
    content: '$ ';
    color: var(--accent5);
  }
  .cursor {
    display: inline-block;
    width: 8px;
    height: 14px;
    background: var(--accent);
    vertical-align: middle;
    margin-left: 2px;
    animation: blink 1s step-end infinite;
  }

  .social-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 0;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.3px;
    text-decoration: none;
    border: 1px solid;
    transition: opacity 0.2s;
  }
  .badge:hover { opacity: 0.8; }
  .badge-blue { background: #1a2b45; border-color: #2d6db4; color: #79c0ff; }
  .badge-green { background: #1a2d1a; border-color: #2d6b2d; color: #56d364; }
  .badge-purple { background: #2d1a45; border-color: #6b3db4; color: #d2a8ff; }
  .badge-orange { background: #2d2010; border-color: #b46a1a; color: #ffa657; }

  /* DIVIDER */
  .divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 32px 0;
  }

  /* SECTION */
  .section {
    margin-bottom: 36px;
    animation: fadeUp 0.6s ease both;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .section-title span.icon {
    font-size: 16px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
    margin-left: 8px;
  }

  /* ABOUT CODE BLOCK */
  .code-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .code-header {
    background: var(--surface2);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid var(--border);
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }

  .code-filename {
    font-size: 11px;
    color: var(--muted);
    margin-left: 8px;
  }

  .code-body {
    padding: 20px 24px;
    font-size: 13px;
    line-height: 1.8;
  }

  .kw { color: #ff7b72; }
  .cls { color: #ffa657; }
  .str { color: #a5d6ff; }
  .comment { color: var(--muted); }
  .field { color: #e6edf3; }
  .val { color: #79c0ff; }
  .grn { color: #3fb950; }
  .indent { display: block; padding-left: 20px; }
  .indent2 { display: block; padding-left: 40px; }
  .indent3 { display: block; padding-left: 60px; }

  /* SKILL GRID */
  .skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
  }

  .skill-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 16px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .skill-card:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .skill-label {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.8px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .tag {
    font-size: 11px;
    padding: 3px 8px;
    border-radius: 4px;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
  }
  .tag.blue { background: #1a2b45; border-color: #2d6db4; color: #79c0ff; }
  .tag.green { background: #1a2d1a; border-color: #2d6b2d; color: #56d364; }
  .tag.purple { background: #2d1a45; border-color: #6b3db4; color: #d2a8ff; }
  .tag.orange { background: #2d2010; border-color: #b46a1a; color: #ffa657; }
  .tag.red { background: #2d1a1a; border-color: #b43d3d; color: #ff7b72; }

  /* EXPERIENCE CARDS */
  .exp-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    border-radius: 10px;
    padding: 16px 18px;
    margin-bottom: 12px;
    transition: border-color 0.2s;
  }
  .exp-card:hover { border-left-color: var(--accent2); }
  .exp-card.tcs { border-left-color: var(--accent4); }
  .exp-card.mc { border-left-color: var(--accent5); }

  .exp-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 12px;
    flex-wrap: wrap;
    margin-bottom: 6px;
  }

  .exp-role {
    font-family: 'Syne', sans-serif;
    font-size: 14px;
    font-weight: 700;
    color: var(--text);
  }

  .exp-company {
    font-size: 12px;
    color: var(--accent);
  }

  .exp-date {
    font-size: 11px;
    color: var(--muted);
    white-space: nowrap;
  }

  .exp-bullets {
    list-style: none;
    margin-top: 8px;
  }
  .exp-bullets li {
    font-size: 12px;
    color: var(--muted);
    padding-left: 14px;
    position: relative;
    margin-bottom: 4px;
    line-height: 1.5;
  }
  .exp-bullets li::before {
    content: '▸';
    color: var(--accent2);
    position: absolute;
    left: 0;
    font-size: 10px;
    top: 2px;
  }

  /* PROJECT TABLE */
  .proj-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 12px;
  }

  .proj-table thead tr {
    border-bottom: 1px solid var(--border);
  }

  .proj-table th {
    text-align: left;
    color: var(--muted);
    font-size: 11px;
    font-weight: 500;
    padding: 8px 10px;
    letter-spacing: 0.5px;
  }

  .proj-table td {
    padding: 10px 10px;
    vertical-align: top;
    border-bottom: 1px solid var(--border-light);
    color: var(--muted);
  }

  .proj-table td:first-child {
    color: var(--accent);
    font-weight: 500;
  }

  .proj-table tr:last-child td { border-bottom: none; }

  .proj-table tbody tr:hover td {
    background: var(--surface2);
  }

  /* STATS */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 12px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 800;
    color: var(--accent);
    display: block;
    margin-bottom: 4px;
  }
  .stat-num.green { color: var(--accent2); }
  .stat-num.purple { color: var(--accent4); }
  .stat-num.orange { color: var(--accent5); }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.5px;
  }

  /* CERTS */
  .cert-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }
  .cert-pill {
    font-size: 11px;
    padding: 6px 14px;
    border-radius: 20px;
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .cert-dot {
    width: 8px; height: 8px; border-radius: 50%;
  }

  /* PUBLICATION */
  .pub-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 18px;
    display: flex;
    align-items: flex-start;
    gap: 14px;
  }
  .pub-icon {
    width: 36px; height: 36px;
    border-radius: 8px;
    background: #1a2b45;
    border: 1px solid #2d6db4;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    color: #79c0ff;
    font-size: 16px;
  }
  .pub-title { font-size: 13px; font-weight: 500; color: var(--text); margin-bottom: 4px; }
  .pub-venue { font-size: 11px; color: var(--muted); }

  /* FOOTER */
  .footer {
    text-align: center;
    padding-top: 32px;
    font-size: 11px;
    color: var(--muted);
  }

  /* ANIMATIONS */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-16px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .section:nth-child(1) { animation-delay: 0.1s; }
  .section:nth-child(2) { animation-delay: 0.2s; }
  .section:nth-child(3) { animation-delay: 0.3s; }
  .section:nth-child(4) { animation-delay: 0.4s; }
  .section:nth-child(5) { animation-delay: 0.5s; }
  .section:nth-child(6) { animation-delay: 0.6s; }

  @media (max-width: 600px) {
    .exp-top { flex-direction: column; }
    .proj-table { display: none; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="avatar">MR</div>
    <div class="name">Madhumitha Raj</div>
    <div class="tagline">Toronto, Ontario &nbsp;·&nbsp; IT Security @ UOIT &nbsp;·&nbsp; PKI · IAM · SIEM</div>
    <div class="typing-container">
      whoami &nbsp;→&nbsp; cybersecurity analyst &amp; master's candidate (2026)<span class="cursor"></span>
    </div>
    <div class="social-links">
      <a class="badge badge-blue" href="mailto:kannamma2511@gmail.com">✉ kannamma2511@gmail.com</a>
      <a class="badge badge-green" href="tel:4372483674">📞 (437) 248-3674</a>
      <a class="badge badge-purple" href="https://linkedin.com/in/MadhumithaRaj" target="_blank">🔗 LinkedIn</a>
      <a class="badge badge-orange" href="https://github.com/MadhumithaRaj" target="_blank">⌥ GitHub</a>
    </div>
  </div>

  <hr class="divider">

  <!-- ABOUT -->
  <div class="section">
    <div class="section-title"><span class="icon">👤</span> About Me</div>
    <div class="code-card">
      <div class="code-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="code-filename">MadhumithaRaj.py</span>
      </div>
      <div class="code-body">
        <span class="kw">class</span> <span class="cls">MadhumithaRaj</span>:<br>
        <span class="indent"><span class="comment"># Master's Candidate · IT Security · UOIT 2026</span></span>
        <br>
        <span class="indent"><span class="field">location</span> &nbsp;&nbsp;&nbsp;&nbsp;= <span class="str">"Toronto, Ontario"</span></span>
        <span class="indent"><span class="field">degree</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;= <span class="str">"M.IT Security — UOIT (2026)"</span></span>
        <span class="indent"><span class="field">undergrad</span> &nbsp;&nbsp;= <span class="str">"B.Eng. ECE — Saveetha Engineering (2024)"</span></span>
        <br>
        <span class="indent"><span class="field">specialties</span> = [</span>
        <span class="indent2"><span class="str">"PKI &amp; X.509 Certificate Lifecycle"</span>,</span>
        <span class="indent2"><span class="str">"IAM Access Control &amp; Least-Privilege"</span>,</span>
        <span class="indent2"><span class="str">"SIEM (Splunk) &amp; Incident Response"</span>,</span>
        <span class="indent2"><span class="str">"Compliance: NIST · PCI-DSS · SOC2"</span>,</span>
        <span class="indent2"><span class="str">"TLS/SSL · CA Trust Hierarchies"</span>,</span>
        <span class="indent">]</span>
        <br>
        <span class="indent"><span class="kw">def</span> <span class="grn">motto</span>(<span class="val">self</span>):</span>
        <span class="indent2"><span class="kw">return</span> <span class="str">"Secure by design. Resilient by practice."</span></span>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-title"><span class="icon">🛠</span> Technical Skills</div>
    <div class="skill-grid">
      <div class="skill-card">
        <div class="skill-label">PKI &amp; Cryptography</div>
        <div class="skill-tags">
          <span class="tag blue">X.509</span>
          <span class="tag blue">TLS/SSL</span>
          <span class="tag blue">CA hierarchies</span>
          <span class="tag blue">Key mgmt</span>
          <span class="tag blue">Asymm. enc.</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-label">Security Tools</div>
        <div class="skill-tags">
          <span class="tag green">Splunk SIEM</span>
          <span class="tag green">Wireshark</span>
          <span class="tag green">Kali Linux</span>
          <span class="tag green">Nmap</span>
          <span class="tag green">Mininet</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-label">Scripting &amp; Dev</div>
        <div class="skill-tags">
          <span class="tag orange">Python</span>
          <span class="tag orange">Bash</span>
          <span class="tag orange">C++</span>
          <span class="tag orange">SQL</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-label">Compliance &amp; Governance</div>
        <div class="skill-tags">
          <span class="tag red">NIST</span>
          <span class="tag red">PCI-DSS</span>
          <span class="tag red">SOC2</span>
          <span class="tag red">IR Lifecycle</span>
          <span class="tag red">MITRE ATT&amp;CK</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-label">Networking</div>
        <div class="skill-tags">
          <span class="tag purple">TCP/IP</span>
          <span class="tag purple">SDN</span>
          <span class="tag purple">IDS/IPS</span>
          <span class="tag purple">Firewall/ACL</span>
        </div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-title"><span class="icon">📊</span> At a Glance</div>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-num">50+</span>
        <span class="stat-label">security incidents triaged / month</span>
      </div>
      <div class="stat-card">
        <span class="stat-num green">30+</span>
        <span class="stat-label">IAM accounts provisioned</span>
      </div>
      <div class="stat-card">
        <span class="stat-num purple">20%</span>
        <span class="stat-label">IR efficiency improvement</span>
      </div>
      <div class="stat-card">
        <span class="stat-num orange">15-20%</span>
        <span class="stat-label">recurring incidents reduced</span>
      </div>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section">
    <div class="section-title"><span class="icon">💼</span> Experience</div>

    <div class="exp-card">
      <div class="exp-top">
        <div>
          <div class="exp-role">Business Analyst Intern — Security Operations</div>
          <div class="exp-company">Cappricio Securities · Chennai, India</div>
        </div>
        <div class="exp-date">Jun 2025 – Dec 2025</div>
      </div>
      <ul class="exp-bullets">
        <li>Monitored and triaged 50+ monthly security incidents; reduced recurring issues by 15-20% through root-cause documentation and remediation tracking.</li>
        <li>Managed IAM access provisioning for 30+ employees under least-privilege policies, improving incident response efficiency by 20% and strengthening audit readiness.</li>
      </ul>
    </div>

    <div class="exp-card tcs">
      <div class="exp-top">
        <div>
          <div class="exp-role">Cybersecurity Analyst Simulation</div>
          <div class="exp-company">Tata Consultancy Services (Forage)</div>
        </div>
        <div class="exp-date">Virtual</div>
      </div>
      <ul class="exp-bullets">
        <li>Performed IAM access reviews, developed security control recommendations, and produced gap analysis reports and audit-ready incident documentation.</li>
        <li>Mapped threat vectors to MITRE ATT&amp;CK techniques; supported certificate-related risk classification relevant to PKI operations.</li>
      </ul>
    </div>

    <div class="exp-card mc">
      <div class="exp-top">
        <div>
          <div class="exp-role">Cybersecurity Analyst Simulation</div>
          <div class="exp-company">Mastercard (Forage)</div>
        </div>
        <div class="exp-date">Virtual</div>
      </div>
      <ul class="exp-bullets">
        <li>Analyzed phishing indicators of compromise and practiced structured alert triage.</li>
        <li>Communicated risk findings to simulated stakeholders using clear, non-technical language — skills applicable to PKI compliance reporting.</li>
      </ul>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-title"><span class="icon">🚀</span> Academic Projects</div>
    <div class="code-card">
      <div class="code-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="code-filename">projects.md</span>
      </div>
      <table class="proj-table">
        <thead>
          <tr>
            <th>Project</th>
            <th>Period</th>
            <th>Highlights</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>SDN Security with QoS &amp; Congestion Control</td>
            <td>Jun – Dec 2025</td>
            <td>Secure SDN topology (Pox Controller) with network segmentation mirroring PKI zone separation; built traffic anomaly detection with real-time rerouting; Wireshark/Nmap monitoring + structured remediation reports.</td>
          </tr>
          <tr>
            <td>Embedded Security &amp; Computer Vision System</td>
            <td>Jul – Dec 2024</td>
            <td>Applied access controls and secure coding on a safety-critical embedded pipeline, enforcing trust boundaries relevant to HSM &amp; CA server access management.</td>
          </tr>
        </tbody>
      </table>
      <!-- Mobile fallback -->
      <div class="code-body" style="display:none;" id="proj-mobile">
        <span class="comment"># SDN Security with QoS &amp; Congestion Control · Jun–Dec 2025</span><br>
        <span class="indent">Secure SDN topology · PKI zone separation analogy · anomaly detection</span><br><br>
        <span class="comment"># Embedded Security &amp; Computer Vision · Jul–Dec 2024</span><br>
        <span class="indent">Secure coding · trust boundaries · HSM/CA server access management</span>
      </div>
    </div>
  </div>

  <!-- PUBLICATION -->
  <div class="section">
    <div class="section-title"><span class="icon">📄</span> Publication</div>
    <div class="pub-card">
      <div class="pub-icon">📰</div>
      <div>
        <div class="pub-title">Driver Drowsiness Detection — A Snippet of ADAS Using OpenCV</div>
        <div class="pub-venue">IEEE ICACCS 2024 · Jun 2023 – Dec 2023 · Real-time ML-based monitoring with behavioral analytics &amp; alerting — analogous to cybersecurity anomaly detection systems.</div>
      </div>
    </div>
  </div>

  <!-- EDUCATION & CERTS -->
  <div class="section">
    <div class="section-title"><span class="icon">🎓</span> Education &amp; Certifications</div>
    <div style="margin-bottom: 14px;">
      <div class="exp-card" style="border-left-color: var(--accent4);">
        <div class="exp-top">
          <div>
            <div class="exp-role">Master of Information Technology Security</div>
            <div class="exp-company">University of Ontario Institute of Technology · Oshawa, ON</div>
            <div style="font-size: 11px; color: var(--muted); margin-top: 4px;">Cryptography &amp; Network Security · Applied PKI · Secure System Design · Incident Response</div>
          </div>
          <div class="exp-date">Sep 2024 – Apr 2026</div>
        </div>
      </div>
      <div class="exp-card" style="border-left-color: var(--accent2);">
        <div class="exp-top">
          <div>
            <div class="exp-role">B.Eng. Electronics &amp; Communication Engineering</div>
            <div class="exp-company">Saveetha Engineering College · Chennai, India</div>
          </div>
          <div class="exp-date">Jun 2020 – Jun 2024</div>
        </div>
      </div>
    </div>
    <div class="cert-row">
      <div class="cert-pill">
        <div class="cert-dot" style="background: #ffa657;"></div>
        Cryptography &amp; Network Security — NPTEL
      </div>
      <div class="cert-pill">
        <div class="cert-dot" style="background: #58a6ff;"></div>
        Cybersecurity Essentials Badge — CISCO (TLS/SSL, CA hierarchies)
      </div>
    </div>
  </div>

  <hr class="divider">

  <div class="footer">
    <div style="margin-bottom: 6px; color: var(--accent);">✦ &nbsp; Currently seeking cybersecurity roles in Toronto &nbsp; ✦</div>
    kannamma2511@gmail.com · (437) 248-3674
  </div>

</div>

<script>
  if (window.innerWidth <= 600) {
    document.querySelector('.proj-table').style.display = 'none';
    document.getElementById('proj-mobile').style.display = 'block';
  }
</script>
</body>
</html>
