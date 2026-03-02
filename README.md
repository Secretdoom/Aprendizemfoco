<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ATIVIDADE QUEM SOU EU - FUNDAÇÃO CDL</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/scrollreveal"></script>
    
    <style>
        :root {
            --bg: #0a0a0a;
            --accent: #ff3333; 
            --glass: rgba(30, 30, 30, 0.6);
            --border: rgba(255, 255, 255, 0.15);
            --text: #eeeeee;
            --number-color: #ffffff; /* Números agora bem claros */
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body { 
            background-color: var(--bg);
            color: var(--text);
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            line-height: 1.7;
        }

        #bg-glow {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 50%, rgba(255, 0, 0, 0.05) 0%, transparent 80%);
            z-index: -1;
        }

        .container { max-width: 850px; margin: 0 auto; padding: 0 25px; }

        header {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-start;
        }

        h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(3.5rem, 12vw, 7rem);
            font-weight: 900;
            letter-spacing: -2px;
            line-height: 0.9;
            color: #fff;
            margin-bottom: 15px;
        }

        .tagline {
            color: var(--accent);
            text-transform: uppercase;
            font-weight: 600;
            letter-spacing: 2px;
            font-size: 0.8rem;
            margin-bottom: 5px;
        }

        section {
            padding: 80px 0;
            border-bottom: 1px solid var(--border);
        }

        .step-info {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .number {
            font-family: 'Orbitron';
            font-size: 3rem;
            color: var(--number-color);
            font-weight: 900;
            opacity: 0.9;
        }

        h2 {
            font-size: 1.2rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #fff;
        }

        .content-box {
            background: var(--glass);
            padding: 35px;
            border-radius: 12px;
            border: 1px solid var(--border);
            backdrop-filter: blur(15px);
            transition: 0.4s;
        }

        .content-box:hover {
            border-color: var(--accent);
            transform: scale(1.01);
        }

        .family-img {
            width: 100%;
            max-width: 400px;
            border-radius: 8px;
            margin-bottom: 25px;
            border: 1px solid var(--accent);
            filter: contrast(1.1);
        }

        .btn-action {
            display: inline-block;
            background: #fff;
            color: #000;
            padding: 18px 35px;
            font-weight: 700;
            text-decoration: none;
            border-radius: 4px;
            margin-top: 50px;
            transition: 0.3s;
            font-family: 'Orbitron';
            font-size: 0.7rem;
        }

        .btn-action:hover {
            background: var(--accent);
            color: #fff;
            box-shadow: 0 10px 30px rgba(255, 51, 51, 0.4);
        }

        .footer-text {
            text-align: center;
            padding: 60px 0;
            font-size: 0.7rem;
            color: #555;
            letter-spacing: 1px;
        }

        @media (max-width: 600px) {
            h1 { font-size: 4rem; }
            .content-box { padding: 20px; }
            .number { font-size: 2.5rem; }
        }
    </style>
</head>
<body>

<div id="bg-glow"></div>

<div class="container">
    <header class="reveal">
        <p class="tagline">Atividade Quem Sou Eu - Fundação CDL</p>
        <h1>KAIO<br>CESAR</h1>
        <p style="color: #888; margin-top: 10px;">Foco no objetivo, fé no processo.</p>
    </header>

    <section>
        <div class="step-info">
            <span class="number">01</span>
            <h2 class="reveal">Quem sou eu hoje?</h2>
        </div>
        <div class="content-box reveal">
            <img src="https://i.imgur.com/ESmxwRf.jpeg" alt="Minha Família" class="family-img">
            <p>Eu me considero um cara muito firme com os meus valores. Minhas três qualidades principais são a educação com todo mundo, a minha humildade de saber de onde eu vim e o fato de eu ser um cara gente boa, que sabe trocar ideia com qualquer pessoa.</p>
        </div>
    </section>

    <section>
        <div class="step-info">
            <span class="number">02</span>
            <h2 class="reveal">O que preciso melhorar?</h2>
        </div>
        <div class="content-box reveal">
            <p>Quero aprender a ser mais estratégico. Meu objetivo é falar apenas o que for necessário para as pessoas certas, guardando meus planos para mim e focando mais na execução do que na fala.</p>
        </div>
    </section>

    <section>
        <div class="step-info">
            <span class="number">03</span>
            <h2 class="reveal">Quem me influencia?</h2>
        </div>
        <div class="content-box reveal">
            <p>Sem dúvidas, minha mãe é a pessoa que mais manda na minha forma de pensar. Essa influência me dá muita força, porque tudo o que eu faço desde os 13 anos, buscando crescer no mundo digital, é para dar uma vida melhor para ela e dar esse susto positivo nela com os meus resultados.</p>
        </div>
    </section>

    <section>
        <div class="step-info">
            <span class="number">04</span>
            <h2 class="reveal">Uma habilidade para o futuro</h2>
        </div>
        <div class="content-box reveal">
            <p>Preciso aprender a dominar minha ansiedade. Às vezes a gente quer que tudo aconteça agora, mas na prática eu vou começar a exercitar a paciência e manter a cabeça no lugar, focando no trabalho de hoje para colher amanhã.</p>
        </div>
    </section>

    <section>
        <div class="step-info">
            <span class="number">05</span>
            <h2 class="reveal">Carta para daqui a 5 anos</h2>
        </div>
        <div class="content-box reveal" style="border-left: 4px solid var(--accent);">
            <p>E aí, Kaio do futuro. Espero que você já esteja com sua equipe de divulgação a todo vapor e que a grana já esteja entrando firme. Você está se tornando aquele cara que cuida de todo mundo e que não esqueceu as raízes.</p>
            <p style="margin-top: 15px;">Tenho medo de você perder essa essência de moleque humilde, então não deixa o sucesso subir à cabeça. O conselho que eu te dou hoje é: continue sendo esse adulto que respeita os outros e não repita os erros de querer abraçar o mundo de uma vez. Devagar a gente chega lá.</p>
        </div>
    </section>

   

<script>
    ScrollReveal().reveal('.reveal', { 
        distance: '40px', duration: 1000, interval: 150, origin: 'bottom', opacity: 0 
    });
</script>

</body>
</html>
