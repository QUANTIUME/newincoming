# newincoming
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Magical Flower Nursery</title>
  <style>
    :root{
      --sakura:#f7c6d9;
      --peach:#ffe5d4;
      --lilac:#e6d9ff;
      --butter:#fff4c2;
      --glow: rgba(255,255,255,0.6);
    }

    *{box-sizing:border-box}

    body{
      margin:0;
      min-height:100vh;
      font-family: 'Segoe UI', 'Poppins', sans-serif;
      background: radial-gradient(circle at top, var(--butter), var(--peach), var(--sakura), var(--lilac));
      overflow:hidden;
      color:#6b4b5a;
    }

    .nursery{
      position:relative;
      width:100%;
      height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
    }

    .card{
      background: rgba(255,255,255,0.45);
      backdrop-filter: blur(14px);
      border-radius:32px;
      padding:48px 56px;
      box-shadow: 0 20px 60px rgba(255,182,193,0.25);
      text-align:center;
      max-width:520px;
      animation: float 6s ease-in-out infinite;
    }

    h1{
      font-size:2.6rem;
      margin:0 0 12px;
      letter-spacing:1px;
    }

    p{
      font-size:1.05rem;
      line-height:1.7;
      opacity:0.9;
    }

    .flowers{
      position:absolute;
      inset:0;
      pointer-events:none;
    }

    .flower{
      position:absolute;
      width:18px;
      height:18px;
      background: radial-gradient(circle, #fff, #ffd6e8);
      border-radius:50%;
      box-shadow: 0 0 12px var(--glow);
      animation: sway 5s ease-in-out infinite, bloom 8s ease-in-out infinite;
    }

    .flower::after{
      content:'';
      position:absolute;
      inset:-6px;
      border-radius:50%;
      background: radial-gradient(circle, rgba(255,255,255,0.8), transparent 70%);
      opacity:0.6;
    }

    .petal{
      position:absolute;
      width:14px;
      height:14px;
      background: linear-gradient(145deg, #ffeaf3, #f7c6d9);
      border-radius: 60% 40% 60% 40%;
      opacity:0.6;
      animation: fall 18s linear infinite;
    }

    @keyframes sway{
      0%,100%{transform:translateX(0)}
      50%{transform:translateX(8px)}
    }

    @keyframes bloom{
      0%,100%{transform:scale(0.6)}
      50%{transform:scale(1)}
    }

    @keyframes fall{
      0%{transform:translateY(-10vh) rotate(0deg)}
      100%{transform:translateY(110vh
