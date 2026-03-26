<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>BSC_DPDM2025 — Tullathorn Sangchangwang</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Syne:wght@400;500;600;700&display=swap');

  :root {
    --navy-950: #040d1a;
    --navy-900: #071428;
    --navy-800: #0d2145;
    --navy-700: #122d5e;
    --navy-600: #1a3d7a;
    --navy-500: #2452a0;
    --navy-400: #3368c4;
    --navy-300: #5b8ee0;
    --navy-200: #93b8f2;
    --navy-100: #cde0fb;
    --navy-50:  #e8f2fe;
    --accent: #4a9eff;
    --accent-dim: rgba(74,158,255,0.12);
    --gold: #c9a227;
    --gold-dim: rgba(201,162,39,0.15);
    --text-primary: #e8f2fe;
    --text-secondary: #7aa8d8;
    --text-muted: #4a6b94;
    --surface-1: rgba(13,33,69,0.9);
    --surface-2: rgba(7,20,40,0.95);
    --border: rgba(74,158,255,0.18);
    --border-strong: rgba(74,158,255,0.35);
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--navy-950);
    color: var(--text-primary);
    font-family: var(--sans);
    font-size: 14px;
    line-height: 1.6;
    min-height: 100vh;
  }

  .root {
    max-width: 780px;
    margin: 0 auto;
    padding: 32px 24px 60px;
  }

  .header {
    border-bottom: 1px solid var(--border);
    padding-bottom: 28px;
    margin-bottom: 32px;
    position: relative;
  }
  .header::before {
    content: '';
    position: absolute;
    top: 0; left: -24px; right: -24px;
    height: 3px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--gold), var(--accent), transparent);
  }

  .course-tag {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .course-tag::before {
    content: '';
    display: block;
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
  }

  .name-block h1 {
    font-size: 26px;
    font-weight: 700;
    color: var(--text-primary);
    letter-spacing: -0.02em;
    line-height: 1.2;
  }
  .name-block .student-id {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-muted);
    margin-top: 4px;
    letter-spacing: 0.08em;
  }

  .header-meta {
    display: flex;
    gap: 10px;
    margin-top: 16px;
    flex-wrap: wrap;
  }
  .tag {
    font-family: var(--mono);
    font-size: 11px;
    padding: 4px 10px;
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--text-secondary);
    background: var(--accent-dim);
    letter-spacing: 0.05em;
  }
  .tag.gold {
    border-color: rgba(201,162,39,0.3);
    background: var(--gold-dim);
    color: var(--gold);
  }

  .section-title {
    font-family: var(--mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--text-muted);
    margin-bottom: 14px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .section-title span { color: var(--accent); }

  .grade-table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 32px;
    font-size: 13px;
  }
  .grade-table th {
    font-family: var(--mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--text-muted);
    padding: 8px 12px;
    text-align: left;
    border-bottom: 1px solid var(--border);
    font-weight: 500;
  }
  .grade-table td {
    padding: 10px 12px;
    border-bottom: 1px solid rgba(74,158,255,0.07);
    color: var(--text-secondary);
  }
  .grade-table tr:hover td {
    background: var(--accent-dim);
    color: var(--text-primary);
  }
  .grade-table .comp { color: var(--text-primary); font-weight: 500; }
  .grade-table .weight {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--accent);
    font-weight: 700;
  }
  .grade-table .total td {
    border-top: 1px solid var(--border-strong);
    border-bottom: none;
    color: var(--text-primary);
    font-weight: 600;
  }
  .grade-table .total .weight { color: var(--gold); }

  .grade-bar {
    height: 3px;
    background: rgba(255,255,255,0.06);
    border-radius: 2px;
    overflow: hidden;
    width: 80px;
  }
  .grade-bar-fill {
    height: 100%;
    border-radius: 2px;
    background: var(--accent);
  }

  .focus-notes {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-bottom: 32px;
  }
  .focus-card {
    background: var(--surface-1);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 12px 14px;
    font-size: 12px;
  }
  .focus-card .label {
    font-family: var(--mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--accent);
    margin-bottom: 4px;
  }
  .focus-card .value { color: var(--text-primary); }

  .chapter-list { margin-bottom: 32px; }
  .chapter-item {
    border: 1px solid var(--border);
    border-radius: 6px;
    margin-bottom: 8px;
    overflow: hidden;
  }
  .chapter-header {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 14px;
    cursor: pointer;
    background: var(--surface-1);
    transition: background 0.15s;
    user-select: none;
  }
  .chapter-header:hover { background: var(--surface-2); }
  .ch-num {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
    background: var(--accent-dim);
    border: 1px solid rgba(74,158,255,0.25);
    padding: 2px 7px;
    border-radius: 3px;
    min-width: 36px;
    text-align: center;
    letter-spacing: 0.05em;
  }
  .ch-title {
    flex: 1;
    font-size: 13px;
    font-weight: 500;
    color: var(--text-primary);
  }
  .ch-arrow {
    font-size: 10px;
    color: var(--text-muted);
    transition: transform 0.2s;
  }
  .chapter-item.open .ch-arrow { transform: rotate(90deg); }
  .chapter-files {
    display: none;
    padding: 8px 14px 12px 62px;
    background: var(--navy-900);
    border-top: 1px solid var(--border);
  }
  .chapter-item.open .chapter-files { display: block; }
  .file-link {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 7px 0;
    border-bottom: 1px solid rgba(74,158,255,0.06);
    font-size: 12px;
    color: var(--text-secondary);
    text-decoration: none;
    transition: color 0.15s;
  }
  .file-link:last-child { border-bottom: none; }
  .file-link:hover { color: var(--accent); }
  .file-link::before { content: '↗'; font-size: 11px; color: var(--text-muted); }
  .file-link:hover::before { color: var(--accent); }

  .tools-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 32px;
  }
  .tool-badge {
    font-family: var(--mono);
    font-size: 11px;
    padding: 5px 10px;
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--text-secondary);
    background: var(--surface-1);
    letter-spacing: 0.04em;
    transition: all 0.15s;
  }
  .tool-badge:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: var(--accent-dim);
  }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    margin-bottom: 32px;
  }
  .about-item {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    padding: 10px 12px;
    background: var(--surface-1);
    border: 1px solid var(--border);
    border-radius: 6px;
    font-size: 12px;
    color: var(--text-secondary);
  }
  .about-dot {
    width: 5px; height: 5px;
    min-width: 5px;
    background: var(--accent);
    border-radius: 50%;
    margin-top: 5px;
  }

  .project-card {
    background: var(--surface-1);
    border: 1px solid var(--border-strong);
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 32px;
    position: relative;
    overflow: hidden;
  }
  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--gold));
  }
  .project-title {
    font-size: 16px;
    font-weight: 600;
    color: var(--text-primary);
    margin-bottom: 6px;
  }
  .project-desc {
    font-size: 12px;
    color: var(--text-secondary);
    margin-bottom: 20px;
    line-height: 1.7;
  }
  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }
  .sub-section-title {
    font-family: var(--mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--accent);
    margin-bottom: 10px;
  }
  .model-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .model-list li {
    font-size: 12px;
    color: var(--text-secondary);
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .model-list li::before {
    content: '';
    width: 4px; height: 4px;
    background: var(--accent);
    border-radius: 50%;
    flex-shrink: 0;
  }
  .method-steps {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .step {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    font-size: 12px;
    color: var(--text-secondary);
  }
  .step-num {
    font-family: var(--mono);
    font-size: 10px;
    color: var(--accent);
    background: var(--accent-dim);
    border: 1px solid rgba(74,158,255,0.2);
    width: 18px; height: 18px;
    border-radius: 3px;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    margin-top: 1px;
  }
  .files-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 12px;
    margin-top: 4px;
  }
  .files-table th {
    font-family: var(--mono);
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--text-muted);
    padding: 6px 8px;
    text-align: left;
    border-bottom: 1px solid var(--border);
  }
  .files-table td {
    padding: 8px;
    color: var(--text-secondary);
    border-bottom: 1px solid rgba(74,158,255,0.06);
  }
  .files-table tr:last-child td { border-bottom: none; }
  .files-table a {
    color: var(--accent);
    text-decoration: none;
    font-family: var(--mono);
    font-size: 11px;
  }
  .files-table a:hover { text-decoration: underline; }

  .footer {
    border-top: 1px solid var(--border);
    padding-top: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .footer-left, .footer-right {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.08em;
  }
</style>
</head>
<body>
<div class="root">

  <div class="header">
    <div class="course-tag">BSC_DPDM2025</div>
    <div class="name-block">
      <h1>Tullathorn Sangchangwang</h1>
      <div class="student-id">ID: 653020207-7 &nbsp;·&nbsp; Statistics (SIDS)</div>
    </div>
    <div class="header-meta">
      <span class="tag">Data Mining</span>
      <span class="tag">Machine Learning</span>
      <span class="tag">Deep Learning</span>
      <span class="tag gold">2025</span>
    </div>
  </div>

  <div class="section-title"><span>#</span> Grading Criteria</div>
  <table class="grade-table">
    <thead>
      <tr><th>Component</th><th>Type</th><th>Weight</th><th></th></tr>
    </thead>
    <tbody>
      <tr><td class="comp">Midterm Exam</td><td>Individual</td><td class="weight">25%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:25%"></div></div></td></tr>
      <tr><td class="comp">Final Exam</td><td>Individual</td><td class="weight">25%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:25%"></div></div></td></tr>
      <tr><td class="comp">Project</td><td>Group (5–6)</td><td class="weight">20%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:20%"></div></div></td></tr>
      <tr><td class="comp">Homework</td><td>Group</td><td class="weight">15%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:15%"></div></div></td></tr>
      <tr><td class="comp">Quiz</td><td>Individual</td><td class="weight">10%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:10%"></div></div></td></tr>
      <tr><td class="comp">GitHub</td><td>Individual</td><td class="weight">5%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:5%"></div></div></td></tr>
      <tr class="total"><td class="comp">Total</td><td></td><td class="weight">100%</td><td><div class="grade-bar"><div class="grade-bar-fill" style="width:100%;background:var(--gold)"></div></div></td></tr>
    </tbody>
  </table>

  <div class="focus-notes">
    <div class="focus-card">
      <div class="label">Midterm Focus</div>
      <div class="value">Data Preprocessing</div>
    </div>
    <div class="focus-card">
      <div class="label">Final Focus</div>
      <div class="value">Data Mining Theory</div>
    </div>
  </div>

  <div class="section-title"><span>#</span> Course Summary</div>
  <div class="chapter-list">

    <div class="chapter-item open">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH01</span>
        <span class="ch-title">Introduction to Data Mining</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/1aaVCedJanliM5n5OWRUkT80MLxjLLlhQ/view?usp=sharing" target="_blank">Introduction</a>
      </div>
    </div>

    <div class="chapter-item">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH02</span>
        <span class="ch-title">Getting to Know Your Data</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/1Dq4gisr4jFebXpReG7uuHLi7o1Zl_xWV/view?usp=sharing" target="_blank">Slide All</a>
      </div>
    </div>

    <div class="chapter-item">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH03</span>
        <span class="ch-title">Data Preprocessing</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/1FVVC57X7owO17ui5fDZI7HhsertR-f08/view?usp=sharing" target="_blank">Summary</a>
        <a class="file-link" href="https://drive.google.com/file/d/19NfVH6HnF96tP5JqaxwXWtbiQklkkXg7/view?usp=drivesdk" target="_blank">Noisy Data</a>
      </div>
    </div>

    <div class="chapter-item">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH06</span>
        <span class="ch-title">Mining Frequent Patterns</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/1kF3gWHYe3WvlpE1zis_C3_TvvMCwASez/view?usp=sharing" target="_blank">Slide All</a>
      </div>
    </div>

    <div class="chapter-item">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH08</span>
        <span class="ch-title">Classification</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/1PqFUDrgULUaT5XL7PCL6a7yDH4F5LBID/view?usp=drivesdk" target="_blank">Decision Tree</a>
        <a class="file-link" href="https://drive.google.com/file/d/1vJT-5cTIPkwryUKN7uTTreXcwqpAmLif/view?usp=sharing" target="_blank">Naive Bayes</a>
        <a class="file-link" href="https://drive.google.com/file/d/1ve5BpoZ6yBWwyFkt2dqOPzMDtavA0ax1/view?usp=sharing" target="_blank">Model Evaluation</a>
      </div>
    </div>

    <div class="chapter-item">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH09</span>
        <span class="ch-title">Advanced Methods</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/19OIUvZv1X1P7hbrygBOrFzkNeJoVrbXB/view?usp=sharing" target="_blank">Advanced Methods</a>
        <a class="file-link" href="https://drive.google.com/file/d/1JjiBAIgmbjXqM2AYOeVzBF6xdGo3CMmi/view?usp=sharing" target="_blank">Neural Network</a>
      </div>
    </div>

    <div class="chapter-item">
      <div class="chapter-header" onclick="toggle(this)">
        <span class="ch-num">CH10</span>
        <span class="ch-title">Cluster Analysis</span>
        <span class="ch-arrow">▶</span>
      </div>
      <div class="chapter-files">
        <a class="file-link" href="https://drive.google.com/file/d/1UZcF0agO2kMs_tnMHGOYvSqfbORRu5gQ/view?usp=sharing" target="_blank">K-Means</a>
        <a class="file-link" href="https://drive.google.com/file/d/1FAjsTTxVQG409cufkqwiNVAiqAN5gZgK/view?usp=sharing" target="_blank">Hierarchical</a>
      </div>
    </div>

  </div>

  <div class="section-title"><span>#</span> Tools & Stack</div>
  <div class="tools-grid">
    <span class="tool-badge">Python</span>
    <span class="tool-badge">Scikit-learn</span>
    <span class="tool-badge">Pandas</span>
    <span class="tool-badge">NumPy</span>
    <span class="tool-badge">Matplotlib</span>
    <span class="tool-badge">Google Colab</span>
    <span class="tool-badge">GitHub</span>
    <span class="tool-badge">VS Code</span>
  </div>

  <div class="section-title"><span>#</span> About</div>
  <div class="about-grid">
    <div class="about-item"><div class="about-dot"></div>Statistics (SIDS) Student</div>
    <div class="about-item"><div class="about-dot"></div>Data Analytics &amp; ML interest</div>
    <div class="about-item"><div class="about-dot"></div>Studying Data Mining and AI</div>
    <div class="about-item"><div class="about-dot"></div>Goal: Data Scientist</div>
  </div>

  <div class="section-title"><span>#</span> Project</div>
  <div class="project-card">
    <div class="project-title">Rainfall Prediction using Machine Learning</div>
    <div class="project-desc">Development of a Machine Learning model for rainfall forecasting using historical meteorological data and climate indices (ENSO, IOD, MJO). Models evaluated via K-Fold cross-validation.</div>
    <div class="two-col">
      <div>
        <div class="sub-section-title">Models</div>
        <ul class="model-list">
          <li>Neural Network (ANN) &amp; LSTM</li>
          <li>Huber Regressor</li>
          <li>K-Nearest Neighbors (KNN)</li>
          <li>Isotonic Regression</li>
        </ul>
      </div>
      <div>
        <div class="sub-section-title">Methodology</div>
        <div class="method-steps">
          <div class="step"><span class="step-num">1</span><span>Data Collection</span></div>
          <div class="step"><span class="step-num">2</span><span>Preprocessing &amp; Feature Selection</span></div>
          <div class="step"><span class="step-num">3</span><span>Model Training</span></div>
          <div class="step"><span class="step-num">4</span><span>K-Fold Cross Validation</span></div>
          <div class="step"><span class="step-num">5</span><span>Model Evaluation</span></div>
        </div>
      </div>
    </div>
    <div class="sub-section-title" style="margin-top:16px">Project Files</div>
    <table class="files-table">
      <thead>
        <tr><th>Resource</th><th>Type</th><th>Link</th></tr>
      </thead>
      <tbody>
        <tr><td>Dataset</td><td>Google Drive</td><td><a href="https://drive.google.com/drive/folders/1Mo47ug7ByaXYZ13tFSONCGlyVoqXeH8a?usp=sharing" target="_blank">Open ↗</a></td></tr>
        <tr><td>Code — LSTM</td><td>Colab</td><td><a href="https://colab.research.google.com/drive/1Gk9EuEXXChMSldHtSLonOcCopUQimXit?usp=sharing" target="_blank">Open ↗</a></td></tr>
        <tr><td>Code — All Models</td><td>Colab</td><td><a href="https://colab.research.google.com/drive/1m6jP76rvJyuHxTIxoO4yJwRiwqcLzMIx?usp=sharing" target="_blank">Open ↗</a></td></tr>
        <tr><td>Report Slide</td><td>PDF</td><td><a href="https://drive.google.com/file/d/1EGUkvyuSD3w1NyALzxHgD9EYzTjplGx7/view?usp=sharing" target="_blank">Open ↗</a></td></tr>
      </tbody>
    </table>
  </div>

  <div class="footer">
    <div class="footer-left">BSC_DPDM2025</div>
    <div class="footer-right">Tullathorn Sangchangwang · 653020207-7</div>
  </div>

</div>
<script>
function toggle(header) {
  header.parentElement.classList.toggle('open');
}
</script>
</body>
</html>
