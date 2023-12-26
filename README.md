# selects

SELECT 
    Cliente.Nome AS NomeCliente,
    Fornecedor.Nome AS NomeFornecedor
FROM 
    Cliente
JOIN 
    Pedido ON Cliente.NúmeroCliente = Pedido.NúmeroCliente
JOIN 
    PedidoProduto ON Pedido.NúmeroPedido = PedidoProduto.NúmeroPedido
JOIN 
    ProdutoFornecedor ON PedidoProduto.NúmeroProduto = ProdutoFornecedor.NúmeroProduto
JOIN 
    Fornecedor ON ProdutoFornecedor.CNPJFornecedor = Fornecedor.CNPJFornecedor;
----------------------------------------------------------------------------------

SELECT Pedido.numeroPedido,COUNT(PedidoProduto.numeroproduto) AS TotalProdutos
FROM Pedido
JOIN PedidoProduto ON Pedido.numeropedido = PedidoProduto.numeropedido
GROUP BY Pedido.numeropedido;
