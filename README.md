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
            background-image: url('imagens/0036.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-repeat: no-repeat;
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
        
        /* Menu Hamburguer - Ajustado para desktop */
        .hamburger {
            display: block;
            cursor: pointer;
            padding: 10px;
            z-index: 1001;
        }
        
        .hamburger div {
            width: 25px;
            height: 3px;
            background-color: var(--primary-color);
            margin: 5px;
            transition: all 0.3s ease;
        }
        
        .nav-links {
            position: fixed;
            top: 0;
            right: -100%;
            width: 300px;
            height: 100vh;
            background: url('imagens/0017.jpg') no-repeat center center/cover;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding-top: 2rem;
            transition: right 0.3s ease;
            box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
            list-style: none;
            z-index: 1000;
        }
        
        .nav-links::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: -1;
        }
        
        .nav-links.active {
            right: 0;
        }
        
        .nav-links li {
            margin: 1.5rem 0;
        }
        
        .nav-links a {
            text-decoration: none;
            color: white;
            font-weight: 500;
            font-size: 1.2rem;
            transition: color 0.3s ease;
            position: relative;
        }
        
        .nav-links a:hover {
            color: var(--secondary-color);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--secondary-color);
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
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 0 2rem;
            margin-top: 70px;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 0;
        }
        
        .hero-content {
            max-width: 800px;
            position: relative;
            z-index: 1;
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
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            margin-bottom: 2rem;
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
            background-color: rgba(248, 249, 250, 0.9);
            margin-bottom: 2rem;
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
            cursor: pointer;
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
        
        .load-more {
            display: block;
            margin: 2rem auto 0;
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 30px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .load-more:hover {
            background-color: #187bcd;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* Modal de Imagem */
        .image-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .image-modal-content {
            position: relative;
            max-width: 90%;
            max-height: 90%;
        }
        
        .image-modal-content img {
            max-width: 100%;
            max-height: 90vh;
            display: block;
            margin: 0 auto;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 35px;
            color: white;
            font-size: 40px;
            font-weight: bold;
            cursor: pointer;
            z-index: 2001;
        }
        
        /* Features Section */
        .features {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            margin-bottom: 2rem;
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
            background-color: rgba(248, 249, 250, 0.9);
            text-align: center;
            margin-bottom: 2rem;
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
        
        /* Simulation Section */
        .simulation {
            padding: 5rem 2rem;
            background-color: rgba(248, 249, 250, 0.9);
            margin-bottom: 2rem;
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
        
        .status-disponivel {
            color: green;
            font-weight: bold;
        }
        
        .status-reservado {
            color: orange;
            font-weight: bold;
        }
        
        /* FAQ Section */
        .faq {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            margin-bottom: 2rem;
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
        
        /* Contact Section */
        .contact {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            margin-bottom: 2rem;
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
        
        .modal-icon {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }
        
        /* Media Queries */
        @media (min-width: 992px) {
            .hamburger {
                display: none;
            }
            
            .nav-links {
                position: static;
                width: auto;
                height: auto;
                background: transparent;
                display: flex;
                flex-direction: row;
                padding-top: 0;
                box-shadow: none;
            }
            
            .nav-links::before {
                display: none;
            }
            
            .nav-links li {
                margin: 0 1rem;
            }
            
            .nav-links a {
                color: var(--dark-color);
            }
            
            .nav-links a:hover {
                color: var(--primary-color);
            }
            
            .nav-links a::after {
                background: var(--primary-color);
            }
        }
        
        @media (max-width: 768px) {
            .header-container {
                padding: 1rem;
            }
            
            .logo h1 {
                font-size: 1.2rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
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
                <!-- Primeiras 9 imagens visíveis inicialmente -->
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
                <!-- Imagens adicionais que serão carregadas com o botão "Veja mais" -->
                <div class="mosaic-item" style="display: none;">
                    <img src="imagens/0032.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item" style="display: none;">
                    <img src="imagens/0033.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item" style="display: none;">
                    <img src="imagens/0034.jpg" alt="Imagem do empreendimento MOSS">
                </div>
                <div class="mosaic-item" style="display: none;">
                    <img src="imagens/0035.jpg" alt="Imagem do empreendimento MOSS">
                </div>
            </div>
            <button class="load-more">Veja mais</button>
        </div>
    </section>
    
    <!-- Modal de Imagem -->
    <div id="imageModal" class="image-modal">
        <span class="close-modal">&times;</span>
        <div class="image-modal-content">
            <img id="expandedImg" src="" alt="Imagem expandida">
        </div>
    </div>
    
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
                        <!-- 1º PAVIMENTO -->
                        <option value="101" data-metragem="34.01" data-valor="475842.41" data-entrada="71376.36" data-parcela="2478.35" data-intercalada="11896.06" data-status="disponivel">101 - 34,01 m² - SUL - R$ 475.842,41</option>
                        <option value="102" data-metragem="27.28" data-valor="392320.50" data-entrada="58848.08" data-parcela="2043.34" data-intercalada="9808.01" data-status="disponivel">102 - 27,28 m² - SUL - R$ 392.320,50</option>
                        <option value="103" data-metragem="27.98" data-valor="402387.38" data-entrada="60358.11" data-parcela="2095.77" data-intercalada="10059.68" data-status="disponivel">103 - 27,98 m² - SUL - R$ 402.387,38</option>
                        <option value="104" data-metragem="32.06" data-valor="461062.88" data-entrada="69159.43" data-parcela="2401.37" data-intercalada="11526.57" data-status="disponivel">104 - 32,06 m² - SUL - R$ 461.062,88</option>
                        <option value="105" data-metragem="33.58" data-valor="481285.35" data-entrada="72192.80" data-parcela="2506.69" data-intercalada="12032.13" data-status="disponivel">105 - 33,58 m² - NASC/SUL - R$ 481.285,35</option>
                        <option value="106" data-metragem="24.27" data-valor="354948.75" data-entrada="53242.31" data-parcela="1848.69" data-intercalada="8873.72" data-status="disponivel">106 - 24,27 m² - NASCENTE - R$ 354.948,75</option>
                        <option value="107" data-metragem="24.65" data-valor="360506.25" data-entrada="54075.94" data-parcela="1877.64" data-intercalada="9012.66" data-status="disponivel">107 - 24,65 m² - NASCENTE - R$ 360.506,25</option>
                        <option value="108" data-metragem="30.11" data-valor="447698.06" data-entrada="67154.71" data-parcela="2331.76" data-intercalada="11192.45" data-status="disponivel">108 - 30,11 m² - NASC/NORTE - R$ 447.698,06</option>
                        
                        <!-- 2º PAVIMENTO -->
                        <option value="201" data-metragem="34.01" data-valor="488043.50" data-entrada="73206.53" data-parcela="2541.89" data-intercalada="12201.09" data-status="disponivel">201 - 34,01 m² - SUL - R$ 488.043,50</option>
                        <option value="202" data-metragem="27.28" data-valor="402380.00" data-entrada="60357.00" data-parcela="2095.73" data-intercalada="10059.50" data-status="disponivel">202 - 27,28 m² - SUL - R$ 402.380,00</option>
                        <option value="203" data-metragem="27.98" data-valor="412705.00" data-entrada="61905.75" data-parcela="2149.51" data-intercalada="10317.63" data-status="disponivel">203 - 27,98 m² - SUL - R$ 412.705,00</option>
                        <option value="204" data-metragem="32.06" data-valor="472885.00" data-entrada="70932.75" data-parcela="2462.94" data-intercalada="11822.13" data-status="disponivel">204 - 32,06 m² - SUL - R$ 472.885,00</option>
                        <option value="205" data-metragem="33.58" data-valor="493626.00" data-entrada="74043.90" data-parcela="2570.97" data-intercalada="12340.65" data-status="disponivel">205 - 33,58 m² - NASC/SUL - R$ 493.626,00</option>
                        <option value="206" data-metragem="24.27" data-valor="364050.00" data-entrada="54607.50" data-parcela="1896.09" data-intercalada="9101.25" data-status="reservado">206 - 24,27 m² - NASCENTE - R$ 364.050,00 (RESERVADO)</option>
                        <option value="207" data-metragem="24.65" data-valor="369750.00" data-entrada="55462.50" data-parcela="1925.78" data-intercalada="9243.75" data-status="disponivel">207 - 24,65 m² - NASCENTE - R$ 369.750,00</option>
                        <option value="208" data-metragem="32.84" data-valor="500810.00" data-entrada="75121.50" data-parcela="2608.39" data-intercalada="12520.25" data-status="disponivel">208 - 32,84 m² - NASC/NORTE - R$ 500.810,00</option>
                        <option value="209" data-metragem="21.06" data-valor="299989.17" data-entrada="44998.38" data-parcela="1562.44" data-intercalada="7499.73" data-status="reservado">209 - 21,06 m² - NORTE - R$ 299.989,17 (RESERVADO)</option>
                        <option value="210" data-metragem="21.67" data-valor="302296.50" data-entrada="45344.48" data-parcela="1574.46" data-intercalada="7557.41" data-status="disponivel">210 - 21,67 m² - NORTE - R$ 302.296,50</option>
                        <option value="211" data-metragem="22.10" data-valor="308295.00" data-entrada="46244.25" data-parcela="1605.70" data-intercalada="7707.38" data-status="disponivel">211 - 22,10 m² - NORTE - R$ 308.295,00</option>
                        <option value="212" data-metragem="30.27" data-valor="446482.50" data-entrada="66972.38" data-parcela="2325.43" data-intercalada="11162.06" data-status="disponivel">212 - 30,27 m² - NORTE - R$ 446.482,50</option>
                        
                        <!-- 3º PAVIMENTO -->
                        <option value="301" data-metragem="34.01" data-valor="500244.59" data-entrada="75036.69" data-parcela="2605.44" data-intercalada="12506.11" data-status="disponivel">301 - 34,01 m² - SUL - R$ 500.244,59</option>
                        <option value="302" data-metragem="27.28" data-valor="412439.50" data-entrada="61865.93" data-parcela="2148.12" data-intercalada="10310.99" data-status="disponivel">302 - 27,28 m² - SUL - R$ 412.439,50</option>
                        <option value="303" data-metragem="27.98" data-valor="423022.63" data-entrada="63453.39" data-parcela="2203.24" data-intercalada="10575.57" data-status="disponivel">303 - 27,98 m² - SUL - R$ 423.022,63</option>
                        <option value="304" data-metragem="32.06" data-valor="482342.70" data-entrada="72351.41" data-parcela="2512.20" data-intercalada="12058.57" data-status="disponivel">304 - 32,06 m² - SUL - R$ 482.342,70</option>
                        <option value="305" data-metragem="33.58" data-valor="505966.65" data-entrada="75895.00" data-parcela="2635.24" data-intercalada="12649.17" data-status="disponivel">305 - 33,58 m² - NASC/SUL - R$ 505.966,65</option>
                        <option value="306" data-metragem="24.27" data-valor="373151.25" data-entrada="55972.69" data-parcela="1943.50" data-intercalada="9328.78" data-status="disponivel">306 - 24,27 m² - NASCENTE - R$ 373.151,25</option>
                        <option value="307" data-metragem="24.65" data-valor="378993.75" data-entrada="56849.06" data-parcela="1973.93" data-intercalada="9474.84" data-status="disponivel">307 - 24,65 m² - NASCENTE - R$ 378.993,75</option>
                        
                        <!-- 4º PAVIMENTO -->
                        <option value="401" data-metragem="34.98" data-valor="527374.88" data-entrada="79106.23" data-parcela="2746.74" data-intercalada="13184.37" data-status="disponivel">401 - 34,98 m² - SUL - R$ 527.374,88</option>
                        <option value="402" data-metragem="23.05" data-valor="357199.37" data-entrada="53579.91" data-parcela="1860.41" data-intercalada="8929.98" data-status="disponivel">402 - 23,05 m² - SUL - R$ 357.199,37</option>
                        <option value="403" data-metragem="23.62" data-valor="366032.50" data-entrada="54904.87" data-parcela="1906.42" data-intercalada="9150.81" data-status="disponivel">403 - 23,62 m² - SUL - R$ 366.032,50</option>
                        <option value="404" data-metragem="37.67" data-valor="565045.48" data-entrada="84756.82" data-parcela="2942.95" data-intercalada="14126.14" data-status="disponivel">404 - 37,67 m² - NASC/SUL - R$ 565.045,48</option>
                        <option value="405" data-metragem="41.95" data-valor="623028.29" data-entrada="93454.24" data-parcela="3244.94" data-intercalada="15575.71" data-status="disponivel">405 - 41,95 m² - NASCENTE - R$ 623.028,29</option>
                        <option value="406" data-metragem="34.13" data-valor="546831.93" data-entrada="82024.79" data-parcela="2848.08" data-intercalada="13670.80" data-status="disponivel">406 - 34,13 m² - NASC/NORTE - R$ 546.831,93</option>
                        <option value="407" data-metragem="20.68" data-valor="340060.89" data-entrada="51009.13" data-parcela="1771.15" data-intercalada="8501.52" data-status="disponivel">407 - 20,68 m² - NORTE - R$ 340.060,89</option>
                        <option value="408" data-metragem="21.19" data-valor="348447.30" data-entrada="52267.10" data-parcela="1814.83" data-intercalada="8711.18" data-status="disponivel">408 - 21,19 m² - NORTE - R$ 348.447,30</option>
                        <option value="409" data-metragem="34.17" data-valor="526427.27" data-entrada="78964.09" data-parcela="2741.81" data-intercalada="13160.68" data-status="disponivel">409 - 34,17 m² - NORTE - R$ 526.427,27</option>
                        
                        <!-- 8º PAVIMENTO -->
                        <option value="801" data-metragem="26.46" data-valor="452166.10" data-entrada="67824.91" data-parcela="2355.03" data-intercalada="11304.15" data-status="disponivel">801 - 26,46 m² - SUL - R$ 452.166,10</option>
                        <option value="802" data-metragem="20.21" data-valor="355055.04" data-entrada="53258.26" data-parcela="1849.25" data-intercalada="8876.38" data-status="reservado">802 - 20,21 m² - SUL - R$ 355.055,04 (RESERVADO)</option>
                        <option value="803" data-metragem="20.78" data-valor="365068.96" data-entrada="54760.34" data-parcela="1901.40" data-intercalada="9126.72" data-status="disponivel">803 - 20,78 m² - SUL - R$ 365.068,96</option>
                        <option value="804" data-metragem="26.55" data-valor="464884.98" data-entrada="69732.75" data-parcela="2421.28" data-intercalada="11622.12" data-status="disponivel">804 - 26,55 m² - NASC/SUL - R$ 464.884,98</option>
                        <option value="805" data-metragem="18.21" data-valor="305876.78" data-entrada="45881.52" data-parcela="1593.11" data-intercalada="7646.92" data-status="disponivel">805 - 18,21 m² - NASCENTE - R$ 305.876,78</option>
                        <option value="806" data-metragem="18.59" data-valor="328694.44" data-entrada="49304.17" data-parcela="1711.95" data-intercalada="8217.36" data-status="disponivel">806 - 18,59 m² - NASCENTE - R$ 328.694,44</option>
                        <option value="807" data-metragem="27.34" data-valor="506241.54" data-entrada="75936.23" data-parcela="2636.67" data-intercalada="12656.04" data-status="disponivel">807 - 27,34 m² - NASC/NORTE - R$ 506.241,54</option>
                        <option value="808" data-metragem="20.68" data-valor="386466.48" data-entrada="57969.97" data-parcela="2012.85" data-intercalada="9661.66" data-status="disponivel">808 - 20,68 m² - NORTE - R$ 386.466,48</option>
                        <option value="809" data-metragem="21.19" data-valor="395997.33" data-entrada="59399.60" data-parcela="2062.49" data-intercalada="9899.93" data-status="disponivel">809 - 21,19 m² - NORTE - R$ 395.997,33</option>
                        <option value="810" data-metragem="28.49" data-valor="490034.66" data-entrada="73505.20" data-parcela="2552.26" data-intercalada="12250.87" data-status="disponivel">810 - 28,49 m² - NORTE - R$ 490.034,66</option>
                        
                        <!-- 9º PAVIMENTO -->
                        <option value="901" data-metragem="26.46" data-valor="474774.40" data-entrada="71216.16" data-parcela="2472.78" data-intercalada="11869.36" data-status="disponivel">901 - 26,46 m² - SUL - R$ 474.774,40</option>
                        <option value="902" data-metragem="20.21" data-valor="372807.79" data-entrada="55921.17" data-parcela="1941.71" data-intercalada="9320.19" data-status="disponivel">902 - 20,21 m² - SUL - R$ 372.807,79</option>
                        <option value="903" data-metragem="20.78" data-valor="383322.41" data-entrada="57498.36" data-parcela="1996.47" data-intercalada="9583.06" data-status="disponivel">903 - 20,78 m² - SUL - R$ 383.322,41</option>
                        <option value="904" data-metragem="26.55" data-valor="488129.22" data-entrada="73219.38" data-parcela="2542.34" data-intercalada="12203.23" data-status="disponivel">904 - 26,55 m² - NASC/SUL - R$ 488.129,22</option>
                        <option value="905" data-metragem="18.21" data-valor="338074.34" data-entrada="50711.15" data-parcela="1760.80" data-intercalada="8451.86" data-status="disponivel">905 - 18,21 m² - NASCENTE - R$ 338.074,34</option>
                        <option value="906" data-metragem="18.59" data-valor="345129.16" data-entrada="51769.37" data-parcela="1797.55" data-intercalada="8628.23" data-status="disponivel">906 - 18,59 m² - NASCENTE - R$ 345.129,16</option>
                        <option value="907" data-metragem="27.34" data-valor="531553.62" data-entrada="79733.04" data-parcela="2768.51" data-intercalada="13288.84" data-status="disponivel">907 - 27,34 m² - NASC/NORTE - R$ 531.553,62</option>
                        <option value="908" data-metragem="20.68" data-valor="405789.80" data-entrada="60868.47" data-parcela="2113.49" data-intercalada="10144.75" data-status="disponivel">908 - 20,68 m² - NORTE - R$ 405.789,80</option>
                        <option value="909" data-metragem="21.19" data-valor="415797.19" data-entrada="62369.58" data-parcela="2165.61" data-intercalada="10394.93" data-status="disponivel">909 - 21,19 m² - NORTE - R$ 415.797,19</option>
                        <option value="910" data-metragem="28.49" data-valor="514536.40" data-entrada="77180.46" data-parcela="2679.88" data-intercalada="12863.41" data-status="disponivel">910 - 28,49 m² - NORTE - R$ 514.536,40</option>
                        
                        <!-- 10º PAVIMENTO -->
                        <option value="1001" data-metragem="26.46" data-valor="498513.12" data-entrada="74776.97" data-parcela="2596.42" data-intercalada="12462.83" data-status="disponivel">1001 - 26,46 m² - SUL - R$ 498.513,12</option>
                        <option value="1002" data-metragem="20.21" data-valor="391448.18" data-entrada="58717.23" data-parcela="2038.79" data-intercalada="9786.20" data-status="disponivel">1002 - 20,21 m² - SUL - R$ 391.448,18</option>
                        <option value="1003" data-metragem="20.78" data-valor="402488.53" data-entrada="60373.28" data-parcela="2096.29" data-intercalada="10062.21" data-status="disponivel">1003 - 20,78 m² - SUL - R$ 402.488,53</option>
                        <option value="1004" data-metragem="26.55" data-valor="512535.69" data-entrada="76880.35" data-parcela="2669.46" data-intercalada="12813.39" data-status="disponivel">1004 - 26,55 m² - NASC/SUL - R$ 512.535,69</option>
                        <option value="1005" data-metragem="18.21" data-valor="354978.06" data-entrada="53246.71" data-parcela="1848.84" data-intercalada="8874.45" data-status="reservado">1005 - 18,21 m² - NASCENTE - R$ 354.978,06 (RESERVADO)</option>
                        <option value="1006" data-metragem="18.59" data-valor="362385.62" data-entrada="54357.84" data-parcela="1887.43" data-intercalada="9059.64" data-status="reservado">1006 - 18,59 m² - NASCENTE - R$ 362.385,62 (RESERVADO)</option>
                        <option value="1007" data-metragem="27.34" data-valor="558131.30" data-entrada="83719.69" data-parcela="2906.93" data-intercalada="13953.28" data-status="disponivel">1007 - 27,34 m² - NASC/NORTE - R$ 558.131,30</option>
                        <option value="1008" data-metragem="20.68" data-valor="426079.29" data-entrada="63911.89" data-parcela="2219.16" data-intercalada="10651.98" data-status="disponivel">1008 - 20,68 m² - NORTE - R$ 426.079,29</option>
                        <option value="1009" data-metragem="21.19" data-valor="436587.05" data-entrada="65488.06" data-parcela="2273.89" data-intercalada="10914.68" data-status="disponivel">1009 - 21,19 m² - NORTE - R$ 436.587,05</option>
                        <option value="1010" data-metragem="28.49" data-valor="540263.21" data-entrada="81039.48" data-parcela="2813.87" data-intercalada="13506.58" data-status="disponivel">1010 - 28,49 m² - NORTE - R$ 540.263,21</option>
                    </select>
                </div>
                
                <div class="value-display">
                    <span>Valor Total do Imóvel:</span>
                    <span id="valor-imovel">R$ 0,00</span>
                    <span id="status-imovel" class="status-disponivel"></span>
                </div>
                
                <div class="form-group">
                    <label for="entrada">Entrada (mínimo 10% do valor do imóvel)</label>
                    <input type="number" id="entrada" placeholder="Digite o valor da entrada" oninput="updateCalculations()">
                    <span id="percentual-entrada" class="percent">0%</span>
                </div>
                
                <div class="value-display">
                    <span>Parcelamento:</span>
                    <span>48x</span>
                </div>
                
                <div class="form-group">
                    <label for="parcela">Valor da Parcela Mensal</label>
                    <input type="number" id="parcela" placeholder="Digite o valor da parcela" oninput="updateCalculations()">
                    <span id="percentual-parcela" class="percent">0%</span>
                </div>
                
                <div class="value-display">
                    <span>Total das Parcelas (48x):</span>
                    <span id="total-parcelas">R$ 0,00</span>
                    <span id="percentual-total-parcelas" class="percent">0%</span>
                </div>
                
                <div class="form-group">
                    <label for="intercalada">Valor de cada Intercalada (8x)</label>
                    <input type="number" id="intercalada" placeholder="Digite o valor de cada intercalada" oninput="updateCalculations()">
                    <span id="percentual-intercalada" class="percent">0%</span>
                </div>
                
                <div class="value-display">
                    <span>Total das Intercaladas (8x):</span>
                    <span id="total-intercaladas">R$ 0,00</span>
                    <span id="percentual-total-intercaladas" class="percent">0%</span>
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
                
                <button type="button" id="enviar-simulacao" class="submit-btn">Enviar Simulação</button>
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
        // Menu Hamburguer - Sempre visível
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
            
            // Adiciona/remove classe no body para evitar scroll quando menu está aberto
            document.body.classList.toggle('no-scroll');
        });
        
        // Fechar menu ao clicar em um link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.classList.remove('active');
                document.body.classList.remove('no-scroll');
            });
        });
        
        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
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
        const statusImovelDisplay = document.getElementById('status-imovel');
        const entradaInput = document.getElementById('entrada');
        const percentualEntrada = document.getElementById('percentual-entrada');
        const parcelaInput = document.getElementById('parcela');
        const percentualParcela = document.getElementById('percentual-parcela');
        const totalParcelasDisplay = document.getElementById('total-parcelas');
        const percentualTotalParcelas = document.getElementById('percentual-total-parcelas');
        const intercaladaInput = document.getElementById('intercalada');
        const percentualIntercalada = document.getElementById('percentual-intercalada');
        const totalIntercaladasDisplay = document.getElementById('total-intercaladas');
        const percentualTotalIntercaladas = document.getElementById('percentual-total-intercaladas');
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
            if (selectedOption.value === "") {
                valorImovel = 0;
                valorImovelDisplay.textContent = "R$ 0,00";
                statusImovelDisplay.textContent = "";
                entradaInput.value = '';
                parcelaInput.value = '';
                intercaladaInput.value = '';
                return;
            }
            
            valorImovel = parseFloat(selectedOption.getAttribute('data-valor'));
            const entradaPadrao = parseFloat(selectedOption.getAttribute('data-entrada'));
            const parcelaPadrao = parseFloat(selectedOption.getAttribute('data-parcela'));
            const intercaladaPadrao = parseFloat(selectedOption.getAttribute('data-intercalada'));
            const status = selectedOption.getAttribute('data-status');
            
            valorImovelDisplay.textContent = formatCurrency(valorImovel);
            
            // Atualiza o status do imóvel
            if (status === 'reservado') {
                statusImovelDisplay.textContent = '(RESERVADO)';
                statusImovelDisplay.className = 'status-reservado';
            } else {
                statusImovelDisplay.textContent = '(DISPONÍVEL)';
                statusImovelDisplay.className = 'status-disponivel';
            }
            
            entradaInput.value = entradaPadrao.toFixed(2);
            parcelaInput.value = parcelaPadrao.toFixed(2);
            intercaladaInput.value = intercaladaPadrao.toFixed(2);
            
            updateCalculations();
        });
        
        // Função para formatar valores monetários
        function formatCurrency(value) {
            return 'R$ ' + value.toFixed(2).replace('.', ',').replace(/(\d)(?=(\d{3})+\,)/g, '$1.');
        }
        
        // Função para calcular e atualizar os valores
        function updateCalculations() {
            // Obter valores dos inputs
            const entrada = parseFloat(entradaInput.value) || 0;
            const parcela = parseFloat(parcelaInput.value) || 0;
            const intercalada = parseFloat(intercaladaInput.value) || 0;
            
            // Calcular totais
            const totalParcelas = parcela * 48;
            const totalIntercaladas = intercalada * 8;
            const subtotal = entrada + totalParcelas + totalIntercaladas;
            const chaves = valorImovel - subtotal;
            const totalFinanciado = subtotal;
            
            // Calcular percentuais
            const percentEntrada = (entrada / valorImovel) * 100;
            const percentParcela = (parcela / valorImovel) * 100;
            const percentTotalParcelasCalc = (totalParcelas / valorImovel) * 100;
            const percentIntercalada = (intercalada / valorImovel) * 100;
            const percentTotalIntercaladasCalc = (totalIntercaladas / valorImovel) * 100;
            const percentSubtotal = (subtotal / valorImovel) * 100;
            const percentChaves = (chaves / valorImovel) * 100;
            const percentTotal = (totalFinanciado / valorImovel) * 100;
            
            // Atualizar displays
            percentualEntrada.textContent = percentEntrada.toFixed(2) + '%';
            percentualParcela.textContent = percentParcela.toFixed(2) + '%';
            totalParcelasDisplay.textContent = formatCurrency(totalParcelas);
            percentualTotalParcelas.textContent = percentTotalParcelasCalc.toFixed(2) + '%';
            percentualIntercalada.textContent = percentIntercalada.toFixed(2) + '%';
            totalIntercaladasDisplay.textContent = formatCurrency(totalIntercaladas);
            percentualTotalIntercaladas.textContent = percentTotalIntercaladasCalc.toFixed(2) + '%';
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
        
        // Atualizar cálculos quando qualquer valor mudar
        [entradaInput, parcelaInput, intercaladaInput].forEach(input => {
            input.addEventListener('input', updateCalculations);
        });
        
        // Enviar simulação para WhatsApp
        document.getElementById('enviar-simulacao').addEventListener('click', function() {
            if (valorImovel === 0) {
                alert('Por favor, selecione uma unidade primeiro.');
                return;
            }
            
            const unidade = unidadeSelect.options[unidadeSelect.selectedIndex].text;
            const valorImovelText = valorImovelDisplay.textContent;
            const statusText = statusImovelDisplay.textContent;
            const entradaText = 'R$ ' + (entradaInput.value || '0') + ' (' + percentualEntrada.textContent + ')';
            const parcelaText = 'R$ ' + (parcelaInput.value || '0') + ' (' + percentualParcela.textContent + ')';
            const totalParcelasText = totalParcelasDisplay.textContent + ' (' + percentualTotalParcelas.textContent + ')';
            const intercaladaText = 'R$ ' + (intercaladaInput.value || '0') + ' (' + percentualIntercalada.textContent + ')';
            const totalIntercaladasText = totalIntercaladasDisplay.textContent + ' (' + percentualTotalIntercaladas.textContent + ')';
            const subtotalText = subtotalDisplay.textContent + ' (' + percentualSubtotal.textContent + ')';
            const chavesText = chavesDisplay.textContent + ' (' + percentualChaves.textContent + ')';
            const totalText = totalFinanciadoDisplay.textContent + ' (' + percentualTotal.textContent + ')';
            
            const message = `Simulação de Imóvel - MOSS\n\n` +
                            `Unidade: ${unidade}\n` +
                            `Valor Total: ${valorImovelText} ${statusText}\n\n` +
                            `Entrada: ${entradaText}\n` +
                            `Parcela: ${parcelaText}\n` +
                            `Total Parcelas (48x): ${totalParcelasText}\n` +
                            `Intercalada: ${intercaladaText}\n` +
                            `Total Intercaladas (8x): ${totalIntercaladasText}\n\n` +
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
        
        // Galeria de Imagens - Veja mais
        const loadMoreBtn = document.querySelector('.load-more');
        const mosaicItems = document.querySelectorAll('.mosaic-item');
        let itemsToShow = 9;
        
        // Mostrar apenas as primeiras 9 imagens inicialmente
        mosaicItems.forEach((item, index) => {
            if (index >= itemsToShow) {
                item.style.display = 'none';
            }
        });
        
        loadMoreBtn.addEventListener('click', () => {
            itemsToShow += 4; // Mostrar mais 4 imagens a cada clique
            
            // Mostrar itens adicionais
            mosaicItems.forEach((item, index) => {
                if (index < itemsToShow) {
                    item.style.display = 'block';
                }
            });
            
            // Esconder o botão se todas as imagens estiverem visíveis
            if (itemsToShow >= mosaicItems.length) {
                loadMoreBtn.style.display = 'none';
            }
        });
        
        // Modal de Imagem
        const imageModal = document.getElementById('imageModal');
        const expandedImg = document.getElementById('expandedImg');
        const closeImageModal = document.querySelector('.image-modal .close-modal');
        
        // Adicionar evento de clique para cada imagem
        document.querySelectorAll('.mosaic-item img').forEach(img => {
            img.addEventListener('click', function() {
                expandedImg.src = this.src;
                expandedImg.alt = this.alt;
                imageModal.style.display = 'flex';
                document.body.style.overflow = 'hidden'; // Desabilita o scroll da página
            });
        });
        
        // Fechar modal de imagem
        closeImageModal.addEventListener('click', () => {
            imageModal.style.display = 'none';
            document.body.style.overflow = 'auto'; // Habilita o scroll da página novamente
        });
        
        // Fechar modal de imagem ao clicar fora
        window.addEventListener('click', (e) => {
            if (e.target === imageModal) {
                imageModal.style.display = 'none';
                document.body.style.overflow = 'auto'; // Habilita o scroll da página novamente
            }
        });
    </script>
</body>
</html>
