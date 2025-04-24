<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MOSS - O equilíbrio perfeito entre o urbano e a natureza</title>
    <link rel="icon" href="favicon.ico" type="image/x-icon">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary-color: #1E90FF;
            --secondary-color: #FFD700;
            --dark-color: #333;
            --light-color: #f8f9fa;
            --overlay-color: rgba(0, 0, 0, 0.7);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: var(--dark-color);
            overflow-x: hidden;
        }
        
        /* Header */
        header {
            background-color: rgba(255, 255, 255, 0.9);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo svg {
            width: 50px;
            height: 50px;
            margin-right: 10px;
        }
        
        .logo h1 {
            font-size: 1.5rem;
            color: var(--primary-color);
        }
        
        /* Hamburger Menu */
        .hamburger {
            display: none;
            cursor: pointer;
            padding: 10px;
        }
        
        .hamburger div {
            width: 25px;
            height: 3px;
            background-color: var(--primary-color);
            margin: 5px;
            transition: all 0.3s ease;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 2rem;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--dark-color);
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }
        
        .nav-links a:hover {
            color: var(--primary-color);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            bottom: -5px;
            left: 0;
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('Capturadetela2025-04-24as15.33.45.png') no-repeat center center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 0 2rem;
            margin-top: 70px;
        }
        
        .hero-content {
            max-width: 800px;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: fadeIn 1.5s ease;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            animation: fadeIn 2s ease;
        }
        
        .cta-button {
            display: inline-block;
            background-color: var(--secondary-color);
            color: var(--dark-color);
            padding: 0.8rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: fadeIn 2.5s ease;
        }
        
        .cta-button:hover {
            background-color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        /* About Section */
        .about {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }
        
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: var(--primary-color);
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            width: 50%;
            height: 3px;
            background: var(--secondary-color);
            bottom: -10px;
            left: 25%;
        }
        
        .about p {
            font-size: 1.1rem;
            margin-bottom: 2rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }
        
        /* Gallery Section */
        .gallery {
            padding: 5rem 2rem;
            background-color: var(--light-color);
        }
        
        .gallery-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .mosaic {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .mosaic-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            height: 250px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }
        
        .mosaic-item:hover {
            transform: translateY(-10px);
        }
        
        .mosaic-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .mosaic-item:hover img {
            transform: scale(1.1);
        }
        
        /* Features Section */
        .features {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .feature-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
        }
        
        .feature-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .feature-content {
            padding: 1.5rem;
        }
        
        .feature-content h3 {
            margin-bottom: 1rem;
            color: var(--primary-color);
        }
        
        /* Location Section */
        .location {
            padding: 5rem 2rem;
            background-color: var(--light-color);
            text-align: center;
        }
        
        .location-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .location-map {
            margin-top: 3rem;
            height: 400px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .location-map img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        /* Contact Section */
        .contact {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }
        
        .contact-form {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .submit-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 30px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .submit-btn:hover {
            background-color: #187bcd;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .contact-info {
            padding: 2rem;
        }
        
        .contact-info h3 {
            margin-bottom: 1.5rem;
            color: var(--primary-color);
        }
        
        .info-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }
        
        .info-item i {
            margin-right: 1rem;
            color: var(--primary-color);
            font-size: 1.2rem;
        }
        
        .whatsapp-btn {
            display: inline-block;
            background-color: #25D366;
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            text-decoration: none;
            margin-top: 1rem;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .whatsapp-btn:hover {
            background-color: #128C7E;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* Simulation Section */
        .simulation {
            padding: 5rem 2rem;
            background-color: var(--light-color);
        }
        
        .simulation-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .simulation-form {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-top: 3rem;
        }
        
        .form-row {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }
        
        .form-row select {
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .results {
            margin-top: 2rem;
            padding: 1.5rem;
            background-color: #f8f9fa;
            border-radius: 5px;
            display: none;
        }
        
        .results h3 {
            margin-bottom: 1rem;
            color: var(--primary-color);
        }
        
        .results-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }
        
        .results-table th,
        .results-table td {
            padding: 0.8rem;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        
        .results-table th {
            background-color: var(--primary-color);
            color: white;
        }
        
        /* FAQ Section */
        .faq {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .faq-container {
            margin-top: 3rem;
        }
        
        .faq-item {
            margin-bottom: 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .faq-question {
            padding: 1.5rem;
            background-color: white;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 500;
        }
        
        .faq-question:hover {
            background-color: #f8f9fa;
        }
        
        .faq-answer {
            padding: 0 1.5rem;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease, padding 0.3s ease;
            background-color: #f8f9fa;
        }
        
        .faq-item.active .faq-answer {
            max-height: 300px;
            padding: 1.5rem;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 3rem 2rem;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }
        
        .footer-logo svg {
            width: 40px;
            height: 40px;
            margin-right: 10px;
        }
        
        .footer-logo h2 {
            font-size: 1.2rem;
            color: white;
        }
        
        .footer-contact h3,
        .footer-social h3 {
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
        }
        
        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }
        
        .social-links a:hover {
            color: var(--secondary-color);
        }
        
        .copyright {
            text-align: center;
            margin-top: 3rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            position: relative;
        }
        
        .close-modal {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-color);
        }
        
        .modal-icon {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hamburger {
                display: block;
            }
            
            .nav-links {
                position: fixed;
                top: 70px;
                right: -100%;
                width: 70%;
                height: calc(100vh - 70px);
                background-color: white;
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 2rem;
                transition: right 0.3s ease;
                box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .nav-links li {
                margin: 1rem 0;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <div class="logo">
                <svg width="64" height="64" viewBox="0 0 64 64">
                    <circle cx="32" cy="20" r="15" fill="#FFD700"/>
                    <rect x="20" y="25" width="24" height="30" fill="#1E90FF"/>
                    <path d="M10,50 Q32,45 54,50 L54,60 Q32,55 10,60 Z" fill="#87CEEB"/>
                </svg>
                <h1>MOSS</h1>
            </div>
            
            <div class="hamburger">
                <div></div>
                <div></div>
                <div></div>
            </div>
            
            <ul class="nav-links">
                <li><a href="#plantas">Plantas</a></li>
                <li><a href="#simule">Simule seu imóvel</a></li>
                <li><a href="#localizacao">Localização</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </div>
    </header>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>O equilíbrio perfeito entre o urbano e a natureza!</h1>
            <p>O MOSS é a tradução perfeita de sofisticação e visão de futuro. Um empreendimento pensado para quem valoriza localização privilegiada, qualidade de vida e retorno financeiro consistente.</p>
            <a href="#contato" class="cta-button">Fale conosco</a>
        </div>
    </section>
    
    <!-- About Section -->
    <section class="about">
        <h2 class="section-title">Sobre o MOSS</h2>
        <p>O MOSS reúne o melhor da vida urbana com o conforto e tranquilidade da natureza. Um empreendimento exclusivo que oferece flats de 20 a 34 m², perfeitos para quem busca praticidade sem abrir mão do luxo e do conforto.</p>
        <p>Com localização privilegiada e arquitetura moderna, o MOSS é o lugar ideal para investidores e moradores que valorizam qualidade de vida e retorno financeiro.</p>
    </section>
    
    <!-- Gallery Section -->
    <section class="gallery" id="plantas">
        <div class="gallery-container">
            <h2 class="section-title">Conheça o MOSS</h2>
            <div class="mosaic">
                <div class="mosaic-item">
                    <img src="0003.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0018.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0019.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0020.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0021.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0022.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0023.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0030.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="0031.jpg" alt="Imagem do empreendimento MOSS">
                </div>
            </div>
        </div>
    </section>
    
    <!-- Features Section -->
    <section class="features">
        <h2 class="section-title">Nossos Flats</h2>
        <p>Conheça nossos modelos de flats, perfeitos para quem busca praticidade e sofisticação.</p>
        
        <div class="features-grid">
            <div class="feature-card">
                <img src="0024.jpg" alt="Flat 20m²">
                <div class="feature-content">
                    <h3>Flat 20m²</h3>
                    <p>O espaço ideal para quem busca praticidade sem abrir mão do conforto. Perfeito para solteiros ou casais.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="0025.jpg" alt="Flat 25m²">
                <div class="feature-content">
                    <h3>Flat 25m²</h3>
                    <p>Um pouco mais espaçoso, com área gourmet e layout inteligente que maximiza o espaço.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="0026.jpg" alt="Flat 30m²">
                <div class="feature-content">
                    <h3>Flat 30m²</h3>
                    <p>Para quem deseja mais espaço e conforto, com área de lazer integrada e varanda gourmet.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="0027.jpg" alt="Flat 34m²">
                <div class="feature-content">
                    <h3>Flat 34m²</h3>
                    <p>Nosso modelo mais espaçoso, com dois ambientes distintos e varanda ampla.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="0028.jpg" alt="Áreas comuns">
                <div class="feature-content">
                    <h3>Áreas Comuns</h3>
                    <p>Espaços de lazer e convivência projetados para seu bem-estar e qualidade de vida.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="0029.jpg" alt="Vista privilegiada">
                <div class="feature-content">
                    <h3>Vista Privilegiada</h3>
                    <p>Aproveite vistas incríveis da cidade e do mar em alguns de nossos flats.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Location Section -->
    <section class="location" id="localizacao">
        <div class="location-container">
            <h2 class="section-title">Localização Privilegiada</h2>
            <p>O MOSS está situado em uma das áreas mais valorizadas da cidade, com fácil acesso a todas as regiões e próximo aos principais pontos de interesse.</p>
            
            <div class="location-map">
                <img src="0011.jpg" alt="Localização do empreendimento MOSS">
            </div>
        </div>
    </section>
    
    <!-- Simulation Section -->
    <section class="simulation" id="simule">
        <div class="simulation-container">
            <h2 class="section-title">Simule seu imóvel</h2>
            <p>Preencha os campos abaixo para simular as condições de aquisição do seu flat no MOSS.</p>
            
            <div class="simulation-form">
                <div class="form-row">
                    <div class="form-group">
                        <label for="unidade">Unidade</label>
                        <select id="unidade">
                            <option value="">Selecione uma unidade</option>
                            <option value="101">101 - 34,01 m² - SUL</option>
                            <option value="102">102 - 27,28 m² - SUL</option>
                            <option value="103">103 - 27,98 m² - SUL</option>
                            <option value="104">104 - 32,06 m² - SUL</option>
                            <option value="105">105 - 33,58 m² - NASC/SUL</option>
                            <option value="106">106 - 24,27 m² - NASCENTE</option>
                            <option value="107">107 - 24,65 m² - NASCENTE</option>
                            <option value="108">108 - 30,11 m² - NASC/NORTE</option>
                            <option value="201">201 - 34,01 m² - SUL</option>
                            <option value="202">202 - 27,28 m² - SUL</option>
                            <option value="203">203 - 27,98 m² - SUL</option>
                            <option value="204">204 - 32,06 m² - SUL</option>
                            <option value="205">205 - 33,58 m² - NASC/SUL</option>
                            <option value="206">206 - 24,27 m² - NASCENTE</option>
                            <option value="207">207 - 24,65 m² - NASCENTE</option>
                            <option value="208">208 - 32,84 m² - NASC/NORTE</option>
                            <option value="209">209 - 21,06 m² - NORTE</option>
                            <option value="210">210 - 21,67 m² - NORTE</option>
                            <option value="211">211 - 22,10 m² - NORTE</option>
                            <option value="212">212 - 30,27 m² - NORTE</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="metragem">Metragem</label>
                        <select id="metragem">
                            <option value="">Selecione a metragem</option>
                            <option value="20-25">20 a 25 m²</option>
                            <option value="26-34">26 a 34 m²</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="entrada">Valor de Entrada (mínimo 10%)</label>
                        <input type="number" id="entrada" placeholder="Digite o valor da entrada">
                    </div>
                    
                    <div class="form-group">
                        <label for="parcelas">Número de Parcelas (até 48x)</label>
                        <select id="parcelas">
                            <option value="12">12x</option>
                            <option value="24">24x</option>
                            <option value="36">36x</option>
                            <option value="48">48x</option>
                        </select>
                    </div>
                </div>
                
                <button id="calcular" class="submit-btn">Calcular</button>
                
                <div class="results" id="results">
                    <h3>Resultado da Simulação</h3>
                    <table class="results-table">
                        <thead>
                            <tr>
                                <th>Descrição</th>
                                <th>Valor</th>
                            </tr>
                        </thead>
                        <tbody id="results-body">
                            <!-- Os resultados serão inseridos aqui via JavaScript -->
                        </tbody>
                    </table>
                    
                    <button id="enviar-simulacao" class="submit-btn" style="margin-top: 1rem;">Enviar Simulação</button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- FAQ Section -->
    <section class="faq">
        <h2 class="section-title">Perguntas Frequentes</h2>
        
        <div class="faq-container">
            <div class="faq-item">
                <div class="faq-question">
                    <span>Quais são as formas de pagamento?</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Oferecemos diversas opções de pagamento, incluindo financiamento bancário, parcelamento direto com a construtora em até 48 vezes, e pagamento à vista com desconto. Entre em contato para saber mais sobre as condições especiais.</p>
                </div>
            </div>
            
            <div class="faq-item">
                <div class="faq-question">
                    <span>Qual o prazo de entrega do empreendimento?</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>A previsão de entrega do MOSS é para o segundo semestre de 2026. Todos os apartamentos serão entregues com acabamento de alto padrão, conforme especificado no memorial descritivo.</p>
                </div>
            </div>
            
            <div class="faq-item">
                <div class="faq-question">
                    <span>Quais documentos são necessários para a compra?</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Para a compra, são necessários: RG, CPF, comprovante de residência, comprovante de renda e, no caso de financiamento, documentos específicos solicitados pelo banco. Nossa equipe está à disposição para orientá-lo sobre todo o processo.</p>
                </div>
            </div>
            
            <div class="faq-item">
                <div class="faq-question">
                    <span>O empreendimento possui áreas comuns?</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Sim, o MOSS conta com diversas áreas comuns de lazer, incluindo piscina, espaço gourmet, fitness, salão de festas e espaço coworking. Todas as áreas foram projetadas para proporcionar conforto e bem-estar aos moradores.</p>
                </div>
            </div>
            
            <div class="faq-item">
                <div class="faq-question">
                    <span>É possível personalizar o acabamento do apartamento?</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Sim, oferecemos opções de personalização de acabamento para atender às preferências de cada cliente. Consulte nossa equipe comercial para conhecer as opções disponíveis e os valores adicionais.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section class="contact" id="contato">
        <h2 class="section-title">Entre em Contato</h2>
        
        <div class="contact-container">
            <div class="contact-form">
                <form id="form-contato">
                    <div class="form-group">
                        <label for="nome">Nome</label>
                        <input type="text" id="nome" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">E-mail</label>
                        <input type="email" id="email" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="telefone">Telefone</label>
                        <input type="tel" id="telefone" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="mensagem">Mensagem</label>
                        <textarea id="mensagem" maxlength="5000" required></textarea>
                    </div>
                    
                    <button type="submit" class="submit-btn">Enviar Mensagem</button>
                </form>
            </div>
            
            <div class="contact-info">
                <h3>Informações de Contato</h3>
                
                <div class="info-item">
                    <i class="fas fa-phone"></i>
                    <span>(21) 98008-1646</span>
                </div>
                
                <div class="info-item">
                    <i class="fas fa-envelope"></i>
                    <span>contato@mossjoaopessoa.com</span>
                </div>
                
                <div class="info-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <span>Avenida Cabo Branco, João Pessoa/PB</span>
                </div>
                
                <a href="https://wa.me/5521980081646" class="whatsapp-btn" target="_blank">
                    <i class="fab fa-whatsapp"></i> Fale pelo WhatsApp
                </a>
                
                <div class="social-links" style="margin-top: 2rem;">
                    <a href="https://www.instagram.com/joaopessoa.invistaimoveis/" target="_blank">
                        <i class="fab fa-instagram"></i>
                    </a>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div>
                <div class="footer-logo">
                    <svg width="64" height="64" viewBox="0 0 64 64">
                        <circle cx="32" cy="20" r="15" fill="#FFD700"/>
                        <rect x="20" y="25" width="24" height="30" fill="#1E90FF"/>
                        <path d="M10,50 Q32,45 54,50 L54,60 Q32,55 10,60 Z" fill="#87CEEB"/>
                    </svg>
                    <h2>MOSS</h2>
                </div>
                <p>O equilíbrio perfeito entre o urbano e a natureza.</p>
            </div>
            
            <div class="footer-contact">
                <h3>Contato</h3>
                <p>(21) 98008-1646</p>
                <p>Avenida Cabo Branco, João Pessoa/PB</p>
            </div>
            
            <div class="footer-social">
                <h3>Redes Sociais</h3>
                <div class="social-links">
                    <a href="https://www.instagram.com/joaopessoa.invistaimoveis/" target="_blank">
                        <i class="fab fa-instagram"></i>
                    </a>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2025 Imóveis João Pessoa Oficial. Todos os direitos reservados.</p>
        </div>
    </footer>
    
    <!-- Modal -->
    <div class="modal" id="modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <div class="modal-icon">
                <i class="fas fa-check-circle"></i>
            </div>
            <h3>Enviado com sucesso!</h3>
            <p>Sua mensagem foi enviada com sucesso. Entraremos em contato em breve.</p>
        </div>
    </div>
    
    <script>
        // Menu Hamburguer
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });
        
        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                if (navLinks.classList.contains('active')) {
                    navLinks.classList.remove('active');
                    hamburger.classList.remove('active');
                }
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 70,
                    behavior: 'smooth'
                });
            });
        });
        
        // FAQ Accordion
        const faqQuestions = document.querySelectorAll('.faq-question');
        
        faqQuestions.forEach(question => {
            question.addEventListener('click', () => {
                const item = question.parentNode;
                item.classList.toggle('active');
                
                const icon = question.querySelector('i');
                if (item.classList.contains('active')) {
                    icon.classList.remove('fa-chevron-down');
                    icon.classList.add('fa-chevron-up');
                } else {
                    icon.classList.remove('fa-chevron-up');
                    icon.classList.add('fa-chevron-down');
                }
            });
        });
        
        // Simulation Calculator
        const calcularBtn = document.getElementById('calcular');
        const enviarSimulacaoBtn = document.getElementById('enviar-simulacao');
        const results = document.getElementById('results');
        const resultsBody = document.getElementById('results-body');
        
        calcularBtn.addEventListener('click', () => {
            const unidade = document.getElementById('unidade').value;
            const metragem = document.getElementById('metragem').value;
            const entrada = parseFloat(document.getElementById('entrada').value);
            const parcelas = parseInt(document.getElementById('parcelas').value);
            
            if (!unidade || !metragem || isNaN(entrada) || isNaN(parcelas)) {
                alert('Por favor, preencha todos os campos corretamente.');
                return;
            }
            
            // Encontrar os dados da unidade selecionada
            let valorImovel, mensalidade, intercalada;
            
            if (metragem === '20-25') {
                mensalidade = 1400;
                intercalada = 8000;
                
                // Ajustar valores conforme a unidade selecionada
                if (unidade === '101' || unidade === '201' || unidade === '301') {
                    valorImovel = 475842.41;
                } else if (unidade === '102' || unidade === '202' || unidade === '302') {
                    valorImovel = 392320.50;
                } else if (unidade === '103' || unidade === '203' || unidade === '303') {
                    valorImovel = 402387.38;
                } else if (unidade === '104' || unidade === '204' || unidade === '304') {
                    valorImovel = 461062.88;
                } else if (unidade === '105' || unidade === '205' || unidade === '305') {
                    valorImovel = 481285.35;
                } else if (unidade === '106' || unidade === '206' || unidade === '306') {
                    valorImovel = 354948.75;
                } else if (unidade === '107' || unidade === '207' || unidade === '307') {
                    valorImovel = 360506.25;
                } else if (unidade === '108' || unidade === '208' || unidade === '308') {
                    valorImovel = 447698.06;
                } else if (unidade === '209') {
                    valorImovel = 299989.17;
                } else if (unidade === '210' || unidade === '211') {
                    valorImovel = 302296.50;
                } else if (unidade === '212') {
                    valorImovel = 446482.50;
                }
            } else {
                mensalidade = 2000;
                intercalada = 10000;
                
                // Ajustar valores conforme a unidade selecionada
                if (unidade === '101' || unidade === '201' || unidade === '301') {
                    valorImovel = 475842.41;
                } else if (unidade === '102' || unidade === '202' || unidade === '302') {
                    valorImovel = 392320.50;
                } else if (unidade === '103' || unidade === '203' || unidade === '303') {
                    valorImovel = 402387.38;
                } else if (unidade === '104' || unidade === '204' || unidade === '304') {
                    valorImovel = 461062.88;
                } else if (unidade === '105' || unidade === '205' || unidade === '305') {
                    valorImovel = 481285.35;
                } else if (unidade === '106' || unidade === '206' || unidade === '306') {
                    valorImovel = 354948.75;
                } else if (unidade === '107' || unidade === '207' || unidade === '307') {
                    valorImovel = 360506.25;
                } else if (unidade === '108' || unidade === '208' || unidade === '308') {
                    valorImovel = 447698.06;
                } else if (unidade === '209') {
                    valorImovel = 299989.17;
                } else if (unidade === '210' || unidade === '211') {
                    valorImovel = 302296.50;
                } else if (unidade === '212') {
                    valorImovel = 446482.50;
                }
            }
            
            // Verificar se a entrada é pelo menos 10% do valor do imóvel
            const entradaMinima = valorImovel * 0.1;
            
            if (entrada < entradaMinima) {
                alert(`O valor mínimo de entrada é R$ ${entradaMinima.toFixed(2)} (10% do valor do imóvel)`);
                return;
            }
            
            // Calcular valores
            const totalParcelas = mensalidade * parcelas;
            const totalPago = entrada + totalParcelas + intercalada;
            const percentualPago = (totalPago / valorImovel) * 100;
            const saldoDevedor = valorImovel - totalPago;
            
            // Verificar se o percentual pago é pelo menos 47%
            if (percentualPago < 47) {
                alert(`O valor total pago deve ser pelo menos 47% do valor do imóvel. Atualmente é ${percentualPago.toFixed(2)}%. Aumente a entrada ou o número de parcelas.`);
                return;
            }
            
            // Exibir resultados
            resultsBody.innerHTML = `
                <tr>
                    <td>Valor do Imóvel</td>
                    <td>R$ ${valorImovel.toFixed(2)}</td>
                </tr>
                <tr>
                    <td>Entrada</td>
                    <td>R$ ${entrada.toFixed(2)} (${((entrada / valorImovel) * 100).toFixed(2)}%)</td>
                </tr>
                <tr>
                    <td>Mensalidade (${parcelas}x)</td>
                    <td>R$ ${mensalidade.toFixed(2)} (Total: R$ ${totalParcelas.toFixed(2)})</td>
                </tr>
                <tr>
                    <td>Intercaladas (8x)</td>
                    <td>R$ ${intercalada.toFixed(2)}</td>
                </tr>
                <tr>
                    <td>Total Pago</td>
                    <td>R$ ${totalPago.toFixed(2)} (${percentualPago.toFixed(2)}%)</td>
                </tr>
                <tr>
                    <td>Saldo Devedor</td>
                    <td>R$ ${saldoDevedor.toFixed(2)}</td>
                </tr>
            `;
            
            results.style.display = 'block';
        });
        
        enviarSimulacaoBtn.addEventListener('click', () => {
            const unidade = document.getElementById('unidade');
            const unidadeText = unidade.options[unidade.selectedIndex].text;
            const resultsText = resultsBody.innerText;
            
            const whatsappUrl = `https://wa.me/5521980081646?text=Olá,%20gostaria%20de%20mais%20informações%20sobre%20a%20simulação%20realizada:%0A%0AUnidade:%20${encodeURIComponent(unidadeText)}%0A%0A${encodeURIComponent(resultsText)}`;
            
            window.open(whatsappUrl, '_blank');
            
            // Mostrar modal de sucesso
            document.getElementById('modal').style.display = 'flex';
        });
        
        // Formulário de Contato
        const formContato = document.getElementById('form-contato');
        
        formContato.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const nome = document.getElementById('nome').value;
            const email = document.getElementById('email').value;
            const telefone = document.getElementById('telefone').value;
            const mensagem = document.getElementById('mensagem').value;
            
            const whatsappUrl = `https://wa.me/5521980081646?text=Olá,%20meu%20nome%20é%20${encodeURIComponent(nome)}.%20Gostaria%20de%20mais%20informações%20sobre%20o%20MOSS.%0A%0AE-mail:%20${encodeURIComponent(email)}%0ATelefone:%20${encodeURIComponent(telefone)}%0A%0AMensagem:%20${encodeURIComponent(mensagem)}`;
            
            window.open(whatsappUrl, '_blank');
            
            // Mostrar modal de sucesso
            document.getElementById('modal').style.display = 'flex';
            
            // Limpar formulário
            formContato.reset();
        });
        
        // Fechar Modal
        const modal = document.getElementById('modal');
        const closeModal = document.querySelector('.close-modal');
        
        closeModal.addEventListener('click', () => {
            modal.style.display = 'none';
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === modal) {
                modal.style.display = 'none';
            }
        });
        
        // Atualizar header ao rolar
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                document.querySelector('header').style.background = 'rgba(255, 255, 255, 0.98)';
                document.querySelector('header').style.boxShadow = '0 2px 15px rgba(0, 0, 0, 0.1)';
            } else {
                document.querySelector('header').style.background = 'rgba(255, 255, 255, 0.9)';
                document.querySelector('header').style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            }
        });
    </script>
</body>
</html>
