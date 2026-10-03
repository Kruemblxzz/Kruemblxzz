<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Typing Text</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: grid;
      place-items: center;
      background: #111;
      color: white;
      font-family: Arial, sans-serif;
    }

    .typewriter {
      font-size: 2.2rem;
      font-weight: bold;
      letter-spacing: 0.04em;
      min-height: 3rem;
      white-space: nowrap;
    }

    .cursor {
      display: inline-block;
      width: 2px;
      height: 1.2em;
      background: #fff;
      animation: blink 0.7s infinite;
      vertical-align: middle;
      margin-left: 4px;
    }

    @keyframes blink {
      0%, 50% { opacity: 1; }
      51%, 100% { opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="typewriter">
    <span id="text"></span><span class="cursor"></span>
  </div>

  <script>
    const phrases = [
      "As fast as a gallimus",
      "Hooray, I'm not extinct!",
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

      const speed = deleting ? 50 : 110;
      setTimeout(typeLoop, speed);
    }

    typeLoop();
  </script>
</body>
</html>
<img width="258" height="402" alt="Image" src="https://github.com/user-attachments/assets/e22d7d3d-4407-4c9e-a7fb-d7d4fae435e3" />
