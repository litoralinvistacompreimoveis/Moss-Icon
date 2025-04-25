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
            height: 70px;
            display: flex;
            align-items: center;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            width: 100%;
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
        
        /* Menu Hamburguer - Sempre visível */
        .hamburger {
            display: block;
            cursor: pointer;
            padding: 10px;
            z-index: 1001;
            position: relative;
            left: -15px;
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

        /* Gallery Section - Imagens responsivas */
        .mosaic-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            height: 250px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
            cursor: pointer;
        }
        
        .mosaic-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .mosaic-item:hover img {
            transform: scale(1.05);
        }

        /* Simulation Section - Responsividade */
        .simulation-form {
            background-color: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-top: 2rem;
            overflow: hidden;
        }
        
        .simulation-form .form-group {
            margin-bottom: 1rem;
        }
        
        .simulation-form label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            font-size: 0.95rem;
        }
        
        .simulation-form input, 
        .simulation-form select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            box-sizing: border-box;
        }
        
        .simulation-form .value-display {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            margin-bottom: 0.8rem;
            gap: 0.5rem;
        }
        
        .simulation-form .value-display span {
            font-weight: bold;
            min-width: 120px;
            font-size: 0.95rem;
        }
        
        .simulation-form .percent {
            color: var(--primary-color);
            font-weight: bold;
            font-size: 0.9rem;
        }
        
        .simulation-form .calculation-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 0.8rem;
            padding: 0.8rem;
            background-color: #f8f9fa;
            border-radius: 5px;
            gap: 0.5rem;
        }
        
        .simulation-form .calculation-row span {
            font-size: 0.95rem;
        }
        
        .simulation-form .total-row {
            background-color: var(--primary-color);
            color: white;
            font-weight: bold;
            margin-top: 1rem;
        }
        
        .simulation-form .break-line {
            height: 1rem;
        }
        
        .simulation-form .submit-btn {
            width: 100%;
            margin-top: 1.5rem;
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
            object-fit: contain;
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

        /* Media Queries para responsividade */
        @media (max-width: 768px) {
            .header-container {
                padding: 1rem;
            }
            
            .logo h1 {
                font-size: 1.2rem;
            }
            
            .simulation-form {
                padding: 1rem;
            }
            
            .simulation-form .value-display span,
            .simulation-form .calculation-row span {
                font-size: 0.85rem;
            }
            
            .simulation-form input, 
            .simulation-form select {
                padding: 0.7rem;
                font-size: 0.9rem;
            }
        }
        
        @media (max-width: 480px) {
            .simulation-form .value-display {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .simulation-form .calculation-row {
                flex-direction: column;
                align-items: flex-start;
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
                <!-- Imagens adicionais -->
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
                        <option value="102" data-metragem="27.28" data-valor="392320.50" data-entrada="40000" data-parcela="1804.95" data-intercalada="8663.74" data-status="disponivel">102 - 27,28 m² - SUL - R$ 392.320,50</option>
                        <option value="201" data-metragem="34.01" data-valor="488043.50" data-entrada="50000" data-parcela="2200.00" data-intercalada="10000.00" data-status="disponivel">201 - 34,01 m² - SUL - R$ 488.043,50</option>
                    </select>
                </div>
                
                <div class="value-display">
                    <span>Valor Total do Imóvel:</span>
                    <span id="valor-imovel">R$ 0,00</span>
                    <span id="status-imovel" class="status-disponivel"></span>
                </div>
                
                <div class="form-group">
                    <label for="entrada">Entrada (mínimo 10% do valor do imóvel)</label>
                    <input type="text" id="entrada" placeholder="Ex: 40000 ou 40.000,00" oninput="formatCurrencyInput(this); updateCalculations()">
                    <span id="percentual-entrada" class="percent">0%</span>
                </div>
                
                <div class="break-line"></div>
                
                <div class="value-display">
                    <span>Parcelamento:</span>
                    <span>48x</span>
                </div>
                
                <div class="form-group">
                    <label for="parcela">Valor da Parcela Mensal</label>
                    <input type="text" id="parcela" placeholder="Ex: 1804,95" oninput="formatCurrencyInput(this); updateCalculations()">
                    <span id="percentual-parcela" class="percent">0%</span>
                </div>
                
                <div class="value-display">
                    <span>Total das Parcelas (48x):</span>
                    <span id="total-parcelas">R$ 0,00</span>
                    <span id="percentual-total-parcelas" class="percent">0%</span>
                </div>
                
                <div class="break-line"></div>
                
                <div class="form-group">
                    <label for="intercalada">Valor de cada Intercalada (8x)</label>
                    <input type="text" id="intercalada" placeholder="Ex: 8663,74" oninput="formatCurrencyInput(this); updateCalculations()">
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
                
                <div class="break-line"></div>
                
                <div class="calculation-row">
                    <span>Para pegar as chaves:</span>
                    <span id="chaves">R$ 0,00</span>
                    <span id="percentual-chaves" class="percent">0%</span>
                </div>
                
                <div class="calculation-row total-row">
                    <span>TOTAL À FINANCIAR (pós chaves):</span>
                    <span id="total-financiado">R$ 0,00</span>
                    <span id="percentual-total" class="percent">0%</span>
                </div>
                
                <button type="button" id="enviar-simulacao" class="submit-btn">Enviar Simulação</button>
            </div>
        </div>
    </section>
    
    <!-- Modal de Imagem -->
    <div id="imageModal" class="image-modal">
        <span class="close-modal">&times;</span>
        <div class="image-modal-content">
            <img id="expandedImg" src="" alt="Imagem expandida">
        </div>
    </div>
    
    <script>
        // Menu Hamburguer
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
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

        // Funções para manipulação de valores monetários
        function formatCurrency(value) {
            return 'R$ ' + value.toFixed(2).replace('.', ',').replace(/(\d)(?=(\d{3})+\,)/g, '$1.');
        }

        function formatCurrencyInput(input) {
            let value = input.value.replace(/[^\d,]/g, '');
            
            // Garante apenas uma vírgula
            const parts = value.split(',');
            if (parts.length > 1) {
                value = parts[0] + ',' + parts.slice(1).join('');
            }
            
            // Limita a 2 casas decimais após a vírgula
            if (value.includes(',')) {
                const decimalPart = value.split(',')[1];
                if (decimalPart && decimalPart.length > 2) {
                    value = value.substring(0, value.indexOf(',') + 3);
                }
            }
            
            // Adiciona separadores de milhar
            const numberPart = value.split(',')[0];
            if (numberPart.length > 3) {
                const formattedNumber = numberPart.replace(/\B(?=(\d{3})+(?!\d))/g, '.');
                value = value.includes(',') ? formattedNumber + ',' + value.split(',')[1] : formattedNumber;
            }
            
            input.value = value;
        }

        function parseCurrency(value) {
            if (!value) return 0;
            return parseFloat(value.replace(/\./g, '').replace(',', '.')) || 0;
        }

        // Variáveis do simulador
        const unidadeSelect = document.getElementById('unidade');
        let valorImovel = 0;

        // Atualizar quando selecionar a unidade
        unidadeSelect.addEventListener('change', function() {
            const selectedOption = this.options[this.selectedIndex];
            if (!selectedOption.value) {
                valorImovel = 0;
                document.getElementById('valor-imovel').textContent = "R$ 0,00";
                document.getElementById('status-imovel').textContent = "";
                return;
            }
            
            valorImovel = parseFloat(selectedOption.getAttribute('data-valor'));
            document.getElementById('valor-imovel').textContent = formatCurrency(valorImovel);
            
            const status = selectedOption.getAttribute('data-status');
            const statusDisplay = document.getElementById('status-imovel');
            statusDisplay.textContent = status === 'reservado' ? '(RESERVADO)' : '(DISPONÍVEL)';
            statusDisplay.className = status === 'reservado' ? 'status-reservado' : 'status-disponivel';
            
            // Preenche os valores padrão
            document.getElementById('entrada').value = selectedOption.getAttribute('data-entrada').replace('.', ',');
            document.getElementById('parcela').value = selectedOption.getAttribute('data-parcela').replace('.', ',');
            document.getElementById('intercalada').value = selectedOption.getAttribute('data-intercalada').replace('.', ',');
            
            updateCalculations();
        });

        // Função principal de cálculo
        function updateCalculations() {
            if (valorImovel <= 0) return;
            
            // Obter valores dos inputs
            const entrada = parseCurrency(document.getElementById('entrada').value);
            const parcela = parseCurrency(document.getElementById('parcela').value);
            const intercalada = parseCurrency(document.getElementById('intercalada').value);
            
            // Cálculos básicos
            const totalParcelas = parcela * 48;
            const totalIntercaladas = intercalada * 8;
            const subtotal = entrada + totalParcelas + totalIntercaladas;
            const chaves = Math.max(valorImovel - subtotal, valorImovel * 0.47); // Garante mínimo de 47%
            const totalFinanciado = chaves;
            
            // Cálculo de percentuais
            const percentEntrada = (entrada / valorImovel) * 100;
            const percentParcela = (parcela / valorImovel) * 100;
            const percentTotalParcelas = (totalParcelas / valorImovel) * 100;
            const percentIntercalada = (intercalada / valorImovel) * 100;
            const percentTotalIntercaladas = (totalIntercaladas / valorImovel) * 100;
            const percentSubtotal = (subtotal / valorImovel) * 100;
            const percentChaves = (chaves / valorImovel) * 100;
            const percentTotal = (totalFinanciado / valorImovel) * 100;
            
            // Atualizar a interface
            document.getElementById('percentual-entrada').textContent = percentEntrada.toFixed(2) + '%';
            document.getElementById('percentual-parcela').textContent = percentParcela.toFixed(2) + '%';
            document.getElementById('total-parcelas').textContent = formatCurrency(totalParcelas);
            document.getElementById('percentual-total-parcelas').textContent = percentTotalParcelas.toFixed(2) + '%';
            document.getElementById('percentual-intercalada').textContent = percentIntercalada.toFixed(2) + '%';
            document.getElementById('total-intercaladas').textContent = formatCurrency(totalIntercaladas);
            document.getElementById('percentual-total-intercaladas').textContent = percentTotalIntercaladas.toFixed(2) + '%';
            document.getElementById('subtotal').textContent = formatCurrency(subtotal);
            document.getElementById('percentual-subtotal').textContent = percentSubtotal.toFixed(2) + '%';
            document.getElementById('chaves').textContent = formatCurrency(chaves);
            document.getElementById('percentual-chaves').textContent = percentChaves.toFixed(2) + '%';
            document.getElementById('total-financiado').textContent = formatCurrency(totalFinanciado);
            document.getElementById('percentual-total').textContent = percentTotal.toFixed(2) + '%';
        }

        // Enviar simulação para WhatsApp
        document.getElementById('enviar-simulacao').addEventListener('click', function() {
            if (valorImovel === 0) {
                alert('Por favor, selecione uma unidade primeiro.');
                return;
            }
            
            const unidade = unidadeSelect.options[unidadeSelect.selectedIndex].text;
            const valorImovelText = document.getElementById('valor-imovel').textContent;
            const statusText = document.getElementById('status-imovel').textContent;
            
            const entradaText = 'R$ ' + (document.getElementById('entrada').value || '0,00') + 
                              ' (' + document.getElementById('percentual-entrada').textContent + ')';
            
            const parcelaText = 'R$ ' + (document.getElementById('parcela').value || '0,00') + 
                               ' (' + document.getElementById('percentual-parcela').textContent + ')';
            
            const totalParcelasText = document.getElementById('total-parcelas').textContent + 
                                     ' (' + document.getElementById('percentual-total-parcelas').textContent + ')';
            
            const intercaladaText = 'R$ ' + (document.getElementById('intercalada').value || '0,00') + 
                                   ' (' + document.getElementById('percentual-intercalada').textContent + ')';
            
            const totalIntercaladasText = document.getElementById('total-intercaladas').textContent + 
                                         ' (' + document.getElementById('percentual-total-intercaladas').textContent + ')';
            
            const subtotalText = document.getElementById('subtotal').textContent + 
                                ' (' + document.getElementById('percentual-subtotal').textContent + ')';
            
            const chavesText = document.getElementById('chaves').textContent + 
                              ' (' + document.getElementById('percentual-chaves').textContent + ')';
            
            const totalText = document.getElementById('total-financiado').textContent + 
                             ' (' + document.getElementById('percentual-total').textContent + ')';
            
            const message = `Simulação de Imóvel - MOSS\n\n` +
                            `Unidade: ${unidade}\n` +
                            `Valor Total: ${valorImovelText} ${statusText}\n\n` +
                            `Entrada: ${entradaText}\n\n` +
                            `Parcela: ${parcelaText}\n` +
                            `Total Parcelas (48x): ${totalParcelasText}\n\n` +
                            `Intercalada: ${intercaladaText}\n` +
                            `Total Intercaladas (8x): ${totalIntercaladasText}\n\n` +
                            `Subtotal antes das chaves: ${subtotalText}\n\n` +
                            `Para pegar as chaves: ${chavesText}\n\n` +
                            `TOTAL À FINANCIAR (pós chaves): ${totalText}\n\n` +
                            `Por favor, entre em contato para mais informações.`;
            
            const whatsappUrl = `https://wa.me/5521980081646?text=${encodeURIComponent(message)}`;
            window.open(whatsappUrl, '_blank');
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
            itemsToShow += 4;
            
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
                document.body.style.overflow = 'hidden';
            });
        });
        
        // Fechar modal de imagem
        closeImageModal.addEventListener('click', () => {
            imageModal.style.display = 'none';
            document.body.style.overflow = 'auto';
        });
        
        // Fechar modal de imagem ao clicar fora
        window.addEventListener('click', (e) => {
            if (e.target === imageModal) {
                imageModal.style.display = 'none';
                document.body.style.overflow = 'auto';
            }
        });
    </script>
</body>
</html>
