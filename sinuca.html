<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>🎱 Sinuca 8 Ball - Buracos Maiores</title>
  <style>
    body {
      background: #064406;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      user-select: none;
    }
    canvas {
      background: #2e8b57;
      border: 12px solid #3b2b1b;
      border-radius: 20px;
      box-shadow: 0 0 30px rgba(0,0,0,0.6);
    }
    h1 {
      position: absolute;
      top: 10px;
      color: white;
      width: 100%;
      text-align: center;
      font-family: Arial, sans-serif;
    }
  </style>
</head>
<body>
  <h1>🎱 Sinuca 8 Ball - Jogador vs NPC (Buracos Maiores)</h1>
  <canvas id="mesa" width="900" height="500"></canvas>

  <script>
    const canvas = document.getElementById("mesa");
    const ctx = canvas.getContext("2d");

    const atrito = 0.985;
    const bolas = [];
    const buracos = [];
    const w = canvas.width;
    const h = canvas.height;

    let vezJogador = true;
    let jogando = false;
    let pontuacaoJogador = 0;
    let pontuacaoNPC = 0;

    class Bola {
      constructor(x, y, cor, numero = null) {
        this.x = x;
        this.y = y;
        this.raio = 12;
        this.vx = 0;
        this.vy = 0;
        this.cor = cor;
        this.numero = numero;
        this.ativa = true;
      }
      desenhar() {
        if (!this.ativa) return;
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.raio, 0, Math.PI * 2);
        ctx.fillStyle = this.cor;
        ctx.fill();
        ctx.strokeStyle = "#000";
        ctx.lineWidth = 1.5;
        ctx.stroke();
        ctx.closePath();

        if (this.numero !== null) {
          ctx.font = "bold 12px Arial";
          ctx.fillStyle = "white";
          ctx.textAlign = "center";
          ctx.textBaseline = "middle";
          ctx.strokeStyle = "black";
          ctx.lineWidth = 2;
          ctx.strokeText(this.numero, this.x, this.y + 1);
          ctx.fillText(this.numero, this.x, this.y + 1);
        }
      }
      mover() {
        if (!this.ativa) return;
        this.x += this.vx;
        this.y += this.vy;

        if (this.x - this.raio < 0 || this.x + this.raio > w) {
          this.vx *= -0.9;
          if (this.x - this.raio < 0) this.x = this.raio;
          if (this.x + this.raio > w) this.x = w - this.raio;
        }
        if (this.y - this.raio < 0 || this.y + this.raio > h) {
          this.vy *= -0.9;
          if (this.y - this.raio < 0) this.y = this.raio;
          if (this.y + this.raio > h) this.y = h - this.raio;
        }

        this.vx *= atrito;
        this.vy *= atrito;
        if (Math.abs(this.vx) < 0.05) this.vx = 0;
        if (Math.abs(this.vy) < 0.05) this.vy = 0;

        for (let b of buracos) {
          const dx = b.x - this.x;
          const dy = b.y - this.y;
          const dist = Math.hypot(dx, dy);
          if (dist < b.raio) {
            if (this.cor !== "white") {
              this.ativa = false;
              if (vezJogador) pontuacaoJogador++;
              else pontuacaoNPC++;
            } else {
              this.x = 120;
              this.y = h / 2;
              this.vx = 0;
              this.vy = 0;
            }
          }
        }
      }
    }

    class Buraco {
      constructor(x, y) {
        this.x = x;
        this.y = y;
        this.raio = 28; // 🔥 buracos maiores
      }
      desenhar() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.raio, 0, Math.PI * 2);
        ctx.fillStyle = "black";
        ctx.fill();
        ctx.closePath();
      }
    }

    // buracos
    buracos.push(new Buraco(0, 0));
    buracos.push(new Buraco(w / 2, 0));
    buracos.push(new Buraco(w, 0));
    buracos.push(new Buraco(0, h));
    buracos.push(new Buraco(w / 2, h));
    buracos.push(new Buraco(w, h));

    // bola branca
    const bolaBranca = new Bola(120, h / 2, "white", null);
    bolas.push(bolaBranca);

    // bolas numeradas
    const cores = [
      "#FFD700", "#FF0000", "#0000FF", "#FFA500",
      "#800080", "#008000", "#8B4513", "#000000"
    ];

    let startX = 700, startY = h / 2, n = 0;
    for (let linha = 0; linha < 5; linha++) {
      for (let col = 0; col <= linha; col++) {
        if (n < cores.length) {
          bolas.push(new Bola(startX + linha * 25, startY - linha * 12 + col * 25, cores[n], n + 1));
          n++;
        }
      }
    }

    function verificarColisoes() {
      for (let i = 0; i < bolas.length; i++) {
        for (let j = i + 1; j < bolas.length; j++) {
          const b1 = bolas[i];
          const b2 = bolas[j];
          if (!b1.ativa || !b2.ativa) continue;

          const dx = b2.x - b1.x;
          const dy = b2.y - b1.y;
          const dist = Math.hypot(dx, dy);
          const overlap = b1.raio + b2.raio - dist;

          if (overlap > 0) {
            const ang = Math.atan2(dy, dx);
            const total = (b1.vx - b2.vx) * Math.cos(ang) + (b1.vy - b2.vy) * Math.sin(ang);
            b1.vx -= total * Math.cos(ang);
            b1.vy -= total * Math.sin(ang);
            b2.vx += total * Math.cos(ang);
            b2.vy += total * Math.sin(ang);
            b1.x -= Math.cos(ang) * overlap / 2;
            b1.y -= Math.sin(ang) * overlap / 2;
            b2.x += Math.cos(ang) * overlap / 2;
            b2.y += Math.sin(ang) * overlap / 2;
          }
        }
      }
    }

    // controle do jogador
    let mouse = { x: 0, y: 0, clicando: false };
    let puxando = false;

    canvas.addEventListener("mousedown", e => {
      if (!vezJogador) return;
      mouse.clicando = true;
      puxando = true;
      mouse.x = e.offsetX;
      mouse.y = e.offsetY;
    });

    canvas.addEventListener("mouseup", e => {
      if (vezJogador && puxando) {
        const dx = mouse.x - bolaBranca.x;
        const dy = mouse.y - bolaBranca.y;
        bolaBranca.vx = dx * -0.15;
        bolaBranca.vy = dy * -0.15;
        puxando = false;
        vezJogador = false;
        jogando = true;
      }
      mouse.clicando = false;
    });

    canvas.addEventListener("mousemove", e => {
      mouse.x = e.offsetX;
      mouse.y = e.offsetY;
    });

    function todasParadas() {
      return bolas.every(b => Math.abs(b.vx) < 0.1 && Math.abs(b.vy) < 0.1);
    }

    function jogadaNPC() {
      const alvo = bolas.find(b => b.ativa && b.cor !== "white");
      if (!alvo) return;
      const dx = alvo.x - bolaBranca.x;
      const dy = alvo.y - bolaBranca.y;
      const ang = Math.atan2(dy, dx);
      bolaBranca.vx = Math.cos(ang) * 9;
      bolaBranca.vy = Math.sin(ang) * 9;
    }

    function loop() {
      ctx.clearRect(0, 0, w, h);
      for (let b of buracos) b.desenhar();

      verificarColisoes();
      for (let bola of bolas) {
        bola.mover();
        bola.desenhar();
      }

      if (puxando && vezJogador) {
        ctx.beginPath();
        ctx.moveTo(bolaBranca.x, bolaBranca.y);
        ctx.lineTo(mouse.x, mouse.y);
        ctx.strokeStyle = "rgba(255,255,255,0.6)";
        ctx.lineWidth = 2;
        ctx.stroke();
        ctx.closePath();
      }

      if (jogando && todasParadas()) {
        jogando = false;
        if (!vezJogador) {
          setTimeout(() => {
            jogadaNPC();
            vezJogador = true;
            jogando = true;
          }, 1000);
        }
      }

      ctx.font = "20px Arial";
      ctx.fillStyle = "white";
      ctx.fillText(`Você: ${pontuacaoJogador} | NPC: ${pontuacaoNPC}`, 20, 30);

      requestAnimationFrame(loop);
    }

    loop();
  </script>
</body>
</html>

