<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Darshan A N — Technical Support, Implementation & Customer Success</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#12181B;
    --panel:#1A2226;
    --panel-2:#1F292E;
    --border:#2B383D;
    --text:#E7EDEE;
    --text-muted:#8FA3A8;
    --text-dim:#617076;
    --teal:#5FCFC4;
    --amber:#E8A94B;
    --red:#E2665A;
    --maxw:940px;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  @media (prefers-reduced-motion: reduce){ html{scroll-behavior:auto;} *{animation-duration:0.01ms !important; transition-duration:0.01ms !important;} }

  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter',sans-serif;
    line-height:1.6;
    font-size:16px;
    -webkit-font-smoothing:antialiased;
  }

  a{color:var(--teal); text-decoration:none;}
  a:hover{text-decoration:underline;}
  a:focus-visible, button:focus-visible{outline:2px solid var(--teal); outline-offset:3px; border-radius:2px;}

  .mono{font-family:'IBM Plex Mono',monospace;}
  .display{font-family:'Space Grotesk',sans-serif;}

  /* ---------- topbar ---------- */
  .topbar{
    position:sticky; top:0; z-index:50;
    background:rgba(18,24,27,0.88);
    backdrop-filter: blur(8px);
    border-bottom:1px solid var(--border);
  }
  .topbar-inner{
    max-width:var(--maxw); margin:0 auto; padding:14px 24px;
    display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap;
  }
  .brand{display:flex; align-items:center; font-family:'Space Grotesk',sans-serif; font-weight:600; font-size:15px;}
  .dot{width:8px; height:8px; border-radius:50%; background:var(--teal); box-shadow:0 0 0 0 rgba(95,207,196,.6); animation:pulse 2.4s infinite; margin-right:9px; display:inline-block;}
  @keyframes pulse{
    0%{box-shadow:0 0 0 0 rgba(95,207,196,.55);}
    70%{box-shadow:0 0 0 8px rgba(95,207,196,0);}
    100%{box-shadow:0 0 0 0 rgba(95,207,196,0);}
  }
  nav{display:flex; gap:22px; font-size:13px; font-family:'IBM Plex Mono',monospace;}
  nav a{color:var(--text-muted); margin-left:22px;}
  nav a:first-child{margin-left:0;}
  nav a:hover{color:var(--teal); text-decoration:none;}

  section{max-width:var(--maxw); margin:0 auto; padding:64px 24px;}
  .section-label{
    font-family:'IBM Plex Mono',monospace; font-size:12px; letter-spacing:.12em;
    color:var(--teal); text-transform:uppercase; margin-bottom:10px; display:flex; align-items:center; gap:8px;
  }
  .section-label::before{content:"//"; color:var(--text-dim);}

  /* ---------- hero ---------- */
  .hero{padding-top:72px; padding-bottom:56px;}
  .status-chip{
    display:inline-flex; align-items:center;
    font-family:'IBM Plex Mono',monospace; font-size:12px; letter-spacing:.06em;
    color:var(--teal); background:rgba(95,207,196,0.08);
    border:1px solid rgba(95,207,196,0.28); padding:6px 12px; border-radius:20px;
    margin-bottom:28px;
  }
  h1.name{font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:clamp(2.4rem,6vw,3.6rem); letter-spacing:-.02em; line-height:1.05;}
  .role{
    font-family:'Space Grotesk',sans-serif; font-weight:500; font-size:clamp(1.1rem,2.4vw,1.4rem);
    color:var(--text-muted); margin-top:10px;
  }
  .lede{max-width:560px; color:var(--text-muted); font-size:1.05rem; margin-top:22px;}
  .cta-row{display:flex; gap:14px; margin-top:32px; flex-wrap:wrap;}
  .btn{
    font-family:'IBM Plex Mono',monospace; font-size:13px; padding:12px 20px; border-radius:6px;
    border:1px solid var(--border); transition:all .15s ease; display:inline-flex; align-items:center; gap:8px;
  }
  .btn:hover{text-decoration:none;}
  .btn-primary{background:var(--teal); color:#0C1213; border-color:var(--teal); font-weight:600;}
  .btn-primary:hover{background:#78D9CF;}
  .btn-ghost{color:var(--text); background:transparent;}
  .btn-ghost:hover{border-color:var(--teal); color:var(--teal);}

  /* ---------- metrics strip (echoes his own dashboard) ---------- */
  .metrics{
    display:grid; grid-template-columns:repeat(4,1fr); gap:1px;
    background:var(--border); border:1px solid var(--border); border-radius:10px;
    overflow:hidden; margin-top:52px;
  }
  .metric{background:var(--panel); padding:20px 18px;}
  .metric .val{font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:1.7rem; color:var(--teal);}
  .metric .lbl{font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--text-dim); text-transform:uppercase; letter-spacing:.06em; margin-top:6px;}
  @media (max-width:680px){ .metrics{grid-template-columns:repeat(2,1fr);} }

  /* ---------- ticket log ---------- */
  .log-head{display:flex; justify-content:space-between; align-items:baseline; flex-wrap:wrap; gap:8px; margin-bottom:8px;}
  .log-head h2{font-family:'Space Grotesk',sans-serif; font-size:1.7rem; font-weight:600;}
  .log-sub{color:var(--text-dim); font-size:.92rem; margin-bottom:34px;}

  .ticket{
    background:var(--panel); border:1px solid var(--border); border-radius:10px;
    padding:20px 22px; margin-bottom:14px; transition:border-color .15s ease, transform .15s ease;
  }
  .ticket:hover{border-color:var(--teal); transform:translateY(-2px);}
  .ticket-top{display:flex; align-items:center; gap:10px; flex-wrap:wrap; margin-bottom:10px;}
  .tid{font-family:'IBM Plex Mono',monospace; font-size:12px; color:var(--text-dim);}
  .tag{
    font-family:'IBM Plex Mono',monospace; font-size:10.5px; text-transform:uppercase; letter-spacing:.05em;
    padding:3px 8px; border-radius:4px; border:1px solid var(--border); color:var(--text-muted);
  }
  .status{font-family:'IBM Plex Mono',monospace; font-size:10.5px; text-transform:uppercase; letter-spacing:.05em; padding:3px 8px; border-radius:4px; font-weight:600;}
  .status.resolved{color:#7CE0A6; background:rgba(124,224,166,0.1); border:1px solid rgba(124,224,166,0.3);}
  .status.ongoing{color:var(--amber); background:rgba(232,169,75,0.1); border:1px solid rgba(232,169,75,0.32);}
  .ticket h3{font-family:'Space Grotesk',sans-serif; font-size:1.05rem; font-weight:600; margin-bottom:8px;}
  .ticket p{color:var(--text-muted); font-size:.95rem;}

  /* ---------- systems / skills ---------- */
  .modules{display:grid; grid-template-columns:repeat(2,1fr); gap:14px;}
  @media (max-width:680px){ .modules{grid-template-columns:1fr;} }
  .module{background:var(--panel); border:1px solid var(--border); border-radius:10px; padding:22px;}
  .module .mod-head{display:flex; align-items:center; margin-bottom:14px;}
  .module .mod-dot{width:7px; height:7px; border-radius:50%; background:var(--teal); margin-right:9px; display:inline-block;}
  .module h3{font-family:'Space Grotesk',sans-serif; font-size:1rem; font-weight:600;}
  .chips{display:flex; flex-wrap:wrap; gap:8px;}
  .chip{
    font-family:'IBM Plex Mono',monospace; font-size:12px; color:var(--text-muted);
    background:var(--panel-2); border:1px solid var(--border); padding:5px 10px; border-radius:5px;
  }

  /* ---------- building now ---------- */
  .builds{display:grid; grid-template-columns:1fr 1fr; gap:16px;}
  @media (max-width:680px){ .builds{grid-template-columns:1fr;} }
  .build-card{background:var(--panel); border:1px solid var(--border); border-radius:10px; padding:24px;}
  .build-card .kicker{font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--amber); text-transform:uppercase; letter-spacing:.06em; margin-bottom:10px;}
  .build-card h3{font-family:'Space Grotesk',sans-serif; font-size:1.1rem; margin-bottom:10px;}
  .build-card p{color:var(--text-muted); font-size:.94rem;}

  /* ---------- contact / footer ---------- */
  footer{border-top:1px solid var(--border); margin-top:20px;}
  .footer-inner{max-width:var(--maxw); margin:0 auto; padding:56px 24px 40px;}
  .contact-grid{display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:28px;}
  .contact-grid h2{font-family:'Space Grotesk',sans-serif; font-size:1.9rem; max-width:420px; line-height:1.25;}
  .contact-links{display:flex; flex-direction:column; gap:10px; font-family:'IBM Plex Mono',monospace; font-size:.92rem;}
  .contact-links a{color:var(--text);}
  .contact-links a:hover{color:var(--teal);}
  .sign-off{margin-top:48px; padding-top:20px; border-top:1px solid var(--border); display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px; color:var(--text-dim); font-family:'IBM Plex Mono',monospace; font-size:12px;}

  /* reveal-on-load */
  .fade-up{opacity:0; transform:translateY(14px); animation:fadeUp .6s ease forwards;}
  @keyframes fadeUp{ to{opacity:1; transform:translateY(0);} }
  .d1{animation-delay:.05s;} .d2{animation-delay:.15s;} .d3{animation-delay:.25s;} .d4{animation-delay:.35s;}
</style>
</head>
<body>

<div class="topbar">
  <div class="topbar-inner">
    <div class="brand"><span class="dot"></span> DARSHAN<span class="mono" style="color:var(--text-dim); font-weight:400;">.ops</span></div>
    <nav>
      <a href="#log">Ticket Log</a>
      <a href="#systems">Systems</a>
      <a href="#building">Building Now</a>
      <a href="#contact">Contact</a>
    </nav>
  </div>
</div>

<section class="hero">
  <div class="status-chip fade-up"><span class="dot"></span> STATUS: OPEN TO NEW OPPORTUNITIES</div>
  <h1 class="name fade-up d1">Darshan A N</h1>
  <div class="role fade-up d1">Technical Support, Implementation &amp; Customer Success — Bengaluru, India</div>
  <p class="lede fade-up d2">Six years resolving what breaks between customers, infrastructure, and product —
    from networking and server configs to the AI agents I now build to handle the routine so I can focus on what actually needs a human.</p>

  <div class="cta-row fade-up d3">
    <a class="btn btn-primary" href="mailto:darshanashok.an7@gmail.com">Email Me →</a>
    <a class="btn btn-ghost" href="https://www.linkedin.com/in/darshan-an-4b6b14290" target="_blank" rel="noopener">LinkedIn</a>
    <a class="btn btn-ghost" href="Darshan_AN_Resume.pdf" target="_blank" rel="noopener">Download Résumé</a>
  </div>
  <div class="fade-up d3 mono" style="font-size:13px; color:var(--text-dim); margin-top:14px;">
    or copy directly: <span style="color:var(--text-muted); user-select:all;">darshanashok.an7@gmail.com</span>
  </div>

  <div class="metrics fade-up d4">
    <div class="metric"><div class="val">500+</div><div class="lbl">Tickets Handled</div></div>
    <div class="metric"><div class="val">79%</div><div class="lbl">Weekly Resolution Rate</div></div>
    <div class="metric"><div class="val">16.3h</div><div class="lbl">Avg Closure Time</div></div>
    <div class="metric"><div class="val">50-100+</div><div class="lbl">Enterprise Accounts</div></div>
  </div>
</section>

<section id="log">
  <div class="section-label">Experience</div>
  <div class="log-head">
    <h2>Ticket Log</h2>
    <span class="mono" style="font-size:12px; color:var(--text-dim);">Pickcel Digital Signage · 2019 – Present</span>
  </div>
  <p class="log-sub">Every entry below is a real resolution from six years on the front line of enterprise support — not a hypothetical.</p>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-014</span>
      <span class="tag">Onboarding</span>
      <span class="status resolved">Resolved</span>
    </div>
    <h3>Owned 50–100+ global enterprise accounts</h3>
    <p>Primary technical and success point of contact across multiple regions — matching product capability to complex customer requirements and driving adoption.</p>
  </div>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-089</span>
      <span class="tag">Customer Success</span>
      <span class="status resolved">Resolved</span>
    </div>
    <h3>Sustained 80–90% CSAT across 200+ monthly interactions</h3>
    <p>Combined fast resolution with deep debugging and clear communication to keep satisfaction consistently high, month over month.</p>
  </div>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-142</span>
      <span class="tag">Retention</span>
      <span class="status resolved">Resolved</span>
    </div>
    <h3>Maintained 80–90% account retention on a global portfolio</h3>
    <p>Proactively resolved technical risk, de-escalated at-risk accounts, and reinforced product value ahead of renewal conversations.</p>
  </div>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-201</span>
      <span class="tag">Root Cause</span>
      <span class="status resolved">Resolved</span>
    </div>
    <h3>Drove root cause analysis across server, network &amp; app layers</h3>
    <p>Reduced repeat escalations and improved product stability through structured bug documentation in Jira and Docker environments.</p>
  </div>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-077</span>
      <span class="tag">Eng. Bridge</span>
      <span class="status resolved">Resolved</span>
    </div>
    <h3>Acted as the technical bridge to engineering</h3>
    <p>Translated customer pain into actionable tickets and fed recurring themes back into the product roadmap.</p>
  </div>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-033</span>
      <span class="tag">Team Ops</span>
      <span class="status resolved">Resolved</span>
    </div>
    <h3>Coordinated cross-functional teams</h3>
    <p>Owned task allocation, onboarding, escalation management, and performance monitoring across operations, implementation, and support.</p>
  </div>

  <div class="ticket">
    <div class="ticket-top">
      <span class="tid">#TKT-118</span>
      <span class="tag">Automation</span>
      <span class="status ongoing">Ongoing</span>
    </div>
    <h3>Building Claude-based AI agents into daily operations</h3>
    <p>Drafting customer responses, summarizing conversations, preparing implementation docs, and standardizing repetitive workflows — cutting manual effort and improving consistency.</p>
  </div>
</section>

<section id="systems">
  <div class="section-label">Skills</div>
  <div class="log-head"><h2>Systems</h2></div>
  <p class="log-sub">The stack I actually work in day to day, grouped the way I'd document it in a runbook.</p>

  <div class="modules">
    <div class="module">
      <div class="mod-head"><span class="mod-dot"></span><h3>Infrastructure</h3></div>
      <div class="chips">
        <span class="chip">Networking</span><span class="chip">Server Config &amp; Hosting</span>
        <span class="chip">On-Prem / VM</span><span class="chip">AWS</span>
        <span class="chip">Microsoft Azure</span><span class="chip">Docker</span>
        <span class="chip">SQL</span><span class="chip">API / Log Debugging</span>
      </div>
    </div>
    <div class="module">
      <div class="mod-head"><span class="mod-dot"></span><h3>Platforms &amp; Tools</h3></div>
      <div class="chips">
        <span class="chip">Freshdesk</span><span class="chip">HubSpot</span>
        <span class="chip">Salesforce / Sales Desk</span><span class="chip">Jira</span>
      </div>
    </div>
    <div class="module">
      <div class="mod-head"><span class="mod-dot"></span><h3>Customer Ops &amp; Delivery</h3></div>
      <div class="chips">
        <span class="chip">Enterprise Account Mgmt</span><span class="chip">Onboarding &amp; Implementation</span>
        <span class="chip">Root Cause Analysis</span><span class="chip">Escalation Management</span>
        <span class="chip">Renewal &amp; Retention</span>
      </div>
    </div>
    <div class="module">
      <div class="mod-head"><span class="mod-dot"></span><h3>Team &amp; AI</h3></div>
      <div class="chips">
        <span class="chip">Cross-Functional Coordination</span><span class="chip">Mentoring</span>
        <span class="chip">AI Agent Building (Claude)</span><span class="chip">Workflow Automation</span>
        <span class="chip">Prompt Engineering</span>
      </div>
    </div>
  </div>
</section>

<section id="building">
  <div class="section-label">Side of Desk</div>
  <div class="log-head"><h2>Building Now</h2></div>
  <p class="log-sub">Projects I'm shipping outside the day job — same instinct for automating the repetitive stuff, pointed at my own workflow.</p>

  <div class="builds">
    <div class="build-card">
      <div class="kicker">In Progress</div>
      <h3>AI Prompt-Generator Web App</h3>
      <p>A Next.js + Supabase + Vercel app for structuring and reusing high-quality prompts — currently in local development, backend wiring in progress.</p>
    </div>
    <div class="build-card">
      <div class="kicker">Live</div>
      <h3>Support Ops AI Agents</h3>
      <p>Claude-based agents handling response drafting, conversation summarization, and documentation for day-to-day support and implementation work.</p>
    </div>
  </div>
</section>

<footer id="contact">
  <div class="footer-inner">
    <div class="contact-grid">
      <h2>Open to Senior Customer Success, Implementation, and Technical Support roles.</h2>
      <div class="contact-links">
        <a href="mailto:darshanashok.an7@gmail.com">darshanashok.an7@gmail.com</a>
        <a href="tel:+918073856141">+91 80738 56141</a>
        <a href="https://www.linkedin.com/in/darshan-an-4b6b14290" target="_blank" rel="noopener">linkedin.com/in/darshan-an-4b6b14290</a>
      </div>
    </div>
    <div class="sign-off">
      <span>© <span id="year"></span> Darshan A N — Bengaluru, India</span>
      <span>system status: accepting new tickets</span>
    </div>
  </div>
</footer>

<script>
  document.getElementById('year').textContent = new Date().getFullYear();
</script>

</body>
</html>
