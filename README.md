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
                    <li><a href="http://practicaejercicios.es/">Inicio</a></li>
                    <li><a href="#" class="nav-link" data-page="language">Lengua Castellana</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/">Matemáticas</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/">Ciencias</a></li>
                    <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/">Sociales</a></li>
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
                    <h1>Domina la Lengua Castellana con Ejercicios Prácticos</h1>
                    <p>Gramática, ortografía, comprensión lectora y más. Miles de ejercicios interactivos para todos los niveles.</p>
                    <a href="#" class="btn btn-language nav-link" data-page="language">Comenzar ahora</a>
                    <a href="#" class="btn btn-outline">Ver ejemplos</a>
                </div>
            </section>
            <section class="topics">
                <div class="container">
                    <div class="section-title">
                        <h2>Temas de Lengua Castellana</h2>
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
                <a href="#" class="back-button nav-link" data-page="home"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Lengua Castellana</h2>
                    <p>Selecciona un área de lengua castellana para practicar</p>
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
                <a href="#" class="back-button nav-link" data-page="language"><i class="fas fa-arrow-left"></i> Volver a Lengua Castellana</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-grammar more-exercises" style="display: none;">Más ejercicios</a>
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
                    <button class="btn btn-grammar check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-grammar next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-grammar more-exercises" style="display: none;">Más ejercicios</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-grammar more-exercises" style="display: none;">Más ejercicios</a>
                </div>
            </div>
        </section>
        <section class="subject-page" id="spelling-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="language"><i class="fas fa-arrow-left"></i> Volver a Lengua Castellana</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-spelling more-exercises" style="display: none;">Más ejercicios</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-spelling more-exercises" style="display: none;">Más ejercicios</a>
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
                    <button class="btn btn-spelling check-answer-btn">Comprobar respuesta</button>
                    <button class="btn btn-spelling next-question-btn" style="display: none; background-color: var(--success-color);">Siguiente ejercicio</button>
                    <div class="exercise-feedback feedback-correct"></div>
                    <div class="exercise-feedback feedback-incorrect"></div>
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-spelling more-exercises" style="display: none;">Más ejercicios</a>
                </div>
            </div>
        </section>
        <section class="subject-page" id="reading-page">
            <div class="container">
                <a href="#" class="back-button nav-link" data-page="language"><i class="fas fa-arrow-left"></i> Volver a Lengua Castellana</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-reading more-exercises" style="display: none;">Más ejercicios</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-reading more-exercises" style="display: none;">Más ejercicios</a>
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
                    <div class="completion-message" style="display: none;"></div>
                    <a href="#" class="btn btn-reading more-exercises" style="display: none;">Más ejercicios</a>
                </div>
            </div>
        </section>
        <section class="subject-page" id="math-page">
            <div class="container">
                <a href="http://practicaejercicios.es/" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Matemáticas</h2>
                    <p>Visita nuestra página de Matemáticas para practicar</p>
                    <a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/" class="btn btn-language">Ir a Matemáticas</a>
                </div>
            </div>
        </section>
        <section class="subject-page" id="science-page">
            <div class="container">
                <a href="http://practicaejercicios.es/" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
                <div class="section-title">
                    <h2>Ciencias</h2>
                    <p>Próximamente: Ejercicios de ciencias</p>
                </div>
            </div>
        </section>
        <section class="subject-page" id="social-page">
            <div class="container">
                <a href="http://practicaejercicios.es/" class="back-button"><i class="fas fa-arrow-left"></i> Volver al inicio</a>
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
                        <li><a href="http://practicaejercicios.es/">Inicio</a></li>
                        <li><a href="#" class="nav-link" data-page="language">Lengua Castellana</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Matem-ticas/">Matemáticas</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias/">Ciencias</a></li>
                        <li><a href="https://ayoubelouardy.github.io/Practicaejercicios-Ciencias-Sociales/">Sociales</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Lengua Castellana</h3>
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
                        <li><i class="fas fa-phone"></i> +34 123 456 789</li>
                        <li><i class="fas fa-map-marker-alt"></i> Barcelona, España</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 PracticaEjercicios.com - Todos los derechos reservados</p>
            </div>
        </div>
    </footer>

    <script>
        let currentExercise = {
            subject: null,
            level: null,
            index: 0
        };

        function showPage(pageId) {
            document.querySelectorAll('.subject-page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(`${pageId}-page`).classList.add('active');
            
            if (['grammar', 'spelling', 'reading'].includes(pageId)) {
                showSubject(pageId);
            }
        }

        function showSubject(subject) {
            showPage(subject);
            const defaultTab = document.querySelector(`#${subject}-page .exercise-tab.active`);
            if (defaultTab) {
                const tabId = defaultTab.dataset.tab;
                showExerciseTab(subject, tabId);
            }
        }

        function showExerciseTab(subject, tabId) {
            const page = document.getElementById(`${subject}-page`);
            page.querySelectorAll('.exercise-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            page.querySelectorAll('.exercise-container').forEach(container => {
                container.classList.remove('active');
            });
            page.querySelector(`[data-tab="${tabId}"]`).classList.add('active');
            const container = page.querySelector(`#${tabId}-exercises`);
            container.classList.add('active');
            
            currentExercise.subject = subject;
            currentExercise.level = tabId.split('-')[1];
            currentExercise.index = 0;
            
            loadExercise();
        }

        function loadExercise() {
            const exercise = exercises[currentExercise.subject][currentExercise.level][currentExercise.index];
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            
            container.querySelector('.exercise-counter').textContent = currentExercise.index + 1;
            
            container.querySelector('.exercise-question').innerHTML = exercise.question;
            
            container.querySelector('.feedback-correct').textContent = exercise.feedbackCorrect;
            container.querySelector('.feedback-incorrect').textContent = exercise.feedbackIncorrect;
            
            const optionsContainer = container.querySelector('.options-container');
            const inputAnswer = container.querySelector('.input-answer');
            
            if (exercise.options) {
                optionsContainer.style.display = 'grid';
                if (inputAnswer) inputAnswer.style.display = 'none';
                
                optionsContainer.innerHTML = exercise.options.map(opt => 
                    `<div class="option" data-correct="${opt.correct}">${opt.text}</div>`
                ).join('');
            } else {
                optionsContainer.style.display = 'none';
                if (inputAnswer) {
                    inputAnswer.style.display = 'block';
                    inputAnswer.value = '';
                }
            }
            
            container.querySelector('.check-answer-btn').style.display = 'block';
            container.querySelector('.next-question-btn').style.display = 'none';
            container.querySelectorAll('.exercise-feedback').forEach(fb => {
                fb.style.display = 'none';
            });
            container.querySelectorAll('.option').forEach(opt => {
                opt.classList.remove('selected', 'correct', 'incorrect');
            });
            
            const completionMessage = container.querySelector('.completion-message');
            if (completionMessage) completionMessage.style.display = 'none';
            const moreExercises = container.querySelector('.more-exercises');
            if (moreExercises) moreExercises.style.display = 'none';
        }

        function checkAnswer() {
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            const exercise = exercises[currentExercise.subject][currentExercise.level][currentExercise.index];
            
            let isCorrect = false;
            
            if (exercise.options) {
                const selectedOption = container.querySelector('.option.selected');
                isCorrect = selectedOption && selectedOption.dataset.correct === 'true';
                
                container.querySelectorAll('.option').forEach(opt => {
                    opt.classList.add(opt.dataset.correct === 'true' ? 'correct' : 'incorrect');
                });
            } else {
                const input = container.querySelector('.input-answer');
                isCorrect = input && input.value.trim() === exercise.answer;
            }
            
            container.querySelector(isCorrect ? '.feedback-correct' : '.feedback-incorrect').style.display = 'block';
            container.querySelector('.check-answer-btn').style.display = 'none';
            container.querySelector('.next-question-btn').style.display = 'block';
            
            userData.completedExercises++;
            userData.totalAnswers++;
            if (isCorrect) userData.correctAnswers++;
            updateUserStats();
        }

        function nextQuestion() {
            currentExercise.index++;
            const container = document.querySelector(`#${currentExercise.subject}-${currentExercise.level}-exercises`);
            const exerciseCount = exercises[currentExercise.subject][currentExercise.level].length;
            
            if (currentExercise.index < exerciseCount) {
                loadExercise();
            } else {
                const completionMessage = container.querySelector('.completion-message');
                if (completionMessage) {
                    completionMessage.innerHTML = `<h3>¡Felicidades!</h3><p>Has completado los ejercicios de ${currentExercise.subject} ${currentExercise.level}.</p>`;
                    completionMessage.style.display = 'block';
                }
                const moreExercises = container.querySelector('.more-exercises');
                if (moreExercises) moreExercises.style.display = 'block';
                
                container.querySelector('.exercise-question').style.display = 'none';
                container.querySelector('.options-container').style.display = 'none';
                if (container.querySelector('.input-answer')) {
                    container.querySelector('.input-answer').style.display = 'none';
                }
                container.querySelector('.check-answer-btn').style.display = 'none';
                container.querySelector('.next-question-btn').style.display = 'none';
            }
        }

        // Event listeners
        document.addEventListener('DOMContentLoaded', () => {
            showPage('home');

            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const page = link.dataset.page;
                    showPage(page);
                });
            });

            document.querySelectorAll('.practice-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    const subject = btn.dataset.subject;
                    showSubject(subject);
                });
            });

            document.querySelectorAll('.exercise-tab').forEach(tab => {
                tab.addEventListener('click', (e) => {
                    e.preventDefault();
                    const subject = tab.closest('.subject-page').id.split('-')[0];
                    const tabId = tab.dataset.tab;
                    showExerciseTab(subject, tabId);
                });
            });

            document.querySelectorAll('.check-answer-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    checkAnswer();
                });
            });

            document.addEventListener('click', (e) => {
                if (e.target.classList.contains('option')) {
                    e.target.closest('.options-container').querySelectorAll('.option').forEach(opt => opt.classList.remove('selected'));
                    e.target.classList.add('selected');
                }
            });

            document.querySelectorAll('.next-question-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    nextQuestion();
                });
            });

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
