# SQL-CADASTROLOJA
Está SQL foi estruturada para fazer o armazenamento das principais informações do cliente que realizou determinada venda, sendo assim obtendo as principais informações da venda(data, id do produto e id do cliente) e armazenamento das informações também dos produtos.
Banco de dados: `atividade11/09`

--
-- Banco de dados: `atividade11/09`
--

-- --------------------------------------------------------

--
-- Estrutura da tabela `clientes`
--

CREATE TABLE `clientes` (
  `ID_Cliente` int(5) NOT NULL,
  `Nome_Cliente` varchar(45) NOT NULL,
  `CPF_Cliente` varchar(15) NOT NULL,
  `Data_de_Nasc` varchar(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

-- --------------------------------------------------------

--
-- Estrutura da tabela `produto`
--

CREATE TABLE `produto` (
  `ID_Produtos` int(5) NOT NULL,
  `Nome_Produto` int(50) NOT NULL,
  `Categoria` varchar(30) NOT NULL,
  `Preço_Produto` varchar(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

-- --------------------------------------------------------

--
-- Estrutura da tabela `vendas`
--

CREATE TABLE `vendas` (
  `ID_Vendas` int(6) NOT NULL,
  `ID_Cliente` int(5) NOT NULL,
  `ID_Produto` int(5) NOT NULL,
  `Quantidade` int(4) NOT NULL,
  `Data_Venda` varchar(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Índices para tabelas despejadas
--

--
-- Índices para tabela `clientes`
--
ALTER TABLE `clientes`
  ADD PRIMARY KEY (`ID_Cliente`);

--
-- Índices para tabela `produto`
--
ALTER TABLE `produto`
  ADD PRIMARY KEY (`ID_Produtos`);

--
-- Índices para tabela `vendas`
--
ALTER TABLE `vendas`
  ADD PRIMARY KEY (`ID_Vendas`),
  ADD UNIQUE KEY `ID_Cliente` (`ID_Cliente`),
  ADD UNIQUE KEY `ID_Produto` (`ID_Produto`);

--
-- Restrições para despejos de tabelas
--

--
-- Limitadores para a tabela `produto`
--
ALTER TABLE `produto`
  ADD CONSTRAINT `produto_ibfk_1` FOREIGN KEY (`ID_Produtos`) REFERENCES `vendas` (`ID_Produto`);

--
-- Limitadores para a tabela `vendas`
--
ALTER TABLE `vendas`
  ADD CONSTRAINT `vendas_ibfk_1` FOREIGN KEY (`ID_Cliente`) REFERENCES `clientes` (`ID_Cliente`);
COMMIT;


Índices para tabela `telefone`



CREATE TABLE `TELEFONE` ( `ID_FONE` int(6) AUTO_INCREMENT PRIMARY KEY, `ID_Cliente` int(5) NOT NULL, `TELEFONE` CHAR (20) NOT NULL, FOREIGN KEY (ID_Cliente) REFERENCES clientes(ID_Cliente));


