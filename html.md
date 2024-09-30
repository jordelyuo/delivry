<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Site Delivery</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #000000f3;
            color: #333;
        }

        header {
            background: linear-gradient(90deg, #434144, #f3cf05de);
            color: rgb(0, 0, 0);
            padding: 20px;
            text-align: center;
        }

        nav ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        nav ul li {
            display: inline;
            margin: 0 15px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        h2 {
            text-align: center;
            color: #eede05;
            margin-top: 40px;
        }

        .categories {
            display: flex;
            justify-content: space-around;
            margin: 20px 0;
        }

        .category {
            text-align: center;
            background: #fff;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .category:hover {
            transform: scale(1.05);
        }

        .card, .promo {
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin: 15px 0;
            padding: 20px;
            transition: transform 0.2s;
        }

        .card:hover, .promo:hover {
            transform: scale(1.02);
        }

        .card h3, .promo h3 {
            margin: 0;
            color: #000000;
        }

        .card p, .promo p {
            color: #666;
        }

        .card span, .promo span {
            font-weight: bold;
            color: #9e1f09;
        }

        .btn {
            background: #030301;
            color: rgba(190, 63, 32, 0.945);
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
            transition: background 0.3s;
        }

        .btn:hover {
            background: #07030c;
        }

        footer {
            text-align: center;
            padding: 20px;
            background: #040105;
            color: white;
            position: relative;
            bottom: 0;
            width: 100%;
        }

        .form-control {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        #carrinho {
            display: none;
            background: rgb(5, 2, 2);
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin: 20px 0;
        }

        #carrinho h3 {
            margin-top: 0;
            color: #cecbcf;
        }

        .pagamento {
            margin-top: 15px;
            padding: 10px;
            background-color: #e20d0d;
            border-radius: 5px;
        }

        .pagamento label {
            display: block;
            margin: 5px 0;
        }

        @media (max-width: 768px) {
            .categories {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Site Delivery</h1>
        <nav>
            <ul>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#promo">Promoções</a></li>
                <li><a href="#contato">Contato</a></li>
                <li><button class="btn" onclick="toggleCarrinho()">Carrinho (<span id="carrinho-count">0</span>)</button></li>
            </ul>
        </nav>
    </header>

    <div class="container">
      <section id="categories">
    <h2>Categorias</h2>
    <div class="categories">
        <div class="category">
            <h3>Pastéis</h3>
            <img src="WhatsApp Image 2024-09-30 at 14.11.14.jpeg" alt="Pastéis" style="width: 200px; height: auto; margin: 20px 0;">
            <p>Diversas opções.</p>
        </div>
        <div class="category">
            <h3>Pizzas</h3>
            <img src="WhatsApp Image 2024-09-30 at 14.11.15.jpeg" alt="Pizzas" style="width: 200px; height: auto; margin: 20px 0;">
            <p>Várias opções de sabores.</p>
        </div>
        <div class="category">
            <h3>Hamburguer</h3>
            <img src="WhatsApp Image 2024-09-30 at 14.11.12.jpeg" alt="Hamburguer" style="width: 200px; height: auto; margin: 20px 0;">
            <p>Hamburguer artesanal.</p>
        </div>
    </div>
</section>



        <section id="menu">
            <h2>Nosso Menu</h2>
            <div class="card">
                <h3>Pastel de queijo</h3>
                <p>Delicioso pastel com queijo e milho.</p>
                <span>Preço: R$12</span>
                <button class="btn" onclick="adicionarAoCarrinho('Pastel de queijo', 12)">Adicionar ao Carrinho</button>
            </div>
            <div class="card">
                <h3>Hamburguer Clássico</h3>
                <p>hamburguer artesanal.</p>
                <span>Preço: R$30</span>
                <button class="btn" onclick="adicionarAoCarrinho('Hamburguer Clássico', 30)">Adicionar ao Carrinho</button>
            </div>
            <div class="card">
                <h3>Pizza</h3>
                <p>Deliciosas pizzas.</p>
                <span>Preço: R$70</span>
                <button class="btn" onclick="adicionarAoCarrinho('Pizza', 70)">Adicionar ao Carrinho</button>
            </div>
        </section>

        <section id="promo">
            <h2>Promoções</h2>
            <div class="promo">
                <h3>Promoção do Dia</h3>
                <p>Peça uma Pizza e ganhe 50% de desconto no segundo item!</p>
                <span>Válido até: 30/10/2024</span>
                <button class="btn" onclick="adicionarAoCarrinho('Promoção Pizza', 45)">Participar</button>
            </div>
        </section>

        <section id="contato">
            
        <div style="text-align: center; margin-top: 20px;">
        <a href="https://wa.me/5533991236596" target="_blank">
            <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" style="width: 50px; height: 50px;">
        </a>
        <p>Entre em contato pelo WhatsApp!</p>
            <h2>Envie sugestões</h2>
            <form id="form-contato" onsubmit="enviarMensagem(event)">
                <input type="text" placeholder="Seu Nome" required class="form-control">
                <input type="email" placeholder="Seu Email" required class="form-control">
                <textarea placeholder="Sua Mensagem" required class="form-control"></textarea>
                <button type="submit" class="btn">Enviar</button>
            </form>
    </div>
        </section>

        <section id="carrinho">
            <h3>Itens no Carrinho</h3>
            <ul id="carrinho-list"></ul>
            <p><strong>Total: R$<span id="total-value">0</span></strong></p>
            <div class="pagamento">
                <h4>Formas de Pagamento</h4>
                <label><input type="radio" name="pagamento" value="Cartão de Crédito"> Cartão de Crédito</label>
                <label><input type="radio" name="pagamento" value="Cartão de Débito"> Cartão de Débito</label>
                <label><input type="radio" name="pagamento" value="Dinheiro"> Dinheiro</label>
                <button class="btn" onclick="finalizarCompra()">Finalizar Compra</button>
            </div>
        </section>
    </div>

    <footer>
        <p>© 2024 Site Delivery</p>
    </footer>

    <script>
        const carrinho = [];
        
        function adicionarAoCarrinho(nome, preco) {
            carrinho.push({ nome, preco });
            document.getElementById('carrinho-count').innerText = carrinho.length;
            alert(`${nome} foi adicionado ao carrinho! Preço: R$${preco}`);
            atualizarCarrinho();
        }

        function toggleCarrinho() {
            const carrinhoSection = document.getElementById('carrinho');
            carrinhoSection.style.display = carrinhoSection.style.display === 'none' || carrinhoSection.style.display === '' ? 'block' : 'none';
            atualizarCarrinho();
        }

        function atualizarCarrinho() {
            const carrinhoList = document.getElementById('carrinho-list');
            const totalValue = document.getElementById('total-value');
            carrinhoList.innerHTML = '';
            let total = 0;

            if (carrinho.length === 0) {
                carrinhoList.innerHTML = '<li>Carrinho vazio</li>';
                totalValue.innerText = '0';
                return;
            }

            carrinho.forEach(item => {
                const listItem = document.createElement('li');
                listItem.innerText = `${item.nome} - R$${item.preco}`;
                carrinhoList.appendChild(listItem);
                total += item.preco;
            });

            totalValue.innerText = total.toFixed(2);
        }

        function finalizarCompra() {
            if (carrinho.length === 0) {
                alert("Seu carrinho está vazio!");
                return;
            }
            alert("Compra finalizada com sucesso!");
            carrinho.length = 0; // Limpa o carrinho
            document.getElementById('carrinho-count').innerText = 0;
            atualizarCarrinho();
            toggleCarrinho(); // Fecha o carrinho
        }

        function enviarMensagem(event) {
            event.preventDefault();
            alert("Mensagem enviada com sucesso!");
            document.getElementById('form-contato').reset();
        }
    </script>
</body>
</html>
