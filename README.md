
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For Gladys ✨</title>
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --primary-glow: #fda4af;
      --accent-rose: #f43f5e;
      --text-main: #fff1f2;
      --text-muted: #fecdd3;
      --glass-bg: rgba(18, 12, 16, 0.65);
      --glass-border: rgba(255, 255, 255, 0.15);
      --glass-shadow: 0 30px 60px -12px rgba(0, 0, 0, 0.6);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      min-height: 100vh;
      color: var(--text-main);
      background-color: #0d090b;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
      position: relative;
      padding: 2rem 1rem;
    }

    /* Fixed Fullscreen Background Image */
    .bg-wrapper {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      background-image: 
        linear-gradient(180deg, rgba(13, 9, 11, 0.5) 0%, rgba(13, 9, 11, 0.88) 100%),
        url("image_0.png");
      background-size: cover;
      background-position: center 25%;
      background-repeat: no-repeat;
      filter: contrast(1.05) brightness(0.85);
      transform: scale(1.02);
      animation: subtleZoom 25s infinite alternate ease-in-out;
    }

    @keyframes subtleZoom {
      0% { transform: scale(1); }
      100% { transform: scale(1.08); }
    }

    /* Interactive Canvas Background */
    #ambient-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 1;
    }

    /* Main Card Container */
    .main-card {
      width: 100%;
      max-width: 560px;
      background: var(--glass-bg);
      backdrop-filter: blur(25px);
      -webkit-backdrop-filter: blur(25px);
      border: 1px solid var(--glass-border);
      border-radius: 32px;
      padding: 3rem 2.2rem;
      text-align: center;
      box-shadow: var(--glass-shadow);
      animation: cardEntrance 1.2s cubic-bezier(0.16, 1, 0.3, 1);
      position: relative;
      z-index: 2;
      transition: transform 0.3s ease;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 0.45rem 1.2rem;
      background: rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.18);
      border-radius: 50px;
      font-size: 0.75rem;
      font-weight: 500;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 2rem;
    }

    /* Polaroid Photo Element */
    .polaroid-wrapper {
      position: relative;
      width: 170px;
      height: 210px;
      margin: 0 auto 2rem auto;
      background: #ffffff;
      padding: 10px 10px 35px 10px;
      border-radius: 8px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.5);
      transform: rotate(-2deg);
      transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1);
      cursor: pointer;
    }

    .polaroid-wrapper:hover {
      transform: rotate(0deg) scale(1.05);
      box-shadow: 0 20px 45px rgba(244, 63, 94, 0.3);
    }

    .polaroid-img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center 20%;
      border-radius: 4px;
      filter: grayscale(100%) contrast(1.1);
      transition: filter 0.6s ease;
    }

    .polaroid-wrapper:hover .polaroid-img {
      filter: grayscale(0%) contrast(1);
    }

    .polaroid-caption {
      position: absolute;
      bottom: 8px;
      left: 0;
      width: 100%;
      text-align: center;
      font-family: 'Cinzel', serif;
      font-size: 0.75rem;
      color: #333;
      letter-spacing: 1px;
    }

    h1 {
      font-family: 'Cinzel', serif;
      font-size: clamp(2.2rem, 5vw, 2.8rem);
      font-weight: 600;
      letter-spacing: 1px;
      line-height: 1.25;
      color: #ffffff;
      margin-bottom: 1rem;
    }

    h1 span {
      display: block;
      color: var(--primary-glow);
      font-style: italic;
      font-weight: 400;
    }

    p.subtitle {
      font-size: 0.95rem;
      line-height: 1.8;
      color: var(--text-muted);
      font-weight: 300;
      margin-bottom: 2rem;
    }

    /* Message Card Box */
    .message-container {
      min-height: 120px;
      background: rgba(0, 0, 0, 0.25);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 20px;
      padding: 1.5rem 1.2rem;
      margin-bottom: 2rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    .message-text {
      font-family: 'Cinzel', serif;
      font-size: 1rem;
      line-height: 1.8;
      color: var(--primary-glow);
      font-style: italic;
    }

    .typing-cursor {
      display: inline-block;
      width: 2px;
      height: 1rem;
      background-color: var(--primary-glow);
      margin-left: 4px;
      animation: blink 0.8s infinite;
      vertical-align: middle;
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }

    .message-counter {
      font-size: 0.7rem;
      color: rgba(255, 255, 255, 0.4);
      margin-top: 0.8rem;
      letter-spacing: 1.5px;
      text-transform: uppercase;
    }

    /* Interactive Buttons */
    .btn-action {
      background: linear-gradient(135deg, rgba(244, 63, 94, 0.85), rgba(225, 29, 72, 0.95));
      color: #ffffff;
      border: 1px solid rgba(255, 255, 255, 0.25);
      padding: 0.95rem 2rem;
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-size: 0.9rem;
      font-weight: 600;
      letter-spacing: 0.5px;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 10px 25px rgba(244, 63, 94, 0.35);
      transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
    }

    .btn-action:hover {
      transform: translateY(-2px) scale(1.02);
      box-shadow: 0 15px 30px rgba(244, 63, 94, 0.5);
    }

    .btn-action:active {
      transform: translateY(1px) scale(0.98);
    }

    @keyframes cardEntrance {
      from {
        opacity: 0;
        transform: translateY(30px) scale(0.97);
      }
      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    /* Click Particle Explosion */
    .burst-particle {
      position: fixed;
      pointer-events: none;
      z-index: 100;
      animation: particleExplode 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    @keyframes particleExplode {
      0% {
        transform: translate(0, 0) scale(1) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translate(var(--dx), var(--dy)) scale(0) rotate(180deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="bg-wrapper"></div>
  <canvas id="ambient-canvas"></canvas>

  <main class="main-card">
    <div class="badge">
      <span>✨</span> Happy Girlfriend's Day
    </div>

    <div class="polaroid-wrapper">
      <img src="image_0.jpeg" alt="Gladys" class="polaroid-img">
      <span class="polaroid-caption">Gladys ❤️</span>
    </div>

    <h1>
      Celebrating You,
      <span>Gladys</span>
    </h1>

    <p class="subtitle">
      To the one who brings warmth, elegance, and effortless grace into every single moment.
    </p>

    <!-- Multi-Message Carousel -->
    <div class="message-container">
      <div class="message-text">
        <span id="typed-text"></span><span class="typing-cursor"></span>
      </div>
      <div class="message-counter" id="message-counter">Message 1 of 4</div>
    </div>

    <button class="btn-action" id="nextBtn">
      Read Next Message ✨
    </button>
  </main>

  <script>
    // 1. Customized Messages for Gladys
    const messages = [
      "\"Thank you for being the quiet beauty in my chaos and the brightest light in my world. Happy Girlfriend’s Day, my love.\"",
      "\"Every moment with you feels like poetry. Your smile effortlessly makes every single day better.\"",
      "\"You carry so much warmth and grace wherever you go. I'm endlessly grateful for you, Gladys.\"",
      "\"Today is all about celebrating you—your laugh, your heart, and everything that makes you, YOU! 💕\""
    ];

    let currentMsgIndex = 0;
    let charIndex = 0;
    let isTyping = false;
    const typedTextElement = document.getElementById('typed-text');
    const messageCounter = document.getElementById('message-counter');
    const nextBtn = document.getElementById('nextBtn');

    // Smooth Typewriter Animation Function
    function typeMessage(text) {
      isTyping = true;
      typedTextElement.textContent = "";
      charIndex = 0;

      function typeChar() {
        if (charIndex < text.length) {
          typedTextElement.textContent += text.charAt(charIndex);
          charIndex++;
          setTimeout(typeChar, 35); // Typing speed
        } else {
          isTyping = false;
        }
      }
      typeChar();
    }

    // Initial Load
    typeMessage(messages[0]);

    // Carousel Button Action
    nextBtn.addEventListener('click', (e) => {
      if (isTyping) return; // Prevent clicking mid-type

      currentMsgIndex = (currentMsgIndex + 1) % messages.length;
      typeMessage(messages[currentMsgIndex]);
      messageCounter.textContent = `Message ${currentMsgIndex + 1} of ${messages.length}`;

      triggerParticleBurst(e);
    });

    // 2. High-Performance Smooth Canvas Physics (Floating Orbs + Mouse Trails)
    const canvas = document.getElementById('ambient-canvas');
    const ctx = canvas.getContext('2d');
    let particles = [];
    let mouseTrail = [];

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();

    class Particle {
      constructor() {
        this.reset();
      }

      reset() {
        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;
        this.size = Math.random() * 2.5 + 0.5;
        this.alpha = Math.random() * 0.5 + 0.1;
        this.speedY = -Math.random() * 0.3 - 0.05;
        this.speedX = (Math.random() - 0.5) * 0.2;
      }

      update() {
        this.y += this.speedY;
        this.x += this.speedX;
        if (this.y < -10 || this.x < -10 || this.x > canvas.width + 10) {
          this.reset();
          this.y = canvas.height + 10;
        }
      }

      draw() {
        ctx.fillStyle = `rgba(254, 205, 211, ${this.alpha})`;
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
        ctx.fill();
      }
    }

    for (let i = 0; i < 50; i++) {
      particles.push(new Particle());
    }

    // Interactive Mouse Trail
    window.addEventListener('mousemove', (e) => {
      if (Math.random() > 0.6) {
        mouseTrail.push({
          x: e.clientX,
          y: e.clientY,
          size: Math.random() * 3 + 1,
          alpha: 0.8,
          color: '#fda4af'
        });
      }
    });

    function renderCanvas() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      // Render Floating Canvas Sparkles
      particles.forEach(p => {
        p.update();
        p.draw();
      });

      // Render Mouse Trail
      for (let i = 0; i < mouseTrail.length; i++) {
        const t = mouseTrail[i];
        ctx.fillStyle = `rgba(253, 164, 175, ${t.alpha})`;
        ctx.beginPath();
        ctx.arc(t.x, t.y, t.size, 0, Math.PI * 2);
        ctx.fill();

        t.alpha -= 0.02;
        t.size *= 0.96;

        if (t.alpha <= 0) {
          mouseTrail.splice(i, 1);
          i--;
        }
      }

      requestAnimationFrame(renderCanvas);
    }
    renderCanvas();

    // 3. Particle Burst on Button Click
    function triggerParticleBurst(e) {
      const rect = nextBtn.getBoundingClientRect();
      const centerX = rect.left + rect.width / 2;
      const centerY = rect.top + rect.height / 2;
      const icons = ['✨', '💖', '🌸', '💕', '🌹'];

      for (let i = 0; i < 18; i++) {
        const particle = document.createElement('div');
        particle.classList.add('burst-particle');
        particle.innerText = icons[Math.floor(Math.random() * icons.length)];

        const angle = (Math.PI * 2 / 18) * i;
        const velocity = Math.random() * 110 + 60;
        const dx = Math.cos(angle) * velocity + 'px';
        const dy = Math.sin(angle) * velocity + 'px';

        particle.style.left = centerX + 'px';
        particle.style.top = centerY + 'px';
        particle.style.setProperty('--dx', dx);
        particle.style.setProperty('--dy', dy);
        particle.style.fontSize = (Math.random() * 0.6 + 0.8) + 'rem';

        document.body.appendChild(particle);

        setTimeout(() => particle.remove(), 1200);
      }
    }
  </script>
</body>
</html>
