<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Karlos Daniel – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --border: #21262d;
    --accent: #58a6ff;
    --green: #3fb950;
    --orange: #f78166;
    --yellow: #e3b341;
    --purple: #bc8cff;
    --text: #e6edf3;
    --muted: #8b949e;
    --card: #1c2128;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 40px 20px;
  }

  .wrapper {
    width: 100%;
    max-width: 860px;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  /* HEADER */
  .header {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 32px 36px;
    position: relative;
    overflow: hidden;
  }

  .header::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(88,166,255,0.10) 0%, transparent 70%);
    pointer-events: none;
  }

  .header-top {
    display: flex;
    align-items: center;
    gap: 24px;
    margin-bottom: 24px;
  }

  .avatar {
    width: 80px; height: 80px;
    border-radius: 50%;
    border: 2px solid var(--accent);
    display: flex; align-items: center; justify-content: center;
    font-size: 38px;
    flex-shrink: 0;
    box-shadow: 0 0 20px rgba(88,166,255,0.2);
    background: #161b22;
    overflow: hidden;
  }

  .header-info h1 {
    font-family: 'Syne', sans-serif;
    font-size: 26px;
    font-weight: 800;
    color: var(--text);
    letter-spacing: -0.5px;
  }

  .header-info .handle {
    color: var(--accent);
    font-size: 13px;
    margin-top: 2px;
  }

  .header-info .badge-row {
    display: flex;
    gap: 8px;
    margin-top: 10px;
    flex-wrap: wrap;
  }

  .badge {
    background: rgba(88,166,255,0.1);
    border: 1px solid rgba(88,166,255,0.25);
    color: var(--accent);
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 20px;
    white-space: nowrap;
  }

  .badge.green { background: rgba(63,185,80,0.1); border-color: rgba(63,185,80,0.3); color: var(--green); }
  .badge.purple { background: rgba(188,140,255,0.1); border-color: rgba(188,140,255,0.3); color: var(--purple); }
  .badge.orange { background: rgba(247,129,102,0.1); border-color: rgba(247,129,102,0.3); color: var(--orange); }

  .greeting {
    font-family: 'Syne', sans-serif;
    font-size: 20px;
    font-weight: 600;
    margin-bottom: 14px;
  }

  .about-text {
    font-size: 13px;
    line-height: 1.8;
    color: #c9d1d9;
    margin-bottom: 20px;
  }

  .about-text strong { color: var(--accent); }
  .about-text .highlight { color: var(--yellow); font-weight: 500; }

  /* CODE BLOCK */
  .code-block {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    font-size: 13px;
    line-height: 1.9;
    position: relative;
  }

  .code-block .copy-btn {
    position: absolute;
    top: 10px; right: 10px;
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--muted);
    border-radius: 6px;
    padding: 4px 8px;
    font-size: 11px;
    cursor: pointer;
    font-family: 'JetBrains Mono', monospace;
    transition: color 0.2s, border-color 0.2s;
  }

  .code-block .copy-btn:hover { color: var(--accent); border-color: var(--accent); }

  .kw { color: #ff7b72; }
  .cl { color: var(--yellow); }
  .str { color: var(--green); }
  .prop { color: var(--accent); }
  .punct { color: var(--muted); }

  .meta-row {
    display: flex;
    gap: 20px;
    margin-top: 18px;
    flex-wrap: wrap;
  }

  .meta-item {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 12px;
    color: var(--muted);
  }

  /* SECTION */
  .section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px 28px;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* TECH BADGES */
  .tech-group {
    display: flex;
    flex-direction: column;
    gap: 18px;
  }

  .tech-row-label {
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .tech-row-label::before { content: '•'; color: var(--accent); }

  .tech-pills {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .pill {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 6px;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.5px;
    border: none;
    cursor: default;
    transition: transform 0.15s, box-shadow 0.15s;
  }

  .pill:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 14px rgba(0,0,0,0.4);
  }

  .pill.java   { background: #e76f00; color: #fff; }
  .pill.html   { background: #e34c26; color: #fff; }
  .pill.css    { background: #264de4; color: #fff; }
  .pill.spring { background: #6db33f; color: #fff; }
  .pill.mysql  { background: #00758f; color: #fff; }
  .pill.git    { background: #f05032; color: #fff; }
  .pill.github { background: #333; color: #fff; border: 1px solid #555; }
  .pill.figma  { background: #a259ff; color: #fff; }
  .pill.trello { background: #0052cc; color: #fff; }

  /* ANIMATIONS */
  .wrapper > * {
    animation: slideUp 0.5s ease both;
  }
  .wrapper > *:nth-child(1) { animation-delay: 0.05s; }
  .wrapper > *:nth-child(2) { animation-delay: 0.15s; }
  .wrapper > *:nth-child(3) { animation-delay: 0.25s; }

  @keyframes slideUp {
    from { opacity: 0; transform: translateY(18px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 600px) {
    .header-top { flex-direction: column; text-align: center; }
    .badge-row { justify-content: center; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="header-top">
      <div class="avatar">🧑‍💻</div>
      <div class="header-info">
        <h1>Karlos Daniel</h1>
        <div class="handle">@karlos-19 · karlosd832@gmail.com</div>
        <div class="badge-row">
          <span class="badge">🏛️ UNICEPLAC</span>
          <span class="badge green">🇧🇷 Brazil</span>
          <span class="badge purple">4º Semestre</span>
          <span class="badge orange">Backend Developer</span>
        </div>
      </div>
    </div>

    <div class="greeting">Karlos Daniel</div>

    <div class="about-text">
      Me chamo Karlos Daniel, tenho grande interesse pela área de tecnologia. Atualmente estudo programação,
      com foco em <strong>Java</strong>, <strong>SpringBoot</strong>, <strong>Banco de Dados</strong> e desenvolvimento web com
      <strong>HTML</strong> e <strong>CSS</strong>, buscando evoluir através de projetos práticos e aprendizado contínuo.
      Também tenho interesse em <span class="highlight">hardware de computadores</span>, explorando diferentes aspectos da tecnologia.
      Cursando engenharia de Software pela Uniceplac, atualmente estou no 4º Semestre.
    </div>

    <div class="code-block">
      <button class="copy-btn" onclick="copyCode(this)">⎘ copy</button>
      <div>
        <span class="kw">public class</span> <span class="cl">Me</span> <span class="punct">{</span>
      </div>
      <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">String</span> name &nbsp;&nbsp;&nbsp;= <span class="str">"Karlos Daniel"</span><span class="punct">;</span></div>
      <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">String</span> workArea = <span class="str">"Backend Developer"</span><span class="punct">;</span></div>
      <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="prop">String</span> email &nbsp;&nbsp;= <span class="str">"karlosd832@gmail.com"</span><span class="punct">;</span></div>
      <div><span class="punct">}</span></div>
    </div>

    <div class="meta-row">
      <div class="meta-item">0 followers · 1 following</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-title">🧠 Tech Stack</div>
    <div class="tech-group">

      <div>
        <div class="tech-row-label">Languages and Frameworks</div>
        <div class="tech-pills">
          <span class="pill java">☕ JAVA</span>
          <span class="pill html">🌐 HTML</span>
          <span class="pill css">🎨 CSS</span>
          <span class="pill spring">🍃 SPRING</span>
        </div>
      </div>

      <div>
        <div class="tech-row-label">Databases</div>
        <div class="tech-pills">
          <span class="pill mysql">🐬 MYSQL</span>
        </div>
      </div>

      <div>
        <div class="tech-row-label">Softwares and Tools</div>
        <div class="tech-pills">
          <span class="pill git">🔀 GIT</span>
          <span class="pill github">🐙 GITHUB</span>
          <span class="pill figma">🎭 FIGMA</span>
          <span class="pill trello">📋 TRELLO</span>
        </div>
      </div>

    </div>
  </div>

</div>

<script>
  function copyCode(btn) {
    const code = `public class Me {\n    String name     = "Karlos Daniel";\n    String workArea = "Backend Developer";\n    String email    = "karlosd832@gmail.com";\n}`;
    navigator.clipboard.writeText(code).then(() => {
      btn.textContent = '✓ copied';
      setTimeout(() => btn.textContent = '⎘ copy', 2000);
    });
  }
</script>
</body>
</html>
