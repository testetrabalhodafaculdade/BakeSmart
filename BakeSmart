# BakeSmart
BakeSmart - Inovação na Gestão de Vendas e Estoque para Padarias

<!DOCTYPE html>
 <html lang="pt-br">
 <head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Controle de Estoque- Padaria</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 margin: 0;
 padding: 20px;
 background-color: #f4f4f9;
 }
 h1 {
 text-align: center;
 }
 .form-container {
 margin: 20px 0;
 padding: 10px;
 background-color: #fff;
 border-radius: 8px;
 box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
 }
 .form-container label {
 margin-right: 10px;
 }
 .form-container input,
 .form-container button,
 .form-container select {
 margin: 5px 0;
 padding: 8px;
 font-size: 14px;
 }
 table {
 width: 100%;
 border-collapse: collapse;
 margin-top: 20px;
 }
 table, th, td {
 border: 1px solid #ccc;
 }
 th, td {
 padding: 10px;
 text-align: left;
 }
 button {
 background-color: #4CAF50;
 color: white;
border: none;
 cursor: pointer;
 }
 button:hover {
 background-color: #45a049;
 }
 </style>
 </head>
 <body>
 <h1>Sistema de Controle de Estoque- Padaria</h1>
 <!-- Formulário para adicionar produto-->
 <div class="form-container">
 <h3>Adicionar Produto ao Estoque</h3>
 <label for="produtoNome">Nome do Produto:</label>
 <input type="text" id="produtoNome" placeholder="Nome do Produto">
 <label for="quantidade">Quantidade:</label>
 <input type="number" id="quantidade" placeholder="Quantidade" min="1">
 <label for="preco">Preço Unitário (R$):</label>
 <input type="number" id="preco" placeholder="Preço" step="0.01" min="0.01">
 <button onclick="adicionarProduto()">Adicionar Produto</button>
 </div>
 <!-- Formulário para registrar venda-->
 <div class="form-container">
 <h3>Registrar Venda</h3>
 <label for="produtoVenda">Produto:</label>
 <select id="produtoVenda"></select>
 <label for="quantidadeVenda">Quantidade Vendida:</label>
 <input type="number" id="quantidadeVenda" min="1">
 <button onclick="registrarVenda()">Registrar Venda</button>
 </div>
 <!-- Tabela para exibir o estoque-->
 <h3>Estoque Atual</h3>
 <table id="tabelaEstoque">
 <thead>
 <tr>
 <th>Produto</th>
 <th>Quantidade</th>
 <th>Preço Unitário (R$)</th>
 <th>Valor Total (R$)</th>
</tr>
 </thead>
 <tbody>
 <!-- O conteúdo da tabela será atualizado dinamicamente-->
 </tbody>
 </table>
 <script>
 // Lista para armazenar os produtos no estoque
 let estoque = [];
 // Função para adicionar produto ao estoque
 function adicionarProduto() {
 const nome = document.getElementById('produtoNome').value;
 const quantidade = parseInt(document.getElementById('quantidade').value);
 const preco = parseFloat(document.getElementById('preco').value);
 // Validação de campos
 if (!nome || quantidade <= 0 || preco <= 0) {
 alert("Por favor, preencha todos os campos corretamente.");
 return;
 }
 // Adicionando o produto ao estoque
 const produto = {
 nome: nome,
 quantidade: quantidade,
 preco: preco
 };
 estoque.push(produto);
 // Atualizar a tabela de estoque e o combo box de produtos para venda
 atualizarEstoque();
 atualizarProdutoVenda();
 }
 // Função para atualizar a tabela de estoque
 function atualizarEstoque() {
 const tabela =
 document.getElementById('tabelaEstoque').getElementsByTagName('tbody')[0];
 tabela.innerHTML = ';
 estoque.forEach(produto => {
 const row = tabela.insertRow();
 row.insertCell(0).textContent = produto.nome;
 row.insertCell(1).textContent = produto.quantidade;
 row.insertCell(2).textContent = produto.preco.toFixed(2);
 row.insertCell(3).textContent = (produto.quantidade * produto.preco).toFixed(2);
});
 }
 // Função para atualizar o combo box de produtos para venda
 function atualizarProdutoVenda() {
 const select = document.getElementById('produtoVenda');
 select.innerHTML = ';
 estoque.forEach((produto, index) => {
 const option = document.createElement('option');
 option.value = index;
 option.textContent = produto.nome;
 select.appendChild(option);
 });
 }
 // Função para registrar uma venda
 function registrarVenda() {
 const produtoIndex = document.getElementById('produtoVenda').value;
 const quantidadeVenda =
 parseInt(document.getElementById('quantidadeVenda').value);
 if (quantidadeVenda <= 0 || produtoIndex === "") {
 alert("Por favor, selecione um produto e insira uma quantidade válida.");
 return;
 }
 const produto = estoque[produtoIndex];
 if (quantidadeVenda > produto.quantidade) {
 alert("Quantidade de venda maior do que a disponível no estoque!");
 return;
 }
 // Atualiza a quantidade no estoque após a venda
 produto.quantidade-= quantidadeVenda;
 // Atualizar a tabela de estoque
 atualizarEstoque();
 }
 </script>
 </body>
 </html
