<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Giro Rápido | Loja de Bicicletas</title>
    <style>
        /* CSS: Estilos e Design Profissional */
        :root {
            --primary-color: #ff5722;
            --dark-color: #333;
            --light-color: #f4f4f4;
            --white: #fff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--light-color);
            color: var(--dark-color);
        }

        /* Cabeçalho / Navegação */
        header {
            background-color: var(--dark-color);
            color: var(--white);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        header h1 {
            color: var(--primary-color);
            font-size: 1.8rem;
        }

        .cart-icon {
            cursor: pointer;
            font-size: 1.2rem;
            position: relative;
        }

        .cart-count {
            background-color: var(--primary-color);
            color: var(--white);
            border-radius: 50%;
            padding: 2px 8px;
            font-size: 0.8rem;
            position: absolute;
            top: -10px;
            right: -15px;
        }

        /* Banner Principal */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1517649763962-0c623066013b?w=1200&q=80') center/cover;
            height: 40vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: var(--white);
            text-align: center;
            padding: 0 20px;
        }

        .hero h2 { font-size: 2.5rem; margin-bottom: 10px; }

        /* Grade de Produtos */
        .container {
            padding: 2rem 5%;
            max-width: 1200px;
            margin: auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 2rem;
            font-size: 2rem;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .product-card {
            background-color: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
            text-align: center;
            padding-bottom: 15px;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .product-info { padding: 15px; }
        .product-title { font-size: 1.2rem; margin-bottom: 10px; }
        .product-price { color: var(--primary-color); font-weight: bold; font-size: 1.4rem; margin-bottom: 15px; }

        button {
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s;
        }

        button:hover { background-color: #e64a19; }

        /* Carrinho Lateral (Modal) */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -100%;
            width: 350px;
            height: 100%;
            background-color: var(--white);
            box-shadow: -2px 0 5px rgba(0,0,0,0.2);
            transition: right 0.3s ease;
            z-index: 101;
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .cart-sidebar.active { right: 0; }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #ddd;
            padding-bottom: 10px;
            margin-bottom: 20px;
        }

        .close-cart { cursor: pointer; font-size: 1.5rem; font-weight: bold; color: #888; }
        .close-cart:hover { color: var(--dark-color); }

        .cart-items { flex-grow: 1; overflow-y: auto; }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }

        .cart-item-title { font-size: 0.9rem; }
        .cart-item-price { color: var(--primary-color); font-weight: bold; }
        
        .remove-item { color: red; cursor: pointer; font-size: 0.8rem; }

        .cart-footer {
            border-top: 1px solid #ddd;
            padding-top: 20px;
            text-align: center;
        }

        .cart-total { font-size: 1.5rem; font-weight: bold; margin-bottom: 15px; }
        .checkout-btn { width: 100%; font-size: 1.1rem; padding: 15px; background-color: #4CAF50;}
        .checkout-btn:hover { background-color: #45a049;}
    </style>
</head>
<body>

    <header>
        <h1>Giro Rápido</h1>
        <div class="cart-icon" onclick="toggleCart()">
            🛒 Carrinho <span class="cart-count" id="cart-count">0</span>
        </div>
    </header>

    <section class="hero">
        <h2>Aventura em Duas Rodas</h2>
        <p>Encontre a bicicleta perfeita para o seu estilo de vida.</p>
    </section>

    <main class="container">
        <h2 class="section-title">Nossos Modelos</h2>
        <div class="products-grid" id="products-grid">
            </div>
    </main>

    <div class="cart-sidebar" id="cart-sidebar">
        <div class="cart-header">
            <h2>Seu Carrinho</h2>
            <span class="close-cart" onclick="toggleCart()">&times;</span>
        </div>
        <div class="cart-items" id="cart-items">
            </div>
        <div class="cart-footer">
            <div class="cart-total">Total: R$ <span id="total-price">0,00</span></div>
            <button class="checkout-btn" onclick="checkout()">Finalizar Compra</button>
        </div>
    </div>

    <script>
        // 1. Banco de Dados Simulado (Array de Objetos)
        const products = [
            {
                id: 1,
                name: "Bicicleta Mountain Bike Pro Aro 29",
                price: 2499.90,
                image: "https://images.unsplash.com/photo-1532298229144-0ec0c57515c7?w=500&q=80"
            },
            {
                id: 2,
                name: "Bicicleta Speed / Estrada Carbono",
                price: 5890.00,
                image: "https://images.unsplash.com/photo-1484081064880-4141995a940e?w=500&q=80"
            },
            {
                id: 3,
                name: "Bicicleta Urbana Retrô Vintage",
                price: 1250.50,
                image: "https://images.unsplash.com/photo-1507035895480-2b3156c31fc8?w=500&q=80"
            },
            {
                id: 4,
                name: "Bicicleta Elétrica EcoCity",
                price: 4500.00,
                image: "https://images.unsplash.com/photo-1558981359-219d6364c9c8?w=500&q=80"
            }
        ];

        let cart = [];

        // 2. Função para mostrar os produtos na tela
        function renderProducts() {
            const grid = document.getElementById('products-grid');
            products.forEach(product => {
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

        // 3. Função para adicionar ao carrinho
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            cart.push(product);
            updateCartUI();
            
            // Abre o carrinho automaticamente ao adicionar
            document.getElementById('cart-sidebar').classList.add('active');
        }

        // 4. Função para remover do carrinho
        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartUI();
        }

        // 5. Função para atualizar a tela do carrinho
        function updateCartUI() {
            const cartItemsContainer = document.getElementById('cart-items');
            const cartCount = document.getElementById('cart-count');
            const totalPriceElement = document.getElementById('total-price');

            cartItemsContainer.innerHTML = ''; // Limpa o carrinho
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
                    <span class="remove-item" onclick="removeFromCart(${index})">Remover</span>
                `;
                cartItemsContainer.appendChild(itemDiv);
            });

            cartCount.innerText = cart.length;
            totalPriceElement.innerText = total.toFixed(2).replace('.', ',');
        }

        // 6. Abrir e Fechar o Carrinho
        function toggleCart() {
            const sidebar = document.getElementById('cart-sidebar');
            sidebar.classList.toggle('active');
        }

        // 7. Simular a finalização da compra
        function checkout() {
            if (cart.length === 0) {
                alert("Seu carrinho está vazio!");
                return;
            }
            alert("Redirecionando para o pagamento seguro... (Funcionalidade de Back-end necessária aqui)");
            cart = []; // Esvazia o carrinho após "comprar"
            updateCartUI();
            toggleCart();
        }

        // Inicializa a loja assim que a página carrega
        window.onload = renderProducts;

    </script>
</body>
</html>
