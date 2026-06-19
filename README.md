<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>✨ Bilal Rafique · dev profile</title>
  <!-- Font & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0b0d15;
      font-family: 'Fira Code', monospace;
      padding: 2rem 1.5rem;
      display: flex;
      justify-content: center;
      min-height: 100vh;
    }

    .profile-wrapper {
      max-width: 1200px;
      width: 100%;
      background: rgba(18, 22, 36, 0.7);
      backdrop-filter: blur(6px);
      border-radius: 48px;
      padding: 2.5rem 2rem;
      border: 1px solid rgba(255, 255, 255, 0.04);
      box-shadow: 0 30px 60px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(0, 255, 255, 0.05);
    }

    /* ---- TYPOGRAPHY & UTILITY ---- */
    .gradient-text {
      background: linear-gradient(135deg, #00f0ff 0%, #a855f7 50%, #ff44ec 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      display: inline-block;
    }

    .glass-panel {
      background: rgba(255, 255, 255, 0.03);
      backdrop-filter: blur(8px);
      border: 1px solid rgba(255, 255, 255, 0.06);
      border-radius: 32px;
      padding: 1.75rem 2rem;
      transition: 0.25s ease;
      box-shadow: 0 12px 30px -10px rgba(0, 0, 0, 0.6);
    }

    .glass-panel:hover {
      border-color: rgba(0, 240, 255, 0.2);
      box-shadow: 0 20px 40px -12px rgba(0, 240, 255, 0.08);
    }

    .badge-glow {
      transition: 0.2s;
      filter: drop-shadow(0 0 4px rgba(0, 240, 255, 0.2));
    }
    .badge-glow:hover {
      filter: drop-shadow(0 0 12px rgba(0, 240, 255, 0.5));
      transform: scale(1.02);
    }

    /* ---- TYPING BANNER ---- */
    .typing-banner {
      text-align: center;
      margin-bottom: 2rem;
    }
    .typing-banner img {
      max-width: 100%;
      height: auto;
    }

    /* ---- CODING GIF ---- */
    .gif-section {
      display: flex;
      justify-content: center;
      margin: 1.2rem 0 2rem 0;
    }
    .gif-section img {
      border-radius: 28px;
      max-width: 480px;
      width: 100%;
      box-shadow: 0 20px 40px -8px #00f0ff33, 0 0 0 1px rgba(0, 240, 255, 0.1);
      transition: 0.3s ease;
    }
    .gif-section img:hover {
      transform: scale(1.01);
      box-shadow: 0 30px 60px -10px #00f0ff55;
    }

    /* ---- DETAILS / ABOUT ---- */
    details {
      margin: 2.2rem 0 1.8rem 0;
      background: rgba(0, 0, 0, 0.25);
      border-radius: 32px;
      padding: 0.5rem 1.8rem 1.8rem 1.8rem;
      border: 1px solid rgba(255, 255, 255, 0.03);
    }
    details summary {
      font-size: 1.7rem;
      font-weight: 600;
      cursor: pointer;
      padding: 0.8rem 0 0.2rem 0;
      color: #c8d6e5;
      letter-spacing: -0.5px;
    }
    details summary h2 {
      display: inline-block;
      font-size: 1.7rem;
    }
    details p {
      color: #b0c4de;
      line-height: 1.8;
      font-size: 1.05rem;
    }
    details ul {
      list-style: none;
      margin-top: 0.8rem;
    }
    details ul li {
      color: #b8d0e8;
      padding: 0.35rem 0;
      font-size: 1.05rem;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    details ul li i {
      color: #00f0ff;
      width: 22px;
      font-size: 1.2rem;
    }

    /* ---- CONNECT BADGES ---- */
    .connect-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px 18px;
      margin: 1.8rem 0 2.5rem 0;
    }
    .connect-grid a {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: rgba(255, 255, 255, 0.02);
      backdrop-filter: blur(4px);
      padding: 0.6rem 1.4rem;
      border-radius: 60px;
      border: 1px solid rgba(255, 255, 255, 0.04);
      color: #d0dff0;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.9rem;
      transition: 0.2s;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
    }
    .connect-grid a i {
      font-size: 1.3rem;
      transition: 0.2s;
    }
    .connect-grid a:hover {
      background: rgba(0, 240, 255, 0.05);
      border-color: #00f0ff60;
      transform: translateY(-3px);
      box-shadow: 0 12px 24px -8px #00f0ff20;
    }
    .connect-grid a:hover i {
      transform: scale(1.1);
      color: #00f0ff;
    }

    /* ---- TECH CARDS ---- */
    .tech-section {
      margin: 2.5rem 0;
    }
    .tech-section h3 {
      font-size: 1.6rem;
      text-align: center;
      margin-bottom: 1.2rem;
      font-weight: 600;
    }

    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 16px 20px;
      background: rgba(0, 0, 0, 0.15);
      border-radius: 48px;
      padding: 1.5rem 1.8rem;
      border: 1px solid rgba(255, 255, 255, 0.02);
      backdrop-filter: blur(4px);
    }

    .tech-grid img {
      filter: drop-shadow(0 0 6px rgba(0, 240, 255, 0.15));
      transition: 0.2s;
    }
    .tech-grid img:hover {
      filter: drop-shadow(0 0 16px rgba(0, 240, 255, 0.4)) brightness(1.1);
      transform: scale(1.04);
    }

    .badge-stack {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px 14px;
      padding: 0.8rem 0;
    }
    .badge-stack img {
      transition: 0.2s;
      filter: drop-shadow(0 0 4px rgba(0, 240, 255, 0.1));
    }
    .badge-stack img:hover {
      filter: drop-shadow(0 0 14px rgba(0, 240, 255, 0.4));
      transform: translateY(-2px);
    }

    /* ---- STATS CARDS ---- */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 28px;
      margin: 2.8rem 0 1.8rem 0;
    }
    .stats-row > a {
      flex: 1 1 320px;
      transition: 0.25s;
    }
    .stats-row > a:hover {
      transform: scale(1.01);
    }
    .stats-row img {
      width: 100%;
      border-radius: 24px;
      box-shadow: 0 15px 35px -10px #000000aa;
      border: 1px solid rgba(255, 255, 255, 0.02);
    }

    .streak-wrapper {
      display: flex;
      justify-content: center;
      margin: 1.5rem 0 2.5rem 0;
    }
    .streak-wrapper img {
      border-radius: 24px;
      max-width: 100%;
      box-shadow: 0 15px 35px -8px #000000bb;
      border: 1px solid rgba(255, 255, 255, 0.02);
    }

    .profile-details-3d {
      display: flex;
      justify-content: center;
      margin: 2rem 0 1.8rem 0;
    }
    .profile-details-3d img {
      border-radius: 28px;
      width: 90%;
      max-width: 1000px;
      border: 1px solid rgba(255, 255, 255, 0.02);
      box-shadow: 0 20px 40px -12px #000000cc;
    }

    /* ---- QUOTE & SNAKE ---- */
    .quote-box {
      display: flex;
      justify-content: center;
      margin: 2.5rem 0 1.8rem 0;
    }
    .quote-box img {
      max-width: 80%;
      border-radius: 48px;
      filter: drop-shadow(0 8px 20px rgba(0, 0, 0, 0.5));
    }

    .snake-container {
      margin: 2rem 0 0.5rem 0;
      background: rgba(0, 0, 0, 0.2);
      border-radius: 48px;
      padding: 12px 0;
      border: 1px solid rgba(255, 255, 255, 0.02);
    }
    .snake-container img {
      width: 100%;
      border-radius: 32px;
      opacity: 0.9;
    }

    .footer-wave {
      margin-top: 2rem;
      opacity: 0.7;
    }
    .footer-wave img {
      width: 100%;
    }

    /* ---- RESPONSIVE ---- */
    @media (max-width: 700px) {
      .profile-wrapper { padding: 1.5rem 1rem; }
      details { padding: 0.2rem 1rem 1.2rem 1rem; }
      .connect-grid a { padding: 0.4rem 1rem; font-size: 0.8rem; }
      .tech-grid { padding: 1rem; gap: 10px; }
      .glass-panel { padding: 1.2rem; }
    }
  </style>
