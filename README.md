# Rayk-<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PedalX Brasil</title>
  <style>
    /* Estilos básicos */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      text-align: center;
    }
    header {
      background-color: #2c3e50;
      color: white;
      padding: 20px;
    }
    .container {
      padding: 20px;
    }
    .product {
      display: inline-block;
      margin: 20px;
      padding: 10px;
      border: 1px solid #ddd;
    }
    footer {
      background-color: #2c3e50;
      color: white;
      padding: 10px;
      margin-top: 20px;
    }
    .payment-methods {
      margin-top: 30px;
      padding: 20px;
      background-color: #f4f4f4;
    }
  </style>
  <!-- Biblioteca para geração do QR Code -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/qrious/4.0.2/qrious.min.js"></script>
</head>
<body>
  <header>
    <h1>PedalX Brasil</h1>
    <p>O melhor lugar para comprar peças de bicicletas!</p>
  </header>
  <div class="container">
    <h2>Produtos em Destaque</h2>
    <div class="product">
      <img src="https://via.placeholder.com/150" alt="Produto 1">
      <h3>Produto 1</h3>
      <p>Descrição breve do produto.</p>
      <button onclick="gerarPix('Produto 1', 100)">Comprar</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/150" alt="Produto 2">
      <h3>Produto 2</h3>
      <p>Descrição breve do produto.</p>
      <button onclick="gerarPix('Produto 2', 150)">Comprar</button>
    </div>
  </div>
  <div class="payment-methods">
    <h2>Formas de Pagamento</h2>
    <p>Aceitamos os seguintes métodos de pagamento:</p>
    <ul>
      <li>Pix (via Nubank)</li>
      <li>Cartão de Crédito</li>
      <li>Cartão de Débito</li>
    </ul>
    <p>Após a compra, um QR Code Pix será gerado automaticamente.</p>
    <div id="qrcode"></div>
  </div>
  <footer>
    <p>&copy; 2025 PedalX Brasil - Todos os direitos reservados.</p>
  </footer>
  <script>
    function gerarPix(produto, valor) {
      // Dados para o QR Code Pix
      let chavePix = "21981071848";
      let nomeRecebedor = "PedalX Brasil";
      let cidade = "SUA_CIDADE"; // Substitua com a sua cidade
      let txid = "TXID123456";   // Você pode gerar um TXID único por transação
      let valorFormatado = valor.toFixed(2);
      
      let payloadPix = `00020126330014BR.GOV.BCB.PIX0114${chavePix}520400005303986540${valorFormatado}5802BR5917${nomeRecebedor}6009${cidade}62190515${txid}6304`;
      
      // Gera o QR Code
      let qr = new QRious({
        element: document.getElementById('qrcode'),
        value: payloadPix,
        size: 200
      });
      
      alert('Escaneie o QR Code Pix para pagamento!');
    }
  </script>
</body>
</html>
