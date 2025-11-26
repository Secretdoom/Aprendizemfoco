<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CDL Aprendiz em Foco | Jornal Interativo</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    
    <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        /* ---------------------------------- */
        /* 1. VARIÁVEIS E ESTILOS GERAIS (Tema Azul Escuro Profissional) */
        /* ---------------------------------- */
        :root {
            --primary-blue: #092C48;    /* Azul Escuro Principal */
            --secondary-blue: #143F64;  /* Azul Mais Claro para Cartões */
            --highlight-blue: #0084ff;  /* Azul de Destaque Vibrante */
            --text-light: #f8f9fa;      /* Texto Claro */
            --text-dark: #ced4da;       /* Texto Secundário Claro */
            --border-color: #275276;    /* Borda sutil */
            --background-body: #051A30; /* Fundo do Body */
            --font-body: 'Open Sans', sans-serif;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: var(--font-body);
            line-height: 1.6;
            color: var(--text-light);
            background-color: var(--background-body);
        }
        h2, h3 { color: var(--text-light); font-weight: 700; margin-bottom: 0.8em; }
        main { padding-top: 70px; }

        /* ---------------------------------- */
        /* 2. CABEÇALHO E NAVEGAÇÃO */
        /* ---------------------------------- */
        .main-header {
            background-color: var(--primary-blue); padding: 10px 5%; display: flex; justify-content: space-between;
            align-items: center; border-bottom: 2px solid var(--highlight-blue); 
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
            position: fixed; width: 100%; top: 0; z-index: 100;
        }
        .logo { height: 50px; width: auto; border-radius: 4px; }
        .logo-container { display: flex; align-items: center; }
        .logo-container h1 { font-size: 1.6em; color: var(--text-light); margin-left: 10px; font-weight: 600; }
        .main-nav ul { list-style: none; display: flex; }
        .main-nav ul li a {
            text-decoration: none; color: var(--text-dark); font-weight: 600;
            padding: 10px 15px; transition: color 0.3s, background-color 0.3s;
            border-radius: 4px;
        }
        .main-nav ul li a:hover { color: var(--text-light); background-color: var(--secondary-blue); }
        
        /* 3. SEÇÕES DE CONTEÚDO E TÍTULOS */
        .section-title { 
            text-align: center; margin-bottom: 50px; 
            font-size: 2.2em; border-bottom: 3px solid var(--highlight-blue);
            padding-bottom: 10px; max-width: 600px; margin-left: auto; margin-right: auto;
            color: var(--highlight-blue);
        }
        .news-section, .journal-section, .interactive-section { padding: 60px 5%; }
        .journal-section, .interactive-section { background-color: var(--primary-blue); }

        /* --- Cartões de Notícia (Com Animação Profissional) --- */
        .news-item {
            display: flex; align-items: center; gap: 40px; margin-bottom: 50px;
            padding: 30px; border-radius: 10px; background-color: var(--secondary-blue);
            border: 1px solid var(--border-color); 
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3); 
            transition: transform 0.3s ease, box-shadow 0.3s ease; /* Animação */
        }
        .news-item:hover { 
            transform: translateY(-5px); 
            box-shadow: 0 12px 30px rgba(0, 132, 255, 0.25); /* Sombra azul mais suave */
        }
        .news-item:nth-child(even) { flex-direction: row-reverse; background-color: var(--primary-blue); }
        .news-item-image { flex: 1; min-width: 280px; max-width: 40%; }
        .news-item-image img { 
            width: 100%; height: auto; border-radius: 8px; 
            object-fit: cover; border: 3px solid var(--highlight-blue); 
            box-shadow: 0 0 15px rgba(0, 132, 255, 0.3);
        }
        .news-item-content { flex: 2; }
        .news-item-content h3 { margin-top: 0; font-size: 1.8em; color: var(--text-light); }
        .news-item-content p { color: var(--text-dark); }
        
        /* Botões dos Jogos */
        .btn-action {
            display: inline-block; background-color: var(--highlight-blue); color: var(--text-light);
            padding: 10px 25px; text-decoration: none; border-radius: 50px; 
            margin-top: 20px; font-weight: 700; 
            box-shadow: 0 4px 10px rgba(0, 132, 255, 0.4);
            transition: background-color 0.3s, transform 0.2s, box-shadow 0.3s;
            border: none;
            cursor: pointer;
        }
        .btn-action:hover { background-color: #0069d9; transform: translateY(-2px); box-shadow: 0 6px 15px rgba(0, 132, 255, 0.6); }

        /* ---------------------------------- */
        /* 4. SEÇÃO DO JORNAL (Imagens) */
        /* ---------------------------------- */
        .journal-section { text-align: center; }
        .journal-grid { 
            display: grid; 
            grid-template-columns: 1fr 1fr; 
            gap: 30px; 
            max-width: 1200px; 
            margin: 40px auto; 
        }
        .journal-page {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease, box-shadow 0.3s ease; /* Animação */
        }
        .journal-page:hover {
            transform: scale(1.02);
            box-shadow: 0 15px 40px rgba(0, 132, 255, 0.25);
        }
        .journal-grid img { 
            width: 100%; 
            height: auto; 
            display: block;
            border: 1px solid var(--border-color);
        }
        .journal-title {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.7);
            color: var(--text-light);
            padding: 10px;
            font-weight: 600;
            font-size: 1.1em;
        }

        /* ---------------------------------- */
        /* 5. ESPAÇO INTERATIVO (Caça-Palavras e Sudoku) */
        /* ---------------------------------- */
        .games-container { display: flex; justify-content: center; flex-wrap: wrap; gap: 40px; margin-top: 30px; }
        .game-box {
            background: var(--primary-blue); padding: 30px; border-radius: 10px; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            width: 100%; max-width: 550px; border: 1px solid var(--border-color); 
            text-align: left;
        }
        .game-box h3 { text-align: center; margin-bottom: 25px; color: var(--highlight-blue); border-bottom: 2px solid var(--border-color); padding-bottom: 10px; }

        /* Caça-Palavras Específico (Corrigido o Grid CSS) */
        .word-search-grid {
            /* Definido grid-template-columns explicitamente para corrigir a falha de visualização */
            display: grid; 
            grid-template-columns: repeat(18, 25px); 
            grid-template-rows: repeat(12, 25px);
            gap: 1px; 
            border: 2px solid var(--highlight-blue); 
            margin: 20px auto; 
            max-width: fit-content;
            background-color: var(--border-color);
        }
        .word-search-cell {
            width: 25px; height: 25px; display: flex; justify-content: center; align-items: center;
            font-size: 0.8em; font-weight: 700; text-transform: uppercase; cursor: pointer;
            background-color: var(--secondary-blue); color: var(--text-light); 
            border: none;
            transition: background-color 0.1s; user-select: none;
        }
        .word-search-cell.selected { background-color: var(--highlight-blue); color: #FFF; } 
        .word-search-cell.found { 
            background-color: #28a745; 
            color: #FFF; 
            font-weight: 700; 
            animation: pulse-found 0.5s ease-out; /* Animação ao encontrar a palavra */
        } 
        @keyframes pulse-found {
            0% { box-shadow: 0 0 0 0 rgba(40, 167, 69, 0.7); }
            70% { box-shadow: 0 0 0 10px rgba(40, 167, 69, 0); }
            100% { box-shadow: 0 0 0 0 rgba(40, 167, 69, 0); }
        }
        .word-list { list-style: none; padding: 0; display: flex; flex-wrap: wrap; gap: 5px 20px; margin-top: 15px; font-size: 1em; color: var(--text-dark); }
        .word-list li { font-weight: 600; }
        .word-list li.found { text-decoration: line-through; color: #6c757d; }

        /* Sudoku Específico */
        .sudoku-grid {
            display: grid; grid-template-columns: repeat(9, 35px); grid-template-rows: repeat(9, 35px);
            gap: 0; border: 3px solid var(--highlight-blue); margin: 20px auto; max-width: fit-content;
        }
        .sudoku-cell { width: 35px; height: 35px; display: flex; justify-content: center; align-items: center; font-size: 1.1em; font-weight: 700; border: 1px solid var(--border-color); }
        .sudoku-cell input { 
            width: 100%; height: 100%; text-align: center; font-size: 1.1em; font-weight: 700; 
            border: none; background-color: var(--secondary-blue); color: var(--text-light); 
            outline: none;
        }
        .sudoku-cell.fixed { background-color: var(--primary-blue); color: var(--text-light); pointer-events: none; }
        .sudoku-grid .cell-border-right { border-right: 3px solid var(--highlight-blue) !important; }
        .sudoku-grid .cell-border-bottom { border-bottom: 3px solid var(--highlight-blue) !important; }
        .sudoku-buttons { text-align: center; margin-top: 25px; }
        .btn-solve { background-color: #dc3545; border-color: #dc3545; }
        .btn-solve:hover { background-color: #c82333; }

        /* ---------------------------------- */
        /* 6. RODAPÉ e RESPONSIVO */
        /* ---------------------------------- */
        .main-footer { 
            background-color: var(--primary-blue); color: var(--text-dark); 
            padding: 30px 5%; text-align: center; margin-top: 0; 
            border-top: 2px solid var(--border-color); 
            font-size: 0.9em;
        }
        @media (max-width: 768px) {
            .main-header { flex-direction: column; position: static; padding-bottom: 10px; }
            main { padding-top: 0; }
            .section-title { font-size: 1.8em; margin-bottom: 30px; }
            .news-item, .news-item:nth-child(even) { flex-direction: column; gap: 20px; align-items: center; text-align: center; padding: 20px; }
            .news-item-image { max-width: 100%; min-width: auto; }
            .journal-grid { grid-template-columns: 1fr; }
            
            /* Ajuste de tamanho para jogos em telas menores */
            .word-search-grid { grid-template-columns: repeat(18, 18px); grid-template-rows: repeat(12, 18px); }
            .word-search-cell { width: 18px; height: 18px; font-size: 0.7em; }
            .sudoku-grid { grid-template-columns: repeat(9, 30px); grid-template-rows: repeat(9, 30px); }
            .sudoku-cell { width: 30px; height: 30px; font-size: 0.9em; }
        }
    </style>
</head>
<body>
    <header class="main-header">
        <div class="logo-container">
            <img src="https://files.catbox.moe/39ztvw.jpg" alt="CDL Aprendiz em Foco Logo" class="logo">
            <h1>APRENDIZ EM FOCO</h1>
        </div>
        <nav class="main-nav">
            <ul>
                <li><a href="#noticias"><i class="fas fa-bullhorn"></i> Notícias</a></li>
                <li><a href="#aprende-jovem"><i class="fas fa-gamepad"></i> Jogos</a></li>
                <li><a href="#jornal"><i class="fas fa-newspaper"></i> Jornal Completo</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="noticias" class="news-section">
            <h2 class="section-title"><i class="fas fa-star"></i> Destaques e Iniciativas CDL</h2>
            
            <article class="news-item">
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/0fuurz.jpg" alt="Aprendizes em Palestra sobre Legado Negro">
                </div>
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-calendar-alt"></i> EVENTO | 20 NOV, 2025</span>
                    <h3>Jovens Aprendizes e o Legado da Consciência Negra</h3>
                    <p>Nossos jovens aprendizes participaram de uma inspiradora palestra sobre a importância da Consciência Negra e o legado de figuras históricas como Luís Gama, promovendo a inclusão e o conhecimento na nossa comunidade.</p>
                </div>
            </article>

            <article class="news-item">
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-laptop-code"></i> PROGRAMA | TECNOLOGIA</span>
                    <h3>CDL Capacita: Mulheres no TI</h3>
                    <p>O programa exclusivo "Mulheres no TI" da CDL oferece capacitação intensiva para aprendizes, preparando-as para as demandas do mercado de tecnologia e garantindo alta empregabilidade no setor.</p>
                </div>
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/e9t6a1.jpg" alt="Grupo de jovens mulheres aprendizes em aula de TI">
                </div>
            </article>
        </section>

        <section id="aprende-jovem" class="interactive-section">
            <h2 class="section-title"><i class="fas fa-brain"></i> Espaço Interativo: Aprenda Jovem</h2>
            
            <div class="games-container">
                <div class="game-box">
                    <h3>Caça Palavras</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Instrução:** Clique na **primeira** letra e depois na **última** letra da palavra para marcá-la em verde.</p>
                    <div class="word-search-grid" id="wordSearchGrid"></div>
                    <h4 style="margin-top: 20px; color: var(--text-light); font-weight: 600;">Palavras a encontrar:</h4>
                    <ul class="word-list" id="wordList"></ul>
                    <div class="word-search-buttons" style="text-align: center;">
                        <button class="btn-action" onclick="resetWordSearch()"><i class="fas fa-redo-alt"></i> Reiniciar</button>
                    </div>
                </div>

                <div class="game-box">
                    <h3>Sudoku</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Regras:** Preencha de 1 a 9 sem repetir na linha, coluna ou bloco 3x3.</p>
                    <div class="sudoku-grid" id="sudokuGrid"></div>
                    <div class="sudoku-buttons">
                        <button class="btn-action" onclick="checkSudoku()"><i class="fas fa-check-square"></i> Verificar</button>
                        <button class="btn-action btn-solve" onclick="solveSudoku()"><i class="fas fa-lightbulb"></i> Resolver</button>
                        <button class="btn-action" onclick="resetSudoku()"><i class="fas fa-redo-alt"></i> Limpar</button>
                    </div>
                </div>
            </div>
        </section>

        <section id="jornal" class="journal-section">
            <h2 class="section-title"><i class="fas fa-book-open"></i> Edição Completa do Jornal</h2>
            <p style="color: var(--text-dark); margin-bottom: 30px;">Confira as páginas originais da nossa última edição do "Aprendiz em Foco".</p>
            
            <div class="journal-grid">
                <div class="journal-page">
                    <img src="https://files.catbox.moe/yylpix.jpg" alt="Página 1 do Jornal CDL Aprendiz em Foco">
                    <div class="journal-title">PÁGINA 1: DESTAQUES</div>
                </div>
                <div class="journal-page">
                    <img src="https://files.catbox.moe/jacct5.jpg" alt="Página 2 do Jornal CDL Aprendiz em Foco (Jogos)">
                    <div class="journal-title">PÁGINA 2: INTERATIVIDADE</div>
                </div>
            </div>
        </section>
    </main>

    <footer class="main-footer">
        <p><i class="fas fa-copyright"></i> 2025 CDL Aprendiz em Foco. Todos os direitos reservados.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // ESSENCIAL: Cria as grades assim que a página é carregada
            createWordSearchGrid();
            createSudokuGrid();
        });


        // --- LÓGICA DO CAÇA-PALAVRAS (2-CLIQUES) ---
        const wordSearchGridElement = document.getElementById('wordSearchGrid');
        const wordListElement = document.getElementById('wordList');
        // A palavra "INCLUSÃO" está na lista, mas sem acento na grade, por isso a normalização é vital.
        const wordsToFind = ['VULNERABILIDADE', 'PROJETO', 'JOVEM', 'NATAL', 'INCLUSÃO', 'HABILIDADES', 'TECNOLOGIA', 'PALESTRA'];
        let foundWords = [];
        let firstClick = null; 

        // Dados da Grade (extraído da imagem do jornal)
        const gridData = [
            ['E', 'M', 'P', 'R', 'E', 'G', 'A', 'B', 'I', 'L', 'I', 'D', 'A', 'D', 'E', 'R', 'A', 'D'],
            ['H', 'V', 'P', 'J', 'O', 'V', 'E', 'M', 'A', 'S', 'C', 'L', 'C', 'B', 'S', 'P', 'S', 'E'],
            ['A', 'U', 'A', 'T', 'E', 'C', 'N', 'O', 'L', 'O', 'G', 'I', 'A', 'I', 'R', 'A', 'I', 'S'],
            ['B', 'L', 'L', 'C', 'O', 'R', 'E', 'M', 'R', 'U', 'N', 'X', 'M', 'B', 'E', 'L', 'S', 'M'],
            ['I', 'N', 'E', 'S', 'I', 'N', 'C', 'L', 'U', 'S', 'A', 'O', 'K', 'L', 'H', 'E', 'A', 'E'],
            ['L', 'E', 'S', 'T', 'R', 'T', 'A', 'R', 'T', 'O', 'B', 'L', 'B', 'O', 'L', 'S', 'N', 'D'],
            ['I', 'R', 'T', 'R', 'O', 'A', 'P', 'T', 'E', 'M', 'I', 'E', 'I', 'T', 'U', 'T', 'T', 'U'],
            ['D', 'A', 'R', 'U', 'J', 'N', 'R', 'H', 'A', 'E', 'B', 'T', 'O', 'E', 'M', 'R', 'A', 'A'],
            ['A', 'V', 'A', 'E', 'P', 'O', 'Z', 'M', 'L', 'L', 'L', 'D', 'T', 'C', 'H', 'A', 'L', 'S'],
            ['D', 'E', 'S', 'M', 'O', 'N', 'C', 'A', 'N', 'K', 'E', 'D', 'E', 'E', 'I', 'T', 'I', 'M'],
            ['E', 'L', 'T', 'E', 'C', 'A', 'I', 'F', 'U', 'W', 'N', 'N', 'C', 'N', 'A', 'R', 'S', 'D'],
            ['S', 'A', 'R', 'R', 'O', 'A', 'G', 'L', 'D', 'N', 'O', 'R', 'A', 'I', 'S', 'E', 'S', 'E']
        ];
        
        function getCellByCoords(r, c) {
            return wordSearchGridElement.querySelector(`[data-row="${r}"][data-col="${c}"]`);
        }

        function createWordSearchGrid() {
            wordSearchGridElement.innerHTML = '';
            gridData.forEach((row, rowIndex) => {
                row.forEach((char, colIndex) => {
                    const cell = document.createElement('div');
                    cell.classList.add('word-search-cell');
                    cell.textContent = char;
                    cell.dataset.row = rowIndex;
                    cell.dataset.col = colIndex;
                    cell.addEventListener('click', handleCellClick);
                    wordSearchGridElement.appendChild(cell);
                });
            });
            updateWordList();
        }
        
        function clearSelectionVisual() {
            wordSearchGridElement.querySelectorAll('.word-search-cell.selected').forEach(cell => cell.classList.remove('selected'));
        }

        function getCellsInLine(r1, c1, r2, c2) {
            let cells = [];
            const dr = Math.sign(r2 - r1);
            const dc = Math.sign(c2 - c1);
            
      0; }
            .section-title { font-size: 1.8em; margin-bottom: 30px; }
            .news-item, .news-item:nth-child(even) { flex-direction: column; gap: 20px; align-items: center; text-align: center; padding: 20px; }
            .news-item-image { max-width: 100%; min-width: auto; }
            .journal-grid { grid-template-columns: 1fr; }
            
            /* Ajuste de tamanho para jogos em telas menores */
            .word-search-grid { grid-template-columns: repeat(18, 18px); grid-template-rows: repeat(12, 18px); }
            .word-search-cell { width: 18px; height: 18px; font-size: 0.7em; }
            .sudoku-grid { grid-template-columns: repeat(9, 30px); grid-template-rows: repeat(9, 30px); }
            .sudoku-cell { width: 30px; height: 30px; font-size: 0.9em; }
        }
    </style>
</head>
<body>
    <header class="main-header">
        <div class="logo-container">
            <img src="https://files.catbox.moe/39ztvw.jpg" alt="CDL Aprendiz em Foco Logo" class="logo">
            <h1>APRENDIZ EM FOCO</h1>
        </div>
        <nav class="main-nav">
            <ul>
                <li><a href="#noticias"><i class="fas fa-bullhorn"></i> Notícias</a></li>
                <li><a href="#aprende-jovem"><i class="fas fa-gamepad"></i> Jogos</a></li>
                <li><a href="#jornal"><i class="fas fa-newspaper"></i> Jornal Completo</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="noticias" class="news-section">
            <h2 class="section-title"><i class="fas fa-star"></i> Destaques e Iniciativas CDL</h2>
            
            <article class="news-item">
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/0fuurz.jpg" alt="Aprendizes em Palestra sobre Legado Negro">
                </div>
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-calendar-alt"></i> EVENTO | 20 NOV, 2025</span>
                    <h3>Jovens Aprendizes e o Legado da Consciência Negra</h3>
                    <p>Nossos jovens aprendizes participaram de uma inspiradora palestra sobre a importância da Consciência Negra e o legado de figuras históricas como Luís Gama, promovendo a inclusão e o conhecimento na nossa comunidade.</p>
                 
                </div>
            </article>

            <article class="news-item">
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-laptop-code"></i> PROGRAMA | TECNOLOGIA</span>
                    <h3>CDL Capacita: Mulheres no TI</h3>
                    <p>O programa exclusivo "Mulheres no TI" da CDL oferece capacitação intensiva para aprendizes, preparando-as para as demandas do mercado de tecnologia e garantindo alta empregabilidade no setor.</p>
                 
                </div>
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/e9t6a1.jpg" alt="Grupo de jovens mulheres aprendizes em aula de TI">
                </div>
            </article>
        </section>

        <section id="aprende-jovem" class="interactive-section">
            <h2 class="section-title"><i class="fas fa-brain"></i> Espaço Interativo: Aprenda Jovem</h2>
            
            <div class="games-container">
                <div class="game-box">
                    <h3>Caça Palavras</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Como jogar:** Clique na **primeira** letra e depois na **última** letra da palavra para marcá-la em verde.</p>
                    <div class="word-search-grid" id="wordSearchGrid"></div>
                    <h4 style="margin-top: 20px; color: var(--text-light); font-weight: 600;">Palavras a encontrar:</h4>
                    <ul class="word-list" id="wordList"></ul>
                    <div class="word-search-buttons" style="text-align: center;">
                        <button class="btn-action" onclick="resetWordSearch()"><i class="fas fa-redo-alt"></i> Reiniciar</button>
                    </div>
                </div>

                <div class="game-box">
                    <h3>Sudoku</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Regras:** Preencha de 1 a 9 sem repetir na linha, coluna ou bloco 3x3.</p>
                    <div class="sudoku-grid" id="sudokuGrid"></div>
                    <div class="sudoku-buttons">
                        <button class="btn-action" onclick="checkSudoku()"><i class="fas fa-check-square"></i> Verificar</button>
                        <button class="btn-action btn-solve" onclick="solveSudoku()"><i class="fas fa-lightbulb"></i> Resolver</button>
                        <button class="btn-action" onclick="resetSudoku()"><i class="fas fa-redo-alt"></i> Limpar</button>
                    </div>
                </div>
            </div>
        </section>

        <section id="jornal" class="journal-section">
            <h2 class="section-title"><i class="fas fa-book-open"></i> Edição Completa do Jornal</h2>
            <p style="color: var(--text-dark); margin-bottom: 30px;">Confira as páginas originais da nossa última edição do "Aprendiz em Foco".</p>
            
            <div class="journal-grid">
                <div class="journal-page">
                    <img src="https://files.catbox.moe/yylpix.jpg" alt="Página 1 do Jornal CDL Aprendiz em Foco">
                    <div class="journal-title">PÁGINA 1: DESTAQUES</div>
                </div>
                <div class="journal-page">
                    <img src="https://files.catbox.moe/jacct5.jpg" alt="Página 2 do Jornal CDL Aprendiz em Foco (Jogos)">
                    <div class="journal-title">PÁGINA 2: INTERATIVIDADE</div>
                </div>
            </div>
        </section>
    </main>

    <footer class="main-footer">
        <p><i class="fas fa-copyright"></i> 2025 CDL Aprendiz em Foco. Todos os direitos reservados.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            createWordSearchGrid();
            createSudokuGrid();
        });


        // --- LÓGICA DO CAÇA-PALAVRAS (2-CLIQUES) ---
        const wordSearchGridElement = document.getElementById('wordSearchGrid');
        const wordListElement = document.getElementById('wordList');
        const wordsToFind = ['VULNERABILIDADE', 'PROJETO', 'JOVEM', 'NATAL', 'INCLUSAO', 'HABILIDADES', 'TECNOLOGIA', 'PALESTRA'];
        let foundWords = [];
        let firstClick = null; 

        const gridData = [
            ['E', 'M', 'P', 'R', 'E', 'G', 'A', 'B', 'I', 'L', 'I', 'D', 'A', 'D', 'E', 'R', 'A', 'D'],
            ['H', 'V', 'P', 'J', 'O', 'V', 'E', 'M', 'A', 'S', 'C', 'L', 'C', 'B', 'S', 'P', 'S', 'E'],
            ['A', 'U', 'A', 'T', 'E', 'C', 'N', 'O', 'L', 'O', 'G', 'I', 'A', 'I', 'R', 'A', 'I', 'S'],
            ['B', 'L', 'L', 'C', 'O', 'R', 'E', 'M', 'R', 'U', 'N', 'X', 'M', 'B', 'E', 'L', 'S', 'M'],
            ['I', 'N', 'E', 'S', 'I', 'N', 'C', 'L', 'U', 'S', 'A', 'O', 'K', 'L', 'H', 'E', 'A', 'E'],
            ['L', 'E', 'S', 'T', 'R', 'T', 'A', 'R', 'T', 'O', 'B', 'L', 'B', 'O', 'L', 'S', 'N', 'D'],
            ['I', 'R', 'T', 'R', 'O', 'A', 'P', 'T', 'E', 'M', 'I', 'E', 'I', 'T', 'U', 'T', 'T', 'U'],
            ['D', 'A', 'R', 'U', 'J', 'N', 'R', 'H', 'A', 'E', 'B', 'T', 'O', 'E', 'M', 'R', 'A', 'A'],
            ['A', 'V', 'A', 'E', 'P', 'O', 'Z', 'M', 'L', 'L', 'L', 'D', 'T', 'C', 'H', 'A', 'L', 'S'],
            ['D', 'E', 'S', 'M', 'O', 'N', 'C', 'A', 'N', 'K', 'E', 'D', 'E', 'E', 'I', 'T', 'I', 'M'],
            ['E', 'L', 'T', 'E', 'C', 'A', 'I', 'F', 'U', 'W', 'N', 'N', 'C', 'N', 'A', 'R', 'S', 'D'],
            ['S', 'A', 'R', 'R', 'O', 'A', 'G', 'L', 'D', 'N', 'O', 'R', 'A', 'I', 'S', 'E', 'S', 'E']
        ];
        
        function getCellByCoords(r, c) {
            return wordSearchGridElement.querySelector(`[data-row="${r}"][data-col="${c}"]`);
        }

        function createWordSearchGrid() {
            wordSearchGridElement.innerHTML = '';
            gridData.forEach((row, rowIndex) => {
                row.forEach((char, colIndex) => {
                    const cell = document.createElement('div');
                    cell.classList.add('word-search-cell');
                    cell.textContent = char;
                    cell.dataset.row = rowIndex;
                    cell.dataset.col = colIndex;
                    cell.addEventListener('click', handleCellClick);
                    wordSearchGridElement.appendChild(cell);
                });
            });
            updateWordList();
        }
        
        function clearSelectionVisual() {
            wordSearchGridElement.querySelectorAll('.word-search-cell.selected').forEach(cell => cell.classList.remove('selected'));
        }

        function getCellsInLine(r1, c1, r2, c2) {
            let cells = [];
            const dr = Math.sign(r2 - r1);
            const dc = Math.sign(c2 - c1);
            
            const isHorizontal = dr === 0 && dc !== 0;
            const isVertical = dr !== 0 && dc === 0;
            const isDiagonal = Math.abs(r2 - r1) === Math.abs(c2 - c1) && dr !== 0 && dc !== 0;

            if (!isHorizontal && !isVertical && !isDiagonal) {
                return []; 
            }

            let r = r1;
            let c = c1;

            while (true) {
                const cell = getCellByCoords(r, c);
                if (!cell) break;
                cells.push(cell);
                
                if (r === r2 && c === c2) break;

                r += dr;
                c += dc;
                
                if (cells.length > 20) break; 
            }
            return cells;
        }

        function handleCellClick(event) {
            const clic            color: var(--highlight-blue);
        }
        .news-section, .journal-section, .interactive-section { padding: 60px 5%; }
        .journal-section, .interactive-section { background-color: var(--primary-blue); }

        /* --- Estilo dos Cartões de Notícia --- */
        .news-item {
            display: flex; align-items: center; gap: 40px; margin-bottom: 50px;
            padding: 30px; border-radius: 10px; background-color: var(--secondary-blue);
            border: 1px solid var(--border-color); 
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3); 
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .news-item:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0, 132, 255, 0.15); }
        .news-item:nth-child(even) { flex-direction: row-reverse; background-color: var(--primary-blue); }
        .news-item-image { flex: 1; min-width: 280px; max-width: 40%; }
        .news-item-image img { 
            width: 100%; height: auto; border-radius: 8px; 
            object-fit: cover; border: 3px solid var(--highlight-blue); 
            box-shadow: 0 0 15px rgba(0, 132, 255, 0.3);
        }
        .news-item-content { flex: 2; }
        .news-item-content h3 { margin-top: 0; font-size: 1.8em; color: var(--text-light); }
        .news-item-content p { color: var(--text-dark); }
        
        .btn-action {
            display: inline-block; background-color: var(--highlight-blue); color: var(--text-light);
            padding: 10px 25px; text-decoration: none; border-radius: 50px; 
            margin-top: 20px; font-weight: 700; 
            box-shadow: 0 4px 10px rgba(0, 132, 255, 0.4);
            transition: background-color 0.3s, transform 0.2s, box-shadow 0.3s;
            border: none;
            cursor: pointer;
        }
        .btn-action:hover { background-color: #0069d9; transform: translateY(-2px); box-shadow: 0 6px 15px rgba(0, 132, 255, 0.6); }

        /* ---------------------------------- */
        /* 4. SEÇÃO DO JORNAL (Imagens) */
        /* ---------------------------------- */
        .journal-section { text-align: center; }
        .journal-grid { 
            display: grid; 
            grid-template-columns: 1fr 1fr; 
            gap: 30px; 
            max-width: 1200px; 
            margin: 40px auto; 
        }
        .journal-page {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s;
        }
        .journal-page:hover {
            transform: scale(1.02);
        }
        .journal-grid img { 
            width: 100%; 
            height: auto; 
            display: block;
            border: 1px solid var(--border-color);
        }
        .journal-title {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.7);
            color: var(--text-light);
            padding: 10px;
            font-weight: 600;
            font-size: 1.1em;
        }

        /* ---------------------------------- */
        /* 5. ESPAÇO INTERATIVO (Caça-Palavras e Sudoku) */
        /* ---------------------------------- */
        .games-container { display: flex; justify-content: center; flex-wrap: wrap; gap: 40px; margin-top: 30px; }
        .game-box {
            background: var(--primary-blue); padding: 30px; border-radius: 10px; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            width: 100%; max-width: 550px; border: 1px solid var(--border-color); 
            text-align: left;
        }
        .game-box h3 { text-align: center; margin-bottom: 25px; color: var(--highlight-blue); border-bottom: 2px solid var(--border-color); padding-bottom: 10px; }

        /* Caça-Palavras Específico (Estilização da Grade) */
        .word-search-grid {
            display: grid; 
            grid-template-columns: repeat(18, 25px); 
            grid-template-rows: repeat(12, 25px);
            gap: 1px; 
            border: 2px solid var(--highlight-blue); 
            margin: 20px auto; 
            max-width: fit-content;
            background-color: var(--border-color);
        }
        .word-search-cell {
            width: 25px; height: 25px; display: flex; justify-content: center; align-items: center;
            font-size: 0.8em; font-weight: 700; text-transform: uppercase; cursor: pointer;
            background-color: var(--secondary-blue); color: var(--text-light); 
            border: none;
            transition: background-color 0.1s; user-select: none;
        }
        .word-search-cell.selected { background-color: var(--highlight-blue); color: #FFF; } 
        .word-search-cell.found { background-color: #28a745; color: #FFF; font-weight: 700; } 
        .word-list { list-style: none; padding: 0; display: flex; flex-wrap: wrap; gap: 5px 20px; margin-top: 15px; font-size: 1em; color: var(--text-dark); }
        .word-list li { font-weight: 600; }
        .word-list li.found { text-decoration: line-through; color: #6c757d; }

        /* Sudoku Específico */
        .sudoku-grid {
            display: grid; grid-template-columns: repeat(9, 35px); grid-template-rows: repeat(9, 35px);
            gap: 0; border: 3px solid var(--highlight-blue); margin: 20px auto; max-width: fit-content;
        }
        .sudoku-cell { width: 35px; height: 35px; display: flex; justify-content: center; align-items: center; font-size: 1.1em; font-weight: 700; border: 1px solid var(--border-color); }
        .sudoku-cell input { 
            width: 100%; height: 100%; text-align: center; font-size: 1.1em; font-weight: 700; 
            border: none; background-color: var(--secondary-blue); color: var(--text-light); 
            outline: none;
        }
        .sudoku-cell.fixed { background-color: var(--primary-blue); color: var(--text-light); pointer-events: none; }
        .sudoku-grid .cell-border-right { border-right: 3px solid var(--highlight-blue) !important; }
        .sudoku-grid .cell-border-bottom { border-bottom: 3px solid var(--highlight-blue) !important; }
        .sudoku-buttons { text-align: center; margin-top: 25px; }
        .btn-solve { background-color: #dc3545; border-color: #dc3545; }
        .btn-solve:hover { background-color: #c82333; }

        /* ---------------------------------- */
        /* 6. RODAPÉ e RESPONSIVO */
        /* ---------------------------------- */
        .main-footer { 
            background-color: var(--primary-blue); color: var(--text-dark); 
            padding: 30px 5%; text-align: center; margin-top: 0; 
            border-top: 2px solid var(--border-color); 
            font-size: 0.9em;
        }
        @media (max-width: 768px) {
            .main-header { flex-direction: column; position: static; padding-bottom: 10px; }
            main { padding-top: 0; }
            .section-title { font-size: 1.8em; margin-bottom: 30px; }
            .news-item, .news-item:nth-child(even) { flex-direction: column; gap: 20px; align-items: center; text-align: center; padding: 20px; }
            .news-item-image { max-width: 100%; min-width: auto; }
            .journal-grid { grid-template-columns: 1fr; }
            
            /* Ajuste de tamanho para jogos em telas menores */
            .word-search-grid { grid-template-columns: repeat(18, 18px); grid-template-rows: repeat(12, 18px); }
            .word-search-cell { width: 18px; height: 18px; font-size: 0.7em; }
            .sudoku-grid { grid-template-columns: repeat(9, 30px); grid-template-rows: repeat(9, 30px); }
            .sudoku-cell { width: 30px; height: 30px; font-size: 0.9em; }
        }
    </style>
</head>
<body>
    <header class="main-header">
        <div class="logo-container">
            <img src="https://files.catbox.moe/39ztvw.jpg" alt="CDL Aprendiz em Foco Logo" class="logo">
            <h1>APRENDIZ EM FOCO</h1>
        </div>
        <nav class="main-nav">
            <ul>
                <li><a href="#noticias"><i class="fas fa-bullhorn"></i> Notícias</a></li>
                <li><a href="#aprende-jovem"><i class="fas fa-gamepad"></i> Jogos</a></li>
                <li><a href="#jornal"><i class="fas fa-newspaper"></i> Jornal Completo</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="noticias" class="news-section">
            <h2 class="section-title"><i class="fas fa-star"></i> Destaques e Iniciativas CDL</h2>
            
            <article class="news-item">
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/0fuurz.jpg" alt="Aprendizes em Palestra sobre Legado Negro">
                </div>
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-calendar-alt"></i> EVENTO | 20 NOV, 2025</span>
                    <h3>Jovens Aprendizes e o Legado da Consciência Negra</h3>
                    <p>Nossos jovens aprendizes participaram de uma inspiradora palestra sobre a importância da Consciência Negra e o legado de figuras históricas como Luís Gama, promovendo a inclusão e o conhecimento na nossa comunidade.</p>
                    </div>
            </article>

            <article class="news-item">
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-laptop-code"></i> PROGRAMA | TECNOLOGIA</span>
                    <h3>CDL Capacita: Mulheres no TI</h3>
                    <p>O programa exclusivo "Mulheres no TI" da CDL oferece capacitação intensiva para aprendizes, preparando-as para as demandas do mercado de tecnologia e garantindo alta empregabilidade no setor.</p>
                    </div>
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/e9t6a1.jpg" alt="Grupo de jovens mulheres aprendizes em aula de TI">
                </div>
            </article>
        </section>

        <section id="aprende-jovem" class="interactive-section">
            <h2 class="section-title"><i class="fas fa-brain"></i> Espaço Interativo: Aprenda Jovem</h2>
            
            <div class="games-container">
                <div class="game-box">
                    <h3>Caça Palavras</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Como jogar:** Clique na **primeira** letra e depois na **última** letra da palavra para marcá-la em verde.</p>
                    <div class="word-search-grid" id="wordSearchGrid"></div>
                    <h4 style="margin-top: 20px; color: var(--text-light); font-weight: 600;">Palavras a encontrar:</h4>
                    <ul class="word-list" id="wordList"></ul>
                    <div class="word-search-buttons" style="text-align: center;">
                        <button class="btn-action" onclick="resetWordSearch()"><i class="fas fa-redo-alt"></i> Reiniciar</button>
                    </div>
                </div>

                <div class="game-box">
                    <h3>Sudoku</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Regras:** Preencha de 1 a 9 sem repetir na linha, coluna ou bloco 3x3.</p>
                    <div class="sudoku-grid" id="sudokuGrid"></div>
                    <div class="sudoku-buttons">
                        <button class="btn-action" onclick="checkSudoku()"><i class="fas fa-check-square"></i> Verificar</button>
                        <button class="btn-action btn-solve" onclick="solveSudoku()"><i class="fas fa-lightbulb"></i> Resolver</button>
                        <button class="btn-action" onclick="resetSudoku()"><i class="fas fa-redo-alt"></i> Limpar</button>
                    </div>
                </div>
            </div>
        </section>

        <section id="jornal" class="journal-section">
            <h2 class="section-title"><i class="fas fa-book-open"></i> Edição Completa do Jornal</h2>
            <p style="color: var(--text-dark); margin-bottom: 30px;">Confira as páginas originais da nossa última edição do "Aprendiz em Foco".</p>
            
            <div class="journal-grid">
                <div class="journal-page">
                    <img src="https://files.catbox.moe/yylpix.jpg" alt="Página 1 do Jornal CDL Aprendiz em Foco">
                    <div class="journal-title">PÁGINA 1: DESTAQUES</div>
                </div>
                <div class="journal-page">
                    <img src="https://files.catbox.moe/jacct5.jpg" alt="Página 2 do Jornal CDL Aprendiz em Foco (Jogos)">
                    <div class="journal-title">PÁGINA 2: INTERATIVIDADE</div>
                </div>
            </div>
        </section>
    </main>

    <footer class="main-footer">
        <p><i class="fas fa-copyright"></i> 2025 CDL Aprendiz em Foco. Todos os direitos reservados.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // ESSENCIAL: Cria as grades assim que a página é carregada
            createWordSearchGrid();
            createSudokuGrid();
        });


        // --- LÓGICA DO CAÇA-PALAVRAS (2-CLIQUES) ---
        const wordSearchGridElement = document.getElementById('wordSearchGrid');
        const wordListElement = document.getElementById('wordList');
        // A palavra "INCLUSÃO" está na lista, mas sem acento na grade
        const wordsToFind = ['VULNERABILIDADE', 'PROJETO', 'JOVEM', 'NATAL', 'INCLUSÃO', 'HABILIDADES', 'TECNOLOGIA', 'PALESTRA'];
        let foundWords = [];
        let firstClick = null; 

        // Dados da Grade (extraído da imagem do jornal)
        const gridData = [
            ['E', 'M', 'P', 'R', 'E', 'G', 'A', 'B', 'I', 'L', 'I', 'D', 'A', 'D', 'E', 'R', 'A', 'D'],
            ['H', 'V', 'P', 'J', 'O', 'V', 'E', 'M', 'A', 'S', 'C', 'L', 'C', 'B', 'S', 'P', 'S', 'E'],
            ['A', 'U', 'A', 'T', 'E', 'C', 'N', 'O', 'L', 'O', 'G', 'I', 'A', 'I', 'R', 'A', 'I', 'S'],
            ['B', 'L', 'L', 'C', 'O', 'R', 'E', 'M', 'R', 'U', 'N', 'X', 'M', 'B', 'E', 'L', 'S', 'M'],
            ['I', 'N', 'E', 'S', 'I', 'N', 'C', 'L', 'U', 'S', 'A', 'O', 'K', 'L', 'H', 'E', 'A', 'E'],
            ['L', 'E', 'S', 'T', 'R', 'T', 'A', 'R', 'T', 'O', 'B', 'L', 'B', 'O', 'L', 'S', 'N', 'D'],
            ['I', 'R', 'T', 'R', 'O', 'A', 'P', 'T', 'E', 'M', 'I', 'E', 'I', 'T', 'U', 'T', 'T', 'U'],
            ['D', 'A', 'R', 'U', 'J', 'N', 'R', 'H', 'A', 'E', 'B', 'T', 'O', 'E', 'M', 'R', 'A', 'A'],
            ['A', 'V', 'A', 'E', 'P', 'O', 'Z', 'M', 'L', 'L', 'L', 'D', 'T', 'C', 'H', 'A', 'L', 'S'],
            ['D', 'E', 'S', 'M', 'O', 'N', 'C', 'A', 'N', 'K', 'E', 'D', 'E', 'E', 'I', 'T', 'I', 'M'],
            ['E', 'L', 'T', 'E', 'C', 'A', 'I', 'F', 'U', 'W', 'N', 'N', 'C', 'N', 'A', 'R', 'S', 'D'],
            ['S', 'A', 'R', 'R', 'O', 'A', 'G', 'L', 'D', 'N', 'O', 'R', 'A', 'I', 'S', 'E', 'S', 'E']
        ];
        
        function getCellByCoords(r, c) {
            return wordSearchGridElement.querySelector(`[data-row="${r}"][data-col="${c}"]`);
        }

        function createWordSearchGrid() {
            wordSearchGridElement.innerHTML = '';
            gridData.forEach((row, rowIndex) => {
                row.forEach((char, colIndex) => {
                    const cell = document.createElement('div');
                    cell.classList.add('word-search-cell');
                    cell.textContent = char;
                    cell.dataset.row = rowIndex;
                    cell.dataset.col = colIndex;
                    cell.addEventListener('click', handleCellClick);
                    wordSearchGridElement.appendChild(cell);
                });
            });
            updateWordList();
        }
        
        function clearSelectionVisual() {
            wordSearchGridElement.querySelectorAll('.word-search-cell.selected').forEach(cell => cell.classList.remove('selected'));
        }

        function getCellsInLine(r1, c1, r2, c2) {
            let cells = [];
            const dr = Math.sign(r2 - r1);
            const dc = Math.sign(c2 - c1);
            
            const isHorizontal = dr === 0 && dc !== 0;
            const isVertical = dr !== 0 && dc === 0;
            const isDiagonal = Math.abs(r2 - r1) === Math.abs(c2 - c1) && dr !== 0 && dc !== 0;

            if (!isHorizontal && !isVertical && !isDiagonal) {
                return []; 
            }

            let r = r1;
            let c = c1;

            while (true) {
                const cell = getCellByCoords(r, c);
                if (!cell) break;
                cells.push(cell);
                
                if (r === r2 && c === c2) break;

                r += dr;
                c += dc;
                        color: var(--highlight-blue);
        }
        .news-section, .journal-section, .interactive-section { padding: 60px 5%; }
        .journal-section, .interactive-section { background-color: var(--primary-blue); }

        /* --- Estilo dos Cartões de Notícia --- */
        .news-item {
            display: flex; align-items: center; gap: 40px; margin-bottom: 50px;
            padding: 30px; border-radius: 10px; background-color: var(--secondary-blue);
            border: 1px solid var(--border-color); 
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3); /* Sombra mais destacada */
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .news-item:hover { transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0, 132, 255, 0.15); }
        .news-item:nth-child(even) { flex-direction: row-reverse; background-color: var(--primary-blue); }
        .news-item-image { flex: 1; min-width: 280px; max-width: 40%; }
        .news-item-image img { 
            width: 100%; height: auto; border-radius: 8px; 
            object-fit: cover; border: 3px solid var(--highlight-blue); 
            box-shadow: 0 0 15px rgba(0, 132, 255, 0.3);
        }
        .news-item-content { flex: 2; }
        .news-item-content h3 { margin-top: 0; font-size: 1.8em; color: var(--text-light); }
        .news-item-content p { color: var(--text-dark); }
        
        .btn-action {
            display: inline-block; background-color: var(--highlight-blue); color: var(--text-light);
            padding: 10px 25px; text-decoration: none; border-radius: 50px; /* Botão arredondado */
            margin-top: 20px; font-weight: 700; 
            box-shadow: 0 4px 10px rgba(0, 132, 255, 0.4);
            transition: background-color 0.3s, transform 0.2s, box-shadow 0.3s;
            border: none;
            cursor: pointer;
        }
        .btn-action:hover { background-color: #0069d9; transform: translateY(-2px); box-shadow: 0 6px 15px rgba(0, 132, 255, 0.6); }

        /* ---------------------------------- */
        /* 4. SEÇÃO DO JORNAL (Com novo design de exibição) */
        /* ---------------------------------- */
        .journal-section { text-align: center; }
        .journal-grid { 
            display: grid; 
            grid-template-columns: 1fr 1fr; 
            gap: 30px; 
            max-width: 1200px; 
            margin: 40px auto; 
        }
        .journal-page {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s;
        }
        .journal-page:hover {
            transform: scale(1.02);
        }
        .journal-grid img { 
            width: 100%; 
            height: auto; 
            display: block;
            border: 1px solid var(--border-color);
        }
        .journal-title {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.7);
            color: var(--text-light);
            padding: 10px;
            font-weight: 600;
            font-size: 1.1em;
        }

        /* ---------------------------------- */
        /* 5. ESPAÇO INTERATIVO (Caça-Palavras e Sudoku) */
        /* ---------------------------------- */
        .games-container { display: flex; justify-content: center; flex-wrap: wrap; gap: 40px; margin-top: 30px; }
        .game-box {
            background: var(--primary-blue); padding: 30px; border-radius: 10px; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            width: 100%; max-width: 550px; border: 1px solid var(--border-color); 
            text-align: left;
        }
        .game-box h3 { text-align: center; margin-bottom: 25px; color: var(--highlight-blue); border-bottom: 2px solid var(--border-color); padding-bottom: 10px; }

        /* Caça-Palavras Específico (Estilização da Grade) */
        .word-search-grid {
            display: grid; grid-template-columns: repeat(18, 25px); grid-template-rows: repeat(12, 25px);
            gap: 1px; border: 2px solid var(--highlight-blue); margin: 20px auto; max-width: fit-content;
            background-color: var(--border-color);
        }
        .word-search-cell {
            width: 25px; height: 25px; display: flex; justify-content: center; align-items: center;
            font-size: 0.8em; font-weight: 700; text-transform: uppercase; cursor: pointer;
            background-color: var(--secondary-blue); color: var(--text-light); 
            border: none;
            transition: background-color 0.1s; user-select: none;
        }
        .word-search-cell.selected { background-color: var(--highlight-blue); color: #FFF; } 
        .word-search-cell.found { background-color: #28a745; color: #FFF; font-weight: 700; } 
        .word-list { list-style: none; padding: 0; display: flex; flex-wrap: wrap; gap: 5px 20px; margin-top: 15px; font-size: 1em; color: var(--text-dark); }
        .word-list li { font-weight: 600; }
        .word-list li.found { text-decoration: line-through; color: #6c757d; }

        /* Sudoku Específico */
        .sudoku-grid {
            display: grid; grid-template-columns: repeat(9, 35px); grid-template-rows: repeat(9, 35px);
            gap: 0; border: 3px solid var(--highlight-blue); margin: 20px auto; max-width: fit-content;
        }
        .sudoku-cell { width: 35px; height: 35px; display: flex; justify-content: center; align-items: center; font-size: 1.1em; font-weight: 700; border: 1px solid var(--border-color); }
        .sudoku-cell input { 
            width: 100%; height: 100%; text-align: center; font-size: 1.1em; font-weight: 700; 
            border: none; background-color: var(--secondary-blue); color: var(--text-light); 
            outline: none;
        }
        .sudoku-cell.fixed { background-color: var(--primary-blue); color: var(--text-light); pointer-events: none; }
        .sudoku-grid .cell-border-right { border-right: 3px solid var(--highlight-blue) !important; }
        .sudoku-grid .cell-border-bottom { border-bottom: 3px solid var(--highlight-blue) !important; }
        .sudoku-buttons { text-align: center; margin-top: 25px; }
        .btn-solve { background-color: #dc3545; border-color: #dc3545; }
        .btn-solve:hover { background-color: #c82333; }

        /* ---------------------------------- */
        /* 6. RODAPÉ e RESPONSIVO */
        /* ---------------------------------- */
        .main-footer { 
            background-color: var(--primary-blue); color: var(--text-dark); 
            padding: 30px 5%; text-align: center; margin-top: 0; 
            border-top: 2px solid var(--border-color); 
            font-size: 0.9em;
        }
        @media (max-width: 768px) {
            .main-header { flex-direction: column; position: static; padding-bottom: 10px; }
            main { padding-top: 0; }
            .section-title { font-size: 1.8em; margin-bottom: 30px; }
            .news-item, .news-item:nth-child(even) { flex-direction: column; gap: 20px; align-items: center; text-align: center; padding: 20px; }
            .news-item-image { max-width: 100%; min-width: auto; }
            .journal-grid { grid-template-columns: 1fr; }
            
            /* Ajuste de tamanho para jogos em telas menores */
            .word-search-grid { grid-template-columns: repeat(18, 18px); grid-template-rows: repeat(12, 18px); }
            .word-search-cell { width: 18px; height: 18px; font-size: 0.7em; }
            .sudoku-grid { grid-template-columns: repeat(9, 30px); grid-template-rows: repeat(9, 30px); }
            .sudoku-cell { width: 30px; height: 30px; font-size: 0.9em; }
        }
    </style>
</head>
<body>
    <header class="main-header">
        <div class="logo-container">
            <img src="https://files.catbox.moe/39ztvw.jpg" alt="CDL Aprendiz em Foco Logo" class="logo">
            <h1>APRENDIZ EM FOCO</h1>
        </div>
        <nav class="main-nav">
            <ul>
                <li><a href="#noticias"><i class="fas fa-bullhorn"></i> Notícias</a></li>
                <li><a href="#aprende-jovem"><i class="fas fa-gamepad"></i> Jogos</a></li>
                <li><a href="#jornal"><i class="fas fa-newspaper"></i> Jornal Completo</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="noticias" class="news-section">
            <h2 class="section-title"><i class="fas fa-star"></i> Destaques e Iniciativas CDL</h2>
            
            <article class="news-item">
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/0fuurz.jpg" alt="Aprendizes em Palestra sobre Legado Negro">
                </div>
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-calendar-alt"></i> EVENTO | 20 NOV, 2025</span>
                    <h3>Jovens Aprendizes e o Legado da Consciência Negra</h3>
                    <p>Nossos jovens aprendizes participaram de uma inspiradora palestra sobre a importância da Consciência Negra e o legado de figuras históricas como Luís Gama, promovendo a inclusão e o conhecimento na nossa comunidade.</p>
                    <a href="#" class="btn-action"><i class="fas fa-arrow-circle-right"></i> Ver Cobertura</a>
                </div>
            </article>

            <article class="news-item">
                <div class="news-item-content">
                    <span style="color: var(--highlight-blue); font-size: 0.9em; font-weight: 600;"><i class="fas fa-laptop-code"></i> PROGRAMA | TECNOLOGIA</span>
                    <h3>CDL Capacita: Mulheres no TI</h3>
                    <p>O programa exclusivo "Mulheres no TI" da CDL oferece capacitação intensiva para aprendizes, preparando-as para as demandas do mercado de tecnologia e garantindo alta empregabilidade no setor.</p>
                    <a href="#" class="btn-action"><i class="fas fa-info-circle"></i> Detalhes do Projeto</a>
                </div>
                <div class="news-item-image">
                    <img src="https://files.catbox.moe/e9t6a1.jpg" alt="Grupo de jovens mulheres aprendizes em aula de TI">
                </div>
            </article>
        </section>

        <section id="aprende-jovem" class="interactive-section">
            <h2 class="section-title"><i class="fas fa-brain"></i> Espaço Interativo: Aprenda Jovem</h2>
            
            <div class="games-container">
                <div class="game-box">
                    <h3>Caça Palavras</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Como jogar:** Clique na **primeira** letra e depois na **última** letra da palavra para marcá-la em verde.</p>
                    <div class="word-search-grid" id="wordSearchGrid"></div>
                    <h4 style="margin-top: 20px; color: var(--text-light); font-weight: 600;">Palavras a encontrar:</h4>
                    <ul class="word-list" id="wordList"></ul>
                    <div class="word-search-buttons" style="text-align: center;">
                        <button class="btn-action" onclick="resetWordSearch()"><i class="fas fa-redo-alt"></i> Reiniciar</button>
                    </div>
                </div>

                <div class="game-box">
                    <h3>Sudoku</h3>
                    <p style="margin-bottom: 15px; color: var(--text-dark);">**Regras:** Preencha de 1 a 9 sem repetir na linha, coluna ou bloco 3x3.</p>
                    <div class="sudoku-grid" id="sudokuGrid"></div>
                    <div class="sudoku-buttons">
                        <button class="btn-action" onclick="checkSudoku()"><i class="fas fa-check-square"></i> Verificar</button>
                        <button class="btn-action btn-solve" onclick="solveSudoku()"><i class="fas fa-lightbulb"></i> Resolver</button>
                        <button class="btn-action" onclick="resetSudoku()"><i class="fas fa-redo-alt"></i> Limpar</button>
                    </div>
                </div>
            </div>
        </section>

        <section id="jornal" class="journal-section">
            <h2 class="section-title"><i class="fas fa-book-open"></i> Edição Completa do Jornal</h2>
            <p style="color: var(--text-dark); margin-bottom: 30px;">Confira as páginas originais da nossa última edição do "Aprendiz em Foco".</p>
            
            <div class="journal-grid">
                <div class="journal-page">
                    <img src="https://files.catbox.moe/yylpix.jpg" alt="Página 1 do Jornal CDL Aprendiz em Foco">
                    <div class="journal-title">PÁGINA 1: DESTAQUES</div>
                </div>
                <div class="journal-page">
                    <img src="https://files.catbox.moe/jacct5.jpg" alt="Página 2 do Jornal CDL Aprendiz em Foco (Jogos)">
                    <div class="journal-title">PÁGINA 2: INTERATIVIDADE</div>
                </div>
            </div>
        </section>
    </main>

    <footer class="main-footer">
        <p><i class="fas fa-copyright"></i> 2025 CDL Aprendiz em Foco. Todos os direitos reservados.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            createWordSearchGrid();
            createSudokuGrid();
        });


        // --- LÓGICA DO CAÇA-PALAVRAS (2-CLIQUES) ---
        const wordSearchGridElement = document.getElementById('wordSearchGrid');
        const wordListElement = document.getElementById('wordList');
        const wordsToFind = ['VULNERABILIDADE', 'PROJETO', 'JOVEM', 'NATAL', 'INCLUSAO', 'HABILIDADES', 'TECNOLOGIA', 'PALESTRA'];
        let foundWords = [];
        let firstClick = null; 

        const gridData = [
            ['E', 'M', 'P', 'R', 'E', 'G', 'A', 'B', 'I', 'L', 'I', 'D', 'A', 'D', 'E', 'R', 'A', 'D'],
            ['H', 'V', 'P', 'J', 'O', 'V', 'E', 'M', 'A', 'S', 'C', 'L', 'C', 'B', 'S', 'P', 'S', 'E'],
            ['A', 'U', 'A', 'T', 'E', 'C', 'N', 'O', 'L', 'O', 'G', 'I', 'A', 'I', 'R', 'A', 'I', 'S'],
            ['B', 'L', 'L', 'C', 'O', 'R', 'E', 'M', 'R', 'U', 'N', 'X', 'M', 'B', 'E', 'L', 'S', 'M'],
            ['I', 'N', 'E', 'S', 'I', 'N', 'C', 'L', 'U', 'S', 'A', 'O', 'K', 'L', 'H', 'E', 'A', 'E'],
            ['L', 'E', 'S', 'T', 'R', 'T', 'A', 'R', 'T', 'O', 'B', 'L', 'B', 'O', 'L', 'S', 'N', 'D'],
            ['I', 'R', 'T', 'R', 'O', 'A', 'P', 'T', 'E', 'M', 'I', 'E', 'I', 'T', 'U', 'T', 'T', 'U'],
            ['D', 'A', 'R', 'U', 'J', 'N', 'R', 'H', 'A', 'E', 'B', 'T', 'O', 'E', 'M', 'R', 'A', 'A'],
            ['A', 'V', 'A', 'E', 'P', 'O', 'Z', 'M', 'L', 'L', 'L', 'D', 'T', 'C', 'H', 'A', 'L', 'S'],
            ['D', 'E', 'S', 'M', 'O', 'N', 'C', 'A', 'N', 'K', 'E', 'D', 'E', 'E', 'I', 'T', 'I', 'M'],
            ['E', 'L', 'T', 'E', 'C', 'A', 'I', 'F', 'U', 'W', 'N', 'N', 'C', 'N', 'A', 'R', 'S', 'D'],
            ['S', 'A', 'R', 'R', 'O', 'A', 'G', 'L', 'D', 'N', 'O', 'R', 'A', 'I', 'S', 'E', 'S', 'E']
        ];
        
        function getCellByCoords(r, c) {
            return wordSearchGridElement.querySelector(`[data-row="${r}"][data-col="${c}"]`);
        }

        function createWordSearchGrid() {
            wordSearchGridElement.innerHTML = '';
            gridData.forEach((row, rowIndex) => {
                row.forEach((char, colIndex) => {
                    const cell = document.createElement('div');
                    cell.classList.add('word-search-cell');
                    cell.textContent = char;
                    cell.dataset.row = rowIndex;
                    cell.dataset.col = colIndex;
                    cell.addEventListener('click', handleCellClick);
                    wordSearchGridElement.appendChild(cell);
                });
            });
            updateWordList();
        }
        
        function clearSelectionVisual() {
            wordSearchGridElement.querySelectorAll('.word-search-cell.selected').forEach(cell => cell.classList.remove('selected'));
        }

        function getCellsInLine(r1, c1, r2, c2) {
            let cells = [];
            const dr = Math.sign(r2 - r1);
            const dc = Math.sign(c2 - c1);
            
            const isHorizontal = dr === 0 && dc !== 0;
            const isVertical = dr !== 0 && dc === 0;
            const isDiagonal = Math.abs(r2 - r1) === Math.abs(c2 - c1) && dr !== 0 && dc !== 0;

            if (!isHorizontal && !isVertical && !isDiagonal) {
                return []; 
            }

            let r = r1;
            let c = c1;

            while (true) {
                const cell = getCellByCoords(r, c);
                if (!cell) break;
                cells.push(cell);
                
                if (r === r2 && c === c2) break;

                r += dr;
                c +       background-color: #1a1f26; /* Slightly lighter row for zebra striping */
        }
        #ibge-insights table tbody tr:hover {
            background-color: #2a313b; /* Hover effect */
        }
        #ibge-insights table td:last-child,
        #ibge-insights table th:last-child {
            text-align: right; /* Align numbers to the right */
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 20px;
            margin-top: 40px;
            color: var(--text-light);
            font-size: 0.9em;
            border-top: 1px solid var(--border-color);
            background-color: var(--bg-darker);
        }

        footer a {
            color: var(--accent-blue);
            text-decoration: none;
        }

        /* --- Responsive Design (Hamburger Menu & Layout) --- */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hamburger-menu {
                display: block;
            }

            .sidebar {
                width: 250px;
            }

            .sidebar.closed {
                width: 0;
            }

            header {
                padding: 15px 20px;
            }

            main {
                padding: 0 15px;
            }

            section {
                padding: 20px;
            }

            h2 {
                font-size: 1.8em;
            }

            h3 {
                font-size: 1.2em;
            }

            .chart-grid {
                grid-template-columns: 1fr;
            }

            .chart-canvas-container {
                height: 250px;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1><i class="fas fa-chart-line"></i> Análise Socioeconômica</h1>
        <nav>
            <ul class="nav-links">
                <li><a href="#sociodemograficas">Sociodemográficas</a></li>
                <li><a href="#trabalho-renda">Trabalho & Renda</a></li>
                <li><a href="#financas-credito">Finanças & Crédito</a></li>
                <li><a href="#ibge-insights">Insights IBGE</a></li>
            </ul>
            <div class="hamburger-menu" onclick="toggleSidebar()">
                <i class="fas fa-bars"></i>
            </div>
        </nav>
    </header>

    <div id="mySidebar" class="sidebar closed">
        <a href="javascript:void(0)" class="closebtn" onclick="toggleSidebar()">&times;</a>
        <a href="#sociodemograficas" onclick="toggleSidebar()">Sociodemográficas</a>
        <a href="#trabalho-renda" onclick="toggleSidebar()">Trabalho & Renda</a>
        <a href="#financas-credito" onclick="toggleSidebar()">Finanças & Crédito</a>
        <a href="#ibge-insights" onclick="toggleSidebar()">Insights IBGE</a>
    </div>

    <main>
        <section id="sociodemograficas">
            <h2><i class="fas fa-users"></i> Informações Sociodemográficas (Dados de Pesquisa)</h2>
            <p class="analysis-text">
                Apresentamos os dados simulados de uma pesquisa para entender a composição da população. Essas informações, como gênero, etnia, idade e estrutura familiar, são a base para o desenvolvimento de políticas públicas e estratégias de inclusão mais eficazes.
            </p>
            <div class="chart-grid">
                <div class="chart-card">
                    <h3>Qual seu gênero?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="genderChart"></canvas>
                    </div>
                    <ul class="survey-answers-list" id="gender-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="genderChart" data-chart-title="Gênero">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A distribuição por gênero é um indicador básico da estrutura demográfica. Entender essa proporção pode influenciar a oferta de serviços e oportunidades, além de ser fundamental para análises de equidade.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Qual sua cor/raça/etnia?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="ethnicityChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="ethnicity-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="ethnicityChart" data-chart-title="Cor/Raça/Etnia">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A análise da composição étnica é crucial para identificar e combater desigualdades históricas e estruturais. Dados desagregados por cor/raça são essenciais para promover a equidade e representatividade em diversos setores da sociedade.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Faixa Etária</h3>
                    <div class="chart-canvas-container">
                        <canvas id="ageChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="age-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="ageChart" data-chart-title="Faixa Etária">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A distribuição etária revela se a população é majoritariamente jovem, adulta ou idosa. Isso tem grandes implicações para o mercado de trabalho, sistemas de previdência, educação e saúde.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Com quantas pessoas você mora?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="householdChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="household-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="householdChart" data-chart-title="Pessoas no Domicílio">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        O tamanho do domicílio pode indicar padrões de moradia, densidade populacional e a necessidade de infraestrutura habitacional. Famílias maiores podem ter desafios diferentes de famílias menores de recursos e espaço.
                    </p>
                </div>
            </div>
        </section>

        <section id="trabalho-renda">
            <h2><i class="fas fa-briefcase"></i> Situação de Trabalho e Renda (Dados de Pesquisa)</h2>
            <p class="analysis-text">
                Compreender a dinâmica do trabalho e da renda é vital para avaliar a saúde econômica de uma população. Esses dados indicam níveis de emprego, tipos de ocupação e as principais fontes de sustento.
            </p>
            <div class="chart-grid">
                <div class="chart-card">
                    <h3>Você está atualmente trabalhando?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="workingChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="working-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="workingChart" data-chart-title="Situação de Trabalho">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A taxa de ocupação é um dos principais indicadores econômicos. Uma alta taxa de pessoas trabalhando geralmente reflete um mercado aquecido e maior geração de renda.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Se sim, quantos trabalhos remunerados você tem?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="jobsCountChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="jobsCount-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="jobsCountChart" data-chart-title="Quantidade de Trabalhos">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A quantidade de trabalhos por pessoa pode indicar a necessidade de complementar a renda, a flexibilidade do mercado de trabalho ou até mesmo a precarização em alguns casos.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Seu(s) trabalho(s) são:</h3>
                    <div class="chart-canvas-container">
                        <canvas id="jobTypeChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="jobType-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="jobTypeChart" data-chart-title="Tipo de Trabalho">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A proporção entre trabalhos formais, informais e mistos reflete a segurança empregatícia e a estrutura da economia. A informalidade, por exemplo, pode indicar menor proteção social.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Qual a sua principal fonte de renda?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="incomeSourceChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="incomeSource-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="incomeSourceChart" data-chart-title="Fonte de Renda">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A predominância de salários formais indica estabilidade, enquanto uma alta dependência de benefícios ou trabalhos informais pode apontar vulnerabilidades econômicas.
                    </p>
                </div>
            </div>
        </section>

        <section id="financas-credito">
            <h2><i class="fas fa-wallet"></i> Situação Financeira e Crédito (Dados de Pesquisa)</h2>
            <p class="analysis-text">
                A saúde financeira e o acesso ao crédito são indicadores importantes do bem-estar econômico individual e familiar, revelando padrões de consumo, endividamento e capacidade de investimento.
            </p>
            <div class="chart-grid">
                <div class="chart-card">
                    <h3>Você utiliza cartão de crédito?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="creditCardChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="creditCard-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="creditCardChart" data-chart-title="Uso de Cartão de Crédito">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        O uso de cartão de crédito reflete tanto o acesso a serviços financeiros quanto o comportamento de consumo. Um uso consciente pode ser um facilitador, mas excessos podem levar ao endividamento.
                    </p>
                </div>
                <div class="chart-card">
                    <h3>Atualmente, você está com dívidas?</h3>
                    <div class="chart-canvas-container">
                        <canvas id="debtChart"></canvas>
                    </div>
                     <ul class="survey-answers-list" id="debt-list">
                        </ul>
                    <button class="copy-graph-btn" data-chart-id="debtChart" data-chart-title="Situação de Dívidas">Copiar gráfico</button>
                    <p class="analysis-text" style="margin-top: 15px;">
                        A proporção de pessoas endividadas é um alerta sobre a estabilidade financeira. Dívidas podem impactar o poder de compra e a qualidade de vida, sendo um fator de vulnerabilidade econômica.
                    </p>
                </div>
            </div>
        </section>

        <section id="ibge-insights">
            <h2><i class="fas fa-globe-americas"></i> Insights do IBGE (Dados Reais)</h2>
            <p class="analysis-text">
                Dados oficiais do Instituto Brasileiro de Geografia e Estatística (IBGE) fornecem um panorama robusto da realidade socioeconômica do Brasil. Estas informações são cruciais para análises mais aprofundadas e formulação de políticas.
            </p>
            <div class="ibge-data-card" id="ibgeUnemploymentData">
                <p class="loading-message"><i class="fas fa-spinner fa-spin"></i> Carregando dados de desocupação (PNADC)...</p>
            </div>
            <p class="analysis-text">
                A taxa de desocupação por nível de instrução do IBGE frequentemente revela uma correlação: **quanto maior o nível de escolaridade, menor a taxa de desocupação.** Isso sublinha a importância da educação como fator de empregabilidade e ascensão social no Brasil. As disparidades observadas refletem desafios estruturais no acesso e permanência na educação, bem como na absorção de mão de obra qualificada pelo mercado.
            </p>

            <div class="ibge-data-card" id="ibgeIncomeData">
                <p class="loading-message"><i class="fas fa-spinner fa-spin"></i> Carregando rendimento domiciliar per capita (PNADC)...</p>
            </div>
            <p class="analysis-text">
                O rendimento domiciliar per capita é um indicador chave da distribuição de renda e da desigualdade regional. As diferenças entre as Unidades da Federação destacam as **disparidades socioeconômicas existentes no país**, influenciadas por fatores históricos, econômicos e de desenvolvimento local. A compreensão dessas diferenças é vital para o planejamento de investimentos e distribuição de recursos.
            </p>

            <div class="ibge-data-card" id="ibgePopulationProjection">
                <p class="loading-message"><i class="fas fa-spinner fa-spin"></i> Carregando projeção populacional (IBGE)...</p>
            </div>
            <p class="analysis-text">
                A projeção populacional do IBGE é fundamental para o planejamento de longo prazo. Ela informa sobre o crescimento ou envelhecimento da população, impactando diretamente nas necessidades de infraestrutura (saúde, educação, moradia) e na dinâmica do mercado de trabalho. Entender a evolução demográfica permite antecipar demandas e otimizar recursos.
            </p>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Análise Socioeconômica. Dados do <a href="https://www.ibge.gov.br/" target="_blank">IBGE</a>.</p>
    </footer>

    <script>
        // Hamburger Menu Toggle
        function toggleSidebar() {
            const sidebar = document.getElementById("mySidebar");
            if (sidebar.classList.contains("closed")) {
                sidebar.classList.remove("closed");
                sidebar.style.width = "250px"; // Open sidebar
            } else {
                sidebar.classList.add("closed");
                sidebar.style.width = "0"; // Close sidebar
            }
        }

        // Smooth Scrolling for Navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
                if (window.innerWidth <= 768) {
                    toggleSidebar(); // Close sidebar after clicking a link on mobile
                }
            });
        });

        // Chart.js Global Configuration
        Chart.defaults.color = 'var(--text-light)'; // Default text color for charts
        Chart.defaults.font.family = 'Inter, "Segoe UI", Roboto, Helvetica, Arial, sans-serif';

        // Custom Color Palette for Charts (avoiding green/red, focusing on blues, grays, and some warm neutrals)
        const chartColorsPalette = [
            '#58a6ff', // Primary Blue (GitHub Accent)
            '#8b949e', // Gray
            '#2188ff', // Brighter Blue
            '#c9d1d9', // Light Gray
            '#a371f7', // Purple-ish
            '#ff8100', // Orange-ish
            '#4092ff', // Medium Blue
            '#6a6a6a', // Darker Gray
            '#0366d6', // Deeper Blue
            '#ddb75d', // Gold-ish
            '#1f6feb'  // Another Blue
        ];

        // Survey Data (based on your analysis of the images)
        // Data updated to reflect better estimations where images were unclear
        const surveyData = {
            gender: {
                type: 'pie',
                labels: ['Feminino', 'Masculino', 'Prefiro não responder'],
                data: [60, 40, 0],
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[3]]
            },
            ethnicity: {
                type: 'pie',
                labels: ['Branca', 'Parda', 'Preta', 'Amarela', 'Indígena', 'Prefiro não responder'],
                data: [55, 30, 15, 0, 0, 0], // Values based on visible image data
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[2], chartColorsPalette[3], chartColorsPalette[4], chartColorsPalette[5]]
            },
            age: {
                type: 'bar', // Bar chart for better comparison across categories
                labels: ['< 18', '18-24', '25-34', '35-44', '45-59', '60+'],
                data: [15, 15, 15, 25, 30, 0], // Values based on visible image data
                backgroundColor: chartColorsPalette[0] // Single color for bar chart
            },
            household: {
                type: 'pie',
                labels: ['0', '1-3', '4-6', '7 ou mais'],
                data: [5, 80, 15, 0], // Values based on visible image data
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[2], chartColorsPalette[3]]
            },
            working: {
                type: 'pie',
                labels: ['Sim', 'Não'],
                data: [80, 20],
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1]]
            },
            jobsCount: {
                type: 'pie',
                labels: ['1', '2', '3 ou mais'],
                data: [75, 18.8, 6.3],
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[2]]
            },
            jobType: {
                type: 'pie',
                labels: ['Todo formal', 'Todos informais', 'Misto'],
                data: [56.3, 31.3, 12.5],
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[2]]
            },
            incomeSource: {
                type: 'pie',
                labels: ['Salário formal', 'Trabalho informal/autônomo', 'Aposentadoria/Pensão', 'Benefício social', 'Outros'],
                data: [60, 20, 15, 5, 0], // 'Mãe' not clearly specified in percentage, assumed 'Outros'
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[2], chartColorsPalette[3], chartColorsPalette[4]]
            },
            creditCard: {
                type: 'pie',
                labels: ['Sim, frequentemente', 'Sim, às vezes', 'Não'],
                data: [40, 30, 30],
                backgroundColor: [chartColorsPalette[0], chartColorsPalette[1], chartColorsPalette[2]]
            },
            debt: {
                type: 'pie',
                labels: ['Sim', 'Não'],
                data: [50, 50], // Placeholder data as exact values were not visible
                backgroundColor: [chartColorsPalette[1], chartColorsPalette[0]]
            }
        };

        const charts = {}; // Store chart instances

        // Function to create a Pie Chart
        function createPieChart(chartId, labels, data, backgroundColor, title = '') {
            const ctx = document.getElementById(chartId).getContext('2d');
            if (charts[chartId]) { // Destroy existing chart if it exists
                charts[chartId].destroy();
            }
            charts[chartId] = new Chart(ctx, {
                type: 'pie',
                data: {
                    labels: labels,
                    datasets: [{
                        data: data,
                        backgroundColor: backgroundColor,
                        borderColor: 'var(--bg-darkest)',
                        borderWidth: 2,
                        hoverOffset: 8
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'right',
                            labels: {
                                color: 'var(--text-light)',
                                font: { size: 14 }
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.label || '';
                                    if (label) { label += ': '; }
                                    if (context.parsed !== null) { label += context.parsed + '%'; }
                                    return label;
                                }
                            },
                            bodyColor: 'var(--text-white)',
                            titleColor: 'var(--accent-blue)',
                            backgroundColor: 'var(--bg-dark)',
                            borderColor: 'var(--border-color)',
                            borderWidth: 1
                        }
                    }
                }
            });
        }

        // Function to create a Bar Chart
        function createBarChart(chartId, labels, data, backgroundColor, title = '') {
            const ctx = document.getElementById(chartId).getContext('2d');
            if (charts[chartId]) { // Destroy existing chart if it exists
                charts[chartId].destroy();
            }
            charts[chartId] = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: labels,
                    datasets: [{
                        data: data,
                        backgroundColor: backgroundColor,
                        borderColor: 'var(--accent-blue-hover)',
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            display: false
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.dataset.label || '';
                                    if (label) { label += ': '; }
                                    if (context.parsed.y !== null) { label += context.parsed.y + '%'; }
                                    return label;
                                }
                            },
                            bodyColor: 'var(--text-white)',
                            titleColor: 'var(--accent-blue)',
                            backgroundColor: 'var(--bg-dark)',
                            borderColor: 'var(--border-color)',
                            borderWidth: 1
                        }
                    },
                    scales: {
                        x: {
                            ticks: { color: 'var(--text-light)' },
                            grid: { color: 'var(--border-color)' }
                        },
                        y: {
                            ticks: { color: 'var(--text-light)' },
                            grid: { color: 'var(--border-color)' }
                        }
                    }
                }
            });
        }

        // Function to populate survey answer lists with percentages
        function populateSurveyLists() {
            for (const key in surveyData) {
                const listElement = document.getElementById(`${key}-list`);
                if (listElement) {
                    listElement.innerHTML = ''; // Clear previous content
                    surveyData[key].labels.forEach((label, index) => {
                        const percentage = surveyData[key].data[index];
                        const listItem = document.createElement('li');
                        listItem.innerHTML = `<span>${label}:</span> <span class="percentage">${percentage}%</span>`;
                        listElement.appendChild(listItem);
                    });
                }
            }
        }

        // Initialize all survey charts
        function initializeSurveyChartsAndLists() {
            for (const key in surveyData) {
                const chartConfig = surveyData[key];
                if (chartConfig.type === 'pie') {
                    createPieChart(key + 'Chart', chartConfig.labels, chartConfig.data, chartConfig.backgroundColor, key);
                } else if (chartConfig.type === 'bar') {
                    createBarChart(key + 'Chart', chartConfig.labels, chartConfig.data, chartConfig.backgroundColor, key);
                }
            }
            populateSurveyLists(); // Populate the lists with percentages
        }


        // Implement "Copy Graph" functionality
        document.querySelectorAll('.copy-graph-btn').forEach(button => {
            button.addEventListener('click', (event) => {
                const chartId = event.target.dataset.chartId;
                const chartTitle = event.target.dataset.chartTitle;
                const chartInstance = charts[chartId];

                if (chartInstance) {
                    const chartData = {
                        title: chartTitle,
                        type: chartInstance.config.type,
                        labels: chartInstance.data.labels,
                        data: chartInstance.data.datasets[0].data
                    };
                    const dataToCopy = JSON.stringify(chartData, null, 2);

                    navigator.clipboard.writeText(dataToCopy)
                        .then(() => {
                            alert(`Dados do gráfico "${chartTitle}" copiados para a área de transferência!`);
                        })
                        .catch(err => {
                            console.error('Falha ao copiar dados do gráfico:', err);
                            alert('Erro ao copiar dados do gráfico. Por favor, tente novamente.');
                        });
                }
            });
        });

        // IBGE API Integration - Real Data Analysis
        // Function to handle API fetches and error display
        async function fetchIbgeData(elementId, url, title, parseFunction) {
            const element = document.getElementById(elementId);
            element.innerHTML = `<p class="loading-message"><i class="fas fa-spinner fa-spin"></i> Carregando ${title.toLowerCase()}...</p>`;
            try {
                const response = await fetch(url);
                if (!response.ok) {
                    throw new Error(`HTTP error! Status: ${response.status}`);
                }
                const data = await response.json();
                
                // Check if data structure is as expected before parsing
                if (data && data.length > 0 && data[0].resultados && data[0].resultados.length > 0) {
                    element.innerHTML = parseFunction(data, title);
                    element.classList.remove('loading-message');
                } else {
                    element.innerHTML = `<p class="error-message"><i class="fas fa-exclamation-triangle"></i> Não foram encontrados dados para ${title.toLowerCase()} neste período. (Resposta da API OK, mas sem dados)</p>`;
                    console.warn(`IBGE API: ${title} - Dados retornados vazios ou em formato inesperado. URL: ${url}`, data);
                }
            } catch (error) {
                console.error(`Erro ao buscar dados do IBGE para ${title}:`, error);
                element.innerHTML = `<p class="error-message"><i class="fas fa-exclamation-circle"></i> Erro ao carregar dados de ${title.toLowerCase()} do IBGE. Verifique a conexão ou tente novamente mais tarde. Detalhes: ${error.message}</p>`;
            }
        }

        // --- Parsing Functions for IBGE Data ---

        // 1. Unemployment Rate by Education Level (PNADC)
        function parseUnemploymentData(data, title) {
            let htmlContent = `<h3><i class="fas fa-percent"></i> ${title}</h3><ul>`;
            const periodName = data[0].resultados[0].periodos[0].nome;
            const seriesData = data[0].resultados[0].series[0].serie;

            const educationLevelsMap = {
                "1": "Sem instrução e F. incompleto",
                "2": "F. completo e M. incompleto",
                "3": "M. completo e S. incompleto",
                "4": "Superior completo",
                "5": "Mestrado",
                "6": "Doutorado"
            };

            for (const classificationId in seriesData) {
                const level = educationLevelsMap[classificationId.split('.')[1]];
                const rate = parseFloat(seriesData[classificationId]).toFixed(2);
                htmlContent += `<li><strong>${level}:</strong> ${rate}%</li>`;
            }
            htmlContent += `</ul><p><em>Período: ${periodName} (Fonte: IBGE - PNADC)</em></p>`;
            return htmlContent;
        }

        // 2. Monthly Nominal Per Capita Household Income (PNADC)
        function parseIncomeData(data, title) {
            let htmlContent = `<h3><i class="fas fa-money-bill-wave"></i> ${title}</h3><table><thead><tr><th>Unidade da Federação</th><th>Rendimento (R$)</th></tr></thead><tbody>`;
            const periodName = data[0].resultados[0].periodos[0].nome;
            const incomeData = [];

            for (const item of data[0].resultados) {
                const ufName = item.localidade.nome;
                // Safely extract the income value using Object.values to handle dynamic period keys
                const incomeValueRaw = Object.values(item.series[0].serie)[0]; // Gets the first (and usually only) value in the series object
                const incomeValue = parseFloat(incomeValueRaw);

                if (!isNaN(incomeValue)) {
                    incomeData.push({ uf: ufName, income: incomeValue });
                }
            }

            incomeData.sort((a, b) => b.income - a.income);

            incomeData.forEach(item => {
                htmlContent += `<tr>
                    <td>${item.uf}</td>
                    <td>R$ ${item.income.toLocaleString('pt-BR', { minimumFractionDigits: 2, maximumFractionDigits: 2 })}</td>
                </tr>`;
            });
            htmlContent += `</tbody></table><p><em>Período: ${periodName} (Fonte: IBGE - PNADC)</em></p>`;
            return htmlContent;
        }

        // 3. Population Projection for Brazil
        function parsePopulationProjectionData(data, title) {
            const period = data[0].resultados[0].periodos[0].nome;
            const populationValue = parseInt(data[0].resultados[0].series[0].serie[period]).toLocaleString('pt-BR');
            return `<h3><i class="fas fa-users"></i> ${title}</h3>
                    <p>Em <strong>${period}</strong>, a população total estimada do Brasil é de aproximadamente <strong>${populationValue}</strong> habitantes.</p>
                    <p><em>Fonte: IBGE - Projeção da População</em></p>`;
        }

        // Execute all data fetches and chart initializations on page load
        document.addEventListener('DOMContentLoaded', () => {
            initializeSurveyChartsAndLists(); // Initialize survey charts and populate lists
            
            fetchIbgeData(
                'ibgeUnemploymentData',
                'https://servicodados.ibge.gov.br/api/v3/agregados/6389/periodos/ultimos/variaveis/4099?localidades=N1[BR]&classificacao=12739[1,2,3,4,5,6]',
                'Taxa de Desocupação por Nível de Instrução',
                parseUnemploymentData
            );

            fetchIbgeData(
                'ibgeIncomeData',
                'https://servicodados.ibge.gov.br/api/v3/agregados/2027/periodos/ultimos/variaveis/8032?localidades=N3[all]',
                'Rendimento Domiciliar Per Capita',
                parseIncomeData
            );

            fetchIbgeData(
                'ibgePopulationProjection',
                'https://servicodados.ibge.gov.br/api/v3/agregados/606/periodos/ultimos/variaveis/606?localidades=N1[BR]',
                'População Estimada do Brasil',
                parsePopulationProjectionData
            );
        });
    </script>
</body>
</html>