</head>
<body>
<div class="profile-wrapper">

  <!-- ===== TYPING BANNER ===== -->
  <div class="typing-banner">
    <a href="https://github.com/bilal-157">
      <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=26&duration=3500&pause=1000&color=00F0FF&center=true&vCenter=true&width=900&height=70&lines=Hi%2C+I'm+Bilal+Rafique;Full-Stack+Next.js+Developer;AI+%26+Data+Science+Explorer;Open-Source+Contributor;Coding+with+passion+%F0%9F%92%BB" alt="Typing animation" />
    </a>
  </div>

  <!-- ===== CODING GIF ===== -->
  <div class="gif-section">
    <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" alt="Coding animation" />
  </div>

  <!-- ===== ABOUT (details) ===== -->
  <details open>
    <summary><h2 style="display:inline-block;">🌟 About Me</h2></summary>
    <ul>
      <li><i class="fas fa-rocket"></i> 🔭 I'm currently working on <strong>AI-powered web applications</strong></li>
      <li><i class="fas fa-brain"></i> 🌱 Learning <strong>Deep Learning &amp; Advanced System Design</strong></li>
      <li><i class="fas fa-lightbulb"></i> 💡 Passionate about <strong>solving complex problems with elegant solutions</strong></li>
      <li><i class="fas fa-handshake"></i> 👯 Looking to collaborate on <strong>open-source projects</strong></li>
      <li><i class="fas fa-cube"></i> ⚡ Fun fact: <strong>I can solve a Rubik's cube in under 2 minutes</strong></li>
      <li><i class="fas fa-code"></i> Curious – exploring modern API development beyond REST</li>
    </ul>
  </details>

  <!-- ===== CONNECT BADGES ===== -->
  <div class="connect-grid">
    <a href="https://discord.gg/bugs119"><i class="fab fa-discord"></i> Discord</a>
    <a href="https://www.facebook.com/share/1B3TzGo6Wu/"><i class="fab fa-facebook"></i> Facebook</a>
    <a href="https://instagram.com/bilal_rafique_11"><i class="fab fa-instagram"></i> Instagram</a>
    <a href="https://www.linkedin.com/in/muhammadbilal711"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
    <a href="mailto:rafiqueb087@gmail.com"><i class="fas fa-envelope"></i> Email</a>
    <a href="https://codeforces.com/profile/bilal_rafi"><i class="fas fa-code"></i> Codeforces</a>
    <a href="https://cses.fi/user/340387/"><i class="fas fa-graduation-cap"></i> CSES</a>
    <a href="https://leetcode.com/u/Bilal157/"><i class="fas fa-terminal"></i> LeetCode</a>
  </div>

  <!-- ===== TECH STACK ===== -->
  <div class="tech-section">
    <h3 class="gradient-text">🌐 Frontend Development</h3>
    <div class="tech-grid">
      <img src="https://skillicons.dev/icons?i=html,css,js,react,nextjs,tailwind,bootstrap&perline=7&theme=light" alt="Frontend" style="max-width:100%;" />
    </div>

    <div style="margin: 1.8rem 0 1.2rem 0;">
      <h3 class="gradient-text" style="background: linear-gradient(135deg,#ff44ec,#00f0ff);">⚙️ Backend &amp; AI</h3>
      <div class="tech-grid" style="margin-top:0.8rem;">
        <img src="https://skillicons.dev/icons?i=nodejs,express,flask,django,mongodb,postgresql,graphql,fastapi,py,cpp,cs,php&perline=9&theme=light" alt="Backend" />
      </div>
    </div>

    <div style="margin: 1.8rem 0 0.8rem 0;">
      <h3 class="gradient-text" style="background: linear-gradient(135deg,#00f0ff,#a855f7);">🛠️ Tools &amp; Deployment</h3>
      <div class="tech-grid" style="margin-top:0.8rem;">
        <img src="https://skillicons.dev/icons?i=git,github,postman,vercel,heroku,netlify,vscode,docker,nginx&perline=7&theme=light" alt="Tools" />
      </div>
    </div>

    <!-- extra badges (glassmorphism table) -->
    <div style="display:flex; flex-wrap:wrap; justify-content:center; gap:20px; margin:2rem 0 0.5rem 0;">
      <div class="glass-panel" style="flex:1 1 280px; padding:1.2rem 1.5rem;">
        <div style="color:#b0c4de; font-weight:600; margin-bottom:12px;">🧩 Core</div>
        <div class="badge-stack">
          <img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white" />
          <img src="https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white" />
          <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" />
          <img src="https://img.shields.io/badge/PHP-777BB4?logo=php&logoColor=white" />
        </div>
      </div>
      <div class="glass-panel" style="flex:1 1 280px; padding:1.2rem 1.5rem;">
        <div style="color:#b0c4de; font-weight:600; margin-bottom:12px;">⚡ Frameworks &amp; DB</div>
        <div class="badge-stack">
          <img src="https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black" />
          <img src="https://img.shields.io/badge/Next.js-000000?logo=next.js&logoColor=white" />
          <img src="https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white" />
          <img src="https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white" />
        </div>
      </div>
      <div class="glass-panel" style="flex:1 1 280px; padding:1.2rem 1.5rem;">
        <div style="color:#b0c4de; font-weight:600; margin-bottom:12px;">🤖 AI &amp; ML</div>
        <div class="badge-stack">
          <img src="https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white" />
          <img src="https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white" />
          <img src="https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white" />
          <img src="https://img.shields.io/badge/Keras-D00000?logo=keras&logoColor=white" />
        </div>
      </div>
    </div>
  </div>

  <!-- ===== SNAKE ===== -->
  <div class="snake-container">
    <img src="https://raw.githubusercontent.com/platane/platane/output/github-contribution-grid-snake.svg" alt="snake" />
  </div>

  <!-- ===== GITHUB STATS ===== -->
  <h2 align="center" style="margin:2rem 0 0.5rem 0; color:#d0e0ff;">📊 GitHub Stats</h2>
  <div class="stats-row">
    <a href="https://github.com/bilal-157">
      <img src="https://github-readme-stats.vercel.app/api?username=bilal-157&show_icons=true&theme=radical&include_all_commits=true&count_private=true&border_radius=16" alt="GitHub Stats" />
    </a>
    <a href="https://github.com/bilal-157">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=bilal-157&layout=compact&langs_count=8&theme=radical&border_radius=16" alt="Top Languages" />
    </a>
  </div>

  <div class="streak-wrapper">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=bilal-157&theme=radical&border_radius=16&fire=DD2727" alt="GitHub Streak" />
  </div>

  <!-- 3D contribution graph -->
  <div class="profile-details-3d">
    <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=bilal-157&theme=radical" alt="3D Contribution" />
  </div>

  <!-- ===== QUOTE ===== -->
  <div class="quote-box">
    <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical&animation=grow_out_in" alt="Dev Quote" />
  </div>

  <!-- ===== FOOTER WAVE ===== -->
  <div class="footer-wave">
    <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&section=footer&animation=fadeIn" alt="footer wave" />
  </div>

</div>
</body>
</html>
