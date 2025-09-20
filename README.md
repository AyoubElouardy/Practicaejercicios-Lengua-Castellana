<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lenguaje - PracticaEjercicios.com</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #1e90ff;
            --secondary-color: #4682b4;
            --accent-color: #87ceeb;
            --light-color: #f8f9fa;
            --dark-color: #343a40;
            --success-color: #28a745;
            --warning-color: #ffc107;
            --danger-color: #dc3545;
            --language-color: #1e90ff;
            --grammar-color: #4682b4;
            --spelling-color: #00b7eb;
            --reading-color: #87cefa;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        header {
            background: linear-gradient(135deg, var(--language-color), #4682b4);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
        }
        
        .logo span {
            color: var(--accent-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--accent-color);
        }
        
        .hero {
            background: linear-gradient(rgba(30, 144, 255, 0.8), rgba(70, 130, 180, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100"><rect fill="%231e90ff" width="100" height="100"/><path fill="%234682b4" d="M0 0L100 100" stroke-width="0"/></svg>');
            background-size: cover;
            color: white;
            padding: 4rem 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: #6ab8e3;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid white;
        }
        
        .btn-outline:hover {
            background: white;
            color: var(--language-color);
        }
        
        .btn-language { background-color: var(--language-color); }
        .btn-language:hover { background-color: #4682b4; }
        .btn-grammar { background-color: var(--grammar-color); }
        .btn-grammar:hover { background-color: #4169e1; }
        .btn-spelling { background-color: var(--spelling-color); }
        .btn-spelling:hover { background-color: #00a1d6; }
        .btn-reading { background-color: var(--reading-color); }
        .btn-reading:hover { background-color: #70b8e3; }
        
        .topics {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--dark-color);
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
        }
        
        .section-title p {
            color: #6c757d;
        }
        
        .topics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .topic-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
            border-top: 5px solid var(--language-color);
        }
        
        .topic-card:hover {
            transform: translateY(-5px);
        }
        
        .topic-card.grammar { border-top-color: var(--grammar-color); }
        .topic-card.spelling { border-top-color: var(--spelling-color); }
        .topic-card.reading { border-top-color: var(--reading-color); }
        
        .topic-icon {
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: white;
        }
        
        .topic-card.grammar .topic-icon { background: linear-gradient(135deg, var(--grammar-color), #4169e1); }
        .topic-card.spelling .topic-icon { background: linear-gradient(135deg, var(--spelling-color), #00a1d6); }
        .topic-card.reading .topic-icon { background: linear-gradient(135deg, var(--reading-color), #70b8e3); }
        
        .topic-content {
            padding: 1.5rem;
        }
        
        .topic-content h3 {
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        .topic-content p {
            color: #6c757d;
            margin-bottom: 1rem;
        }
        
        .exercises {
            padding: 4rem 0;
            background-color: #f8f9fa;
        }
        
        .exercise-tabs {
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 2rem;
            border-bottom: 1px solid #ddd;
        }
        
        .exercise-tab {
            padding: 0.8rem 1.5rem;
            cursor: pointer;
            background-color: #eee;
            margin-right: 0.5rem;
            border-radius: 5px 5px 0 0;
            transition: all 0.3s;
        }
        
        .exercise-tab.active {
            background-color: white;
            border: 1px solid #ddd;
            border-bottom: none;
            color: var(--language-color);
            font-weight: 600;
        }
        
        .exercise-container {
            background-color: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            margin-bottom: 2rem;
            display: none;
        }
        
        .exercise-container.active {
            display: block;
        }
        
        .exercise-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .exercise-title {
            font-size: 1.5rem;
            color: var(--dark-color);
        }
        
        .exercise-progress {
            display: flex;
            align-items: center;
            background-color: #f0f2f5;
            padding: 0.5rem 1rem;
            border-radius: 50px;
        }
        
        .exercise-question {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }
        
        .options-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1rem;
            margin-bottom: 1.5rem;
        }
        
        .option {
            background-color: #f8f9fa;
            padding: 1rem;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .option:hover {
            border-color: var(--accent-color);
        }
        
        .option.selected {
            border-color: var(--primary-color);
            background-color: #e8f4fd;
        }
        
        .option.correct {
            border-color: var(--success-color);
            background-color: #d4edda;
        }
        
        .option.incorrect {
            border-color: var(--danger-color);
            background-color: #f8d7da;
        }
        
        .input-answer {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            margin-bottom: 1rem;
        }
        
        .exercise-feedback {
            padding: 1rem;
            border-radius: 8px;
            margin-top: 1rem;
            display: none;
        }
        
        .feedback-correct {
            background-color: #d4edda;
            border-left: 4px solid var(--success-color);
        }
        
        .feedback-incorrect {
            background-color: #f8d7da;
            border-left: 4px solid var(--danger-color);
        }
        
        .subject-page {
            display: none;
            padding: 2rem 0;
        }
        
        .subject-page.active {
            display: block;
        }
        
        .back-button {
            display: inline-flex;
            align-items: center;
            margin-bottom: 2rem;
            color: var(--language-color);
            text-decoration: none;
            font-weight: 600;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            background-color: #f8f9fa;
            transition: all 0.3s;
        }
        
        .back-button:hover {
            background-color: #e9ecef;
        }
        
        .back-button i {
            margin-right: 0.5rem;
        }
        
        .difficulty {
            padding: 4rem 0;
            background-color: white;
        }
        
        .difficulty-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .difficulty-card {
            text-align: center;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .difficulty-card:hover {
            transform: translateY(-5px);
        }
        
        .difficulty-basic { border-top: 5px solid var(--success-color); }
        .difficulty-intermediate { border-top: 5px solid var(--warning-color); }
        .difficulty-advanced { border-top: 5px solid var(--language-color); }
        
        .difficulty-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .difficulty-basic .difficulty-icon { color: var(--success-color); }
        .difficulty-intermediate .difficulty-icon { color: var(--warning-color); }
        .difficulty-advanced .difficulty-icon { color: var(--language-color); }
        
        .difficulty-card h3 {
            margin-bottom: 1rem;
            color: var(--dark-color);
        }
        
        .difficulty-card ul {
            list-style: none;
            text-align: left;
            margin-top: 1rem;
            max-height: 200px;
            overflow-y: auto;
        }
        
        .difficulty-card ul li {
            margin-bottom: 0.5rem;
            padding-left: 1.5rem;
            position: relative;
        }
        
        .difficulty-card ul li:before {
            content: "•";
            color: var(--language-color);
            font-weight: bold;
            position: absolute;
            left: 0;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 10px;
            width: 100%;
            max-width: 400px;
            padding: 2rem;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.2);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .close-modal {
            font-size: 1.5rem;
            cursor: pointer;
            color: #6c757d;
            background: none;
            border: none;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--dark-color);
        }
        
        .form-group input {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
        }
        
        .user-menu {
            position: relative;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--accent-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        .user-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            width: 200px;
            padding: 1rem;
            margin-top: 0.5rem;
            display: none;
        }
        
        .user-dropdown.active {
            display: block;
            animation: fadeIn 0.3s;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }
        
        .user-details {
            margin-left: 0.5rem;
        }
        
        .user-name {
            font-weight: 600;
            color: var(--dark-color);
        }
        
        .user-email {
            font-size: 0.8rem;
            color: #6c757d;
        }
        
        .user-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .stat-label {
            font-size: 0.8rem;
            color: #6c757d;
        }
        
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 3rem 0 1rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column ul li a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #495057;
            color: #adb5bd;
            font-size: 0.9rem;
        }
        
        .completion-message {
            text-align: center;
            padding: 2rem;
            background-color: #e8f5e9;
            border-radius: 8px;
            margin-top: 1.5rem;
            border-left: 4px solid var(--success-color);
            display: none;
        }
        
        .more-exercises {
            text-align: center;
            margin-top: 1rem;
            font-size: 0.9rem;
            color: #6c757d;
            font-style: italic;
            display: none;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 0.5rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .topics-grid, .difficulty-cards {
                grid-template-columns: 1fr;
            }
            
            .options-container {
                grid-template-columns: 1fr;
            }
            
            .exercise-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .exercise-progress {
                margin-top: 1rem;
            }
            
            .exercise-tabs {
                flex-direction: column;
            }
            
            .exercise-tab {
                margin-bottom: 0.5rem;
                border-radius: 5px;
            }
            
            .exercise-tab.active {
                border: 1px solid #ddd;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">Practica<span>Ejercicios</span></div>
            <nav>
                <ul>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios/" target="_blank">Inicio</a></li>
                    <li><a href="#" class="nav-link" data-page="language">Lenguaje</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank">Matemáticas</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank">Ciencias</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank">Sociales</a></li>
                </ul>
            </nav>
            <div class="user-menu">
                <div class="user-avatar" id="userAvatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="user-dropdown" id="userDropdown">
                    <div class="user-info">
                        <div class="user-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="user-details">
                            <div class="user-name" id="userName">Invitado</div>
                            <div class="user-email" id="userEmail">No has iniciado sesión</div>
                        </div>
                    </div>
                    <div class="user-stats">
                        <div class="stat">
                            <div class="stat-value" id="completedExercises">0</div>
                            <div class="stat-label">Completados</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value" id="correctAnswers">0%</div>
                            <div class="stat-label">Precisión</div>
                        </div>
                    </div>
                    <button class="btn btn-language" id="loginBtn">Iniciar Sesión</button>
                </div>
            </div>
        </div>
    </header>

    <main id="main-content">
        <section class="subject-page active" id="home-page">
            <section class="hero">
                <div class="container">
                    <h1>Domina el Lenguaje con Ejercicios Prácticos</h1>
                    <p>Gramática, ortografía, comprensión lectora y más. Miles de ejercicios interactivos para todos los niveles.</p>
                    <a href="#" class="btn btn-language nav-link" data-page="language">Comenzar ahora</a>
                    <a href="#" class="btn btn-outline">Ver ejemplos</a>
                </div>
            </section>
            <section class="topics">
                <div class="container">
                    <div class="section-title">
                        <h2>Temas de Lenguaje</h2>
                        <p>Explora nuestros ejercicios por área del español</p>
                    </div>
                    <div class="topics-grid">
                        <div class="topic-card grammar">
                            <div class="topic-icon">✍️</div>
                            <div class="topic-content">
                                <h3>Gramática</h3>
                                <p>Verbos, sustantivos, adjetivos y estructuras gramaticales.</p>
                                <a href="#" class="btn btn-grammar practice-btn" data-subject="grammar">Practicar</a>
                            </div>
                        </div>
                        <div class="topic-card spelling">
                            <div class="topic-icon">📝</div>
                            <div class="topic-content">
                                <h3>Ortografía</h3>
                                <p>Acentuación, puntuación y reglas ortográficas.</p>
                                <a href="#" class="btn btn-spelling practice-btn" data-subject="spelling">Practicar</a>
                            </div>
                        </div>
                        <div class="topic-card reading">
                            <div class="topic-icon">📚</div>
                            <div class="topic-content">
                                <h3>Comprensión Lectora</h3>
                                <p>Análisis de textos, inferencias y comprensión.</p>
                                <a href="#" class="btn btn-reading practice-btn" data-subject="reading">Practicar</a>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <section class="difficulty">
                <div class="container">
                    <div class="section-title">
                        <h2>Ejercicios por Nivel</h2>
                        <p>Selecciona ejercicios según tu nivel de conocimiento</p>
                    </div>
                    <div class="difficulty-cards">
                        <div class="difficulty-card difficulty-basic">
                            <div class="difficulty-icon"><i class="fas fa-star"></i></div>
                            <h3>Nivel Básico</h3>
                            <p>Ejercicios para principiantes y estudiantes de primaria</p>
                            <ul>
                                <li>Reglas básicas de ortografía</li>
                                <li>Identificación de partes de la oración</li>
                                <li>Comprensión de textos cortos</li>
                            </ul>
                            <a href="#" class="btn">Comenzar</a>
                        </div>
                        <div class="difficulty-card difficulty-intermediate">
                            <div class="difficulty-icon"><i class="fas fa-star-half-alt"></i></div>
                            <h3>Nivel Intermedio</h3>
                            <p>Ejercicios para estudiantes de secundaria</p>
                            <ul>
                                <li>Conjugación verbal compleja</li>
                                <li>Reglas de acentuación avanzada</li>
                                <li>Análisis de textos narrativos</li>
                            </ul>
                            <a href="#" class="btn">Comenzar</a>
                        </div>
                        <div class="difficulty-card difficulty-advanced">
                            <div class="difficulty-icon"><i class="fas fa-stars"></i></div>
                            <h3>Nivel Avanzado</h3>
                            <p>Ejercicios para bachillerato y universidad</p>
                            <ul>
                                <li>Análisis sintáctico</li>
                                <li>Ortografía técnica</li>
                                <li>Comprensión de textos complejos</li>
                            </ul>
                            <a href="#" class="btn">Comenzar</a>
                        </div>
                    </div>
                </div>
            </section>
        </section>
        <section class="subject-page" id="language-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios/" target="_blank" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Lenguaje</h2>
                    <p>Selecciona un área de lenguaje para practicar</p>
                </div>
                <div class="topics-grid">
                    <div class="topic-card grammar">
                        <div class="topic-icon">✍️</div>
                        <div class="topic-content">
                            <h3>Gramática</h3>
                            <p>Verbos, sustantivos, adjetivos y estructuras gramaticales.</p>
                            <a href="#" class="btn btn-grammar practice-btn" data-subject="grammar">Practicar</a>
                        </div>
                    </div>
                    <div class="topic-card spelling">
                        <div class="topic-icon">📝</div>
                        <div class="topic-content">
                            <h3>Ortografía</h3>
                            <p>Acentuación, puntuación y reglas ortográficas.</p>
                            <a href="#" class="btn btn-spelling practice-btn" data-subject="spelling">Practicar</a>
                        </div>
                    </div>
                    <div class="topic-card reading">
                        <div class="topic-icon">📚</div>
                        <div class="topic-content">
                            <h3>Comprensión Lectora</h3>
                            <p>Análisis de textos, inferencias y comprensión.</p>
                            <a href="#" class="btn btn-reading practice-btn" data-subject="reading">Practicar</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="grammar-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="language"><i class="fas fa-arrow-left"></i> Volver a Lenguaje</a>
                <div class="section-title">
                    <h2>Gramática</h2>
                    <p>Practica con más de 50 ejercicios de gramática de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="grammar-basic">Básico</div>
                    <div class="exercise-tab" data-tab="grammar-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="grammar-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="grammar-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Gramática Básica: Partes de la Oración</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-grammar check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-grammar next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="grammar-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Gramática Intermedia: Conjugación Verbal</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <input type="text" class="input-answer" style="display: none;">
                    <button class="btn btn-grammar check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-grammar next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="grammar-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Gramática Avanzada: Análisis Sintáctico</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-grammar check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-grammar next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="spelling-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="language"><i class="fas fa-arrow-left"></i> Volver a Lenguaje</a>
                <div class="section-title">
                    <h2>Ortografía</h2>
                    <p>Practica con más de 50 ejercicios de ortografía de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="spelling-basic">Básico</div>
                    <div class="exercise-tab" data-tab="spelling-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="spelling-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="spelling-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Ortografía Básica: Acentuación</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-spelling check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-spelling next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="spelling-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Ortografía Intermedia: Puntuación</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-spelling check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-spelling next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="spelling-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Ortografía Avanzada: Uso de Letras</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <input type="text" class="input-answer" style="display: none;">
                    <button class="btn btn-spelling check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-spelling next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="reading-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="language"><i class="fas fa-arrow-left"></i> Volver a Lenguaje</a>
                <div class="section-title">
                    <h2>Comprensión Lectora</h2>
                    <p>Practica con más de 50 ejercicios de comprensión lectora de diferentes niveles</p>
                </div>
                <div class="exercise-tabs">
                    <div class="exercise-tab active" data-tab="reading-basic">Básico</div>
                    <div class="exercise-tab" data-tab="reading-intermediate">Intermedio</div>
                    <div class="exercise-tab" data-tab="reading-advanced">Avanzado</div>
                </div>
                <div class="exercise-container active" id="reading-basic-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Comprensión Lectora Básica: Textos Cortos</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-reading check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-reading next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="reading-intermediate-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Comprensión Lectora Intermedia: Textos Narrativos</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-reading check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-reading next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
                <div class="exercise-container" id="reading-advanced-exercises">
                    <div class="exercise-header">
                        <h3 class="exercise-title">Comprensión Lectora Avanzada: Textos Argumentativos</h3>
                        <div class="exercise-progress">
                            <i class="fas fa-star" style="color: gold; margin-right: 5px;"></i>
                            <span>Ejercicio <span class="exercise-counter">1</span> de 50</span>
                        </div>
                    </div>
                    <div class="exercise-question"></div>
                    <div class="options-container"></div>
                    <button class="btn btn-reading check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-reading next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                </div>
            </div>
        </section>
        <section class="subject-page" id="math-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Matemáticas</h2>
                    <p>Visita nuestra página de Matemáticas para practicar</p>
                    <a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank" class="btn btn-language">Ir a Matemáticas</a>
                </div>
            </div>
        </section>
        <section class="subject-page" id="science-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Ciencias</h2>
                    <p>Próximamente: Ejercicios de ciencias</p>
                </div>
            </div>
        </section>
        <section class="subject-page" id="social-page">
            <div class="container">
                <a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Sociales</h2>
                    <p>Próximamente: Ejercicios de sociales</p>
                </div>
            </div>
        </section>
    </main>

    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Iniciar Sesión</h2>
                <button class="close-modal">&times;</button>
            </div>
            <form id="loginForm">
                <div class="form-group">
                    <label for="email">Correo electrónico</label>
                    <input type="email" id="email" required placeholder="tu@email.com">
                </div>
                <div class="form-group">
                    <label for="password">Contraseña</label>
                    <input type="password" id="password" required placeholder="Tu contraseña">
                </div>
                <button type="submit" class="btn btn-language">Iniciar Sesión</button>
                <div class="form-footer">
                    <p>¿No tienes cuenta? <a href="#" id="registerLink">Regístrate aquí</a></p>
                </div>
            </form>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>PracticaEjercicios</h3>
                    <p>Plataforma educativa con miles de ejercicios gratuitos para estudiantes de todos los niveles.</p>
                </div>
                <div class="footer-column">
                    <h3>Enlaces rápidos</h3>
                    <ul>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios/" target="_blank">Inicio</a></li>
                        <li><a href="#" class="nav-link" data-page="language">Lenguaje</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" target="_blank">Matemáticas</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/" target="_blank">Ciencias</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/" target="_blank">Sociales</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Lenguaje</h3>
                    <ul>
                        <li><a href="#" class="practice-btn" data-subject="grammar">Gramática</a></li>
                        <li><a href="#" class="practice-btn" data-subject="spelling">Ortografía</a></li>
                        <li><a href="#" class="practice-btn" data-subject="reading">Comprensión Lectora</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contacto</h3>
                    <ul>
                        <li><i class="fas fa-envelope"></i> info@practicaejercicios.com</li>
                        <li><i class="fas fa-phone"></i> +34 912 345 678</li>
                        <li><i class="fas fa-map-marker-alt"></i> Madrid, España</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 PracticaEjercicios.com - Todos los derechos reservados</p>
            </div>
        </div>
    </footer>

    <script>
        // Datos del usuario (simulados)
        let userData = {
            loggedIn: false,
            name: "Invitado",
            email: "",
            completedExercises: 0,
            correctAnswers: 0,
            totalAnswers: 0
        };

        // Estado del ejercicio actual
        let currentExercise = {
            subject: null,
            level: null,
            index: 0
        };

        // Número de ejercicios por nivel
        const exerciseCount = 50;

        // Función auxiliar para mezclar un arreglo
        const shuffleArray = (array) => {
            const result = [...array];
            for (let i = result.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [result[i], result[j]] = [result[j], result[i]];
            }
            return result;
        };

        // Conjuntos de ejercicios para cada nivel y asignatura
        const sentencePools = {
            grammar: {
                basic: [
                    { sentence: "El sol brilla en el cielo azul.", answer: "azul", incorrect: ["sol", "brilla", "cielo"] },
                    { sentence: "María lee un libro interesante.", answer: "interesante", incorrect: ["libro", "lee", "María"] },
                    { sentence: "Los niños juegan en el parque verde.", answer: "verde", incorrect: ["niños", "juegan", "parque"] },
                    { sentence: "Ana escribe una carta larga.", answer: "larga", incorrect: ["carta", "escribe", "Ana"] },
                    { sentence: "El perro ladra por la noche oscura.", answer: "oscura", incorrect: ["perro", "ladra", "noche"] },
                    { sentence: "La casa vieja está abandonada.", answer: "vieja", incorrect: ["casa", "está", "abandonada"] },
                    { sentence: "El río rápido fluye hacia el mar.", answer: "rápido", incorrect: ["río", "fluye", "mar"] },
                    { sentence: "La flor hermosa atrae a las abejas.", answer: "hermosa", incorrect: ["flor", "atrae", "abejas"] },
                    { sentence: "El coche nuevo es muy rápido.", answer: "nuevo", incorrect: ["coche", "es", "rápido"] },
                    { sentence: "La montaña alta toca el cielo.", answer: "alta", incorrect: ["montaña", "toca", "cielo"] },
                    { sentence: "El pájaro canta en la rama alta.", answer: "alta", incorrect: ["pájaro", "canta", "rama"] },
                    { sentence: "El cielo despejado brilla intensamente.", answer: "despejado", incorrect: ["cielo", "brilla", "intensamente"] },
                    { sentence: "La ciudad grande nunca duerme.", answer: "grande", incorrect: ["ciudad", "nunca", "duerme"] },
                    { sentence: "El árbol frondoso da mucha sombra.", answer: "frondoso", incorrect: ["árbol", "da", "sombra"] },
                    { sentence: "El niño pequeño juega con su pelota.", answer: "pequeño", incorrect: ["niño", "juega", "pelota"] },
                    { sentence: "La playa tranquila invita al descanso.", answer: "tranquila", incorrect: ["playa", "invita", "descanso"] },
                    { sentence: "El libro antiguo está en la biblioteca.", answer: "antiguo", incorrect: ["libro", "está", "biblioteca"] },
                    { sentence: "El camino estrecho lleva al pueblo.", answer: "estrecho", incorrect: ["camino", "lleva", "pueblo"] },
                    { sentence: "La luna llena ilumina la noche.", answer: "llena", incorrect: ["luna", "ilumina", "noche"] },
                    { sentence: "El viento fuerte sopla en las montañas.", answer: "fuerte", incorrect: ["viento", "sopla", "montañas"] },
                    { sentence: "El gato perezoso duerme en el sofá.", answer: "perezoso", incorrect: ["gato", "duerme", "sofá"] },
                    { sentence: "La comida deliciosa atrae a todos.", answer: "deliciosa", incorrect: ["comida", "atrae", "todos"] },
                    { sentence: "El reloj antiguo marca las horas.", answer: "antiguo", incorrect: ["reloj", "marca", "horas"] },
                    { sentence: "La ventana abierta deja entrar el aire.", answer: "abierta", incorrect: ["ventana", "deja", "aire"] },
                    { sentence: "El bosque denso esconde muchos secretos.", answer: "denso", incorrect: ["bosque", "esconde", "secretos"] },
                    { sentence: "El sol ardiente calienta la arena.", answer: "ardiente", incorrect: ["sol", "calienta", "arena"] },
                    { sentence: "La torre alta domina la ciudad.", answer: "alta", incorrect: ["torre", "domina", "ciudad"] },
                    { sentence: "El mercado animado está lleno de gente.", answer: "animado", incorrect: ["mercado", "está", "gente"] },
                    { sentence: "La lámpara brillante ilumina la sala.", answer: "brillante", incorrect: ["lámpara", "ilumina", "sala"] },
                    { sentence: "El puente largo cruza el río.", answer: "largo", incorrect: ["puente", "cruza", "río"] },
                    { sentence: "La calle silenciosa está desierta.", answer: "silenciosa", incorrect: ["calle", "está", "desierta"] },
                    { sentence: "El tren rápido pasa por el pueblo.", answer: "rápido", incorrect: ["tren", "pasa", "pueblo"] },
                    { sentence: "La nube oscura cubre el sol.", answer: "oscura", incorrect: ["nube", "cubre", "sol"] },
                    { sentence: "El cuadro colorido adorna la pared.", answer: "colorido", incorrect: ["cuadro", "adorna", "pared"] },
                    { sentence: "El lago tranquilo refleja las montañas.", answer: "tranquilo", incorrect: ["lago", "refleja", "montañas"] },
                    { sentence: "La puerta pesada se abre lentamente.", answer: "pesada", incorrect: ["puerta", "se abre", "lentamente"] },
                    { sentence: "El cielo estrellado fascina a todos.", answer: "estrellado", incorrect: ["cielo", "fascina", "todos"] },
                    { sentence: "El camino empinado lleva a la cima.", answer: "empinado", incorrect: ["camino", "lleva", "cima"] },
                    { sentence: "La casa moderna tiene grandes ventanas.", answer: "moderna", incorrect: ["casa", "tiene", "ventanas"] },
                    { sentence: "El parque alegre está lleno de niños.", answer: "alegre", incorrect: ["parque", "está", "niños"] },
                    { sentence: "El río cristalino fluye suavemente.", answer: "cristalino", incorrect: ["río", "fluye", "suavemente"] },
                    { sentence: "La montaña nevada brilla al sol.", answer: "nevada", incorrect: ["montaña", "brilla", "sol"] },
                    { sentence: "El campo verde atrae a los visitantes.", answer: "verde", incorrect: ["campo", "atrae", "visitantes"] },
                    { sentence: "La playa soleada es perfecta para descansar.", answer: "soleada", incorrect: ["playa", "es", "descansar"] },
                    { sentence: "El edificio alto se ve desde lejos.", answer: "alto", incorrect: ["edificio", "se ve", "lejos"] },
                    { sentence: "La flor fragante perfuma el jardín.", answer: "fragante", incorrect: ["flor", "perfuma", "jardín"] },
                    { sentence: "El cielo nublado anuncia lluvia.", answer: "nublado", incorrect: ["cielo", "anuncia", "lluvia"] },
                    { sentence: "El bosque oscuro es muy misterioso.", answer: "oscuro", incorrect: ["bosque", "es", "misterioso"] },
                    { sentence: "La ciudad moderna tiene muchos edificios.", answer: "moderna", incorrect: ["ciudad", "tiene", "edificios"] },
                    { sentence: "El río ancho atraviesa el valle.", answer: "ancho", incorrect: ["río", "atraviesa", "valle"] }
                ],
                intermediate: [
                    { question: "Conjuga el verbo 'cantar' en presente de subjuntivo, primera persona singular.", answer: "cante", incorrect: ["canto", "cantas", "canté"] },
                    { question: "Conjuga el verbo 'comer' en pretérito imperfecto de subjuntivo, tercera persona plural.", answer: "comieran", incorrect: ["comían", "comieron", "coman"] },
                    { question: "Conjuga el verbo 'vivir' en futuro, primera persona singular.", answer: "viviré", incorrect: ["vivo", "vivía", "viví"] },
                    { question: "Conjuga el verbo 'jugar' en presente, tercera persona singular.", answer: "juega", incorrect: ["juego", "juegas", "jugó"] },
                    { question: "Conjuga el verbo 'escribir' en pretérito perfecto, primera persona plural.", answer: "hemos escrito", incorrect: ["escribimos", "habíamos escrito", "escríbanos"] },
                    { question: "Conjuga el verbo 'hablar' en pretérito imperfecto, segunda persona singular.", answer: "hablabas", incorrect: ["hablas", "hablaste", "hablaras"] },
                    { question: "Conjuga el verbo 'ser' en condicional, tercera persona singular.", answer: "sería", incorrect: ["es", "fue", "sea"] },
                    { question: "Conjuga el verbo 'tener' en presente de subjuntivo, primera persona plural.", answer: "tengamos", incorrect: ["tenemos", "tuvimos", "teníamos"] },
                    { question: "Conjuga el verbo 'ir' en pretérito perfecto, tercera persona singular.", answer: "ha ido", incorrect: ["fue", "va", "había ido"] },
                    { question: "Conjuga el verbo 'hacer' en futuro, segunda persona singular.", answer: "harás", incorrect: ["haces", "hiciste", "hagas"] },
                    { question: "Conjuga el verbo 'ver' en presente, primera persona singular.", answer: "veo", incorrect: ["ves", "vi", "vea"] },
                    { question: "Conjuga el verbo 'dormir' en presente de subjuntivo, tercera persona singular.", answer: "duerma", incorrect: ["duerme", "durmió", "dormía"] },
                    { question: "Conjuga el verbo 'estudiar' en pretérito imperfecto, primera persona plural.", answer: "estudiábamos", incorrect: ["estudiamos", "estudiaron", "estudiaran"] },
                    { question: "Conjuga el verbo 'caminar' en futuro, tercera persona plural.", answer: "caminarán", incorrect: ["caminan", "caminaron", "caminaban"] },
                    { question: "Conjuga el verbo 'pensar' en presente de subjuntivo, segunda persona singular.", answer: "pienses", incorrect: ["piensas", "pensaste", "pensaras"] },
                    { question: "Conjuga el verbo 'trabajar' en pretérito perfecto, primera persona singular.", answer: "he trabajado", incorrect: ["trabajo", "trabajé", "había trabajado"] },
                    { question: "Conjuga el verbo 'beber' en condicional, tercera persona singular.", answer: "bebería", incorrect: ["bebe", "bebió", "bebiera"] },
                    { question: "Conjuga el verbo 'correr' en presente, tercera persona singular.", answer: "corre", incorrect: ["corro", "corres", "corrió"] },
                    { question: "Conjuga el verbo 'aprender' en pretérito imperfecto de subjuntivo, primera persona singular.", answer: "aprendiera", incorrect: ["aprendía", "aprendí", "aprenda"] },
                    { question: "Conjuga el verbo 'salir' en futuro, primera persona singular.", answer: "saldré", incorrect: ["salgo", "salí", "salía"] },
                    { question: "Conjuga el verbo 'escuchar' en presente de subjuntivo, tercera persona plural.", answer: "escuchen", incorrect: ["escuchan", "escucharon", "escuchaban"] },
                    { question: "Conjuga el verbo 'bailar' en pretérito perfecto, segunda persona singular.", answer: "has bailado", incorrect: ["bailaste", "bailas", "habías bailado"] },
                    { question: "Conjuga el verbo 'llegar' en condicional, primera persona plural.", answer: "llegaríamos", incorrect: ["llegamos", "llegaremos", "llegáramos"] },
                    { question: "Conjuga el verbo 'abrir' en presente, primera persona singular.", answer: "abro", incorrect: ["abres", "abrí", "abra"] },
                    { question: "Conjuga el verbo 'cantar' en pretérito imperfecto, tercera persona plural.", answer: "cantaban", incorrect: ["cantaron", "cantan", "cantaran"] },
                    { question: "Conjuga el verbo 'comer' en futuro, segunda persona plural.", answer: "comeréis", incorrect: ["coméis", "comisteis", "comáis"] },
                    { question: "Conjuga el verbo 'vivir' en presente de subjuntivo, primera persona singular.", answer: "viva", incorrect: ["vivo", "viví", "vivía"] },
                    { question: "Conjuga el verbo 'trabajar' en pretérito perfecto, tercera persona plural.", answer: "han trabajado", incorrect: ["trabajaron", "trabajan", "trabajaban"] },
                    { question: "Conjuga el verbo 'jugar' en condicional, primera persona singular.", answer: "jugaría", incorrect: ["juego", "jugaba", "juegue"] },
                    { question: "Conjuga el verbo 'estudiar' en presente, segunda persona singular.", answer: "estudias", incorrect: ["estudio", "estudiaste", "estudies"] },
                    { question: "Conjuga el verbo 'ser' en pretérito imperfecto de subjuntivo, tercera persona singular.", answer: "fuera", incorrect: ["fue", "es", "sea"] },
                    { question: "Conjuga el verbo 'tener' en futuro, tercera persona singular.", answer: "tendrá", incorrect: ["tiene", "tuvo", "tenga"] },
                    { question: "Conjuga el verbo 'ir' en presente de subjuntivo, segunda persona singular.", answer: "vayas", incorrect: ["vas", "fuiste", "vaya"] },
                    { question: "Conjuga el verbo 'hacer' en pretérito perfecto, primera persona singular.", answer: "he hecho", incorrect: ["hice", "hago", "había hecho"] },
                    { question: "Conjuga el verbo 'ver' en condicional, tercera persona plural.", answer: "verían", incorrect: ["ven", "vieron", "vieran"] },
                    { question: "Conjuga el verbo 'dormir' en pretérito imperfecto, primera persona singular.", answer: "dormía", incorrect: ["duermo", "dormí", "durmiera"] },
                    { question: "Conjuga el verbo 'caminar' en presente de subjuntivo, primera persona plural.", answer: "caminemos", incorrect: ["caminamos", "caminábamos", "camináramos"] },
                    { question: "Conjuga el verbo 'pensar' en futuro, tercera persona singular.", answer: "pensará", incorrect: ["piensa", "pensó", "piense"] },
                    { question: "Conjuga el verbo 'trabajar' en pretérito imperfecto, segunda persona plural.", answer: "trabajabais", incorrect: ["trabajáis", "trabajasteis", "trabajárais"] },
                    { question: "Conjuga el verbo 'beber' en presente, primera persona singular.", answer: "bebo", incorrect: ["bebes", "bebí", "beba"] },
                    { question: "Conjuga el verbo 'correr' en pretérito perfecto, tercera persona singular.", answer: "ha corrido", incorrect: ["corrió", "corre", "había corrido"] },
                    { question: "Conjuga el verbo 'aprender' en condicional, primera persona singular.", answer: "aprendería", incorrect: ["aprendo", "aprendí", "aprenda"] },
                    { question: "Conjuga el verbo 'salir' en presente de subjuntivo, tercera persona singular.", answer: "salga", incorrect: ["sale", "salió", "salía"] },
                    { question: "Conjuga el verbo 'escuchar' en futuro, primera persona plural.", answer: "escucharemos", incorrect: ["escuchamos", "escuchábamos", "escucháramos"] },
                    { question: "Conjuga el verbo 'bailar' en pretérito imperfecto, tercera persona singular.", answer: "bailaba", incorrect: ["bailó", "baila", "bailara"] },
                    { question: "Conjuga el verbo 'llegar' en presente, primera persona singular.", answer: "llego", incorrect: ["llegas", "llegué", "llegue"] },
                    { question: "Conjuga el verbo 'abrir' en pretérito perfecto, tercera persona plural.", answer: "han abierto", incorrect: ["abrieron", "abren", "abrían"] },
                    { question: "Conjuga el verbo 'cantar' en condicional, segunda persona singular.", answer: "cantarías", incorrect: ["cantas", "cantaste", "cantes"] },
                    { question: "Conjuga el verbo 'comer' en presente de subjuntivo, tercera persona plural.", answer: "coman", incorrect: ["comen", "comieron", "comían"] },
                    { question: "Conjuga el verbo 'vivir' en pretérito imperfecto, primera persona singular.", answer: "vivía", incorrect: ["vivo", "viví", "viva"] }
                ],
                advanced: [
                    { sentence: "Aunque llovía intensamente, los excursionistas continuaron su camino hacia la cima.", answer: "Aunque llovía intensamente", incorrect: ["los excursionistas continuaron", "hacia la cima", "intensamente"] },
                    { sentence: "El libro que leí ayer, escrito por un autor desconocido, me fascinó por su estilo.", answer: "que leí ayer", incorrect: ["me fascinó por su estilo", "escrito por un autor", "el libro"] },
                    { sentence: "Cuando llegamos al pueblo, donde todos nos esperaban, comenzó la fiesta.", answer: "donde todos nos esperaban", incorrect: ["comenzó la fiesta", "cuando llegamos al pueblo", "al pueblo"] },
                    { sentence: "Si hubieras estudiado más, habrías aprobado el examen con facilidad.", answer: "Si hubieras estudiado más", incorrect: ["habrías aprobado el examen", "con facilidad", "el examen"] },
                    { sentence: "El proyecto que presentamos ayer fue aceptado por unanimidad.", answer: "que presentamos ayer", incorrect: ["fue aceptado por unanimidad", "el proyecto", "por unanimidad"] },
                    { sentence: "Aunque no lo creas, el equipo que perdió el partido sigue en la competencia.", answer: "Aunque no lo creas", incorrect: ["el equipo que perdió", "sigue en la competencia", "el partido"] },
                    { sentence: "La casa donde crecí está ahora en venta.", answer: "donde crecí", incorrect: ["la casa", "está ahora en venta", "en venta"] },
                    { sentence: "Si el tren llega tarde, perderemos la conexión al aeropuerto.", answer: "Si el tren llega tarde", incorrect: ["perderemos la conexión", "al aeropuerto", "la conexión"] },
                    { sentence: "El científico que descubrió la teoría trabaja en una universidad prestigiosa.", answer: "que descubrió la teoría", incorrect: ["trabaja en una universidad", "el científico", "prestigiosa"] },
                    { sentence: "Aunque el clima estaba frío, los niños jugaron en el parque todo el día.", answer: "Aunque el clima estaba frío", incorrect: ["los niños jugaron", "en el parque", "todo el día"] },
                    { sentence: "El cuadro que pintó el artista fue subastado por millones.", answer: "que pintó el artista", incorrect: ["fue subastado por millones", "el cuadro", "por millones"] },
                    { sentence: "Si no terminas el trabajo hoy, no podrás descansar mañana.", answer: "Si no terminas el trabajo hoy", incorrect: ["no podrás descansar mañana", "el trabajo", "mañana"] },
                    { sentence: "La ciudad donde ocurrió el evento es famosa por su cultura.", answer: "donde ocurrió el evento", incorrect: ["es famosa por su cultura", "la ciudad", "por su cultura"] },
                    { sentence: "Aunque estaba cansado, terminó el libro en una noche.", answer: "Aunque estaba cansado", incorrect: ["terminó el libro", "en una noche", "el libro"] },
                    { sentence: "El estudiante que ganó el concurso recibió una beca completa.", answer: "que ganó el concurso", incorrect: ["recibió una beca completa", "el estudiante", "una beca"] },
                    { sentence: "Si llueve esta tarde, cancelaremos el picnic.", answer: "Si llueve esta tarde", incorrect: ["cancelaremos el picnic", "esta tarde", "el picnic"] },
                    { sentence: "La novela que leímos en clase es un clásico de la literatura.", answer: "que leímos en clase", incorrect: ["es un clásico de la literatura", "la novela", "en clase"] },
                    { sentence: "Aunque el camino era difícil, lograron llegar a la cima.", answer: "Aunque el camino era difícil", incorrect: ["lograron llegar a la cima", "el camino", "a la cima"] },
                    { sentence: "El equipo que diseñó el puente ganó un premio internacional.", answer: "que diseñó el puente", incorrect: ["ganó un premio internacional", "el equipo", "un premio"] },
                    { sentence: "Si no practicas, no mejorarás tu nivel de inglés.", answer: "Si no practicas", incorrect: ["no mejorarás tu nivel", "de inglés", "tu nivel"] },
                    { sentence: "La playa donde pasamos las vacaciones es muy tranquila.", answer: "donde pasamos las vacaciones", incorrect: ["es muy tranquila", "la playa", "las vacaciones"] },
                    { sentence: "Aunque el examen fue difícil, todos aprobaron.", answer: "Aunque el examen fue difícil", incorrect: ["todos aprobaron", "el examen", "difícil"] },
                    { sentence: "El escritor que publicó la novela vive en Madrid.", answer: "que publicó la novela", incorrect: ["vive en Madrid", "el escritor", "la novela"] },
                    { sentence: "Si terminas temprano, podremos ir al cine.", answer: "Si terminas temprano", incorrect: ["podremos ir al cine", "temprano", "al cine"] },
                    { sentence: "La montaña donde escalamos es muy famosa.", answer: "donde escalamos", incorrect: ["es muy famosa", "la montaña", "famosa"] },
                    { sentence: "Aunque no tenía experiencia, obtuvo el trabajo.", answer: "Aunque no tenía experiencia", incorrect: ["obtuvo el trabajo", "el trabajo", "experiencia"] },
                    { sentence: "El poema que recitó el niño emocionó a todos.", answer: "que recitó el niño", incorrect: ["emocionó a todos", "el poema", "a todos"] },
                    { sentence: "Si estudias con dedicación, aprobarás el curso.", answer: "Si estudias con dedicación", incorrect: ["aprobarás el curso", "con dedicación", "el curso"] },
                    { sentence: "La ciudad que visitamos ayer tiene un castillo antiguo.", answer: "que visitamos ayer", incorrect: ["tiene un castillo antiguo", "la ciudad", "un castillo"] },
                    { sentence: "Aunque el proyecto era ambicioso, lo terminaron a tiempo.", answer: "Aunque el proyecto era ambicioso", incorrect: ["lo terminaron a tiempo", "el proyecto", "a tiempo"] },
                    { sentence: "El libro que recomendó el profesor es muy interesante.", answer: "que recomendó el profesor", incorrect: ["es muy interesante", "el libro", "el profesor"] },
                    { sentence: "Si no llegas pronto, perderás el autobús.", answer: "Si no llegas pronto", incorrect: ["perderás el autobús", "pronto", "el autobús"] },
                    { sentence: "La casa donde vivimos tiene un jardín grande.", answer: "donde vivimos", incorrect: ["tiene un jardín grande", "la casa", "un jardín"] },
                    { sentence: "Aunque el día estaba nublado, salimos a caminar.", answer: "Aunque el día estaba nublado", incorrect: ["salimos a caminar", "el día", "a caminar"] },
                    { sentence: "El artista que pintó el mural es muy conocido.", answer: "que pintó el mural", incorrect: ["es muy conocido", "el artista", "el mural"] },
                    { sentence: "Si practicas diario, mejorarás rápidamente.", answer: "Si practicas diario", incorrect: ["mejorarás rápidamente", "diario", "rápidamente"] },
                    { sentence: "La escuela donde estudiamos organiza eventos culturales.", answer: "donde estudiamos", incorrect: ["organiza eventos culturales", "la escuela", "eventos culturales"] },
                    { sentence: "Aunque el libro era largo, lo leí en dos días.", answer: "Aunque el libro era largo", incorrect: ["lo leí en dos días", "el libro", "en dos días"] },
                    { sentence: "El equipo que ganó el torneo celebró toda la noche.", answer: "que ganó el torneo", incorrect: ["celebró toda la noche", "el equipo", "toda la noche"] },
                    { sentence: "Si no estudias, no aprobarás el examen.", answer: "Si no estudias", incorrect: ["no aprobarás el examen", "el examen", "aprobarás"] },
                    { sentence: "La película que vimos anoche fue muy emocionante.", answer: "que vimos anoche", incorrect: ["fue muy emocionante", "la película", "anoche"] },
                    { sentence: "Aunque el camino estaba oscuro, seguimos adelante.", answer: "Aunque el camino estaba oscuro", incorrect: ["seguimos adelante", "el camino", "adelante"] },
                    { sentence: "El profesor que nos enseñó matemáticas es muy paciente.", answer: "que nos enseñó matemáticas", incorrect: ["es muy paciente", "el profesor", "matemáticas"] },
                    { sentence: "Si llegas tarde, no entrarás a la clase.", answer: "Si llegas tarde", incorrect: ["no entrarás a la clase", "tarde", "la clase"] },
                    { sentence: "La ciudad donde nací tiene un río hermoso.", answer: "donde nací", incorrect: ["tiene un río hermoso", "la ciudad", "un río"] },
                    { sentence: "Aunque el concierto fue largo, todos disfrutaron.", answer: "Aunque el concierto fue largo", incorrect: ["todos disfrutaron", "el concierto", "largo"] },
                    { sentence: "El libro que escribí será publicado pronto.", answer: "que escribí", incorrect: ["será publicado pronto", "el libro", "pronto"] },
                    { sentence: "Si no practicas, no ganarás la competencia.", answer: "Si no practicas", incorrect: ["no ganarás la competencia", "la competencia", "ganarás"] },
                    { sentence: "La casa donde creció mi madre está renovada.", answer: "donde creció mi madre", incorrect: ["está renovada", "la casa", "mi madre"] },
                    { sentence: "Aunque el día era soleado, preferimos quedarnos en casa.", answer: "Aunque el día era soleado", incorrect: ["preferimos quedarnos en casa", "el día", "en casa"] },
                    { sentence: "El estudiante que presentó el proyecto obtuvo la mejor nota.", answer: "que presentó el proyecto", incorrect: ["obtuvo la mejor nota", "el estudiante", "la mejor nota"] }
                ]
            },
            spelling: {
                basic: [
                    { sentence: "El (arbol/árbol) es alto y verde.", answer: "árbol", incorrect: ["arbol", "árboll", "arból"] },
                    { sentence: "La (musica/música) suena fuerte.", answer: "música", incorrect: ["musica", "mùsica", "músicá"] },
                    { sentence: "El (sol/sól) brilla en el cielo.", answer: "sol", incorrect: ["sól", "sòl", "soĺ"] },
                    { sentence: "Ella (esta/está) muy cansada.", answer: "está", incorrect: ["esta", "està", "ésta"] },
                    { sentence: "El (te/té) está caliente.", answer: "té", incorrect: ["te", "tè", "téé"] },
                    { sentence: "Voy al (cine/ciné) esta noche.", answer: "cine", incorrect: ["ciné", "cìne", "cinè"] },
                    { sentence: "La (luna/lúna) ilumina la noche.", answer: "luna", incorrect: ["lúna", "lùna", "luná"] },
                    { sentence: "El (rio/río) fluye rápido.", answer: "río", incorrect: ["rio", "rìo", "riò"] },
                    { sentence: "Ella (baila/bailá) muy bien.", answer: "baila", incorrect: ["bailá", "bàila", "bailà"] },
                    { sentence: "El (aroma/aróma) es agradable.", answer: "aroma", incorrect: ["aróma", "àroma", "aròma"] },
                    { sentence: "La (casa/cása) es grande.", answer: "casa", incorrect: ["cása", "càsa", "casá"] },
                    { sentence: "El (jardin/jardín) está florido.", answer: "jardín", incorrect: ["jardin", "jàrdin", "jardìn"] },
                    { sentence: "El (avion/avión) vuela alto.", answer: "avión", incorrect: ["avion", "àvion", "aviòn"] },
                    { sentence: "La (nube/núbe) es blanca.", answer: "nube", incorrect: ["núbe", "nùbe", "nubé"] },
                    { sentence: "El (arroz/arróz) está listo.", answer: "arroz", incorrect: ["arróz", "àrroz", "aròz"] },
                    { sentence: "Ella (canta/cantá) una canción.", answer: "canta", incorrect: ["cantá", "cànta", "cantà"] },
                    { sentence: "El (camino/caminó) es largo.", answer: "camino", incorrect: ["caminó", "càmino", "camìno"] },
                    { sentence: "La (flor/flór) es hermosa.", answer: "flor", incorrect: ["flór", "flòr", "flór"] },
                    { sentence: "El (pais/país) es muy bonito.", answer: "país", incorrect: ["pais", "pàis", "paìs"] },
                    { sentence: "Ella (corre/corré) muy rápido.", answer: "corre", incorrect: ["corré", "còrre", "corrè"] },
                    { sentence: "El (cielo/ciélo) está despejado.", answer: "cielo", incorrect: ["ciélo", "cìelo", "cieló"] },
                    { sentence: "La (mesa/mésa) es de madera.", answer: "mesa", incorrect: ["mésa", "mèsa", "mesá"] },
                    { sentence: "El (sol/sól) calienta mucho.", answer: "sol", incorrect: ["sól", "sòl", "soĺ"] },
                    { sentence: "Ella (lee/lée) un libro.", answer: "lee", incorrect: ["lée", "lèe", "leé"] },
                    { sentence: "El (arbol/árbol) tiene flores.", answer: "árbol", incorrect: ["arbol", "árboll", "arból"] },
                    { sentence: "La (luna/lúna) brilla mucho.", answer: "luna", incorrect: ["lúna", "lùna", "luná"] },
                    { sentence: "El (rio/río) es profundo.", answer: "río", incorrect: ["rio", "rìo", "riò"] },
                    { sentence: "Ella (baila/bailá) con gracia.", answer: "baila", incorrect: ["bailá", "bàila", "bailà"] },
                    { sentence: "El (avion/avión) despega ahora.", answer: "avión", incorrect: ["avion", "àvion", "aviòn"] },
                    { sentence: "La (nube/núbe) cubre el sol.", answer: "nube", incorrect: ["núbe", "nùbe", "nubé"] },
                    { sentence: "El (arroz/arróz) es sabroso.", answer: "arroz", incorrect: ["arróz", "àrroz", "aròz"] },
                    { sentence: "Ella (canta/cantá) en el coro.", answer: "canta", incorrect: ["cantá", "cànta", "cantà"] },
                    { sentence: "El (camino/caminó) está mojado.", answer: "camino", incorrect: ["caminó", "càmino", "camìno"] },
                    { sentence: "La (flor/flór) es roja.", answer: "flor", incorrect: ["flór", "flòr", "flór"] },
                    { sentence: "El (pais/país) tiene montañas.", answer: "país", incorrect: ["pais", "pàis", "paìs"] },
                    { sentence: "Ella (corre/corré) en el parque.", answer: "corre", incorrect: ["corré", "còrre", "corrè"] },
                    { sentence: "El (cielo/ciélo) es azul.", answer: "cielo", incorrect: ["ciélo", "cìelo", "cieló"] },
                    { sentence: "La (mesa/mésa) está limpia.", answer: "mesa", incorrect: ["mésa", "mèsa", "mesá"] },
                    { sentence: "El (sol/sól) sale temprano.", answer: "sol", incorrect: ["sól", "sòl", "soĺ"] },
                    { sentence: "Ella (lee/lée) una novela.", answer: "lee", incorrect: ["lée", "lèe", "leé"] },
                    { sentence: "El (arbol/árbol) da frutas.", answer: "árbol", incorrect: ["arbol", "árboll", "arból"] },
                    { sentence: "La (luna/lúna) está llena.", answer: "luna", incorrect: ["lúna", "lùna", "luná"] },
                    { sentence: "El (rio/río) lleva agua.", answer: "río", incorrect: ["rio", "rìo", "riò"] },
                    { sentence: "Ella (baila/bailá) en la fiesta.", answer: "baila", incorrect: ["bailá", "bàila", "bailà"] },
                    { sentence: "El (avion/avión) llega tarde.", answer: "avión", incorrect: ["avion", "àvion", "aviòn"] },
                    { sentence: "La (nube/núbe) es gris.", answer: "nube", incorrect: ["núbe", "nùbe", "nubé"] },
                    { sentence: "El (arroz/arróz) está cocido.", answer: "arroz", incorrect: ["arróz", "àrroz", "aròz"] },
                    { sentence: "Ella (canta/cantá) con alegría.", answer: "canta", incorrect: ["cantá", "cànta", "cantà"] },
                    { sentence: "El (camino/caminó) es recto.", answer: "camino", incorrect: ["caminó", "càmino", "camìno"] },
                    { sentence: "La (flor/flór) tiene pétalos.", answer: "flor", incorrect: ["flór", "flòr", "flór"] }
                ],
                intermediate: [
                    { sentence: "Juan dijo que vendría pero no llegó.", answer: "Juan dijo que vendría, pero no llegó.", incorrect: ["Juan dijo que vendría pero no llegó.", "Juan dijo que vendría pero, no llegó.", "Juan dijo que vendría; pero no llegó."] },
                    { sentence: "María estudia mucho sin embargo no aprueba.", answer: "María estudia mucho, sin embargo, no aprueba.", incorrect: ["María estudia mucho sin embargo no aprueba.", "María estudia mucho; sin embargo no aprueba.", "María estudia mucho sin embargo, no aprueba."] },
                    { sentence: "Voy al mercado luego vuelvo a casa.", answer: "Voy al mercado, luego vuelvo a casa.", incorrect: ["Voy al mercado luego vuelvo a casa.", "Voy al mercado; luego vuelvo a casa.", "Voy al mercado luego, vuelvo a casa."] },
                    { sentence: "Estudiaré toda la noche porque mañana tengo examen.", answer: "Estudiaré toda la noche, porque mañana tengo examen.", incorrect: ["Estudiaré toda la noche porque mañana tengo examen.", "Estudiaré toda la noche; porque tengo examen.", "Estudiaré toda la noche porque, mañana tengo examen."] },
                    { sentence: "Llegué tarde por eso perdí el tren.", answer: "Llegué tarde, por eso perdí el tren.", incorrect: ["Llegué tarde por eso perdí el tren.", "Llegué tarde; por eso perdí el tren.", "Llegué tarde por eso, perdí el tren."] },
                    { sentence: "Ana quiere salir además necesita descansar.", answer: "Ana quiere salir, además, necesita descansar.", incorrect: ["Ana quiere salir además necesita descansar.", "Ana quiere salir; además necesita descansar.", "Ana quiere salir además, necesita descansar."] },
                    { sentence: "El libro es interesante por lo tanto lo terminé rápido.", answer: "El libro es interesante, por lo tanto, lo terminé rápido.", incorrect: ["El libro es interesante por lo tanto lo terminé rápido.", "El libro es interesante; por lo tanto lo terminé rápido.", "El libro es interesante por lo tanto, lo terminé rápido."] },
                    { sentence: "No estudié así que reprobé el examen.", answer: "No estudié, así que reprobé el examen.", incorrect: ["No estudié así que reprobé el examen.", "No estudié; así que reprobé el examen.", "No estudié así que, reprobé el examen."] },
                    { sentence: "Voy a la playa aunque está lloviendo.", answer: "Voy a la playa, aunque está lloviendo.", incorrect: ["Voy a la playa aunque está lloviendo.", "Voy a la playa; aunque está lloviendo.", "Voy a la playa aunque, está lloviendo."] },
                    { sentence: "El equipo ganó por consiguiente celebraron.", answer: "El equipo ganó, por consiguiente, celebraron.", incorrect: ["El equipo ganó por consiguiente celebraron.", "El equipo ganó; por consiguiente celebraron.", "El equipo ganó por consiguiente, celebraron."] },
                    { sentence: "Ella canta muy bien además toca el piano.", answer: "Ella canta muy bien, además, toca el piano.", incorrect: ["Ella canta muy bien además toca el piano.", "Ella canta muy bien; además toca el piano.", "Ella canta muy bien además, toca el piano."] },
                    { sentence: "No tengo dinero por lo tanto no iré de viaje.", answer: "No tengo dinero, por lo tanto, no iré de viaje.", incorrect: ["No tengo dinero por lo tanto no iré de viaje.", "No tengo dinero; por lo tanto no iré de viaje.", "No tengo dinero por lo tanto, no iré de viaje."] },
                    { sentence: "Estudiaré hoy porque mañana es el examen.", answer: "Estudiaré hoy, porque mañana es el examen.", incorrect: ["Estudiaré hoy porque mañana es el examen.", "Estudiaré hoy; porque mañana es el examen.", "Estudiaré hoy porque, mañana es el examen."] },
                    { sentence: "El día está soleado sin embargo hace frío.", answer: "El día está soleado, sin embargo, hace frío.", incorrect: ["El día está soleado sin embargo hace frío.", "El día está soleado; sin embargo hace frío.", "El día está soleado sin embargo, hace frío."] },
                    { sentence: "Quiero ir al cine pero tengo tarea.", answer: "Quiero ir al cine, pero tengo tarea.", incorrect: ["Quiero ir al cine pero tengo tarea.", "Quiero ir al cine; pero tengo tarea.", "Quiero ir al cine pero, tengo tarea."] },
                    { sentence: "Ella corre rápido por eso ganó la carrera.", answer: "Ella corre rápido, por eso ganó la carrera.", incorrect: ["Ella corre rápido por eso ganó la carrera.", "Ella corre rápido; por eso ganó la carrera.", "Ella corre rápido por eso, ganó la carrera."] },
                    { sentence: "No salí ayer porque estaba enfermo.", answer: "No salí ayer, porque estaba enfermo.", incorrect: ["No salí ayer porque estaba enfermo.", "No salí ayer; porque estaba enfermo.", "No salí ayer porque, estaba enfermo."] },
                    { sentence: "El libro es largo sin embargo es interesante.", answer: "El libro es largo, sin embargo, es interesante.", incorrect: ["El libro es largo sin embargo es interesante.", "El libro es largo; sin embargo es interesante.", "El libro es largo sin embargo, es interesante."] },
                    { sentence: "Voy al parque aunque está nublado.", answer: "Voy al parque, aunque está nublado.", incorrect: ["Voy al parque aunque está nublado.", "Voy al parque; aunque está nublado.", "Voy al parque aunque, está nublado."] },
                    { sentence: "Ella estudió mucho por lo tanto aprobó.", answer: "Ella estudió mucho, por lo tanto, aprobó.", incorrect: ["Ella estudió mucho por lo tanto aprobó.", "Ella estudió mucho; por lo tanto aprobó.", "Ella estudiÓ mucho por lo tanto, aprobó."] },
                    { sentence: "No tengo tiempo así que no iré.", answer: "No tengo tiempo, así que no iré.", incorrect: ["No tengo tiempo así que no iré.", "No tengo tiempo; así que no iré.", "No tengo tiempo así que, no iré."] },
                    { sentence: "El equipo jugó bien por consiguiente ganó.", answer: "El equipo jugó bien, por consiguiente, ganó.", incorrect: ["El equipo jugó bien por consiguiente ganó.", "El equipo jugó bien; por consiguiente ganó.", "El equipo jugó bien por consiguiente, ganó."] },
                    { sentence: "Ella lee mucho además escribe cuentos.", answer: "Ella lee mucho, además, escribe cuentos.", incorrect: ["Ella lee mucho además escribe cuentos.", "Ella lee mucho; además escribe cuentos.", "Ella lee mucho además, escribe cuentos."] },
                    { sentence: "No salimos ayer porque llovió.", answer: "No salimos ayer, porque llovió.", incorrect: ["No salimos ayer porque llovió.", "No salimos ayer; porque llovió.", "No salimos ayer porque, llovió."] },
                    { sentence: "El día es caluroso sin embargo prefiero quedarme.", answer: "El día es caluroso, sin embargo, prefiero quedarme.", incorrect: ["El día es caluroso sin embargo prefiero quedarme.", "El día es caluroso; sin embargo prefiero quedarme.", "El día es caluroso sin embargo, prefiero quedarme."] },
                    { sentence: "Quiero viajar pero no tengo dinero.", answer: "Quiero viajar, pero no tengo dinero.", incorrect: ["Quiero viajar pero no tengo dinero.", "Quiero viajar; pero no tengo dinero.", "Quiero viajar pero, no tengo dinero."] },
                    { sentence: "Ella canta bien por eso la aplaudieron.", answer: "Ella canta bien, por eso la aplaudieron.", incorrect: ["Ella canta bien por eso la aplaudieron.", "Ella canta bien; por eso la aplaudieron.", "Ella canta bien por eso, la aplaudieron."] },
                    { sentence: "No estudié mucho por lo tanto reprobé.", answer: "No estudié mucho, por lo tanto, reprobé.", incorrect: ["No estudié mucho por lo tanto reprobé.", "No estudié mucho; por lo tanto reprobé.", "No estudié mucho por lo tanto, reprobé."] },
                    { sentence: "Voy al cine aunque es tarde.", answer: "Voy al cine, aunque es tarde.", incorrect: ["Voy al cine aunque es tarde.", "Voy al cine; aunque es tarde.", "Voy al cine aunque, es tarde."] },
                    { sentence: "El equipo entrenó mucho por consiguiente venció.", answer: "El equipo entrenó mucho, por consiguiente, venció.", incorrect: ["El equipo entrenó mucho por consiguiente venció.", "El equipo entrenó mucho; por consiguiente venció.", "El equipo entrenó mucho por consiguiente, venció."] },
                    { sentence: "Ella pinta bien además esculpe.", answer: "Ella pinta bien, además, esculpe.", incorrect: ["Ella pinta bien además esculpe.", "Ella pinta bien; además esculpe.", "Ella pinta bien además, esculpe."] },
                    { sentence: "No fui al parque porque llovió.", answer: "No fui al parque, porque llovió.", incorrect: ["No fui al parque porque llovió.", "No fui al parque; porque llovió.", "No fui al parque porque, llovió."] },
                    { sentence: "El libro es corto sin embargo es profundo.", answer: "El libro es corto, sin embargo, es profundo.", incorrect: ["El libro es corto sin embargo es profundo.", "El libro es corto; sin embargo es profundo.", "El libro es corto sin embargo, es profundo."] },
                    { sentence: "Quiero leer pero estoy cansado.", answer: "Quiero leer, pero estoy cansado.", incorrect: ["Quiero leer pero estoy cansado.", "Quiero leer; pero estoy cansado.", "Quiero leer pero, estoy cansado."] },
                    { sentence: "Ella baila bien por eso ganó.", answer: "Ella baila bien, por eso ganó.", incorrect: ["Ella baila bien por eso ganó.", "Ella baila bien; por eso ganó.", "Ella baila bien por eso, ganó."] },
                    { sentence: "No salí hoy porque estoy enfermo.", answer: "No salí hoy, porque estoy enfermo.", incorrect: ["No salí hoy porque estoy enfermo.", "No salí hoy; porque estoy enfermo.", "No salí hoy porque, estoy enfermo."] },
                    { sentence: "El día está nublado sin embargo salimos.", answer: "El día está nublado, sin embargo, salimos.", incorrect: ["El día está nublado sin embargo salimos.", "El día está nublado; sin embargo salimos.", "El día está nublado sin embargo, salimos."] },
                    { sentence: "Voy a estudiar aunque estoy cansado.", answer: "Voy a estudiar, aunque estoy cansado.", incorrect: ["Voy a estudiar aunque estoy cansado.", "Voy a estudiar; aunque estoy cansado.", "Voy a estudiar aunque, estoy cansado."] },
                    { sentence: "El equipo jugó mal por lo tanto perdió.", answer: "El equipo jugó mal, por lo tanto, perdió.", incorrect: ["El equipo jugó mal por lo tanto perdió.", "El equipo jugó mal; por lo tanto perdió.", "El equipo jugó mal por lo tanto, perdió."] },
                    { sentence: "Ella lee mucho además estudia.", answer: "Ella lee mucho, además, estudia.", incorrect: ["Ella lee mucho además estudia.", "Ella lee mucho; además estudia.", "Ella lee mucho además, estudia."] },
                    { sentence: "No fui al cine porque trabajé.", answer: "No fui al cine, porque trabajé.", incorrect: ["No fui al cine porque trabajé.", "No fui al cine; porque trabajé.", "No fui al cine porque, trabajé."] },
                    { sentence: "El libro es difícil sin embargo lo leí.", answer: "El libro es difícil, sin embargo, lo leí.", incorrect: ["El libro es difícil sin embargo lo leí.", "El libro es difícil; sin embargo lo leí.", "El libro es difícil sin embargo, lo leí."] },
                    { sentence: "Quiero viajar aunque no tengo tiempo.", answer: "Quiero viajar, aunque no tengo tiempo.", incorrect: ["Quiero viajar aunque no tengo tiempo.", "Quiero viajar; aunque no tengo tiempo.", "Quiero viajar aunque, no tengo tiempo."] },
                    { sentence: "Ella canta bien por consiguiente la contrataron.", answer: "Ella canta bien, por consiguiente, la contrataron.", incorrect: ["Ella canta bien por consiguiente la contrataron.", "Ella canta bien; por consiguiente la contrataron.", "Ella canta bien por consiguiente, la contrataron."] },
                    { sentence: "No estudié por eso reprobé.", answer: "No estudié, por eso reprobé.", incorrect: ["No estudié por eso reprobé.", "No estudié; por eso reprobé.", "No estudié por eso, reprobé."] },
                    { sentence: "Voy al parque porque es soleado.", answer: "Voy al parque, porque es soleado.", incorrect: ["Voy al parque porque es soleado.", "Voy al parque; porque es soleado.", "Voy al parque porque, es soleado."] },
                    { sentence: "El libro es interesante por lo tanto lo recomiendo.", answer: "El libro es interesante, por lo tanto, lo recomiendo.", incorrect: ["El libro es interesante por lo tanto lo recomiendo.", "El libro es interesante; por lo tanto lo recomiendo.", "El libro es interesante por lo tanto, lo recomiendo."] },
                    { sentence: "No salí porque hacía frío.", answer: "No salí, porque hacía frío.", incorrect: ["No salí porque hacía frío.", "No salí; porque hacía frío.", "No salí porque, hacía frío."] },
                    { sentence: "Ella estudia mucho sin embargo no aprueba.", answer: "Ella estudia mucho, sin embargo, no aprueba.", incorrect: ["Ella estudia mucho sin embargo no aprueba.", "Ella estudia mucho; sin embargo no aprueba.", "Ella estudia mucho sin embargo, no aprueba."] },
                    { sentence: "Voy al cine aunque llueve.", answer: "Voy al cine, aunque llueve.", incorrect: ["Voy al cine aunque llueve.", "Voy al cine; aunque llueve.", "Voy al cine aunque, llueve."] }
                ],
                advanced: [
                    { sentence: "No sé si (vaya/baya/valla) al concierto esta noche.", answer: "vaya", incorrect: ["baya", "valla", "bayas"] },
                    { sentence: "El (echo/hecho) es que llegamos tarde.", answer: "hecho", incorrect: ["echo", "eho", "heco"] },
                    { sentence: "Voy a (ver/ber) la película mañana.", answer: "ver", incorrect: ["ber", "verr", "beer"] },
                    { sentence: "La (casa/caza) está en el bosque.", answer: "casa", incorrect: ["caza", "cassa", "casza"] },
                    { sentence: "No sé (como/cómo) lo hicieron.", answer: "cómo", incorrect: ["como", "còmo", "comó"] },
                    { sentence: "El (tubo/tuvo) está roto.", answer: "tubo", incorrect: ["tuvo", "tùbo", "tubò"] },
                    { sentence: "Ella (sabia/sabía) la respuesta.", answer: "sabía", incorrect: ["sabia", "sàbia", "sabìa"] },
                    { sentence: "Voy a (hacer/aser) mi tarea.", answer: "hacer", incorrect: ["aser", "hasser", "hazer"] },
                    { sentence: "El (cayo/calló) al suelo.", answer: "calló", incorrect: ["cayo", "cayó", "callo"] },
                    { sentence: "No (se/sé) la respuesta correcta.", answer: "sé", incorrect: ["se", "sè", "sée"] },
                    { sentence: "La (vaca/baca) está en el tejado.", answer: "baca", incorrect: ["vaca", "vàca", "bàca"] },
                    { sentence: "El (haya/aya) creció rápido.", answer: "haya", incorrect: ["aya", "hàya", "hayà"] },
                    { sentence: "Ella (bino/vino) a la fiesta.", answer: "vino", incorrect: ["bino", "vìno", "vinò"] },
                    { sentence: "No (de/dee) dinero a nadie.", answer: "dé", incorrect: ["de", "dè", "dee"] },
                    { sentence: "El (te/té) está en la mesa.", answer: "té", incorrect: ["te", "tè", "tée"] },
                    { sentence: "Voy a (echar/échar) la carta.", answer: "echar", incorrect: ["échar", "èchar", "echár"] },
                    { sentence: "Ella (sabe/sábe) cocinar bien.", answer: "sabe", incorrect: ["sábe", "sàbe", "sabé"] },
                    { sentence: "El (cabo/cavo) está roto.", answer: "cabo", incorrect: ["cavo", "càbo", "cabò"] },
                    { sentence: "No (se/sé) nadar muy bien.", answer: "sé", incorrect: ["se", "sè", "sée"] },
                    { sentence: "La (baca/vaca) está en el garaje.", answer: "baca", incorrect: ["vaca", "vàca", "bàca"] },
                    { sentence: "El (haya/aya) está en el bosque.", answer: "haya", incorrect: ["aya", "hàya", "hayà"] },
                    { sentence: "Ella (bino/vino) ayer.", answer: "vino", incorrect: ["bino", "vìno", "vinò"] },
                    { sentence: "No (de/dee) nada gratis.", answer: "dé", incorrect: ["de", "dè", "dee"] },
                    { sentence: "El (te/té) está frío.", answer: "té", incorrect: ["te", "tè", "tée"] },
                    { sentence: "Voy a (echar/échar) agua.", answer: "echar", incorrect: ["échar", "èchar", "echár"] },
                    { sentence: "Ella (sabe/sábe) cantar.", answer: "sabe", incorrect: ["sábe", "sàbe", "sabé"] },
                    { sentence: "El (cabo/cavo) es largo.", answer: "cabo", incorrect: ["cavo", "càbo", "cabò"] },
                    { sentence: "No (se/sé) la hora.", answer: "sé", incorrect: ["se", "sè", "sée"] },
                    { sentence: "La (baca/vaca) está en el coche.", answer: "baca", incorrect: ["vaca", "vàca", "bàca"] },
                    { sentence: "El (haya/aya) da sombra.", answer: "haya", incorrect: ["aya", "hàya", "hayà"] },
                    { sentence: "Ella (bino/vino) temprano.", answer: "vino", incorrect: ["bino", "vìno", "vinò"] },
                    { sentence: "No (de/dee) consejos.", answer: "dé", incorrect: ["de", "dè", "dee"] },
                    { sentence: "El (te/té) es verde.", answer: "té", incorrect: ["te", "tè", "tée"] },
                    { sentence: "Voy a (echar/échar) sal.", answer: "echar", incorrect: ["échar", "èchar", "echár"] },
                    { sentence: "Ella (sabe/sábe) bailar.", answer: "sabe", incorrect: ["sábe", "sàbe", "sabé"] },
                    { sentence: "El (cabo/cavo) está atado.", answer: "cabo", incorrect: ["cavo", "càbo", "cabò"] },
                    { sentence: "No (se/sé) el camino.", answer: "sé", incorrect: ["se", "sè", "sée"] },
                    { sentence: "La (baca/vaca) está en el tejado.", answer: "baca", incorrect: ["vaca", "vàca", "bàca"] },
                    { sentence: "El (haya/aya) está seco.", answer: "haya", incorrect: ["aya", "hàya", "hayà"] },
                    { sentence: "Ella (bino/vino) sola.", answer: "vino", incorrect: ["bino", "vìno", "vinò"] },
                    { sentence: "No (de/dee) comida a extraños.", answer: "dé", incorrect: ["de", "dè", "dee"] },
                    { sentence: "El (te/té) está dulce.", answer: "té", incorrect: ["te", "tè", "tée"] },
                    { sentence: "Voy a (echar/échar) leña.", answer: "echar", incorrect: ["échar", "èchar", "echár"] },
                    { sentence: "Ella (sabe/sábe) nadar.", answer: "sabe", incorrect: ["sábe", "sàbe", "sabé"] },
                    { sentence: "El (cabo/cavo) es corto.", answer: "cabo", incorrect: ["cavo", "càbo", "cabò"] },
                    { sentence: "No (se/sé) la respuesta.", answer: "sé", incorrect: ["se", "sè", "sée"] },
                    { sentence: "La (baca/vaca) está rota.", answer: "baca", incorrect: ["vaca", "vàca", "bàca"] },
                    { sentence: "El (haya/aya) está verde.", answer: "haya", incorrect: ["aya", "hàya", "hayà"] },
                    { sentence: "Ella (bino/vino) con amigos.", answer: "vino", incorrect: ["bino", "vìno", "vinò"] },
                    { sentence: "No (de/dee) órdenes.", answer: "dé", incorrect: ["de", "dè", "dee"] }
                ]
            },
            reading: {
                basic: [
                    { text: "El gato negro juega en el jardín con una pelota roja.", question: "¿Qué hace el gato?", answer: "juega con una pelota roja", incorrect: ["en el jardín", "negro", "es un gato"] },
                    { text: "María pinta un cuadro con colores vivos.", question: "¿Qué pinta María?", answer: "un cuadro", incorrect: ["colores vivos", "María", "en el cuadro"] },
                    { text: "El perro corre tras una mariposa amarilla.", question: "¿Qué persigue el perro?", answer: "una mariposa amarilla", incorrect: ["corre", "el perro", "en el campo"] },
                    { text: "Ana lee un libro en la biblioteca silenciosa.", question: "¿Dónde lee Ana?", answer: "en la biblioteca silenciosa", incorrect: ["un libro", "Ana", "lee"] },
                    { text: "El sol brilla sobre el campo verde.", question: "¿Qué hace el sol?", answer: "brilla", incorrect: ["sobre el campo", "verde", "el sol"] },
                    { text: "Los niños cantan en el patio alegre.", question: "¿Qué hacen los niños?", answer: "cantan", incorrect: ["en el patio", "alegre", "los niños"] },
                    { text: "La luna ilumina el cielo oscuro.", question: "¿Qué ilumina la luna?", answer: "el cielo oscuro", incorrect: ["la luna", "ilumina", "oscuro"] },
                    { text: "El pájaro vuela sobre el árbol alto.", question: "¿Qué hace el pájaro?", answer: "vuela", incorrect: ["sobre el árbol", "alto", "el pájaro"] },
                    { text: "El río fluye entre las montañas grandes.", question: "¿Dónde fluye el río?", answer: "entre las montañas grandes", incorrect: ["el río", "fluye", "grandes"] },
                    { text: "Ella baila en la fiesta animada.", question: "¿Qué hace ella?", answer: "baila", incorrect: ["en la fiesta", "animada", "ella"] },
                    { text: "El coche rojo pasa por la calle ancha.", question: "¿Qué hace el coche?", answer: "pasa", incorrect: ["por la calle", "rojo", "ancho"] },
                    { text: "La flor crece en el jardín colorido.", question: "¿Dónde crece la flor?", answer: "en el jardín colorido", incorrect: ["la flor", "crece", "colorido"] },
                    { text: "El niño juega con un balón azul.", question: "¿Con qué juega el niño?", answer: "un balón azul", incorrect: ["el niño", "juega", "azul"] },
                    { text: "La nube cubre el cielo gris.", question: "¿Qué cubre la nube?", answer: "el cielo gris", incorrect: ["la nube", "cubre", "gris"] },
                    { text: "El tren viaja por el campo abierto.", question: "¿Qué hace el tren?", answer: "viaja", incorrect: ["por el campo", "abierto", "el tren"] },
                    { text: "Ella escribe en un cuaderno nuevo.", question: "¿Qué hace ella?", answer: "escribe", incorrect: ["en un cuaderno", "nuevo", "ella"] },
                    { text: "El perro ladra en el patio grande.", question: "¿Qué hace el perro?", answer: "ladra", incorrect: ["en el patio", "grande", "el perro"] },
                    { text: "La casa blanca está en la colina.", question: "¿Dónde está la casa?", answer: "en la colina", incorrect: ["blanca", "la casa", "está"] },
                    { text: "El sol calienta la playa soleada.", question: "¿Qué hace el sol?", answer: "calienta", incorrect: ["la playa", "soleada", "el sol"] },
                    { text: "Los niños corren en el parque verde.", question: "¿Qué hacen los niños?", answer: "corren", incorrect: ["en el parque", "verde", "los niños"] },
                    { text: "La luna brilla en la noche clara.", question: "¿Qué hace la luna?", answer: "brilla", incorrect: ["en la noche", "clara", "la luna"] },
                    { text: "El pájaro canta en la rama verde.", question: "¿Qué hace el pájaro?", answer: "canta", incorrect: ["en la rama", "verde", "el pájaro"] },
                    { text: "El río pasa por el valle tranquilo.", question: "¿Dónde pasa el río?", answer: "por el valle tranquilo", incorrect: ["el río", "pasa", "tranquilo"] },
                    { text: "Ella baila en el escenario brillante.", question: "¿Qué hace ella?", answer: "baila", incorrect: ["en el escenario", "brillante", "ella"] },
                    { text: "El coche azul cruza el puente largo.", question: "¿Qué hace el coche?", answer: "cruza", incorrect: ["el puente", "largo", "azul"] },
                    { text: "La flor roja crece en el campo.", question: "¿Qué crece en el campo?", answer: "la flor roja", incorrect: ["el campo", "crece", "roja"] },
                    { text: "El niño pinta un dibujo colorido.", question: "¿Qué pinta el niño?", answer: "un dibujo colorido", incorrect: ["el niño", "pinta", "colorido"] },
                    { text: "La nube flota en el cielo azul.", question: "¿Qué hace la nube?", answer: "flota", incorrect: ["en el cielo", "azul", "la nube"] },
                    { text: "El tren para en la estación grande.", question: "¿Dónde para el tren?", answer: "en la estación grande", incorrect: ["el tren", "para", "grande"] },
                    { text: "Ella lee en la sala tranquila.", question: "¿Dónde lee ella?", answer: "en la sala tranquila", incorrect: ["ella", "lee", "tranquila"] },
                    { text: "El perro juega en el jardín verde.", question: "¿Qué hace el perro?", answer: "juega", incorrect: ["en el jardín", "verde", "el perro"] },
                    { text: "La casa roja está en el pueblo.", question: "¿Dónde está la casa?", answer: "en el pueblo", incorrect: ["roja", "la casa", "está"] },
                    { text: "El sol sale por la mañana temprano.", question: "¿Cuándo sale el sol?", answer: "por la mañana temprano", incorrect: ["el sol", "sale", "temprano"] },
                    { text: "Los niños cantan en el coro alegre.", question: "¿Qué hacen los niños?", answer: "cantan", incorrect: ["en el coro", "alegre", "los niños"] },
                    { text: "La luna aparece en el cielo oscuro.", question: "¿Dónde aparece la luna?", answer: "en el cielo oscuro", incorrect: ["la luna", "aparece", "oscuro"] },
                    { text: "El pájaro vuela en el cielo claro.", question: "¿Qué hace el pájaro?", answer: "vuela", incorrect: ["en el cielo", "claro", "el pájaro"] },
                    { text: "El río corre por el bosque denso.", question: "¿Dónde corre el río?", answer: "por el bosque denso", incorrect: ["el río", "corre", "denso"] },
                    { text: "Ella escribe una carta larga.", question: "¿Qué escribe ella?", answer: "una carta larga", incorrect: ["ella", "escribe", "larga"] },
                    { text: "El coche negro pasa por la ciudad.", question: "¿Qué hace el coche?", answer: "pasa", incorrect: ["por la ciudad", "negro", "el coche"] },
                    { text: "La flor crece en el prado verde.", question: "¿Dónde crece la flor?", answer: "en el prado verde", incorrect: ["la flor", "crece", "verde"] },
                    { text: "El niño juega en el parque soleado.", question: "¿Dónde juega el niño?", answer: "en el parque soleado", incorrect: ["el niño", "juega", "soleado"] },
                    { text: "La nube cubre el sol brillante.", question: "¿Qué cubre la nube?", answer: "el sol brillante", incorrect: ["la nube", "cubre", "brillante"] },
                    { text: "El tren viaja por la llanura amplia.", question: "¿Dónde viaja el tren?", answer: "por la llanura amplia", incorrect: ["el tren", "viaja", "amplia"] },
                    { text: "Ella pinta en el taller luminoso.", question: "¿Dónde pinta ella?", answer: "en el taller luminoso", incorrect: ["ella", "pinta", "luminoso"] },
                    { text: "El perro corre en el campo abierto.", question: "¿Qué hace el perro?", answer: "corre", incorrect: ["en el campo", "abierto", "el perro"] },
                    { text: "La casa está en la montaña alta.", question: "¿Dónde está la casa?", answer: "en la montaña alta", incorrect: ["la casa", "está", "alta"] },
                    { text: "El sol brilla en el cielo despejado.", question: "¿Qué hace el sol?", answer: "brilla", incorrect: ["en el cielo", "despejado", "el sol"] },
                    { text: "Los niños juegan en el patio grande.", question: "¿Qué hacen los niños?", answer: "juegan", incorrect: ["en el patio", "grande", "los niños"] },
                    { text: "La luna ilumina el lago tranquilo.", question: "¿Qué ilumina la luna?", answer: "el lago tranquilo", incorrect: ["la luna", "ilumina", "tranquilo"] },
                    { text: "El pájaro canta en el árbol frondoso.", question: "¿Qué hace el pájaro?", answer: "canta", incorrect: ["en el árbol", "frondoso", "el pájaro"] }
                ],
                intermediate: [
                    { text: "En un pequeño pueblo vivía un carpintero que fabricaba muebles muy hermosos.", question: "¿Qué fabricaba el carpintero?", answer: "muebles muy hermosos", incorrect: ["un carpintero", "en un pequeño pueblo", "vivía"] },
                    { text: "Ana y Pedro encontraron un tesoro escondido en una cueva oscura.", question: "¿Qué encontraron Ana y Pedro?", answer: "un tesoro escondido", incorrect: ["en una cueva oscura", "Ana y Pedro", "encontraron"] },
                    { text: "El festival de música atrajo a miles de personas al parque central.", question: "¿Qué atrajo el festival?", answer: "a miles de personas", incorrect: ["al parque central", "el festival", "de música"] },
                    { text: "María soñaba con viajar a París para ver la Torre Eiffel.", question: "¿Qué soñaba María?", answer: "viajar a París", incorrect: ["ver la Torre Eiffel", "María", "soñaba"] },
                    { text: "El equipo de fútbol entrenó duro para ganar el campeonato.", question: "¿Por qué entrenó el equipo?", answer: "para ganar el campeonato", incorrect: ["el equipo de fútbol", "entrenó duro", "el campeonato"] },
                    { text: "La tormenta sorprendió a los excursionistas en la montaña.", question: "¿Qué sorprendió a los excursionistas?", answer: "la tormenta", incorrect: ["en la montaña", "los excursionistas", "sorprendió"] },
                    { text: "El escritor publicó su primera novela a los 25 años.", question: "¿Qué publicó el escritor?", answer: "su primera novela", incorrect: ["a los 25 años", "el escritor", "publicó"] },
                    { text: "Los niños construyeron un castillo de arena en la playa.", question: "¿Qué construyeron los niños?", answer: "un castillo de arena", incorrect: ["en la playa", "los niños", "construyeron"] },
                    { text: "El científico descubrió una nueva especie en el océano.", question: "¿Qué descubrió el científico?", answer: "una nueva especie", incorrect: ["en el océano", "el científico", "descubrió"] },
                    { text: "La familia decidió mudarse a una ciudad más grande para mejores oportunidades.", question: "¿Por qué se mudó la familia?", answer: "para mejores oportunidades", incorrect: ["a una ciudad más grande", "la familia", "decidió"] },
                    { text: "Juan salvó al perro que estaba atrapado en el río.", question: "¿Qué salvó Juan?", answer: "al perro", incorrect: ["atrapado en el río", "Juan", "salvó"] },
                    { text: "La maestra contó una historia fascinante a los alumnos.", question: "¿Qué contó la maestra?", answer: "una historia fascinante", incorrect: ["a los alumnos", "la maestra", "contó"] },
                    { text: "Pedro perdió su billetera en el autobús abarrotado.", question: "¿Dónde perdió Pedro su billetera?", answer: "en el autobús abarrotado", incorrect: ["su billetera", "Pedro", "perdió"] },
                    { text: "La niña dibujó un paisaje hermoso con crayones.", question: "¿Qué dibujó la niña?", answer: "un paisaje hermoso", incorrect: ["con crayones", "la niña", "dibujó"] },
                    { text: "El piloto aterrizó el avión de manera segura durante la tormenta.", question: "¿Cómo aterrizó el piloto el avión?", answer: "de manera segura", incorrect: ["el avión", "durante la tormenta", "el piloto"] },
                    { text: "Sofía encontró una moneda antigua en el jardín.", question: "¿Qué encontró Sofía?", answer: "una moneda antigua", incorrect: ["en el jardín", "Sofía", "encontró"] },
                    { text: "El grupo de amigos organizó un picnic en el bosque.", question: "¿Qué organizó el grupo de amigos?", answer: "un picnic", incorrect: ["en el bosque", "el grupo de amigos", "organizó"] },
                    { text: "La abuela cocinó una cena deliciosa para la familia.", question: "¿Qué cocinó la abuela?", answer: "una cena deliciosa", incorrect: ["para la familia", "la abuela", "cocinó"] },
                    { text: "Carlos reparó la bicicleta rota de su hermano.", question: "¿Qué reparó Carlos?", answer: "la bicicleta rota", incorrect: ["de su hermano", "Carlos", "reparó"] },
                    { text: "La bailarina practicó su rutina durante horas.", question: "¿Qué practicó la bailarina?", answer: "su rutina", incorrect: ["durante horas", "la bailarina", "practicó"] },
                    { text: "El explorador subió la montaña nevada con dificultad.", question: "¿Qué subió el explorador?", answer: "la montaña nevada", incorrect: ["con dificultad", "el explorador", "subió"] },
                    { text: "Laura plantó flores en el jardín frontal.", question: "¿Qué plantó Laura?", answer: "flores", incorrect: ["en el jardín frontal", "Laura", "plantó"] },
                    { text: "El mago realizó un truco sorprendente en el espectáculo.", question: "¿Qué realizó el mago?", answer: "un truco sorprendente", incorrect: ["en el espectáculo", "el mago", "realizó"] },
                    { text: "Los bomberos extinguieron el fuego en la casa.", question: "¿Qué extinguieron los bomberos?", answer: "el fuego", incorrect: ["en la casa", "los bomberos", "extinguieron"] },
                    { text: "Elena escribió una carta a su amiga lejana.", question: "¿Qué escribió Elena?", answer: "una carta", incorrect: ["a su amiga lejana", "Elena", "escribió"] },
                    { text: "El pintor creó una obra maestra en su taller.", question: "¿Qué creó el pintor?", answer: "una obra maestra", incorrect: ["en su taller", "el pintor", "creó"] },
                    { text: "Los vecinos celebraron una fiesta en el barrio.", question: "¿Qué celebraron los vecinos?", answer: "una fiesta", incorrect: ["en el barrio", "los vecinos", "celebraron"] },
                    { text: "El detective resolvió el misterio del robo.", question: "¿Qué resolvió el detective?", answer: "el misterio del robo", incorrect: ["el detective", "resolvió", "del robo"] },
                    { text: "La cantante interpretó una canción emotiva en el concierto.", question: "¿Qué interpretó la cantante?", answer: "una canción emotiva", incorrect: ["en el concierto", "la cantante", "interpretó"] },
                    { text: "Miguel construyó una casa de juguete para su hijo.", question: "¿Qué construyó Miguel?", answer: "una casa de juguete", incorrect: ["para su hijo", "Miguel", "construyó"] },
                    { text: "La bibliotecaria organizó los libros en los estantes.", question: "¿Qué organizó la bibliotecaria?", answer: "los libros", incorrect: ["en los estantes", "la bibliotecaria", "organizó"] },
                    { text: "El jardinero podó los arbustos en el parque.", question: "¿Qué podó el jardinero?", answer: "los arbustos", incorrect: ["en el parque", "el jardinero", "podó"] },
                    { text: "Sonia rescató un pájaro herido en el bosque.", question: "¿Qué rescató Sonia?", answer: "un pájaro herido", incorrect: ["en el bosque", "Sonia", "rescató"] },
                    { text: "El chef preparó un plato exquisito para los invitados.", question: "¿Qué preparó el chef?", answer: "un plato exquisito", incorrect: ["para los invitados", "el chef", "preparó"] },
                    { text: "Los estudiantes presentaron un proyecto científico en la feria.", question: "¿Qué presentaron los estudiantes?", answer: "un proyecto científico", incorrect: ["en la feria", "los estudiantes", "presentaron"] },
                    { text: "La actriz interpretó un papel principal en la obra.", question: "¿Qué interpretó la actriz?", answer: "un papel principal", incorrect: ["en la obra", "la actriz", "interpretó"] },
                    { text: "El mecánico arregló el motor del coche averiado.", question: "¿Qué arregló el mecánico?", answer: "el motor del coche averiado", incorrect: ["el mecánico", "arregló", "averiado"] },
                    { text: "Paula encontró un collar perdido en la calle.", question: "¿Qué encontró Paula?", answer: "un collar perdido", incorrect: ["en la calle", "Paula", "encontró"] },
                    { text: "El músico compuso una melodía hermosa para el piano.", question: "¿Qué compuso el músico?", answer: "una melodía hermosa", incorrect: ["para el piano", "el músico", "compuso"] },
                    { text: "Los atletas compitieron en una carrera de larga distancia.", question: "¿En qué compitieron los atletas?", answer: "en una carrera de larga distancia", incorrect: ["los atletas", "compitieron", "de larga distancia"] },
                    { text: "La diseñadora creó un vestido elegante para la gala.", question: "¿Qué creó la diseñadora?", answer: "un vestido elegante", incorrect: ["para la gala", "la diseñadora", "creó"] },
                    { text: "El fotógrafo capturó un momento único en la naturaleza.", question: "¿Qué capturó el fotógrafo?", answer: "un momento único", incorrect: ["en la naturaleza", "el fotógrafo", "capturó"] },
                    { text: "Los voluntarios limpiaron el río contaminado.", question: "¿Qué limpiaron los voluntarios?", answer: "el río contaminado", incorrect: ["los voluntarios", "limpiaron", "contaminado"] },
                    { text: "El profesor explicó una lección complicada a los alumnos.", question: "¿Qué explicó el profesor?", answer: "una lección complicada", incorrect: ["a los alumnos", "el profesor", "explicó"] },
                    { text: "La niña adoptó un gato abandonado de la calle.", question: "¿Qué adoptó la niña?", answer: "un gato abandonado", incorrect: ["de la calle", "la niña", "adoptó"] },
                    { text: "El ingeniero diseñó un puente resistente para el río.", question: "¿Qué diseñó el ingeniero?", answer: "un puente resistente", incorrect: ["para el río", "el ingeniero", "diseñó"] },
                    { text: "Los amigos compartieron historias alrededor de la fogata.", question: "¿Qué compartieron los amigos?", answer: "historias", incorrect: ["alrededor de la fogata", "los amigos", "compartieron"] },
                    { text: "La exploradora descubrió una ruina antigua en la jungla.", question: "¿Qué descubrió la exploradora?", answer: "una ruina antigua", incorrect: ["en la jungla", "la exploradora", "descubrió"] },
                    { text: "El niño inventó un juego nuevo con sus juguetes.", question: "¿Qué inventó el niño?", answer: "un juego nuevo", incorrect: ["con sus juguetes", "el niño", "inventó"] },
                    { text: "La familia visitó un museo histórico en la ciudad.", question: "¿Qué visitó la familia?", answer: "un museo histórico", incorrect: ["en la ciudad", "la familia", "visitó"] }
                ],
                advanced: [
                    { text: "La globalización ha transformado las economías, conectando mercados mundiales.", question: "¿Qué ha transformado la globalización?", answer: "las economías", incorrect: ["conectando mercados mundiales", "la globalización", "mercados mundiales"] },
                    { text: "La educación es esencial para el desarrollo personal y social.", question: "¿Para qué es esencial la educación?", answer: "el desarrollo personal y social", incorrect: ["la educación", "esencial", "personal y social"] },
                    { text: "El cambio climático representa una amenaza grave para el planeta.", question: "¿Qué representa el cambio climático?", answer: "una amenaza grave", incorrect: ["para el planeta", "el cambio climático", "grave"] },
                    { text: "La tecnología ha revolucionado la forma en que comunicamos.", question: "¿Qué ha revolucionado la tecnología?", answer: "la forma en que comunicamos", incorrect: ["la tecnología", "revolucionado", "comunicamos"] },
                    { text: "La igualdad de género es fundamental para una sociedad justa.", question: "¿Para qué es fundamental la igualdad de género?", answer: "una sociedad justa", incorrect: ["la igualdad de género", "fundamental", "justa"] },
                    { text: "El ejercicio regular beneficia la salud física y mental.", question: "¿Qué beneficia el ejercicio regular?", answer: "la salud física y mental", incorrect: ["el ejercicio regular", "beneficia", "física y mental"] },
                    { text: "La preservación del medio ambiente es responsabilidad de todos.", question: "¿De quién es responsabilidad la preservación del medio ambiente?", answer: "de todos", incorrect: ["la preservación", "del medio ambiente", "responsabilidad"] },
                    { text: "La lectura fomenta la imaginación y el conocimiento.", question: "¿Qué fomenta la lectura?", answer: "la imaginación y el conocimiento", incorrect: ["la lectura", "fomenta", "imaginación"] },
                    { text: "La democracia permite la participación ciudadana en el gobierno.", question: "¿Qué permite la democracia?", answer: "la participación ciudadana", incorrect: ["en el gobierno", "la democracia", "permite"] },
                    { text: "El arte expresa emociones y refleja la cultura.", question: "¿Qué expresa el arte?", answer: "emociones", incorrect: ["refleja la cultura", "el arte", "expresa"] },
                    { text: "La ciencia avanza mediante la experimentación y la observación.", question: "¿Mediante qué avanza la ciencia?", answer: "la experimentación y la observación", incorrect: ["la ciencia", "avanza", "experimentación"] },
                    { text: "La diversidad cultural enriquece a las sociedades modernas.", question: "¿Qué enriquece la diversidad cultural?", answer: "a las sociedades modernas", incorrect: ["la diversidad cultural", "enriquece", "modernas"] },
                    { text: "El turismo sostenible protege los recursos naturales.", question: "¿Qué protege el turismo sostenible?", answer: "los recursos naturales", incorrect: ["el turismo sostenible", "protege", "naturales"] },
                    { text: "La innovación tecnológica impulsa el crecimiento económico.", question: "¿Qué impulsa la innovación tecnológica?", answer: "el crecimiento económico", incorrect: ["la innovación tecnológica", "impulsa", "económico"] },
                    { text: "La ética en los negocios fomenta la confianza pública.", question: "¿Qué fomenta la ética en los negocios?", answer: "la confianza pública", incorrect: ["la ética", "en los negocios", "fomenta"] },
                    { text: "La meditación reduce el estrés y mejora la concentración.", question: "¿Qué reduce la meditación?", answer: "el estrés", incorrect: ["mejora la concentración", "la meditación", "reduce"] },
                    { text: "La cooperación internacional resuelve conflictos globales.", question: "¿Qué resuelve la cooperación internacional?", answer: "conflictos globales", incorrect: ["la cooperación internacional", "resuelve", "globales"] },
                    { text: "La nutrición adecuada previene enfermedades crónicas.", question: "¿Qué previene la nutrición adecuada?", answer: "enfermedades crónicas", incorrect: ["la nutrición adecuada", "previene", "crónicas"] },
                    { text: "La libertad de expresión es un derecho humano fundamental.", question: "¿Qué es la libertad de expresión?", answer: "un derecho humano fundamental", incorrect: ["la libertad de expresión", "es", "fundamental"] },
                    { text: "El deporte promueve la disciplina y el trabajo en equipo.", question: "¿Qué promueve el deporte?", answer: "la disciplina y el trabajo en equipo", incorrect: ["el deporte", "promueve", "en equipo"] },
                    { text: "La investigación científica impulsa avances médicos.", question: "¿Qué impulsa la investigación científica?", answer: "avances médicos", incorrect: ["la investigación científica", "impulsa", "médicos"] },
                    { text: "La sostenibilidad ambiental asegura el futuro de las generaciones.", question: "¿Qué asegura la sostenibilidad ambiental?", answer: "el futuro de las generaciones", incorrect: ["la sostenibilidad ambiental", "asegura", "de las generaciones"] },
                    { text: "La educación inclusiva beneficia a todos los estudiantes.", question: "¿A quién beneficia la educación inclusiva?", answer: "a todos los estudiantes", incorrect: ["la educación inclusiva", "beneficia", "todos"] },
                    { text: "La música une a las personas de diferentes culturas.", question: "¿Qué une la música?", answer: "a las personas de diferentes culturas", incorrect: ["la música", "une", "diferentes culturas"] },
                    { text: "La responsabilidad social corporativa mejora la imagen de las empresas.", question: "¿Qué mejora la responsabilidad social corporativa?", answer: "la imagen de las empresas", incorrect: ["la responsabilidad social corporativa", "mejora", "de las empresas"] },
                    { text: "El voluntariado fortalece las comunidades locales.", question: "¿Qué fortalece el voluntariado?", answer: "las comunidades locales", incorrect: ["el voluntariado", "fortalece", "locales"] },
                    { text: "La literatura inspira el pensamiento crítico.", question: "¿Qué inspira la literatura?", answer: "el pensamiento crítico", incorrect: ["la literatura", "inspira", "crítico"] },
                    { text: "La economía circular reduce los residuos ambientales.", question: "¿Qué reduce la economía circular?", answer: "los residuos ambientales", incorrect: ["la economía circular", "reduce", "ambientales"] },
                    { text: "La empatía fomenta relaciones saludables.", question: "¿Qué fomenta la empatía?", answer: "relaciones saludables", incorrect: ["la empatía", "fomenta", "saludables"] },
                    { text: "La inteligencia artificial transforma la industria.", question: "¿Qué transforma la inteligencia artificial?", answer: "la industria", incorrect: ["la inteligencia artificial", "transforma", "artificial"] },
                    { text: "La preservación histórica mantiene la identidad cultural.", question: "¿Qué mantiene la preservación histórica?", answer: "la identidad cultural", incorrect: ["la preservación histórica", "mantiene", "cultural"] },
                    { text: "El aprendizaje continuo adapta a los cambios laborales.", question: "¿A qué adapta el aprendizaje continuo?", answer: "a los cambios laborales", incorrect: ["el aprendizaje continuo", "adapta", "laborales"] },
                    { text: "La biodiversidad sostiene los ecosistemas terrestres.", question: "¿Qué sostiene la biodiversidad?", answer: "los ecosistemas terrestres", incorrect: ["la biodiversidad", "sostiene", "terrestres"] },
                    { text: "La diplomacia resuelve disputas internacionales.", question: "¿Qué resuelve la diplomacia?", answer: "disputas internacionales", incorrect: ["la diplomacia", "resuelve", "internacionales"] },
                    { text: "La creatividad impulsa la innovación en los negocios.", question: "¿Qué impulsa la creatividad?", answer: "la innovación en los negocios", incorrect: ["la creatividad", "impulsa", "en los negocios"] },
                    { text: "La higiene personal previene enfermedades infecciosas.", question: "¿Qué previene la higiene personal?", answer: "enfermedades infecciosas", incorrect: ["la higiene personal", "previene", "infecciosas"] },
                    { text: "La igualdad educativa promueve la movilidad social.", question: "¿Qué promueve la igualdad educativa?", answer: "la movilidad social", incorrect: ["la igualdad educativa", "promueve", "social"] },
                    { text: "La fotografía captura momentos históricos importantes.", question: "¿Qué captura la fotografía?", answer: "momentos históricos importantes", incorrect: ["la fotografía", "captura", "importantes"] },
                    { text: "La energía renovable reduce la dependencia de combustibles fósiles.", question: "¿Qué reduce la energía renovable?", answer: "la dependencia de combustibles fósiles", incorrect: ["la energía renovable", "reduce", "de combustibles"] },
                    { text: "La resiliencia ayuda a superar adversidades personales.", question: "¿Qué ayuda la resiliencia?", answer: "a superar adversidades personales", incorrect: ["la resiliencia", "ayuda", "personales"] },
                    { text: "La colaboración interdisciplinaria resuelve problemas complejos.", question: "¿Qué resuelve la colaboración interdisciplinaria?", answer: "problemas complejos", incorrect: ["la colaboración interdisciplinaria", "resuelve", "complejos"] },
                    { text: "La alfabetización digital empodera a los individuos en la era moderna.", question: "¿Qué empodera la alfabetización digital?", answer: "a los individuos en la era moderna", incorrect: ["la alfabetización digital", "empodera", "en la era moderna"] },
                    { text: "La conservación marina protege la vida oceánica.", question: "¿Qué protege la conservación marina?", answer: "la vida oceánica", incorrect: ["la conservación marina", "protege", "oceánica"] },
                    { text: "La ética periodística asegura la veracidad de la información.", question: "¿Qué asegura la ética periodística?", answer: "la veracidad de la información", incorrect: ["la ética periodística", "asegura", "de la información"] },
                    { text: "La actividad física regular mejora la calidad de vida.", question: "¿Qué mejora la actividad física regular?", answer: "la calidad de vida", incorrect: ["la actividad física regular", "mejora", "de vida"] },
                    { text: "La gobernanza transparente reduce la corrupción.", question: "¿Qué reduce la gobernanza transparente?", answer: "la corrupción", incorrect: ["la gobernanza transparente", "reduce", "transparente"] },
                    { text: "La diversidad en el lugar de trabajo fomenta la innovación.", question: "¿Qué fomenta la diversidad en el lugar de trabajo?", answer: "la innovación", incorrect: ["la diversidad", "en el lugar de trabajo", "fomenta"] },
                    { text: "La investigación espacial expande el conocimiento humano.", question: "¿Qué expande la investigación espacial?", answer: "el conocimiento humano", incorrect: ["la investigación espacial", "expande", "humano"] },
                    { text: "La empatía cultural promueve la paz global.", question: "¿Qué promueve la empatía cultural?", answer: "la paz global", incorrect: ["la empatía cultural", "promueve", "global"] },
                    { text: "La agricultura sostenible asegura la seguridad alimentaria.", question: "¿Qué asegura la agricultura sostenible?", answer: "la seguridad alimentaria", incorrect: ["la agricultura sostenible", "asegura", "alimentaria"] }
                ]
            }
        };

        // Generar ejercicios a partir de los conjuntos predefinidos
        const exercises = {
            grammar: {
                basic: sentencePools.grammar.basic.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `En la oración: <strong>${item.sentence}</strong> Identifica el adjetivo en la oración.`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                }),
                intermediate: sentencePools.grammar.intermediate.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: item.question,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                }),
                advanced: sentencePools.grammar.advanced.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `En la oración: <strong>${item.sentence}</strong> Identifica la oración subordinada en la frase.`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                })
            },
            spelling: {
                basic: sentencePools.spelling.basic.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `Selecciona la palabra con acento correcto en la oración: <strong>${item.sentence}</strong>`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                }),
                intermediate: sentencePools.spelling.intermediate.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `Corrige la puntuación de la oración: <strong>${item.sentence}</strong>`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                }),
                advanced: sentencePools.spelling.advanced.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `Selecciona la palabra correcta para completar la oración: <strong>${item.sentence}</strong>`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                })
            },
            reading: {
                basic: sentencePools.reading.basic.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `Lee el texto: <strong>${item.text}</strong> ${item.question}`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                }),
                intermediate: sentencePools.reading.intermediate.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `Lee el texto: <strong>${item.text}</strong> ${item.question}`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                }),
                advanced: sentencePools.reading.advanced.map((item, i) => {
                    const options = shuffleArray([{ text: item.answer, correct: true }, ...item.incorrect.map(text => ({ text, correct: false }))]);
                    return {
                        id: i + 1,
                        question: `Lee el texto: <strong>${item.text}</strong> ${item.question}`,
                        options,
                        feedbackCorrect: `¡Correcto! La respuesta es "${item.answer}".`,
                        feedbackIncorrect: `Incorrecto. La respuesta correcta es "${item.answer}".`
                    };
                })
            }
        };

        // Manejo de navegación
        function showPage(pageId) {
            document.querySelectorAll('.subject-page').forEach(page => {
                page.classList.remove('active');
            });
            const page = document.querySelector(`#${pageId}-page`);
            if (page) {
                page.classList.add('active');
                if (['grammar', 'spelling', 'reading'].includes(pageId)) {
                    showSubject(pageId);
                }
            }
        }

        function showSubject(subject) {
            currentExercise.subject = subject;
            showPage(subject);
            const defaultTab = document.querySelector(`#${subject}-page .exercise-tab.active`);
            if (defaultTab) {
                const tabId = defaultTab.dataset.tab;
                showExerciseTab(subject, tabId);
            }
        }

        function showExerciseTab(subject, tabId) {
            currentExercise.level = tabId.split('-')[1];
            currentExercise.index = 0;
            const page = document.querySelector(`#${subject}-page`);
            page.querySelectorAll('.exercise-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            page.querySelectorAll('.exercise-container').forEach(container => {
                container.classList.remove('active');
            });
            page.querySelector(`[data-tab="${tabId}"]`).classList.add('active');
            const container = page.querySelector(`#${tabId}-exercises`);
            container.classList.add('active');
            loadExercise();
        }

        function loadExercise() {
            const exercise = exercises[currentExercise.subject][currentExercise.level][currentExercise.index];
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            
            // Asegurarse de que el contenedor exista
            if (!container) return;

            // Actualizar el contador de ejercicios
            container.querySelector('.exercise-counter').textContent = currentExercise.index + 1;
            
            // Establecer la pregunta
            container.querySelector('.exercise-question').innerHTML = exercise.question;
            
            // Establecer los mensajes de retroalimentación
            container.querySelector('.feedback-correct').textContent = exercise.feedbackCorrect;
            container.querySelector('.feedback-incorrect').textContent = exercise.feedbackIncorrect;
            
            const optionsContainer = container.querySelector('.options-container');
            const inputAnswer = container.querySelector('.input-answer');
            
            // Manejar diferentes tipos de ejercicios
            if (exercise.options) {
                // Ejercicio de opción múltiple
                optionsContainer.style.display = 'grid';
                if (inputAnswer) inputAnswer.style.display = 'none';
                
                optionsContainer.innerHTML = exercise.options.map(opt => 
                    `<div class="option" data-correct="${opt.correct}">${opt.text}</div>`
                ).join('');
            } else {
                // Ejercicio de entrada de texto
                optionsContainer.style.display = 'none';
                if (inputAnswer) {
                    inputAnswer.style.display = 'block';
                    inputAnswer.value = '';
                }
            }
            
            // Restablecer el estado de la interfaz
            container.querySelector('.check-answer-btn').style.display = 'block';
            container.querySelector('.next-question-btn').style.display = 'none';
            container.querySelectorAll('.exercise-feedback').forEach(fb => {
                fb.style.display = 'none';
            });
            container.querySelectorAll('.option').forEach(opt => {
                opt.classList.remove('selected', 'correct', 'incorrect');
            });
            
            // Ocultar el mensaje de finalización
            const completionMessage = container.querySelector('.completion-message');
            const moreExercises = container.querySelector('.more-exercises');
            if (completionMessage) completionMessage.style.display = 'none';
            if (moreExercises) moreExercises.style.display = 'none';
        }

        function checkAnswer() {
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            if (!container) return;

            const exercise = exercises[currentExercise.subject][currentExercise.level][currentExercise.index];
            
            let isCorrect = false;
            
            if (exercise.options) {
                // Ejercicio de opción múltiple
                const selectedOption = container.querySelector('.option.selected');
                isCorrect = selectedOption && selectedOption.dataset.correct === 'true';
                
                // Mostrar estados correcto/incorrecto
                container.querySelectorAll('.option').forEach(opt => {
                    opt.classList.add(opt.dataset.correct === 'true' ? 'correct' : 'incorrect');
                });
            } else {
                // Ejercicio de entrada de texto
                const input = container.querySelector('.input-answer');
                isCorrect = input && input.value.trim() === exercise.answer;
            }
            
            // Mostrar retroalimentación
            container.querySelector(isCorrect ? '.feedback-correct' : '.feedback-incorrect').style.display = 'block';
            container.querySelector('.check-answer-btn').style.display = 'none';
            container.querySelector('.next-question-btn').style.display = 'block';
            
            // Actualizar estadísticas del usuario
            userData.completedExercises++;
            userData.totalAnswers++;
            if (isCorrect) userData.correctAnswers++;
            updateUserStats();
        }

        function nextQuestion() {
            currentExercise.index++;
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            if (!container) return;

            const exerciseCount = exercises[currentExercise.subject][currentExercise.level].length;
            
            if (currentExercise.index < exerciseCount) {
                loadExercise();
            } else {
                // Mostrar mensaje de finalización
                showCompletionMessage();
            }
        }

        function showCompletionMessage() {
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            if (!container) return;

            const completionMessage = container.querySelector('.completion-message');
            const moreExercises = container.querySelector('.more-exercises');
            
            if (completionMessage) {
                completionMessage.innerHTML = `<h3>¡Felicidades!</h3><p>Has completado los ${exercises[currentExercise.subject][currentExercise.level].length} ejercicios de ${currentExercise.subject} ${currentExercise.level}.</p>`;
                completionMessage.style.display = 'block';
            }
            if (moreExercises) moreExercises.style.display = 'block';
            
            // Ocultar elementos del ejercicio
            container.querySelector('.exercise-question').style.display = 'none';
            container.querySelector('.options-container').style.display = 'none';
            if (container.querySelector('.input-answer')) {
                container.querySelector('.input-answer').style.display = 'none';
            }
            container.querySelector('.check-answer-btn').style.display = 'none';
            container.querySelector('.next-question-btn').style.display = 'none';
        }

        // Oyentes de eventos
        document.addEventListener('DOMContentLoaded', () => {
            // Agregar elementos de mensaje de finalización y más ejercicios a cada contenedor de ejercicios
            document.querySelectorAll('.exercise-container').forEach(container => {
                const completionDiv = document.createElement('div');
                completionDiv.className = 'completion-message';
                container.appendChild(completionDiv);
                
                const moreDiv = document.createElement('div');
                moreDiv.className = 'more-exercises';
                moreDiv.textContent = 'Pronto añadiremos más ejercicios.';
                container.appendChild(moreDiv);
            });

            // Inicializar página de inicio
            showPage('home');

            // Enlaces de navegación
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const page = link.dataset.page;
                    showPage(page);
                });
            });

            // Botones de práctica de asignaturas
            document.querySelectorAll('.practice-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    const subject = btn.dataset.subject;
                    showSubject(subject);
                });
            });

            // Pestañas de ejercicios
            document.querySelectorAll('.exercise-tab').forEach(tab => {
                tab.addEventListener('click', (e) => {
                    e.preventDefault();
                    const subject = tab.closest('.subject-page').id.split('-')[0];
                    const tabId = tab.dataset.tab;
                    showExerciseTab(subject, tabId);
                });
            });

            // Botones de comprobación de respuestas
            document.querySelectorAll('.check-answer-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    checkAnswer();
                });
            });

            // Selección de opciones
            document.addEventListener('click', (e) => {
                if (e.target.classList.contains('option')) {
                    const optionsContainer = e.target.closest('.options-container');
                    if (optionsContainer) {
                        optionsContainer.querySelectorAll('.option').forEach(opt => opt.classList.remove('selected'));
                        e.target.classList.add('selected');
                    }
                }
            });

            // Botones de siguiente pregunta
            document.querySelectorAll('.next-question-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    nextQuestion();
                });
            });

            // Modal de inicio de sesión
            const loginModal = document.getElementById('loginModal');
            document.getElementById('loginBtn').addEventListener('click', (e) => {
                e.preventDefault();
                loginModal.style.display = 'flex';
            });
            document.querySelector('.close-modal').addEventListener('click', (e) => {
                e.preventDefault();
                loginModal.style.display = 'none';
            });
            document.getElementById('loginForm').addEventListener('submit', (e) => {
                e.preventDefault();
                userData.loggedIn = true;
                userData.name = document.getElementById('email').value.split('@')[0];
                userData.email = document.getElementById('email').value;
                updateUserStats();
                loginModal.style.display = 'none';
            });

            // Menú desplegable del usuario
            document.getElementById('userAvatar').addEventListener('click', (e) => {
                e.preventDefault();
                document.getElementById('userDropdown').classList.toggle('active');
            });
        });

        function updateUserStats() {
            document.getElementById('userName').textContent = userData.name;
            document.getElementById('userEmail').textContent = userData.email || 'No has iniciado sesión';
            document.getElementById('completedExercises').textContent = userData.completedExercises;
            document.getElementById('correctAnswers').textContent = userData.totalAnswers ? 
                Math.round((userData.correctAnswers / userData.totalAnswers) * 100) + '%' : '0%';
        }
    </script>
</body>
</html>
