<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Lanchonete Videira </title>
    <link rel="stylesheet" href="styles.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 0;
            background-color: #f8f9fa;
        }

        .container {
            max-width: 100%;
            margin: auto;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1, h2 {
            text-align: center;
        }

        .item {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid #ddd;
        }

        .button {
            background-color: green;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 5px;
        }

        .categories button {
            margin-right: 10px;
            padding: 8px 16px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
            margin-bottom: 10px;
        }

        .categories button:hover {
            background-color: #0056b3;
        }

        /* Media Query para telas menores que 600px */
        @media (max-width: 600px) {
    body {
        padding: 10px;
    }

    .container {
        width: 100%;
        padding: 10px;
    }

    .categories button {
        width: 100%;
        margin: 5px 0;
        text-align: center;
    }

    .item {
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
}
    </style>
</head>
<body>

     <!-- Cabeçalho -->
    <header>
        <h1>Lanchonete Videira</h1>
            <section id="menu">
                <div class="categories">
                    <button onclick="showCategory('sanduiches')">Sanduiches</button>
                    <button onclick="showCategory('kikao')">Kikão</button>
                    <button onclick="showCategory('batatas')">Batatas</button>
                    <button onclick="showCategory('pizzas')">Pizzas</button>
                    <button onclick="showCategory('pizzas especiais')">Pizzas Especiais</button>
                    <button onclick="showCategory('combos')">Combos</button>
                    <button onclick="toggleCart()">Carrinho (<span id="cart-count">0</span>)</button>
                </div>
            </section>
        </header>

    <!-- Lanches -->
    <section id="sanduiches" style="display: block;">
        <h2>Sanduiches</h2>
        <div class="item">
            <h3>Misto</h3>
            <p>Pão, queijo, e presunto.</p>
            <p>R$ 5,00</p>
            <button aria-label="Adicionar Misto ao carrinho" onclick="adicionarAoCarrinho('Misto', 5.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>X-Egg</h3>
            <p>Pão bola, queijo, presunto, ovo, e alface.</p>
            <p>R$ 6,00</p>
            <button onclick="adicionarAoCarrinho('X-Egg', 6.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>X-Burguer</h3>
            <p>Pão bola, carne de hambúrguer, queijo, presunto.</p>
            <p>R$ 7,00</p>
            <button onclick="adicionarAoCarrinho('X-Burguer', 7.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>X-Salada</h3>
            <p>Pão bola, carne de hambúrguer, ovo, queijo, presunto, alface, e tomate.</p>
            <p>R$ 10,00</p>
            <button onclick="adicionarAoCarrinho('X-Salada', 10.00)">Adicionar</button>        
        </div>

        <div class="item">
            <h3>X-Salsicha</h3>
            <p>R$ 13,00</p>
            <p>Pão bola, carne de hambúrguer, queijo, presunto, salsicha, ovo, alface e tomate.</p>
            <button onclick="adicionarAoCarrinho('X-Salsicha', 13.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>X-Calabresa</h3>
            <p>R$ 15,00</p>
            <p>Pão bola, carne de hambúrguer, calabresa, queijo, presunto, ovo, alface e tomate.</p>
            <button onclick="adicionarAoCarrinho('X-Calabresa', 15.00)">Adicionar</button>        </div>

        <div class="item">
            <h3>X-Bacon</h3>
            <p>Pão bola, carne de hambúrguer, bacon, queijo, presunto, ovo, alface e tomate.</p>
            <p>R$ 17,00</p>
            <button onclick="adicionarAoCarrinho('X-Bacon', 17.00)">Adicionar</button>     
           </div>

        <div class="item">
            <h3>X-Tudo</h3>
            <p>Pão bola, carne de hambúrguer, bacon, salsicha, calabresa, queijo, presunto, ovo, alface e tomate.</p>
            <p>R$ 20,00</p>
            <button onclick="adicionarAoCarrinho('X-Tudo', 20.00)">Adicionar</button>
        </div>
    </section>

    <!-- Kikão -->
    <section id="kikao" style="display: none;">
        <h2>Kikão</h2>
        <div class="item">
            <h3>Kikão simples</h3>
            <p>Pão, molho especial salsicha, batata palha, queijo ralado, ketchup, e maionese.</p>
            <p>R$ 7,00</p>
            <button onclick="adicionarAoCarrinho('kikão', 7.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Dog Pizza</h3>
            <p>Pão, molho especial 2 salsichas, batata palha, queijo, presunto, tomate, azeitonas, queijo ralado, ketchup, e maionese.</p>
            <p>R$ 15,00</p>
            <button onclick="adicionarAoCarrinho('Dog Pizza', 15.00)">Adicionar</button> 
               </div>
    </section>

    <!-- Batatas -->
    <section id="batatas" style="display: none;">
        <h2>Batatas</h2>
        <div class="item">
            <h3>Batata Frita</h3>
            <p>Porção de batatas fritas crocantes.</p>
            <p>Marmita: R$ 20,00</p>
            <button onclick="adicionarAoCarrinho('Batata Frita Marmita', 20.00)">Adicionar</button>
            <p>P: R$ 35,00</p>
            <button onclick="adicionarAoCarrinho('Batata Frita P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata Frita M', 50.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Batata Gourmet - Cheddar</h3>
            <p>Batata frita coberta com cheddar cremoso.</p> 
            <p>P: R$ 35,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Cheddar P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Cheddar M', 50.00)">Adicionar</button>
            <p>G: R$ 70,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Cheddar G', 70.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Batata Gourmet - Calabresa e Cheddar</h3>
            <p>Batata frita com calabresa e cheddar cremoso.</p>
            <p>P: R$ 35,00</p>        
            <button onclick="adicionarAoCarrinho('Batata Gourmet Calabresa e Cheddar P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Calabresa e Cheddar M', 50.00)">Adicionar</button>
            <p>G: R$ 70,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Calabresa e Cheddar G', 70.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Batata Gourmet - Cheddar e Catupiry</h3>
            <p>Batata frita com cheddar cremoso e catupiry.</p>
            <p>P: R$ 35,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Cheddar e Catupiry P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Cheddar e Catupiry M', 50.00)">Adicionar</button>
            <p>G: R$ 70,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Cheddar e Catupiry', 70.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Batata Gourmet - Bacon e Cheddar</h3>
            <p>Batata frita com bacon crocante e cheddar cremoso.</p>
            <p>P: R$ 35,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Bacone Cheddar P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Bacon e Cheddar M', 50.00)">Adicionar</button>
            <p>G: R$ 70,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Bacon e Cheddar G', 70.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Batata Gourmet - Calabresa e Catupiry</h3>
            <p>Batata frita com calabresa e catupiry.</p>
            <p>P: R$ 35,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet calabresa e Catupiry P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata calabresa e catupiry M', 50.00)">Adicionar</button>
            <p>G: R$ 70,00</p>
            <button onclick="adicionarAoCarrinho('Batata calabresa e catupiry G', 70.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Batata Gourmet - Bacon e Catupiry</h3>
            <p>Batata frita com bacon crocante e catupiry.</p>
            <p>P: R$ 35,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Bacon e Catupiry P', 35.00)">Adicionar</button>
            <p>M: R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Bacon e Catupiry M', 50.00)">Adicionar</button>
            <p>G: R$ 70,00</p>
            <button onclick="adicionarAoCarrinho('Batata Gourmet Bacon e Catupiry G', 70.00)">Adicionar</button>
    </div>
    </section>

    <!-- Pizzas -->
    <section id="pizzas" style="display: none;">
        <h2>Pizzas</h2>
        <div class="item">
            <h3>Calabresa</h3>
            <p>Massa, molho de tomate, queijo, presunto, calabresa, cebola e orégano.</p>
            <p>Média - R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Calabresa Média', 50.00)">Adicionar</button>
            <p>Grande - R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Calabresa Grande', 65.00)">Adicionar</button>
            
        </div>

        <div class="item">
            <h3>Mussarela</h3>
            <p>Massa, molho de tomate, queijo, tomate, azeitonas e orégano.</p>
            <p>Média - R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Mussarela Média', 50.00)">Adicionar</button>
            <p>Grande - R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Mussarela Grande', 65.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Portuguesa</h3>
            <p>Massa, molho de tomate, queijo, presunto, tomate, cebola, ovo, pimentão, azeitonas e orégano.</p>
            <p>Média - R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Portuguesa Média', 50.00)">Adicionar</button>
            <p>Grande - R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Portuguesa Grande', 65.00)">Adicionar</button>
        </div>
        </section>

     <!-- Pizzas Especiais -->
    <section id="pizzas especiais" style="display: none;">
        <h2>Pizzas Especiais</h2>
        <div class="item">
            <h3>Frango c/ Catupiry</h3>
            <p>Massa, molho de tomate, queijo, Frango desfiado, e catupiry.</p>
            <p>Média - R$ 65,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Frango c/ Catupiry Média', 65.00)">Adicionar</button>
            <p>Grande - R$ 80,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Frango c/ Catupiry Grande', 80.00)">Adicionar</button>
            </div>

        <div class="item">
            <h3>Calabresa c/ creme cheese</h3>
            <p>Massa, molho de tomate, queijo, presunto, calabresa, cebola, e creme cheese.</p>
            <p>Média - R$ 65,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Calabresa c/ creme cheese Média', 65.00)">Adicionar</button>
            <p>Grande - R$ 80,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Calabresa c/ creme cheese Grande', 80.00)">Adicionar</button>
        </div>

        <div class="item">
            <h3>Moda da Casa</h3>
            <p>Massa, molho de tomate, queijo, bacon, calabresa, ovo, tomate, cebola e orégano.</p>
            <p>Média - R$ 65,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Moda da Casa Média', 65.00)">Adicionar</button>
            <p>Grande - R$ 80,00</p>
            <button onclick="adicionarAoCarrinho('Pizza Moda da Casa Grande', 80.00)">Adicionar</button>
        </div>
    </section>

    <!-- Combos -->
    <section id="combos" style="display: none;">
        <h2>Combos</h2>
        <div class="item">
            <h3>Combo 1</h3>
            <p>3 kikão simples.</p>
            <p>R$ 18,00</p>
            <button onclick="adicionarAoCarrinho('Combo 1', 18.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 2</h3>
            <p>3 X-Salada.</p>
            <p>R$ 25,00</p>
            <button onclick="adicionarAoCarrinho('Combo 2', 25.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 3</h3>
            <p>2 X-Salada, + 1 kikão.</p>
            <p>R$ 25,00</p>
            <button onclick="adicionarAoCarrinho('Combo 3', 25.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 4</h3>
            <p> 4 X-Salada, + refrigerante 1,5l</p>
            <p>R$ 40,00</p>
            <button onclick="adicionarAoCarrinho('Combo 4', 40.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 5</h3>
            <p>2 X-Salada, + 2 kikão, + refrigerante 1,5l.</p>
            <p>R$ 38,00</p>
            <button onclick="adicionarAoCarrinho('Combo 5', 38.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 6</h3>
            <p>3 X-Burguer, e refrigerante 1,5l.</p>
            <p>R$ 20,00</p>
            <button onclick="adicionarAoCarrinho('Combo 6', 20.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 7</h3>
            <p>3 X-Salada, + batata G, e refrigerante 1,5l.</p>
            <p>R$ 50,00</p>
            <button onclick="adicionarAoCarrinho('Combo 7', 50.00)">Adicionar</button> 
        </div>

        <div class="item">
            <h3>Combo 8</h3>
            <p>3 X-Kikão, + batata G, e refrigerante 1,5l.</p> 
            <p>R$ 45,00</p>
            <button onclick="adicionarAoCarrinho('Combo 8', 45.00)">Adicionar</button> 
        </div>
    </section>

        <div id="cart" style="display: none;">
            <h2>Carrinho</h2>
            <ul id="cart-items"></ul>
            <p>Total: R$ <span id="total-price">0.00</span></p>
        </div>
  
  <script>
    let cart = [];
    let total = 0;

    function showCategory(category) {
        const sections = document.querySelectorAll('section');
        sections.forEach(section => section.style.display = 'none');
        document.getElementById(category).style.display = 'block';
    }

    function adicionarAoCarrinho(item, price) {
        cart.push({ item, price });
        total += price;
        updateCart();
    }

    function updateCart() {
        const cartCount = document.getElementById('cart-count');
        const cartItems = document.getElementById('cart-items');
        const totalPrice = document.getElementById('total-price');

        cartCount.textContent = cart.length;
        cartItems.innerHTML = '';
        cart.forEach(item => {
            const li = document.createElement('li');
            li.textContent = `${item.item} - R$ ${item.price.toFixed(2)}`;
            cartItems.appendChild(li);
        });

        totalPrice.textContent = total.toFixed(2);
    }

    function toggleCart() {
        const cartSection = document.getElementById('cart');
        cartSection.style.display = cartSection.style.display === 'none' ? 'block' : 'none';
    }
</script>

    <footer>
        <p>&copy; 2025 - Lanchonete Videira | Contato: (92) 984964947</p>
    </footer>

    
<script src="carrinho lachonete.js"></script>

</body>
</html>
