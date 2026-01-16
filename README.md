#LET TRY SOMETHING NEWWWWWWWWWW
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>Bloom</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root {
  --bg: #050805;
  --green: #0f2e1a;
  --neon: #3cff8f;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: var(--bg);
  overflow: hidden;
  font-family: 'Segoe UI', system-ui, sans-serif;
}

.scene {
  position: relative;
  width: 100vw;
  height: 100vh;
  background: radial-gradient(circle at center, #07150d 0%, #050805 60%);
}

/* subtle cyber grid */
.scene::before {
  content: "";
  position: absolute;
  inset: 0;
  background:
    linear-gradient(to right, rgba(60,255,143,0.04) 1px, transparent 1px),
    linear-gradient(to top, rgba(60,255,143,0.04) 1px, transparent 1px);
  background-size: 80px 80px;
  opacity: 0.15;
}

/* flower container */
.flower {
  position: absolute;
  bottom: -150px;
  left: 50%;
  transform: translateX(-50%);
  animation: rise 22s linear infinite;
}

/* stem */
.stem {
  width: 4px;
  height: 0;
  background: linear-gradient(to top, var(--green), var(--neon));
  margin: 0 auto;
  animation: growStem 6s ease-out forwards;
}

/* bloom */
.bloom {
  width: 40px;
  height: 40px;
  position: relative;
  margin: 0 auto;
  transform: scale(0);
  animation: bloom 6s ease-out forwards;
  animation-delay: 2s;
}

.petal {
  position: absolute;
  width: 20px;
  height: 30px;
  background: radial-gradient(circle at center, var(--neon), var(--green));
  border-radius: 50% 50% 50% 50%;
  transform-origin: bottom center;
  opacity: 0.9;
  filter: drop-shadow(0 0 6px rgba(60,255,143,0.4));
}

.petal:nth-child(1) { transform: rotate(0deg) translateY(-15px); }
.petal:nth-child(2) { transform: rotate(60deg) translateY(-15px); }
.petal:nth-child(3) { transform: rotate(120deg) translateY(-15px); }
.petal:nth-child(4) { transform: rotate(180deg) translateY(-15px); }
.petal:nth-child(5) { transform: rotate(240deg) translateY(-15px); }
.petal:nth-child(6) { transform: rotate(300deg) translateY(-15px); }

/* animations */
@keyframes rise {
  from { bottom: -200px; }
  to { bottom: 120vh; }
}

@keyframes growStem {
  from { height: 0; }
  to { height: 160px; }
}

@keyframes bloom {
  from { transform: scale(0); }
  to { transform: scale(1); }
}

/* soft breathing motion */
.flower {
  animation-timing-function: ease-in-out;
}

@keyframes breathe {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

/* typography */
.title {
  position: absolute;
  top: 12%;
  width: 100%;
  text-align: center;
  font-size: 2rem;
  letter-spacing: 0.3em;
  color: rgba(200,255,220,0.6);
  opacity: 0;
  animation: fadeIn 6s ease forwards;
}

@keyframes fadeIn {
  to { opacity: 1; }
}
</style>
</head>

<body>
<div class="scene">
  <div class="title">BLOOM</div>

  <div class="flower">
    <div class="bloom">
      <div class="petal"></div>
      <div class="petal"></div>
      <div class="petal"></div>
      <div class="petal"></div>
      <div class="petal"></div>
      <div class="petal"></div>
    </div>
    <div class="stem"></div>
  </div>
</div>
</body>
</html>
