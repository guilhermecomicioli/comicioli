# comicioli<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduPlay - Jogos e Músicas Educativas</title>
    <style>
        /* Configurações Globais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #6366f1; /* Roxo Indigo */
            --secondary: #06b6d4; /* Turquesa */
            --dark: #1e1b4b; /* Fundo Escuro Nobre */
            --light: #f8fafc; /* Fundo Claro */
            --success: #10b981;
            --white: #ffffff;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--light);
            color: #334155;
            line-height: 1.6;
        }

        /* Menu de Navegação */
        header {
            background-color: var(--white);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 2rem;
        }
        .logo {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        .nav-links a {
            text-decoration: none;
            color: #475569;
            font-weight: 600;
            transition: color 0.3s;
        }
        .nav-links a:hover {
            color: var(--primary);
        }

        /* Banner Principal (Hero) */
        .hero {
            background: linear-gradient(135deg, var(--dark) 0%, var(--primary) 100%);
            color: var(--white);
            padding: 6rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 800;
        }
        .hero p {
            font-size: 1.25rem;
            max-width: 600px;
            margin: 0 auto;
            opacity: 0.9;
        }

        /* Container de Conteúdo */
        .container {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.2rem;
            color: var(--dark);
            margin-bottom: 3rem;
        }
        .section-title span {
            color: var(--primary);
        }

        /* SEÇÃO DE JOGOS (Grid e Área do Jogo) */
        .grid-layout {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-bottom: 5rem;
        }

        .card {
            background: var(--white);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0,0,0,0.05);
            transition: transform 0.3s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .card:hover {
            transform: translateY(-8px);
        }
        .card-content {
            padding: 2rem;
        }
        .card-tag {
            display: inline-block;
            padding: 0.25rem 0.75rem;
            background-color: #e0e7ff;
            color: var(--primary);
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }
        .card h3 {
            color: var(--dark);
            margin-bottom: 0.5rem;
            font-size: 1.4rem;
        }
        .card p {
            color: #64748b;
            font-size: 0.95rem;
        }

        /* Área Interativa do Jogo de Matemática */
        .interactive-game-box {
            background: var(--white);
            max-width: 600px;
            margin: 0 auto 5rem auto;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.1);
            text-align: center;
            border: 2px solid #e2e8f0;
        }
        .game-screen h4 {
            font-size: 1.5rem;
            color: var(--dark);
            margin-bottom: 1.5rem;
        }
        .math-problem {
            font-size: 3.5rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 1.5rem;
        }
        .game-input {
            width: 120px;
            padding: 0.75rem;
            font-size: 1.5rem;
            text-align: center;
            border: 2px solid #cbd5e1;
            border-radius: 10px;
            margin-bottom: 1rem;
            outline: none;
        }
        .game-input:focus {
            border-color: var(--primary);
        }
        .btn-game {
            display: block;
            width: 200px;
            margin: 0 auto;
            padding: 0.75rem;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }
        .btn-game:hover { background: #4f46e5; }
        .score-board {
            margin-top: 1.5rem;
            font-weight: bold;
            color: var(--success);
            font-size: 1.1rem;
        }

        /* SEÇÃO DE MÚSICA (Player de Áudio) */
        .music-section {
            background: linear-gradient(135deg, #f1f5f9 0%, #e2e8f0 100%);
            padding: 4rem 2rem;
            border-radius: 24px;
            margin-bottom: 4rem;
        }
        .audio-player-container {
            max-width: 500px;
            margin: 0 auto;
            background: var(--white);
            padding: 2rem;
            border-radius: 16px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            text-align: center;
        }
        .track-info h4 {
            font-size: 1.3rem;
            color: var(--dark);
            margin-bottom: 0.25rem;
        }
        .track-info p {
            color: #64748b;
            font-size: 0.9rem;
            margin-bottom: 1.5rem;
        }
        audio {
            width: 100%;
            outline: none;
        }

        /* Rodapé */
        footer {
            background-color: var(--dark);
            color: #94a3b8;
            text-align: center;
            padding: 2.5rem;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <div class="nav-container">
            <a href="#" class="logo">🎮 EduPlay</a>
            <nav>
                <ul class="nav-links">
                    <li><a href="#inicio">Início</a></li>
                    <li><a href="#jogos">Jogos</a></li>
                    <li><a href="#desafio-matematica">Jogar Agora</a></li>
                    <li><a href="#musicas">Músicas</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="inicio" class="hero">
            <h1>Aprender nunca foi tão divertido!</h1>
            <p>Explore nossa coleção exclusiva de jogos interativos e músicas educativas desenvolvidas para estimular a mente e a criatividade.</p>
        </section>

        <div class="container">
            
            <section id="jogos">
                <h2 class="section-title">Nossos <span>Jogos Educativos</span></h2>
                <div class="grid-layout">
                    <div class="card">
                        <div class="card-content">
                            <span class="card-tag">Matemática</span>
                            <h3>Mestre dos Números</h3>
                            <p>Desafios lógicos e contas rápidas de adição e multiplicação para treinar o raciocínio rápido.</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-content">
                            <span class="card-tag">Português</span>
                            <h3>Caçadores de Palavras</h3>
                            <p>Um jogo de ortografia e gramática onde a missão é completar as frases e expandir o vocabulário.</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-content">
                            <span class="card-tag">Ciências</span>
                            <h3>Laboratório Espacial</h3>
                            <p>Descubra os segredos do sistema solar e os elementos químicos em uma jornada interestelar simulada.</p>
                        </div>
                    </div>
                </div>
            </section>

            <section id="desafio-matematica" class="interactive-game-box">
                <div class="game-screen">
                    <h4>Desafio Matemático Rápido</h4>
                    <p style="color: #64748b; margin-bottom: 1rem;">Resolva o problema abaixo:</p>
                    <div class="math-problem" id="problem-text">5 + 3</div>
                    <input type="number" id="user-answer" class="game-input" placeholder="?">
                    <button class="btn-game" onclick="checkMathAnswer()">Enviar Resposta</button>
                    <div class="score-board" id="score-board">Pontuação: 0</div>
                </div>
            </section>

            <section id="musicas" class="music-section">
                <h2 class="section-title">Playlists <span>Educativas & Foco</span></h2>
                <p style="text-align: center; margin-top: -2rem; margin-bottom: 3rem; color: #64748b;">Músicas calmas para estudar, focar e aprender melhor.</p>
                
                <div class="audio-player-container">
                    <div class="track-info">
                        <span class="card-tag" style="background-color: #cffafe; color: var(--secondary);">Áudio Ativo</span>
                        <h4 id="track-title">Sinfonia do Aprendizado</h4>
                        <p id="track-author">Canal EduPlay Instrumental</p>
                    </div>
                    <audio controls id="audio-player">
                        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
                        Seu navegador não suporta o elemento de áudio.
                    </audio>
                </div>
            </section>

        </div>
    </main>

    <footer>
        <p>&copy; 2026 EduPlay Hub. Conteúdo educacional seguro, profissional e divertido.</p>
    </footer>

    <script>
        let num1, num2, correctAnswer;
        let currentScore = 0;

        function generateProblem() {
            // Gera números aleatórios de 1 a 10
            num1 = Math.floor(Math.random() * 10) + 1;
            num2 = Math.floor(Math.random() * 10) + 1;
            
            // Alterna aleatoriamente entre Soma e Multiplicação
            const isMultiplication = Math.random() > 0.5;

            if(isMultiplication) {
                correctAnswer = num1 * num2;
                document.getElementById('problem-text').innerText = `${num1} × ${num2}`;
            } else {
                correctAnswer = num1 + num2;
                document.getElementById('problem-text').innerText = `${num1} + ${num2}`;
            }
            
            document.getElementById('user-answer').value = '';
            document.getElementById('user-answer').focus();
        }

        function checkMathAnswer() {
            const userAnswer = parseInt(document.getElementById('user-answer').value);
            
            if (userAnswer === correctAnswer) {
                currentScore += 10;
                alert("Parabéns! Resposta Correta! 🎉");
            } else {
                currentScore = Math.max(0, currentScore - 5); // Não deixa a pontuação ficar menor que zero
                alert(`Ops! A resposta correta era ${correctAnswer}. Tente a próxima! 👍`);
            }

            document.getElementById('score-board').innerText = `Pontuação: ${currentScore}`;
            generateProblem();
        }

        // Inicia o primeiro problema assim que a página abre
        generateProblem();
    </script>
</body>
</html>