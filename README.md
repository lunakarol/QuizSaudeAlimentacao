
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Alimentação Saudável e Saúde</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Comic Sans MS', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #e0f7fa 0%, #bbdefb 100%);
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background-color: white;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            padding: 30px;
        }
        
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 20px;
            font-size: 2.5rem;
        }
        
        h2 {
            color: #3498db;
            margin-bottom: 15px;
            text-align: center;
            font-size: 1.8rem;
        }
        
        h3 {
            color: #2c3e50;
            margin-bottom: 15px;
        }
        
        .screen {
            display: none;
            animation: fadeIn 0.5s ease-in-out;
        }
        
        .active-screen {
            display: block;
        }
        
        .teams-intro {
            display: flex;
            justify-content: space-around;
            margin: 30px 0;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .team-card {
            flex: 1;
            min-width: 250px;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .team-card:hover {
            transform: translateY(-5px) scale(1.02);
        }
        
        .team-blue {
            background: linear-gradient(145deg, #e3f2fd, #bbdefb);
            border: 4px solid #2196f3;
        }
        
        .team-green {
            background: linear-gradient(145deg, #e8f5e9, #c8e6c9);
            border: 4px solid #4caf50;
        }
        
        .team-icon {
            font-size: 70px;
            margin-bottom: 20px;
            filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.2));
        }
        
        .team-name {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .team-blue .team-name {
            color: #1565c0;
        }
        
        .team-green .team-name {
            color: #2e7d32;
        }
        
        .instructions {
            background-color: #f1f8e9;
            padding: 25px;
            border-radius: 15px;
            margin: 25px 0;
            line-height: 1.6;
            font-size: 18px;
            border-left: 6px solid #7cb342;
        }
        
        .config-container {
            background-color: #e8f5e9;
            padding: 25px;
            border-radius: 15px;
            margin: 25px 0;
        }
        
        .config-section {
            margin-bottom: 30px;
        }
        
        .config-title {
            color: #2e7d32;
            margin-bottom: 15px;
            font-size: 22px;
            text-align: center;
        }
        
        .team-config {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .team-config-item {
            flex: 1;
            min-width: 300px;
        }
        
        .input-group {
            margin-bottom: 20px;
        }
        
        .input-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #2e7d32;
            font-size: 18px;
        }
        
        .input-group input, .input-group select {
            width: 100%;
            padding: 15px;
            border: 3px solid #81c784;
            border-radius: 10px;
            font-size: 18px;
            text-align: center;
        }
        
        .input-group select {
            appearance: none;
            background-color: white;
            cursor: pointer;
        }
        
        .input-group input:focus, .input-group select:focus {
            outline: none;
            border-color: #4caf50;
            box-shadow: 0 0 10px rgba(76, 175, 80, 0.3);
        }
        
        .participant-counter {
            font-size: 20px;
            color: #2e7d32;
            font-weight: bold;
            margin-top: 10px;
        }
        
        .animal-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 15px;
            margin-top: 10px;
        }
        
        .animal-option {
            padding: 15px;
            border: 3px solid #bbdefb;
            border-radius: 10px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            background-color: white;
        }
        
        .animal-option:hover {
            transform: scale(1.05);
            border-color: #42a5f5;
        }
        
        .animal-option.selected {
            background-color: #e3f2fd;
            border-color: #2196f3;
            box-shadow: 0 5px 15px rgba(33, 150, 243, 0.3);
        }
        
        .animal-emoji {
            font-size: 40px;
            margin-bottom: 5px;
        }
        
        .btn {
            display: block;
            margin: 30px auto;
            padding: 18px 50px;
            font-size: 20px;
            font-weight: bold;
            color: white;
            background: linear-gradient(145deg, #42a5f5, #2196f3);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 8px 20px rgba(33, 150, 243, 0.3);
        }
        
        .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(33, 150, 243, 0.4);
        }
        
        .btn:active {
            transform: scale(0.98);
        }
        
        .question-container {
            background: linear-gradient(145deg, #f5f5f5, #e0e0e0);
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 25px;
            border: 4px solid #42a5f5;
        }
        
        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .question-number {
            font-size: 22px;
            color: #1565c0;
            font-weight: bold;
            background-color: #e3f2fd;
            padding: 10px 20px;
            border-radius: 30px;
        }
        
        .current-participant {
            font-size: 22px;
            color: #2e7d32;
            font-weight: bold;
            background-color: #e8f5e9;
            padding: 10px 20px;
            border-radius: 30px;
        }
        
        .question-text {
            font-size: 28px;
            font-weight: 600;
            margin-bottom: 30px;
            color: #1a237e;
            text-align: center;
            line-height: 1.4;
        }
        
        .options-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .option {
            background-color: white;
            border: 3px solid #bbdefb;
            border-radius: 15px;
            padding: 20px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            font-size: 20px;
        }
        
        .option:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            border-color: #42a5f5;
        }
        
        .option.correct {
            background-color: #c8e6c9;
            border-color: #4caf50;
        }
        
        .option.wrong {
            background-color: #ffcdd2;
            border-color: #f44336;
        }
        
        .option-icon {
            font-size: 40px;
            margin-right: 20px;
        }
        
        .team-turn {
            text-align: center;
            font-size: 26px;
            font-weight: bold;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .blue-turn {
            background: linear-gradient(145deg, #bbdefb, #90caf9);
            color: #0d47a1;
            border: 4px solid #2196f3;
        }
        
        .green-turn {
            background: linear-gradient(145deg, #c8e6c9, #a5d6a7);
            color: #1b5e20;
            border: 4px solid #4caf50;
        }
        
        .score-container {
            display: flex;
            justify-content: space-around;
            margin: 30px 0;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .score-card {
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            min-width: 200px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            flex: 1;
        }
        
        .score-blue {
            background: linear-gradient(145deg, #bbdefb, #90caf9);
            border: 4px solid #2196f3;
        }
        
        .score-green {
            background: linear-gradient(145deg, #c8e6c9, #a5d6a7);
            border: 4px solid #4caf50;
        }
        
        .score-value {
            font-size: 52px;
            font-weight: bold;
            margin: 15px 0;
        }
        
        .score-blue .score-value {
            color: #0d47a1;
        }
        
        .score-green .score-value {
            color: #1b5e20;
        }
        
        .feedback-container {
            background-color: #fffde7;
            padding: 25px;
            border-radius: 15px;
            margin: 30px 0;
            border: 4px solid #ffd54f;
            text-align: center;
        }
        
        .feedback-title {
            color: #f57c00;
            margin-bottom: 15px;
            font-size: 24px;
        }
        
        .feedback-text {
            font-size: 22px;
            margin-bottom: 20px;
            line-height: 1.5;
        }
        
        .challenge-container {
            background: linear-gradient(145deg, #fff3e0, #ffccbc);
            padding: 30px;
            border-radius: 15px;
            margin: 30px 0;
            border: 4px solid #ff9800;
            text-align: center;
        }
        
        .challenge-title {
            color: #e65100;
            margin-bottom: 20px;
            font-size: 28px;
        }
        
        .challenge-text {
            font-size: 24px;
            margin-bottom: 25px;
            line-height: 1.5;
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            border: 3px dashed #ff9800;
        }
        
        .action-btn {
            padding: 18px 40px;
            font-size: 20px;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            margin: 10px;
            min-width: 250px;
        }
        
        .next-btn {
            background: linear-gradient(145deg, #4caf50, #2e7d32);
            color: white;
            box-shadow: 0 8px 20px rgba(46, 125, 50, 0.3);
        }
        
        .next-btn:hover {
            background: linear-gradient(145deg, #2e7d32, #1b5e20);
            transform: scale(1.05);
        }
        
        .challenge-btn {
            background: linear-gradient(145deg, #ff9800, #f57c00);
            color: white;
            box-shadow: 0 8px 20px rgba(245, 124, 0, 0.3);
        }
        
        .challenge-btn:hover {
            background: linear-gradient(145deg, #f57c00, #e65100);
            transform: scale(1.05);
        }
        
        .challenge-options {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 30px;
        }
        
        .challenge-complete {
            background: linear-gradient(145deg, #4caf50, #2e7d32);
            color: white;
            box-shadow: 0 8px 20px rgba(46, 125, 50, 0.3);
        }
        
        .challenge-complete:hover {
            background: linear-gradient(145deg, #2e7d32, #1b5e20);
            transform: scale(1.05);
        }
        
        .challenge-skip {
            background: linear-gradient(145deg, #f44336, #d32f2f);
            color: white;
            box-shadow: 0 8px 20px rgba(211, 47, 47, 0.3);
        }
        
        .challenge-skip:hover {
            background: linear-gradient(145deg, #d32f2f, #b71c1c);
            transform: scale(1.05);
        }
        
        .final-message {
            background: linear-gradient(145deg, #e1f5fe, #b3e5fc);
            padding: 40px;
            border-radius: 20px;
            margin: 40px 0;
            text-align: center;
            border: 6px solid #0288d1;
        }
        
        .final-title {
            color: #01579b;
            margin-bottom: 30px;
            font-size: 32px;
        }
        
        .final-text {
            font-size: 22px;
            line-height: 1.6;
            margin-bottom: 20px;
            text-align: left;
        }
        
        .winner-announcement {
            font-size: 36px;
            font-weight: bold;
            margin: 30px 0;
            padding: 25px;
            border-radius: 20px;
            background: linear-gradient(145deg, #fff9c4, #fff59d);
            border: 6px solid #ffd600;
            color: #f57f17;
        }
        
        .emoji {
            font-size: 40px;
            margin: 0 10px;
            vertical-align: middle;
        }
        
        .progress-bar {
            height: 20px;
            background-color: #e0e0e0;
            border-radius: 10px;
            margin: 20px 0;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #42a5f5, #2196f3);
            border-radius: 10px;
            transition: width 0.5s ease;
        }
        
        .animal-display {
            font-size: 50px;
            margin-bottom: 10px;
        }
        
        .category-badge {
            display: inline-block;
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 16px;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        .category-food {
            background-color: #c8e6c9;
            color: #1b5e20;
        }
        
        .category-health {
            background-color: #bbdefb;
            color: #0d47a1;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        .bounce {
            animation: bounce 0.5s ease infinite;
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .team-card {
                min-width: 100%;
            }
            
            .team-config {
                flex-direction: column;
            }
            
            .team-config-item {
                min-width: 100%;
            }
            
            .options-container {
                grid-template-columns: 1fr;
            }
            
            .question-text {
                font-size: 24px;
            }
            
            .option {
                font-size: 18px;
                padding: 15px;
            }
            
            .challenge-options {
                flex-direction: column;
                align-items: center;
            }
            
            .action-btn {
                width: 100%;
                max-width: 300px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Tela 1: Apresentação -->
        <div id="screen1" class="screen active-screen">
            <h1>🏆 Quiz Alimentação Saudável e Saúde 🏆</h1>
            <div class="teams-intro">
                <div class="team-card team-blue">
                    <div class="team-icon">🐬</div>
                    <div class="team-name">Equipe Azul</div>
                    <p style="font-size: 18px; margin-top: 10px;">Escolha seu animal favorito!</p>
                </div>
                
                <div class="team-card team-green">
                    <div class="team-icon">🐢</div>
                    <div class="team-name">Equipe Verde</div>
                    <p style="font-size: 18px; margin-top: 10px;">Escolha seu animal favorito!</p>
                </div>
            </div>
            
            <div class="instructions">
                <h3>📋 Como Funciona o Jogo:</h3>
                <p>1. Escolha o animal e número de participantes para cada equipe</p>
                <p>2. Cada participante responde 1 pergunta sobre alimentação saudável e saúde</p>
                <p>3. Acerto: <strong>+10 pontos</strong> para a equipe</p>
                <p>4. Erro: <strong>desafio psicomotor</strong> com duas opções:</p>
                <p>&nbsp;&nbsp;&nbsp;&nbsp;✅ Cumprir desafio: <strong>+10 pontos</strong></p>
                <p>&nbsp;&nbsp;&nbsp;&nbsp;❌ Não cumprir: <strong>-10 pontos</strong></p>
                <p>5. As equipes se alternam a cada pergunta</p>
                <p>6. No final, aprendemos sobre alimentação saudável e saúde!</p>
            </div>
            
            <button id="startBtn" class="btn">Vamos Começar! 🚀</button>
        </div>
        
        <!-- Tela 2: Configuração dos Participantes -->
        <div id="screen2" class="screen">
            <h1>👥 Configurar Equipes</h1>
            
            <div class="config-container">
                <div class="config-section">
                    <h3 class="config-title">Equipe Azul</h3>
                    <div class="team-config">
                        <div class="team-config-item">
                            <div class="input-group">
                                <label for="blueAnimal">Escolha o animal da Equipe Azul:</label>
                                <div class="animal-options" id="blueAnimalOptions">
                                    <!-- Opções serão inseridas pelo JavaScript -->
                                </div>
                            </div>
                        </div>
                        <div class="team-config-item">
                            <div class="input-group">
                                <label for="blueParticipants">Número de participantes:</label>
                                <input type="number" id="blueParticipants" min="1" max="20" value="5">
                                <div class="participant-counter">Máximo: 20 participantes</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="config-section">
                    <h3 class="config-title">Equipe Verde</h3>
                    <div class="team-config">
                        <div class="team-config-item">
                            <div class="input-group">
                                <label for="greenAnimal">Escolha o animal da Equipe Verde:</label>
                                <div class="animal-options" id="greenAnimalOptions">
                                    <!-- Opções serão inseridas pelo JavaScript -->
                                </div>
                            </div>
                        </div>
                        <div class="team-config-item">
                            <div class="input-group">
                                <label for="greenParticipants">Número de participantes:</label>
                                <input type="number" id="greenParticipants" min="1" max="20" value="5">
                                <div class="participant-counter">Máximo: 20 participantes</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="instructions">
                <p>🎯 Cada pergunta vale <strong>10 pontos</strong>.</p>
                <p>💪 Se errar, a equipe pode escolher entre cumprir o desafio (+10 pontos) ou não cumpri-lo (-10 pontos).</p>
                <p>🐾 Escolham animais que representem a energia da equipe!</p>
            </div>
            
            <button id="configBtn" class="btn">Iniciar Quiz! 🎮</button>
        </div>
        
        <!-- Tela 3: Perguntas -->
        <div id="screen3" class="screen">
            <h1>❓ Pergunta do Quiz</h1>
            
            <div id="teamTurnIndicator" class="team-turn blue-turn">
                Vez da Equipe Azul
            </div>
            
            <div class="progress-bar">
                <div id="progressFill" class="progress-fill" style="width: 0%"></div>
            </div>
            
            <div class="question-container">
                <div class="question-header">
                    <div class="question-number" id="questionNumber">Pergunta 1</div>
                    <div class="current-participant" id="currentParticipant">Participante 1</div>
                </div>
                
                <div class="category-badge" id="questionCategory">Alimentação</div>
                
                <div class="question-text" id="questionText">
                    Carregando pergunta...
                </div>
                
                <div class="options-container" id="optionsContainer">
                    <!-- Opções serão inseridas aqui pelo JavaScript -->
                </div>
            </div>
            
            <div class="score-container">
                <div class="score-card score-blue">
                    <div id="blueTeamName">Equipe Azul</div>
                    <div class="animal-display" id="blueAnimalDisplay">🐬</div>
                    <div class="score-value" id="scoreBlue">0</div>
                    <div>pontos</div>
                </div>
                
                <div class="score-card score-green">
                    <div id="greenTeamName">Equipe Verde</div>
                    <div class="animal-display" id="greenAnimalDisplay">🐢</div>
                    <div class="score-value" id="scoreGreen">0</div>
                    <div>pontos</div>
                </div>
            </div>
        </div>
        
        <!-- Tela 4: Feedback da Resposta -->
        <div id="screen4" class="screen">
            <h1>📝 Resultado da Resposta</h1>
            
            <div id="feedbackContainer" class="feedback-container">
                <h2 class="feedback-title" id="feedbackTitle">Resposta Correta! 🎉</h2>
                <div class="feedback-text" id="feedbackText">
                    Parabéns! Você acertou a resposta.
                </div>
                <button id="feedbackBtn" class="action-btn next-btn">Próxima Pergunta ➡️</button>
            </div>
            
            <div class="instructions" id="challengeInstruction" style="display: none;">
                <p>⚠️ Como a resposta estava incorreta, a equipe terá que realizar um desafio psicomotor.</p>
                <p>💪 <strong>Cumprir o desafio:</strong> +10 pontos para a equipe</p>
                <p>❌ <strong>Não cumprir o desafio:</strong> -10 pontos para a equipe</p>
            </div>
        </div>
        
        <!-- Tela 5: Desafio Psicomotor -->
        <div id="screen5" class="screen">
            <h1>💪 Desafio Psicomotor</h1>
            
            <div class="challenge-container">
                <h2 class="challenge-title" id="challengeTitle">Desafio para a Equipe</h2>
                <div class="challenge-text" id="challengeText">
                    Carregando desafio...
                </div>
                
                <div class="challenge-options">
                    <button id="completeChallengeBtn" class="action-btn challenge-complete">✅ Cumprir Desafio (+10 pts)</button>
                    <button id="skipChallengeBtn" class="action-btn challenge-skip">❌ Não Cumprir (-10 pts)</button>
                </div>
            </div>
            
            <div class="instructions">
                <p>🎯 A equipe tem 1 minuto para decidir se cumpre ou não o desafio.</p>
                <p>😊 Lembre-se: o importante é participar, se divertir e aprender!</p>
            </div>
        </div>
        
        <!-- Tela 6: Resultados Finais -->
        <div id="screen6" class="screen">
            <h1>🏆 Resultado Final</h1>
            
            <div id="winnerAnnouncement" class="winner-announcement">
                Carregando resultado...
            </div>
            
            <div class="score-container">
                <div class="score-card score-blue">
                    <div id="finalBlueTeamName">Equipe Azul</div>
                    <div class="animal-display" id="finalBlueAnimalDisplay">🐬</div>
                    <div class="score-value" id="finalScoreBlue">0</div>
                    <div>pontos</div>
                </div>
                
                <div class="score-card score-green">
                    <div id="finalGreenTeamName">Equipe Verde</div>
                    <div class="animal-display" id="finalGreenAnimalDisplay">🐢</div>
                    <div class="score-value" id="finalScoreGreen">0</div>
                    <div>pontos</div>
                </div>
            </div>
            
            <div class="final-message">
                <h2 class="final-title">🌟 A Importância da Alimentação Saudável e Saúde 🌟</h2>
                
                <div class="final-text">
                    <p>🍎 <strong>Alimentação Saudável:</strong> Comer frutas, verduras e legumes nos dá energia, ajuda no crescimento e mantém nosso corpo forte para brincar e aprender!</p>
                    
                    <p>💧 <strong>Hidratação:</strong> Beber água é essencial para nosso corpo funcionar bem. Ajuda na digestão, mantém a pele saudável e regula a temperatura do corpo.</p>
                    
                    <p>🏃‍♂️ <strong>Atividade Física:</strong> Brincar, correr, pular e se movimentar fortalece os músculos e ossos, melhora o humor e ajuda a ter um bom sono.</p>
                    
                    <p>😴 <strong>Descanso:</strong> Dormir bem é tão importante quanto se alimentar bem. Nosso corpo precisa descansar para crescer e se recuperar.</p>
                    
                    <p>🧠 <strong>Mente Saudável:</strong> Além do corpo, precisamos cuidar da mente. Brincar com amigos, ler livros e aprender coisas novas mantém nosso cérebro ativo e feliz!</p>
                    
                    <p>🦷 <strong>Higiene:</strong> Lavar as mãos, escovar os dentes e tomar banho são hábitos essenciais para evitar doenças e manter a saúde.</p>
                </div>
                
                <p style="font-size: 24px; margin-top: 30px; font-weight: bold; color: #d32f2f;">
                    Lembre-se: cuidar da saúde é o melhor presente que podemos dar para nós mesmos! 💖
                </p>
            </div>
            
            <button id="restartBtn" class="btn">Jogar Novamente 🔄</button>
        </div>
    </div>

    <script>
        // Dados do jogo
        const gameData = {
            currentScreen: 1,
            currentQuestionIndex: 0,
            scores: {
                blue: 0,
                green: 0
            },
            currentTeam: 'blue',
            blueParticipants: 5,
            greenParticipants: 5,
            blueAnimal: { name: 'Golfinho', emoji: '🐬' },
            greenAnimal: { name: 'Tartaruga', emoji: '🐢' },
            currentParticipant: {
                blue: 1,
                green: 1
            },
            totalQuestions: 0,
            answeredQuestions: 0,
            lastAnswerCorrect: true,
            
            // Lista de animais disponíveis
            availableAnimals: [
                { name: 'Golfinho', emoji: '🐬', description: 'Ágil e inteligente' },
                { name: 'Tartaruga', emoji: '🐢', description: 'Sábia e persistente' },
                { name: 'Leão', emoji: '🦁', description: 'Corajoso e líder' },
                { name: 'Coala', emoji: '🐨', description: 'Calmo e tranquilo' },
                { name: 'Elefante', emoji: '🐘', description: 'Forte e memorioso' },
                { name: 'Águia', emoji: '🦅', description: 'Observadora e focada' },
                { name: 'Macaco', emoji: '🐒', description: 'Divertido e ágil' },
                { name: 'Panda', emoji: '🐼', description: 'Pacífico e amigável' },
                { name: 'Girafa', emoji: '🦒', description: 'Elegante e observadora' },
                { name: 'Tigre', emoji: '🐯', description: 'Determinado e focado' },
                { name: 'Pinguim', emoji: '🐧', description: 'Trabalhador em equipe' },
                { name: 'Coruja', emoji: '🦉', description: 'Sábia e atenta' }
            ],
            
            // Perguntas fornecidas (20 de alimentação + 20 de saúde)
            questions: [
                // Alimentação Saudável (20 perguntas)
                {
                    id: 1,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses é uma fruta?',
                    options: [
                        { text: 'Cenoura', emoji: '🥕', correct: false },
                        { text: 'Banana', emoji: '🍌', correct: true },
                        { text: 'Pão', emoji: '🍞', correct: false }
                    ],
                    explanation: 'A banana é uma fruta natural, cresce nas árvores e faz bem para o corpo. Cenoura é legume e pão é feito de farinha.',
                    challenge: 'Fazer 10 polichinelos.',
                    team: 'blue'
                },
                {
                    id: 2,
                    category: 'Alimentação Saudável',
                    text: 'Qual alimento ajuda no crescimento dos ossos?',
                    options: [
                        { text: 'Leite', emoji: '🥛', correct: true },
                        { text: 'Bala', emoji: '🍬', correct: false },
                        { text: 'Refrigerante', emoji: '🥤', correct: false }
                    ],
                    explanation: 'O leite tem cálcio, que ajuda no crescimento e fortalecimento dos ossos e dos dentes.',
                    challenge: 'Imitar um animal (cachorro, sapo ou cobra) por 15 segundos.',
                    team: 'green'
                },
                {
                    id: 3,
                    category: 'Alimentação Saudável',
                    text: 'O que é melhor comer no café da manhã?',
                    options: [
                        { text: 'Bolo com refrigerante', emoji: '🍰🥤', correct: false },
                        { text: 'Pão, fruta e leite', emoji: '🍞🍎🥛', correct: true },
                        { text: 'Apenas doces', emoji: '🍭', correct: false }
                    ],
                    explanation: 'Esse café da manhã é equilibrado, pois fornece energia, vitaminas e nutrientes importantes para começar bem o dia.',
                    challenge: 'Pular 5 vezes com os dois pés juntos.',
                    team: 'blue'
                },
                {
                    id: 4,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses é um legume?',
                    options: [
                        { text: 'Maçã', emoji: '🍎', correct: false },
                        { text: 'Arroz', emoji: '🍚', correct: false },
                        { text: 'Cenoura', emoji: '🥕', correct: true }
                    ],
                    explanation: 'A cenoura é um legume, cresce na terra e é rica em vitaminas que fazem bem à visão e à saúde.',
                    challenge: 'Caminhar em linha reta, colocando um pé na frente do outro.',
                    team: 'green'
                },
                {
                    id: 5,
                    category: 'Alimentação Saudável',
                    text: 'Qual bebida é mais saudável para o corpo?',
                    options: [
                        { text: 'Refrigerante', emoji: '🥤', correct: false },
                        { text: 'Suco natural', emoji: '🧃', correct: false },
                        { text: 'Água', emoji: '💧', correct: true }
                    ],
                    explanation: 'A água é essencial para o corpo funcionar bem, ajuda na hidratação e não tem açúcar nem corantes.',
                    challenge: 'Correr no lugar por 20 segundos.',
                    team: 'blue'
                },
                {
                    id: 6,
                    category: 'Alimentação Saudável',
                    text: 'Comer frutas todos os dias faz bem porque elas têm:',
                    options: [
                        { text: 'Vitaminas', emoji: '💊', correct: true },
                        { text: 'Açúcar artificial', emoji: '🍬', correct: false },
                        { text: 'Gordura', emoji: '🥓', correct: false }
                    ],
                    explanation: 'As frutas possuem vitaminas que ajudam a proteger o corpo contra doenças e fortalecem o organismo.',
                    challenge: 'Ficar equilibrado em um pé só por 10 segundos (trocar o pé).',
                    team: 'green'
                },
                {
                    id: 7,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses alimentos é natural?',
                    options: [
                        { text: 'Batata frita de pacote', emoji: '🍟', correct: false },
                        { text: 'Maçã', emoji: '🍎', correct: true },
                        { text: 'Bala', emoji: '🍭', correct: false }
                    ],
                    explanation: 'A maçã é um alimento natural, sem conservantes, diferente dos alimentos industrializados.',
                    challenge: 'Dar 3 pulos para frente como um coelho.',
                    team: 'blue'
                },
                {
                    id: 8,
                    category: 'Alimentação Saudável',
                    text: 'Para ter energia para brincar, é importante comer:',
                    options: [
                        { text: 'Apenas doces', emoji: '🍭', correct: false },
                        { text: 'Alimentos variados', emoji: '🥗', correct: true },
                        { text: 'Só salgadinhos', emoji: '🥨', correct: false }
                    ],
                    explanation: 'Comer diferentes tipos de alimentos garante energia, força e saúde, pois cada alimento tem uma função no corpo.',
                    challenge: 'Agachar e levantar 8 vezes.',
                    team: 'green'
                },
                {
                    id: 9,
                    category: 'Alimentação Saudável',
                    text: 'Qual alimento vem do leite?',
                    options: [
                        { text: 'Queijo', emoji: '🧀', correct: true },
                        { text: 'Arroz', emoji: '🍚', correct: false },
                        { text: 'Alface', emoji: '🥬', correct: false }
                    ],
                    explanation: 'O queijo é feito do leite e mantém os nutrientes importantes, como o cálcio.',
                    challenge: 'Girar o corpo duas vezes e parar sem cair.',
                    team: 'blue'
                },
                {
                    id: 10,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses ajuda o intestino a funcionar melhor?',
                    options: [
                        { text: 'Frutas e verduras', emoji: '🍎🥦', correct: true },
                        { text: 'Refrigerante', emoji: '🥤', correct: false },
                        { text: 'Chocolate', emoji: '🍫', correct: false }
                    ],
                    explanation: 'Frutas e verduras têm fibras, que ajudam o intestino a funcionar melhor.',
                    challenge: 'Tocar o chão e depois esticar os braços para o alto 5 vezes.',
                    team: 'green'
                },
                {
                    id: 11,
                    category: 'Alimentação Saudável',
                    text: 'Qual é um exemplo de lanche saudável?',
                    options: [
                        { text: 'Fruta com iogurte', emoji: '🍓🥛', correct: true },
                        { text: 'Bala com refrigerante', emoji: '🍬🥤', correct: false },
                        { text: 'Só biscoito recheado', emoji: '🍪', correct: false }
                    ],
                    explanation: 'Fruta com iogurte é um lanche saudável porque combina vitaminas, proteínas e energia para o corpo.',
                    challenge: 'Arremessar uma bola em um alvo.',
                    team: 'blue'
                },
                {
                    id: 12,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses alimentos é rico em vitaminas?',
                    options: [
                        { text: 'Verduras', emoji: '🥬', correct: true },
                        { text: 'Doces', emoji: '🍭', correct: false },
                        { text: 'Frituras', emoji: '🍟', correct: false }
                    ],
                    explanation: 'As verduras são ricas em vitaminas e minerais importantes para o crescimento e a proteção do corpo.',
                    challenge: 'Passar a bola para um colega 5 vezes sem deixar cair.',
                    team: 'green'
                },
                {
                    id: 13,
                    category: 'Alimentação Saudável',
                    text: 'Comer muitos doces pode:',
                    options: [
                        { text: 'Fazer bem sempre', emoji: '👍', correct: false },
                        { text: 'Prejudicar a saúde', emoji: '😷', correct: true },
                        { text: 'Ajudar no crescimento', emoji: '📈', correct: false }
                    ],
                    explanation: 'Comer muitos doces pode causar cáries, falta de energia e outros problemas de saúde.',
                    challenge: 'Andar como um caranguejo por 10 segundos.',
                    team: 'blue'
                },
                {
                    id: 14,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses alimentos vem da horta?',
                    options: [
                        { text: 'Alface', emoji: '🥬', correct: true },
                        { text: 'Hambúrguer', emoji: '🍔', correct: false },
                        { text: 'Pizza', emoji: '🍕', correct: false }
                    ],
                    explanation: 'A alface cresce na horta e é um alimento natural e saudável.',
                    challenge: 'Fazer 5 saltos laterais.',
                    team: 'green'
                },
                {
                    id: 15,
                    category: 'Alimentação Saudável',
                    text: 'Qual alimento ajuda a proteger contra doenças?',
                    options: [
                        { text: 'Frutas', emoji: '🍎', correct: true },
                        { text: 'Balas', emoji: '🍭', correct: false },
                        { text: 'Refrigerante', emoji: '🥤', correct: false }
                    ],
                    explanation: 'As frutas ajudam a proteger o corpo contra doenças por causa das vitaminas que fortalecem o sistema de defesa.',
                    challenge: 'Bater palmas seguindo um ritmo.',
                    team: 'blue'
                },
                {
                    id: 16,
                    category: 'Alimentação Saudável',
                    text: 'O que devemos beber ao sentir sede?',
                    options: [
                        { text: 'Refrigerante', emoji: '🥤', correct: false },
                        { text: 'Água', emoji: '💧', correct: true },
                        { text: 'Suco artificial', emoji: '🧃', correct: false }
                    ],
                    explanation: 'A água mata a sede e ajuda o corpo a regular a temperatura e o funcionamento dos órgãos.',
                    challenge: 'Fingir que está remando um barco por 15 segundos.',
                    team: 'green'
                },
                {
                    id: 17,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses alimentos é mais saudável?',
                    options: [
                        { text: 'Fruta', emoji: '🍎', correct: true },
                        { text: 'Biscoito recheado', emoji: '🍪', correct: false },
                        { text: 'Doce', emoji: '🍭', correct: false }
                    ],
                    explanation: 'As frutas são mais saudáveis do que doces e biscoitos, pois têm nutrientes importantes.',
                    challenge: 'Pular dentro e fora de um círculo imaginário 6 vezes.',
                    team: 'blue'
                },
                {
                    id: 18,
                    category: 'Alimentação Saudável',
                    text: 'Comer bem ajuda a:',
                    options: [
                        { text: 'Ficar cansado', emoji: '😴', correct: false },
                        { text: 'Ter mais energia', emoji: '⚡', correct: true },
                        { text: 'Dormir mal', emoji: '🛌', correct: false }
                    ],
                    explanation: 'Comer bem ajuda o corpo a ter energia para brincar, estudar e praticar atividades físicas.',
                    challenge: 'Caminhar rápido e depois lento, alternando o ritmo.',
                    team: 'green'
                },
                {
                    id: 19,
                    category: 'Alimentação Saudável',
                    text: 'Para uma alimentação saudável, é importante:',
                    options: [
                        { text: 'Comer sempre a mesma coisa', emoji: '🔄', correct: false },
                        { text: 'Comer só doces', emoji: '🍭', correct: false },
                        { text: 'Comer alimentos variados', emoji: '🥗', correct: true }
                    ],
                    explanation: 'Uma alimentação variada garante que o corpo receba todos os nutrientes de que precisa para crescer e se manter saudável.',
                    challenge: 'Fazer 5 abdominais simples.',
                    team: 'blue'
                },
                {
                    id: 20,
                    category: 'Alimentação Saudável',
                    text: 'Qual desses alimentos ajuda a manter o corpo hidratado além da água?',
                    options: [
                        { text: 'Melancia', emoji: '🍉', correct: true },
                        { text: 'Salgadinho', emoji: '🥨', correct: false },
                        { text: 'Bala', emoji: '🍭', correct: false }
                    ],
                    explanation: 'A melancia tem muita água e ajuda na hidratação do corpo.',
                    challenge: 'Imitar um robô andando duro por 15 segundos.',
                    team: 'green'
                },
                
                // Saúde (20 perguntas)
                {
                    id: 21,
                    category: 'Saúde',
                    text: 'Por que precisamos dormir todos os dias?',
                    options: [
                        { text: 'Para perder tempo', emoji: '⏰', correct: false },
                        { text: 'Para o corpo descansar e crescer', emoji: '😴', correct: true },
                        { text: 'Para não brincar', emoji: '🚫', correct: false }
                    ],
                    explanation: 'Durante o sono, o corpo descansa, cresce e recupera as energias.',
                    challenge: 'Fazer corrida em zigue-zague entre objetos.',
                    team: 'blue'
                },
                {
                    id: 22,
                    category: 'Saúde',
                    text: 'Qual órgão bate o tempo todo dentro do nosso corpo?',
                    options: [
                        { text: 'Pulmão', emoji: '🫁', correct: false },
                        { text: 'Estômago', emoji: '🤢', correct: false },
                        { text: 'Coração', emoji: '❤️', correct: true }
                    ],
                    explanation: 'O coração bate sem parar para levar sangue para todo o corpo.',
                    challenge: 'Saltar por cima de uma linha imaginária 6 vezes.',
                    team: 'green'
                },
                {
                    id: 23,
                    category: 'Saúde',
                    text: 'Por que lavar as mãos é importante?',
                    options: [
                        { text: 'Para molhar as mãos', emoji: '💦', correct: false },
                        { text: 'Para tirar sujeira e germes', emoji: '🧼', correct: true },
                        { text: 'Para gastar água', emoji: '💧', correct: false }
                    ],
                    explanation: 'Lavar as mãos remove germes que podem causar doenças.',
                    challenge: 'Ficar em posição de avião por 10 segundos.',
                    team: 'blue'
                },
                {
                    id: 24,
                    category: 'Saúde',
                    text: 'O que acontece quando bebemos pouca água?',
                    options: [
                        { text: 'O corpo funciona melhor', emoji: '👍', correct: false },
                        { text: 'O corpo pode ficar desidratado', emoji: '😵', correct: true },
                        { text: 'O coração para', emoji: '🫀', correct: false }
                    ],
                    explanation: 'Sem água suficiente, o corpo não funciona bem e pode ficar desidratado.',
                    challenge: 'Andar para trás com cuidado por 10 passos.',
                    team: 'green'
                },
                {
                    id: 25,
                    category: 'Saúde',
                    text: 'Qual parte do corpo usamos para respirar?',
                    options: [
                        { text: 'Estômago', emoji: '🤢', correct: false },
                        { text: 'Pulmões', emoji: '🫁', correct: true },
                        { text: 'Pernas', emoji: '🦵', correct: false }
                    ],
                    explanation: 'Os pulmões são responsáveis por puxar o ar para dentro do corpo.',
                    challenge: 'Fingir que está nadando.',
                    team: 'blue'
                },
                {
                    id: 26,
                    category: 'Saúde',
                    text: 'Por que praticar atividade física faz bem?',
                    options: [
                        { text: 'Porque cansa', emoji: '😫', correct: false },
                        { text: 'Porque fortalece o corpo', emoji: '💪', correct: true },
                        { text: 'Porque dá fome', emoji: '🍽️', correct: false }
                    ],
                    explanation: 'A atividade física fortalece músculos, ossos e melhora a saúde.',
                    challenge: 'Fazer 5 flexões na parede.',
                    team: 'green'
                },
                {
                    id: 27,
                    category: 'Saúde',
                    text: 'Qual hábito ajuda a manter os dentes saudáveis?',
                    options: [
                        { text: 'Comer doces', emoji: '🍭', correct: false },
                        { text: 'Escovar os dentes', emoji: '🦷', correct: true },
                        { text: 'Beber refrigerante', emoji: '🥤', correct: false }
                    ],
                    explanation: 'Escovar os dentes remove restos de comida e evita cáries.',
                    challenge: 'Pular como sapo e voltar andando.',
                    team: 'blue'
                },
                {
                    id: 28,
                    category: 'Saúde',
                    text: 'Por que precisamos comer frutas e verduras?',
                    options: [
                        { text: 'Só pelo sabor', emoji: '😋', correct: false },
                        { text: 'Porque têm vitaminas', emoji: '💊', correct: true },
                        { text: 'Porque são caras', emoji: '💰', correct: false }
                    ],
                    explanation: 'Elas têm vitaminas que ajudam o corpo a se proteger de doenças.',
                    challenge: 'Marchar levantando bem os joelhos por 20 segundos.',
                    team: 'green'
                },
                {
                    id: 29,
                    category: 'Saúde',
                    text: 'O que ajuda a evitar doenças?',
                    options: [
                        { text: 'Não lavar as mãos', emoji: '🚫', correct: false },
                        { text: 'Vacinas', emoji: '💉', correct: true },
                        { text: 'Comer doces', emoji: '🍭', correct: false }
                    ],
                    explanation: 'As vacinas protegem o corpo contra várias doenças.',
                    challenge: 'Criar um movimento de dança livre por 15 segundos.',
                    team: 'blue'
                },
                {
                    id: 30,
                    category: 'Saúde',
                    text: 'Por que precisamos tomar sol com cuidado?',
                    options: [
                        { text: 'Para ficar vermelho', emoji: '🔴', correct: false },
                        { text: 'Para ajudar na vitamina D', emoji: '☀️', correct: true },
                        { text: 'Para passar mal', emoji: '🤢', correct: false }
                    ],
                    explanation: 'O sol ajuda o corpo a produzir vitamina D, importante para os ossos.',
                    challenge: 'Bater os pés no chão seguindo um ritmo.',
                    team: 'green'
                },
                {
                    id: 31,
                    category: 'Saúde',
                    text: 'Qual parte do corpo nos ajuda a pensar?',
                    options: [
                        { text: 'Coração', emoji: '❤️', correct: false },
                        { text: 'Cérebro', emoji: '🧠', correct: true },
                        { text: 'Pulmão', emoji: '🫁', correct: false }
                    ],
                    explanation: 'O cérebro controla pensamentos, emoções e movimentos.',
                    challenge: 'Fazer um alongamento de braços e pernas.',
                    team: 'blue'
                },
                {
                    id: 32,
                    category: 'Saúde',
                    text: 'Por que é importante brincar e se movimentar?',
                    options: [
                        { text: 'Para sujar a roupa', emoji: '👕', correct: false },
                        { text: 'Para o corpo e a mente ficarem saudáveis', emoji: '💪🧠', correct: true },
                        { text: 'Para cansar', emoji: '😫', correct: false }
                    ],
                    explanation: 'Brincar ajuda no desenvolvimento físico e emocional.',
                    challenge: 'Girar os braços para frente e para trás.',
                    team: 'green'
                },
                {
                    id: 33,
                    category: 'Saúde',
                    text: 'O que acontece quando ficamos muito tempo sentados?',
                    options: [
                        { text: 'O corpo fica mais saudável', emoji: '👍', correct: false },
                        { text: 'O corpo fica parado demais', emoji: '🪑', correct: true },
                        { text: 'Ficamos mais fortes', emoji: '💪', correct: false }
                    ],
                    explanation: 'Ficar parado por muito tempo não faz bem para o corpo.',
                    challenge: 'Passar por baixo de uma "ponte" feita com um colega.',
                    team: 'blue'
                },
                {
                    id: 34,
                    category: 'Saúde',
                    text: 'Por que devemos respirar pelo nariz?',
                    options: [
                        { text: 'Porque é mais bonito', emoji: '👃', correct: false },
                        { text: 'Porque o nariz filtra o ar', emoji: '🌬️', correct: true },
                        { text: 'Porque cansa menos', emoji: '😴', correct: false }
                    ],
                    explanation: 'O nariz filtra sujeiras antes do ar chegar aos pulmões.',
                    challenge: 'Fingir que empurra uma parede por 10 segundos.',
                    team: 'green'
                },
                {
                    id: 35,
                    category: 'Saúde',
                    text: 'O que ajuda a manter o corpo limpo e saudável?',
                    options: [
                        { text: 'Tomar banho', emoji: '🚿', correct: true },
                        { text: 'Não se lavar', emoji: '🚫', correct: false },
                        { text: 'Dormir sujo', emoji: '🛌', correct: false }
                    ],
                    explanation: 'O banho remove sujeiras e ajuda a evitar doenças.',
                    challenge: 'Imitar um esporte (futebol, basquete ou corrida).',
                    team: 'blue'
                },
                {
                    id: 36,
                    category: 'Saúde',
                    text: 'Por que precisamos comer todos os dias?',
                    options: [
                        { text: 'Só por gosto', emoji: '😋', correct: false },
                        { text: 'Para ter energia', emoji: '⚡', correct: true },
                        { text: 'Para engordar', emoji: '📈', correct: false }
                    ],
                    explanation: 'Os alimentos fornecem energia para o corpo funcionar.',
                    challenge: 'Criar um movimento novo e mostrar para a turma.',
                    team: 'green'
                },
                {
                    id: 37,
                    category: 'Saúde',
                    text: 'Qual hábito ajuda a evitar gripes?',
                    options: [
                        { text: 'Cobrir a boca ao espirrar', emoji: '🤧', correct: true },
                        { text: 'Tossir na mão', emoji: '🤲', correct: false },
                        { text: 'Não lavar as mãos', emoji: '🚫', correct: false }
                    ],
                    explanation: 'Cobrir a boca evita espalhar germes para outras pessoas.',
                    challenge: 'Pular alternando os pés (direito e esquerdo) 10 vezes.',
                    team: 'blue'
                },
                {
                    id: 38,
                    category: 'Saúde',
                    text: 'Por que rir faz bem para a saúde?',
                    options: [
                        { text: 'Porque cansa', emoji: '😫', correct: false },
                        { text: 'Porque melhora o humor', emoji: '😊', correct: true },
                        { text: 'Porque dá fome', emoji: '🍽️', correct: false }
                    ],
                    explanation: 'Rir ajuda a relaxar e melhora o bem-estar.',
                    challenge: 'Andar na ponta dos pés por 15 segundos.',
                    team: 'green'
                },
                {
                    id: 39,
                    category: 'Saúde',
                    text: 'O que acontece quando cuidamos bem do corpo?',
                    options: [
                        { text: 'Ficamos mais doentes', emoji: '😷', correct: false },
                        { text: 'Temos mais saúde', emoji: '👍', correct: true },
                        { text: 'Perdemos energia', emoji: '🔋', correct: false }
                    ],
                    explanation: 'Bons hábitos ajudam o corpo a funcionar melhor.',
                    challenge: 'Andar na ponta dos pés por 15 segundos.',
                    team: 'blue'
                },
                {
                    id: 40,
                    category: 'Saúde',
                    text: 'Ter hábitos saudáveis significa:',
                    options: [
                        { text: 'Cuidar do corpo todos os dias', emoji: '✅', correct: true },
                        { text: 'Comer só doces', emoji: '🍭', correct: false },
                        { text: 'Não dormir', emoji: '🚫', correct: false }
                    ],
                    explanation: 'Hábitos saudáveis ajudam a crescer forte e com saúde.',
                    challenge: 'Equilibrar-se agachado por 10 segundos.',
                    team: 'green'
                }
            ]
        };

        // Elementos da DOM
        const screens = {
            screen1: document.getElementById('screen1'),
            screen2: document.getElementById('screen2'),
            screen3: document.getElementById('screen3'),
            screen4: document.getElementById('screen4'),
            screen5: document.getElementById('screen5'),
            screen6: document.getElementById('screen6')
        };

        // Inicialização do jogo
        document.addEventListener('DOMContentLoaded', function() {
            // Botões de navegação
            document.getElementById('startBtn').addEventListener('click', () => {
                showScreen(2);
                loadAnimalOptions();
            });
            document.getElementById('configBtn').addEventListener('click', startQuiz);
            
            // Botão de feedback (muda de função dependendo da resposta)
            document.getElementById('feedbackBtn').addEventListener('click', handleFeedbackButton);
            
            // Botões de desafio
            document.getElementById('completeChallengeBtn').addEventListener('click', () => completeChallenge(true));
            document.getElementById('skipChallengeBtn').addEventListener('click', () => completeChallenge(false));
            
            // Botão de reiniciar
            document.getElementById('restartBtn').addEventListener('click', restartGame);
            
            // Inicializar a primeira tela
            showScreen(1);
        });

        // Carregar opções de animais
        function loadAnimalOptions() {
            const blueAnimalOptions = document.getElementById('blueAnimalOptions');
            const greenAnimalOptions = document.getElementById('greenAnimalOptions');
            
            blueAnimalOptions.innerHTML = '';
            greenAnimalOptions.innerHTML = '';
            
            gameData.availableAnimals.forEach((animal, index) => {
                // Para equipe azul
                const blueOption = document.createElement('div');
                blueOption.className = 'animal-option';
                if (index === 0) {
                    blueOption.classList.add('selected');
                    gameData.blueAnimal = animal;
                }
                blueOption.innerHTML = `
                    <div class="animal-emoji">${animal.emoji}</div>
                    <div>${animal.name}</div>
                `;
                blueOption.addEventListener('click', () => {
                    document.querySelectorAll('#blueAnimalOptions .animal-option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    blueOption.classList.add('selected');
                    gameData.blueAnimal = animal;
                });
                blueAnimalOptions.appendChild(blueOption);
                
                // Para equipe verde
                const greenOption = document.createElement('div');
                greenOption.className = 'animal-option';
                if (index === 1) {
                    greenOption.classList.add('selected');
                    gameData.greenAnimal = animal;
                }
                greenOption.innerHTML = `
                    <div class="animal-emoji">${animal.emoji}</div>
                    <div>${animal.name}</div>
                `;
                greenOption.addEventListener('click', () => {
                    document.querySelectorAll('#greenAnimalOptions .animal-option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    greenOption.classList.add('selected');
                    gameData.greenAnimal = animal;
                });
                greenAnimalOptions.appendChild(greenOption);
            });
        }

        // Função para mostrar uma tela específica
        function showScreen(screenNumber) {
            // Esconder todas as telas
            Object.values(screens).forEach(screen => {
                screen.classList.remove('active-screen');
            });
            
            // Mostrar a tela desejada
            screens[`screen${screenNumber}`].classList.add('active-screen');
            gameData.currentScreen = screenNumber;
            
            // Configurações específicas para cada tela
            if (screenNumber === 3) {
                loadQuestion();
            } else if (screenNumber === 5) {
                updateChallenge();
            } else if (screenNumber === 6) {
                updateFinalResults();
            }
        }

        // Iniciar o quiz com configurações
        function startQuiz() {
            // Obter número de participantes
            const blueInput = document.getElementById('blueParticipants');
            const greenInput = document.getElementById('greenParticipants');
            
            gameData.blueParticipants = Math.min(20, Math.max(1, parseInt(blueInput.value) || 5));
            gameData.greenParticipants = Math.min(20, Math.max(1, parseInt(greenInput.value) || 5));
            
            // Resetar dados do jogo
            gameData.scores.blue = 0;
            gameData.scores.green = 0;
            gameData.currentQuestionIndex = 0;
            gameData.currentParticipant.blue = 1;
            gameData.currentParticipant.green = 1;
            gameData.answeredQuestions = 0;
            gameData.totalQuestions = gameData.blueParticipants + gameData.greenParticipants;
            
            // Atualizar a interface
            document.getElementById('scoreBlue').textContent = '0';
            document.getElementById('scoreGreen').textContent = '0';
            
            // Atualizar nomes das equipes com animais escolhidos
            document.getElementById('blueTeamName').textContent = `Equipe Azul - ${gameData.blueAnimal.name}`;
            document.getElementById('greenTeamName').textContent = `Equipe Verde - ${gameData.greenAnimal.name}`;
            document.getElementById('blueAnimalDisplay').textContent = gameData.blueAnimal.emoji;
            document.getElementById('greenAnimalDisplay').textContent = gameData.greenAnimal.emoji;
            
            // Ir para a tela de perguntas
            showScreen(3);
        }

        // Carregar pergunta atual
        function loadQuestion() {
            // Determinar qual equipe responde
            const totalAnswered = gameData.answeredQuestions;
            const isBlueTurn = (totalAnswered % 2 === 0);
            
            gameData.currentTeam = isBlueTurn ? 'blue' : 'green';
            
            // Verificar se a equipe ainda tem participantes
            if (isBlueTurn && gameData.currentParticipant.blue > gameData.blueParticipants) {
                // Equipe azul já respondeu todos, próxima é verde
                gameData.currentTeam = 'green';
            } else if (!isBlueTurn && gameData.currentParticipant.green > gameData.greenParticipants) {
                // Equipe verde já respondeu todos, próxima é azul
                gameData.currentTeam = 'blue';
            }
            
            // Encontrar uma pergunta para a equipe atual
            let question;
            if (gameData.currentTeam === 'blue') {
                // Encontrar pergunta não respondida para equipe azul
                const blueQuestions = gameData.questions.filter(q => q.team === 'blue');
                question = blueQuestions[gameData.currentParticipant.blue - 1];
            } else {
                // Encontrar pergunta não respondida para equipe verde
                const greenQuestions = gameData.questions.filter(q => q.team === 'green');
                question = greenQuestions[gameData.currentParticipant.green - 1];
            }
            
            if (!question) {
                // Se não houver mais perguntas, finalizar
                showScreen(6);
                return;
            }
            
            // Atualizar interface
            const teamTurnIndicator = document.getElementById('teamTurnIndicator');
            if (gameData.currentTeam === 'blue') {
                teamTurnIndicator.textContent = `Vez da Equipe Azul - ${gameData.blueAnimal.name} ${gameData.blueAnimal.emoji} (Participante ${gameData.currentParticipant.blue} de ${gameData.blueParticipants})`;
                teamTurnIndicator.className = 'team-turn blue-turn';
            } else {
                teamTurnIndicator.textContent = `Vez da Equipe Verde - ${gameData.greenAnimal.name} ${gameData.greenAnimal.emoji} (Participante ${gameData.currentParticipant.green} de ${gameData.greenParticipants})`;
                teamTurnIndicator.className = 'team-turn green-turn';
            }
            
            // Atualizar número da pergunta
            document.getElementById('questionNumber').textContent = `Pergunta ${gameData.answeredQuestions + 1} de ${gameData.totalQuestions}`;
            
            // Atualizar participante atual
            document.getElementById('currentParticipant').textContent = 
                gameData.currentTeam === 'blue' 
                    ? `Participante ${gameData.currentParticipant.blue}` 
                    : `Participante ${gameData.currentParticipant.green}`;
            
            // Atualizar categoria da pergunta
            const categoryBadge = document.getElementById('questionCategory');
            categoryBadge.textContent = question.category;
            categoryBadge.className = 'category-badge ' + 
                (question.category === 'Alimentação Saudável' ? 'category-food' : 'category-health');
            
            // Atualizar texto da pergunta
            document.getElementById('questionText').textContent = question.text;
            
            // Atualizar opções
            const optionsContainer = document.getElementById('optionsContainer');
            optionsContainer.innerHTML = '';
            
            question.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.innerHTML = `
                    <span class="option-icon">${option.emoji}</span>
                    <span>${option.text}</span>
                `;
                
                optionElement.addEventListener('click', () => selectOption(option, index, question));
                optionsContainer.appendChild(optionElement);
            });
            
            // Atualizar progresso
            const progress = (gameData.answeredQuestions / gameData.totalQuestions) * 100;
            document.getElementById('progressFill').style.width = `${progress}%`;
            
            // Atualizar pontuação
            document.getElementById('scoreBlue').textContent = gameData.scores.blue;
            document.getElementById('scoreGreen').textContent = gameData.scores.green;
        }

        // Selecionar uma opção
        function selectOption(selectedOption, optionIndex, question) {
            const options = document.querySelectorAll('.option');
            
            // Marcar todas as opções como corretas/erradas
            options.forEach((option, index) => {
                option.classList.remove('correct', 'wrong');
                if (question.options[index].correct) {
                    option.classList.add('correct');
                } else if (index === optionIndex) {
                    option.classList.add('wrong');
                }
            });
            
            // Verificar se a resposta está correta
            const isCorrect = selectedOption.correct;
            gameData.lastAnswerCorrect = isCorrect;
            
            // Atualizar pontuação se estiver correto
            if (isCorrect) {
                gameData.scores[gameData.currentTeam] += 10;
            }
            
            // Preparar feedback
            const feedbackTitle = document.getElementById('feedbackTitle');
            const feedbackText = document.getElementById('feedbackText');
            const challengeInstruction = document.getElementById('challengeInstruction');
            const feedbackBtn = document.getElementById('feedbackBtn');
            
            if (isCorrect) {
                feedbackTitle.textContent = 'Resposta Correta! 🎉';
                feedbackTitle.style.color = '#4caf50';
                feedbackText.innerHTML = `<strong>${selectedOption.emoji} ${selectedOption.text}</strong> está correto!<br><br>${question.explanation}`;
                challengeInstruction.style.display = 'none';
                
                // Mudar o botão para "Próxima Pergunta"
                feedbackBtn.textContent = 'Próxima Pergunta ➡️';
                feedbackBtn.className = 'action-btn next-btn';
            } else {
                feedbackTitle.textContent = 'Resposta Incorreta 😕';
                feedbackTitle.style.color = '#f44336';
                const correctOption = question.options.find(opt => opt.correct);
                feedbackText.innerHTML = `<strong>${selectedOption.emoji} ${selectedOption.text}</strong> não está correto.<br><br>
                                          <strong>A resposta correta é:</strong> ${correctOption.emoji} ${correctOption.text}<br><br>
                                          ${question.explanation}`;
                challengeInstruction.style.display = 'block';
                
                // Mudar o botão para "Cumprir Desafio"
                feedbackBtn.textContent = 'Cumprir Desafio 💪';
                feedbackBtn.className = 'action-btn challenge-btn';
                
                // Guardar o desafio específico da pergunta
                gameData.currentChallenge = question.challenge;
            }
            
            // Mostrar tela de feedback após um breve delay
            setTimeout(() => showScreen(4), 1000);
        }

        // Lidar com o botão de feedback (muda função dependendo da resposta)
        function handleFeedbackButton() {
            if (gameData.lastAnswerCorrect) {
                // Se a resposta foi correta, vai para a próxima pergunta
                nextQuestion();
            } else {
                // Se a resposta foi incorreta, vai para a tela de desafio
                showScreen(5);
            }
        }

        // Avançar para próxima pergunta
        function nextQuestion() {
            // Incrementar contador de participante da equipe atual
            if (gameData.currentTeam === 'blue') {
                gameData.currentParticipant.blue++;
            } else {
                gameData.currentParticipant.green++;
            }
            
            gameData.answeredQuestions++;
            
            // Verificar se o jogo terminou
            checkGameEnd();
        }

        // Atualizar desafio
        function updateChallenge() {
            // Usar o desafio específico da pergunta
            const challenge = gameData.currentChallenge;
            
            document.getElementById('challengeTitle').textContent = 
                `Desafio para Equipe ${gameData.currentTeam === 'blue' ? `Azul - ${gameData.blueAnimal.name} ${gameData.blueAnimal.emoji}` : `Verde - ${gameData.greenAnimal.name} ${gameData.greenAnimal.emoji}`}`;
            document.getElementById('challengeText').textContent = challenge;
        }

        // Completar desafio
        function completeChallenge(didComplete) {
            // Ajustar pontuação baseado na escolha
            if (didComplete) {
                gameData.scores[gameData.currentTeam] += 10; // +10 por cumprir o desafio
            } else {
                gameData.scores[gameData.currentTeam] -= 10; // -10 por não cumprir
            }
            
            // Garantir que a pontuação não fique negativa
            if (gameData.scores[gameData.currentTeam] < 0) {
                gameData.scores[gameData.currentTeam] = 0;
            }
            
            // Avançar para próxima pergunta
            nextQuestion();
        }

        // Verificar se o jogo terminou
        function checkGameEnd() {
            const blueFinished = gameData.currentParticipant.blue > gameData.blueParticipants;
            const greenFinished = gameData.currentParticipant.green > gameData.greenParticipants;
            
            if (blueFinished && greenFinished) {
                // Todas as perguntas respondidas
                showScreen(6);
            } else {
                // Carregar próxima pergunta
                loadQuestion();
                showScreen(3);
            }
        }

        // Atualizar resultados finais
        function updateFinalResults() {
            // Atualizar pontuações finais
            document.getElementById('finalScoreBlue').textContent = gameData.scores.blue;
            document.getElementById('finalScoreGreen').textContent = gameData.scores.green;
            
            // Atualizar nomes das equipes
            document.getElementById('finalBlueTeamName').textContent = `Equipe Azul - ${gameData.blueAnimal.name}`;
            document.getElementById('finalGreenTeamName').textContent = `Equipe Verde - ${gameData.greenAnimal.name}`;
            document.getElementById('finalBlueAnimalDisplay').textContent = gameData.blueAnimal.emoji;
            document.getElementById('finalGreenAnimalDisplay').textContent = gameData.greenAnimal.emoji;
            
            // Determinar o vencedor
            const winnerAnnouncement = document.getElementById('winnerAnnouncement');
            
            if (gameData.scores.blue > gameData.scores.green) {
                winnerAnnouncement.innerHTML = `🏆 Equipe Azul - ${gameData.blueAnimal.name} Venceu! ${gameData.blueAnimal.emoji}<br><small>Parabéns pela vitória!</small>`;
                winnerAnnouncement.style.background = 'linear-gradient(145deg, #bbdefb, #90caf9)';
                winnerAnnouncement.style.color = '#0d47a1';
            } else if (gameData.scores.green > gameData.scores.blue) {
                winnerAnnouncement.innerHTML = `🏆 Equipe Verde - ${gameData.greenAnimal.name} Venceu! ${gameData.greenAnimal.emoji}<br><small>Parabéns pela vitória!</small>`;
                winnerAnnouncement.style.background = 'linear-gradient(145deg, #c8e6c9, #a5d6a7)';
                winnerAnnouncement.style.color = '#1b5e20';
            } else {
                winnerAnnouncement.innerHTML = '🤝 Empate!<br><small>Ambas as equipes foram incríveis!</small>';
                winnerAnnouncement.style.background = 'linear-gradient(145deg, #fff9c4, #fff59d)';
                winnerAnnouncement.style.color = '#f57f17';
            }
        }

        // Reiniciar o jogo
        function restartGame() {
            // Voltar para a primeira tela
            showScreen(1);
        }
    </script>
</body>
</html>
