<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MOSS - O equilíbrio perfeito entre o urbano e a natureza</title>
    <link rel="icon" href="imagens/favicon.ico" type="image/x-icon">
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
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('imagens/Capturadetela2025-04-24as15.33.45.png') no-repeat center center/cover;
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
        
        .simulation-form .form-group {
            margin-bottom: 1rem;
        }
        
        .simulation-form label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .simulation-form input, 
        .simulation-form select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .value-display {
            display: flex;
            align-items: center;
            margin-bottom: 0.5rem;
        }
        
        .value-display span {
            font-weight: bold;
            margin-right: 10px;
            min-width: 150px;
        }
        
        .percent {
            color: var(--primary-color);
            font-weight: bold;
        }
        
        .calculation-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            padding: 0.8rem;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .total-row {
            background-color: var(--primary-color);
            color: white;
            font-weight: bold;
            margin-top: 1rem;
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
                    <img src="imagens/0003.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0018.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0019.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0020.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0021.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0022.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0023.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0030.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item">
                    <img src="imagens/0031.jpg" alt="Imagem do empreendimento MOSS">
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
                <img src="imagens/0024.jpg" alt="Flat 20m²">
                <div class="feature-content">
                    <h3>Flat 20m²</h3>
                    <p>O espaço ideal para quem busca praticidade sem abrir mão do conforto. Perfeito para solteiros ou casais.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="imagens/0025.jpg" alt="Flat 25m²">
                <div class="feature-content">
                    <h3>Flat 25m²</h3>
                    <p>Um pouco mais espaçoso, com área gourmet e layout inteligente que maximiza o espaço.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="imagens/0026.jpg" alt="Flat 30m²">
                <div class="feature-content">
                    <h3>Flat 30m²</h3>
                    <p>Para quem deseja mais espaço e conforto, com área de lazer integrada e varanda gourmet.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="imagens/0027.jpg" alt="Flat 34m²">
                <div class="feature-content">
                    <h3>Flat 34m²</h3>
                    <p>Nosso modelo mais espaçoso, com dois ambientes distintos e varanda ampla.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="imagens/0028.jpg" alt="Áreas comuns">
                <div class="feature-content">
                    <h3>Áreas Comuns</h3>
                    <p>Espaços de lazer e convivência projetados para seu bem-estar e qualidade de vida.</p>
                </div>
            </div>
            
            <div class="feature-card">
                <img src="imagens/0029.jpg" alt="Vista privilegiada">
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
                <img src="imagens/0011.jpg" alt="Localização do empreendimento MOSS">
            </div>
        </div>
    </section>
    
    <!-- Simulation Section -->
    <section class="simulation" id="simule">
        <div class="simulation-container">
            <h2 class="section-title">Simule seu imóvel</h2>
            <p>Preencha os campos abaixo para simular as condições de aquisição do seu flat no MOSS.</p>
            
            <div class="simulation-form">
                <div class="form-group">
                    <label for="unidade">Selecione a Unidade</label>
                    <select id="unidade">
                        <option value="">Selecione uma unidade</option>
                        <option value="101" data-metragem="34.01" data-valor="475842.41">101 - 34,01 m² - SUL</option>
                        <option value="102" data-metragem="27.28" data-valor="392320.50">102 - 27,28 m² - SUL</option>
                        <option value="103" data-metragem="27.98" data-valor="402387.38">103 - 27,98 m² - SUL</option>
                        <option value="104" data-metragem="32.06" data-valor="461062.88">104 - 32,06 m² - SUL</option>
                        <option value="105" data-metragem="33.58" data-valor="481285.35">105 - 33,58 m² - NASC/SUL</option>
                        <option value="106" data-metragem="24.27" data-valor="354948.75">106 - 24,27 m² - NASCENTE</option>
                        <option value="107" data-metragem="24.65" data-valor="360506.25">107 - 24,65 m² - NASCENTE</option>
                        <option value="108" data-metragem="30.11" data-valor="447698.06">108 - 30,11 m² - NASC/NORTE</option>
                        <option value="201" data-metragem="34.01" data-valor="488043.50">201 - 34,01 m² - SUL</option>
                        <option value="202" data-metragem="27.28" data-valor="402380.00">202 - 27,28 m² - SUL</option>
                        <option value="203" data-metragem="27.98" data-valor="412705.00">203 - 27,98 m² - SUL</option>
                        <option value="204" data-metragem="32.06" data-valor="472885.00">204 - 32,06 m² - SUL</option>
                        <option value="205" data-metragem="33.58" data-valor="493626.00">205 - 33,58 m² - NASC/SUL</option>
                        <option value="206" data-metragem="24.27" data-valor="364050.00">206 - 24,27 m² - NASCENTE</option>
                        <option value="207" data-metragem="24.65" data-valor="369750.00">207 - 24,65 m² - NASCENTE</option>
                        <option value="208" data-metragem="32.84" data-valor="500810.00">208 - 32,84 m² - NASC/NORTE</option>
                        <option value="209" data-metragem="21.06" data-valor="299989.17">209 - 21,06 m² - NORTE</option>
                        <option value="210" data-metragem="21.67" data-valor="302296.50">210 - 21,67 m² - NORTE</option>
                        <option value="211" data-metragem="22.10" data-valor="308295.00">211 - 22,10 m² - NORTE</option>
                        <option value="212" data-metragem="30.27" data-valor="446482.50">212 - 30,27 m² - NORTE</option>
                    </select>
                </div>
                
                <div class="value-display">
                    <span>Valor Total do Imóvel:</span>
                    <span id="valor-imovel">R$ 0,00</span>
                </div>
                
                <div class="form-group">
                    <label for="entrada">Entrada (mínimo 10% do valor do imóvel)</label>
                    <input type="number" id="entrada" placeholder="Digite o valor da entrada">
                    <span id="percentual-entrada" class="percent">0%</span>
                </div>
                
                <div class="value-display">
                    <span>Parcelamento:</span>
                    <span>48x</span>
                </div>
                
                <div class="form-group">
                    <label for="parcela">Valor da Parcela Mensal</label>
                    <input type="number" id="parcela" placeholder="Digite o valor da parcela">
                    <span id="percentual-parcela" class="percent">0%</span>
                </div>
                
                <div class="value-display">
                    <span>Total das Parcelas (48x):</span>
                    <span id="total-parcelas">R$ 0,00</span>
                    <span id="percentual-total-parcelas" class="percent">0%</span>
                </div>
                
                <div class="form-group">
                    <label for="intercalada">Intercaladas</label>
                    <input type="number" id="intercalada" placeholder="Digite o valor das intercaladas">
                    <span id="percentual-intercalada" class="percent">0%</span>
                </div>
                
                <div class="calculation-row">
                    <span>Subtotal antes das chaves:</span>
                    <span id="subtotal">R$ 0,00</span>
                    <span id="percentual-subtotal" class="percent">0%</span>
                </div>
                
                <div class="calculation-row">
                    <span>Chaves:</span>
                    <span id="chaves">R$ 0,00</span>
                    <span id="percentual-chaves" class="percent">0%</span>
                </div>
                
                <div class="calculation-row total-row">
                    <span>Total Financiado:</span>
                    <span id="total-financiado">R$ 0,00</span>
                    <span id="percentual-total" class="percent">0%</span>
                </div>
                
                <div id="aviso-minimo" style="color: red; margin: 1rem 0; display: none;">
                    Atenção: O valor total financiado deve ser no mínimo 47% do valor do imóvel.
                </div>
                
                <button id="enviar-simulacao" class="submit-btn">Enviar Simulação</button>
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
        
        // Simulador de Imóvel
        const unidadeSelect = document.getElementById('unidade');
        const valorImovelDisplay = document.getElementById('valor-imovel');
        const entradaInput = document.getElementById('entrada');
        const percentualEntrada = document.getElementById('percentual-entrada');
        const parcelaInput = document.getElementById('parcela');
        const percentualParcela = document.getElementById('percentual-parcela');
        const totalParcelasDisplay = document.getElementById('total-parcelas');
        const percentualTotalParcelas = document.getElementById('percentual-total-parcelas');
        const intercaladaInput = document.getElementById('intercalada');
        const percentualIntercalada = document.getElementById('percentual-intercalada');
        const subtotalDisplay = document.getElementById('subtotal');
        const percentualSubtotal = document.getElementById('percentual-subtotal');
        const chavesDisplay = document.getElementById('chaves');
        const percentualChaves = document.getElementById('percentual-chaves');
        const totalFinanciadoDisplay = document.getElementById('total-financiado');
        const percentualTotal = document.getElementById('percentual-total');
        const avisoMinimo = document.getElementById('aviso-minimo');
        
        let valorImovel = 0;
        
        // Atualizar quando selecionar a unidade
        unidadeSelect.addEventListener('change', function() {
            const selectedOption = this.options[this.selectedIndex];
            valorImovel = parseFloat(selectedOption.getAttribute('data-valor'));
            valorImovelDisplay.textContent = formatCurrency(valorImovel);
            
            // Limpar outros campos
            entradaInput.value = '';
            parcelaInput.value = '';
            intercaladaInput.value = '';
            updateCalculations();
        });
        
        // Atualizar cálculos quando qualquer valor mudar
        [entradaInput, parcelaInput, intercaladaInput].forEach(input => {
            input.addEventListener('input', updateCalculations);
        });
        
        function updateCalculations() {
            // Obter valores dos inputs
            const entrada = parseFloat(entradaInput.value) || 0;
            const parcela = parseFloat(parcelaInput.value) || 0;
            const intercalada = parseFloat(intercaladaInput.value) || 0;
            
            // Verificar entrada mínima
            const entradaMinima = valorImovel * 0.1;
            if (entrada > 0 && entrada < entradaMinima) {
                alert(`A entrada mínima é de R$ ${formatCurrency(entradaMinima)} (10% do valor do imóvel)`);
                entradaInput.value = '';
                return;
            }
            
            // Calcular totais
            const totalParcelas = parcela * 48;
            const subtotal = entrada + totalParcelas + intercalada;
            const chaves = valorImovel - subtotal;
            const totalFinanciado = subtotal;
            
            // Calcular percentuais
            const percentEntrada = (entrada / valorImovel) * 100;
            const percentParcela = (parcela / valorImovel) * 100;
            const percentTotalParcelas = (totalParcelas / valorImovel) * 100;
            const percentIntercalada = (intercalada / valorImovel) * 100;
            const percentSubtotal = (subtotal / valorImovel) * 100;
            const percentChaves = (chaves / valorImovel) * 100;
            const percentTotal = (totalFinanciado / valorImovel) * 100;
            
            // Atualizar displays
            percentualEntrada.textContent = percentEntrada.toFixed(2) + '%';
            percentualParcela.textContent = percentParcela.toFixed(2) + '%';
            totalParcelasDisplay.textContent = formatCurrency(totalParcelas);
            percentualTotalParcelas.textContent = percentTotalParcelas.toFixed(2) + '%';
            percentualIntercalada.textContent = percentIntercalada.toFixed(2) + '%';
            subtotalDisplay.textContent = formatCurrency(subtotal);
            percentualSubtotal.textContent = percentSubtotal.toFixed(2) + '%';
            chavesDisplay.textContent = formatCurrency(chaves);
            percentualChaves.textContent = percentChaves.toFixed(2) + '%';
            totalFinanciadoDisplay.textContent = formatCurrency(totalFinanciado);
            percentualTotal.textContent = percentTotal.toFixed(2) + '%';
            
            // Verificar mínimo de 47%
            if (percentTotal < 47 && percentTotal > 0) {
                avisoMinimo.style.display = 'block';
            } else {
                avisoMinimo.style.display = 'none';
            }
        }
        
        function formatCurrency(value) {
            return 'R$ ' + value.toFixed(2).replace('.', ',').replace(/(\d)(?=(\d{3})+\,)/g, '$1.');
        }
        
        // Enviar simulação para WhatsApp
        document.getElementById('enviar-simulacao').addEventListener('click', function() {
            if (valorImovel === 0) {
                alert('Por favor, selecione uma unidade primeiro.');
                return;
            }
            
            const unidade = unidadeSelect.options[unidadeSelect.selectedIndex].text;
            const valorImovelText = valorImovelDisplay.textContent;
            const entradaText = 'R$ ' + (entradaInput.value || '0') + ' (' + percentualEntrada.textContent + ')';
            const parcelaText = 'R$ ' + (parcelaInput.value || '0') + ' (' + percentualParcela.textContent + ')';
            const totalParcelasText = totalParcelasDisplay.textContent + ' (' + percentualTotalParcelas.textContent + ')';
            const intercaladaText = 'R$ ' + (intercaladaInput.value || '0') + ' (' + percentualIntercalada.textContent + ')';
            const subtotalText = subtotalDisplay.textContent + ' (' + percentualSubtotal.textContent + ')';
            const chavesText = chavesDisplay.textContent + ' (' + percentualChaves.textContent + ')';
            const totalText = totalFinanciadoDisplay.textContent + ' (' + percentualTotal.textContent + ')';
            
            const message = `Simulação de Imóvel - MOSS\n\n` +
                            `Unidade: ${unidade}\n` +
                            `Valor Total: ${valorImovelText}\n\n` +
                            `Entrada: ${entradaText}\n` +
                            `Parcela: ${parcelaText}\n` +
                            `Total Parcelas (48x): ${totalParcelasText}\n` +
                            `Intercaladas: ${intercaladaText}\n\n` +
                            `Subtotal antes das chaves: ${subtotalText}\n` +
                            `Chaves: ${chavesText}\n\n` +
                            `TOTAL FINANCIADO: ${totalText}\n\n` +
                            `Por favor, entre em contato para mais informações.`;
            
            const whatsappUrl = `https://wa.me/5521980081646?text=${encodeURIComponent(message)}`;
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
