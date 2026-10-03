<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body {
      margin: 0;
      background: #111;
      display: flex;
      justify-content: center;
      padding-top: 30px;
      font-family: Arial, sans-serif;
    }

    .typing-wrap {
      text-align: center;
      width: 100%;
      max-width: 500px;
    }

    .typing-text {
      display: inline-block;
      font-size: clamp(1.2rem, 3vw, 1.8rem);
      font-weight: bold;
      line-height: 1.4;
      white-space: nowrap;
      background: linear-gradient(90deg, #7C3AED, #FACC15, #22C55E);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .cursor {
      display: inline-block;
      width: 2px;
      height: 1.1em;
      background: #fff;
      vertical-align: middle;
      margin-left: 4px;
      animation: blink 0.7s steps(1) infinite;
    }

    @keyframes blink {
      50% { opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="typing-wrap">
    <div class="typing-text">
      <span id="text"></span><span class="cursor"></span>
    </div>
  </div>

  <script>
    const phrases = [
      "As fast as a gallmius",
      "Hooray im not extinct!",
      "You got this!"
    ];

    let phraseIndex = 0;
    let charIndex = 0;
    let deleting = false;
    const textEl = document.getElementById("text");

    function typeLoop() {
      const current = phrases[phraseIndex];

      if (!deleting) {
        charIndex++;
        textEl.textContent = current.slice(0, charIndex);

        if (charIndex === current.length) {
          deleting = true;
          setTimeout(typeLoop, 1200);
          return;
        }
      } else {
        charIndex--;
        textEl.textContent = current.slice(0, charIndex);

        if (charIndex === 0) {
          deleting = false;
          phraseIndex = (phraseIndex + 1) % phrases.length;
        }
      }

      const speed = deleting ? 50 : 100;
      setTimeout(typeLoop, speed);
    }

    typeLoop();
  </script>
</body>
</html><img src="your-image.jpg" alt="image" style="width:100%; max-width:500px; display:block; margin:20px auto;" />
<img width="258" height="402" alt="Image" src="https://github.com/user-attachments/assets/e22d7d3d-4407-4c9e-a7fb-d7d4fae435e3" />
