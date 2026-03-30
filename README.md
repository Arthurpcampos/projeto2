<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VeloCity | A sua loja de bicicletas</title>
    <style>
        /* Variáveis de Cores e Estilos Básicos */
        :root {
            --primary: #10b981; /* Verde Esmeralda */
            --primary-hover: #059669;
            --dark: #1e293b; /* Chumbo */
            --light: #f8fafc;
            --gray: #64748b;
            --white: #ffffff;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            scroll-behavior: smooth; /* Rolagem suave ao clicar nos links */
        }

        body {
            background-color: var(--light);
            color: var(--dark);
        }

        /* Cabeçalho Superior (Navbar) */
        header {
            background-color: var(--white);
            box-shadow: var(--shadow);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
            flex-wrap: wrap;
            gap: 15px;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--dark);
            text-decoration: none;
        }

        .logo span {
            color: var(--primary);
        }

        nav {
            display: flex;
            gap: 20px;
        }

        nav a {
            text-decoration: none;
            color: var(--gray);
            font-weight: 600;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--primary);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        /* Barra de Pesquisa */
        .search-bar {
            padding: 8px 15px;
            border: 1px solid #cbd5e1;
            border-radius: 20px;
            outline: none;
            width: 200px;
            transition: width 0.3s, border-color 0.3s;
        }

        .search-bar:focus {
            width: 250px;
            border-color: var(--primary);
        }

        /* Ícone do Carrinho */
        .cart-icon {
            cursor: pointer;
            font-size: 1.5rem;
            position: relative;
            display: flex;
            align-items: center;
        }

        .cart-count {
            background-color: var(--primary);
            color: var(--white);
            border-radius: 50%;
            padding: 2px 6px;
            font-size: 0.75rem;
            font-weight: bold;
            position: absolute;
            top: -5px;
            right: -10px;
        }

        /* Banner Principal */
        .hero {
            background: linear-gradient(rgba(30, 41, 59, 0.7), rgba(30, 41, 59, 0.7)), url('https://images.unsplash.com/photo-1511994298241-608e28f14fde?w=1200&q=80') center/cover;
            height: 50vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: var(--white);
            text-align: center;
            padding: 0 20px;
        }

        .hero h2 { font-size: 3rem; margin-bottom: 15px; text-transform: uppercase; letter-spacing: 2px; }
        .hero p { font-size: 1.2rem; max-width: 600px; }

        /* Grade de Produtos */
        .container {
            padding: 4rem 5%;
            max-width: 1200px;
            margin: auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.5rem;
            color: var(--dark);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        /* Cartão de Produto Aprimorado */
        .product-card {
            background-color: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        .product-card img {
            width: 100%;
            aspect-ratio: 4/3; /* Mantém todas as imagens do mesmo tamanho */
            object-fit: cover;
            border-bottom: 1px solid #f1f5f9;
        }

        .product-info { 
            padding: 20px; 
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .product-title { 
            font-size: 1.2rem; 
            margin-bottom: 10px; 
            color: var(--dark);
        }

        .product-price { 
            color: var(--primary); 
            font-weight: 800; 
            font-size: 1.5rem; 
            margin-bottom: 15px; 
            margin-top: auto; /* Empurra o preço para baixo */
        }

        button {
            background-color: var(--primary);
            color: var(--white);
            border: none;
            padding: 12px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1rem;
            transition: background 0.3s;
            width: 100%;
        }

        button:hover { background-color: var(--primary-hover); }

        /* Mensagem de "Nenhum produto encontrado" */
        .no-results {
            text-align: center;
            grid-column: 1 / -1;
            font-size: 1.2rem;
            color: var(--gray);
            padding: 40px;
        }

        /* Rodapé / Contatos */
        footer {
            background-color: var(--dark);
            color: var(--white);
            padding: 3rem 5%;
            text-align: center;
            margin-top: 2rem;
        }

        footer h3 { margin-bottom: 15px; color: var(--primary); }
        footer p { margin-bottom: 10px; color: #cbd5e1; }

        /* Carrinho Lateral (Mantido e Ajustado) */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -100%;
            width: 380px;
            max-width: 100vw;
            height: 100%;
            background-color: var(--white);
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1000;
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .cart-sidebar.active { right: 0; }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid var(--light);
            padding-bottom: 15px;
            margin-bottom: 20px;
        }

        .close-cart { cursor: pointer; font-size: 2rem; color: var(--gray); line-height: 1; }
        .close-cart:hover { color: var(--dark); }

        .cart-items { flex-grow: 1; overflow-y: auto; }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            background-color: var(--light);
            padding: 10px;
            border-radius: 8px;
        }

        .cart-item-title { font-size: 0.95rem; font-weight: 600; }
        .cart-item-price { color: var(--primary); font-weight: bold; }
        .remove-item { color: #ef4444; cursor: pointer; font-size: 0.85rem; font-weight: bold; }

        .cart-footer {
            border-top: 2px solid var(--light);
            padding-top: 20px;
            text-align: center;
        }

        .cart-total { font-size: 1.5rem; font-weight: bold; margin-bottom: 15px; color: var(--dark);}
    </style>
</head>
<body>

    <header>
        <a href="#inicio" class="logo">Velo<span>City</span></a>
        
        <nav>
            <a href="#inicio">Início</a>
            <a href="#produtos">Produtos</a>
            <a href="#contatos">Contatos</a>
        </nav>

        <div class="header-actions">
            <input type="text" id="search-input" class="search-bar" placeholder="Buscar por nome...">
            
            <div class="cart-icon" onclick="toggleCart()">
                🛒 <span class="cart-count" id="cart-count">0</span>
            </div>
        </div>
    </header>

    <section id="inicio" class="hero">
        <h2>Sua Próxima Aventura Começa Aqui</h2>
        <p>Descubra nossa seleção premium de bicicletas para montanha, estrada e uso urbano.</p>
    </section>

    <main id="produtos" class="container">
        <h2 class="section-title">Nossa Coleção</h2>
        <div class="products-grid" id="products-grid">
            </div>
    </main>

    <footer id="contatos">
        <h3>VeloCity Bicicletas</h3>
        <p>📍 Avenida das Rodas, 123 - Centro, São Paulo</p>
        <p>📞 (11) 99999-0000 | ✉️ contato@velocity.com.br</p>
        <p style="margin-top: 20px; font-size: 0.8rem;">© 2026 VeloCity. Todos os direitos reservados.</p>
    </footer>

    <div class="cart-sidebar" id="cart-sidebar">
        <div class="cart-header">
            <h2>Seu Carrinho</h2>
            <span class="close-cart" onclick="toggleCart()">&times;</span>
        </div>
        <div class="cart-items" id="cart-items"></div>
        <div class="cart-footer">
            <div class="cart-total">Total: R$ <span id="total-price">0,00</span></div>
            <button onclick="checkout()">Finalizar Compra Segura</button>
        </div>
    </div>

    <script>
        // Banco de Dados com mais produtos
        const products = [
            { id: 1, name: "Mountain Bike Pro Aro 29", price: 2499.90, image: "https://images.unsplash.com/photo-1532298229144-0ec0c57515c7?w=600&q=80" },
            { id: 2, name: "Speed Carbono Velo", price: 5890.00, image: "https://images.unsplash.com/photo-1484081064880-4141995a940e?w=600&q=80" },
            { id: 3, name: "Urbana Retrô Vintage", price: 1250.50, image: "https://images.unsplash.com/photo-1507035895480-2b3156c31fc8?w=600&q=80" },
            { id: 4, name: "Bicicleta Elétrica EcoCity", price: 4500.00, image: "https://images.unsplash.com/photo-1558981359-219d6364c9c8?w=600&q=80" },
            { id: 5, name: "BMX Freestyle Extreme", price: 1850.00, image: "https://images.unsplash.com/photo-1565129654714-25712e0e4c63?w=600&q=80" },
            { id: 6, name: "Dobrável Compacta City", price: 2100.00, image: "https://images.unsplash.com/photo-1593026338573-0533591c3d18?w=600&q=80" }
        ];

        let cart = [];

        // Função para mostrar os produtos (agora aceita uma lista para permitir filtragem)
        function renderProducts(productsToShow) {
            const grid = document.getElementById('products-grid');
            grid.innerHTML = ''; // Limpa a grade antes de adicionar

            if (productsToShow.length === 0) {
                grid.innerHTML = '<div class="no-results">Nenhum produto encontrado com este nome.</div>';
                return;
            }

            productsToShow.forEach(product => {
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <img src="${product.image}" alt="${product.name}">
                    <div class="product-info">
                        <h3 class="product-title">${product.name}</h3>
                        <div class="product-price">R$ ${product.price.toFixed(2).replace('.', ',')}</div>
                        <button onclick="addToCart(${product.id})">Adicionar ao Carrinho</button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Sistema de Busca
        document.getElementById('search-input').addEventListener('input', function(event) {
            const termoBusca = event.target.value.toLowerCase();
            const produtosFiltrados = products.filter(product => 
                product.name.toLowerCase().includes(termoBusca)
            );
            renderProducts(produtosFiltrados);
        });

        // Funções do Carrinho
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            cart.push(product);
            updateCartUI();
            document.getElementById('cart-sidebar').classList.add('active');
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartUI();
        }

        function updateCartUI() {
            const cartItemsContainer = document.getElementById('cart-items');
            const cartCount = document.getElementById('cart-count');
            const totalPriceElement = document.getElementById('total-price');

            cartItemsContainer.innerHTML = ''; 
            let total = 0;

            cart.forEach((item, index) => {
                total += item.price;
                const itemDiv = document.createElement('div');
                itemDiv.className = 'cart-item';
                itemDiv.innerHTML = `
                    <div>
                        <div class="cart-item-title">${item.name}</div>
                        <div class="cart-item-price">R$ ${item.price.toFixed(2).replace('.', ',')}</div>
                    </div>
                    <span class="remove-item" onclick="removeFromCart(${index})">X Remover</span>
                `;
                cartItemsContainer.appendChild(itemDiv);
            });

            cartCount.innerText = cart.length;
            totalPriceElement.innerText = total.toFixed(2).replace('.', ',');
        }

        function toggleCart() {
            document.getElementById('cart-sidebar').classList.toggle('active');
        }

        function checkout() {
            if (cart.length === 0) {
                alert("Seu carrinho está vazio!");
                return;
            }
            alert("A funcionalidade de pagamento real requer um Back-end (ex: integração com Mercado Pago). O carrinho será esvaziado agora.");
            cart = []; 
            updateCartUI();
            toggleCart();
        }

        // Inicializa mostrando todos os produtos
        window.onload = () => renderProducts(products);

    </script>
</body>
</html>
