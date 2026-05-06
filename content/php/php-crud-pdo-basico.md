# PDO (PHP Data Objects)

O **PDO (PHP Data Objects)** é uma interface poderosa que funciona como uma camada de abstração entre o código PHP e o banco de dados. Sua principal importância reside na **segurança**, pois, ao utilizar *Prepared Statements*, ele protege a aplicação contra ataques de SQL Injection, filtrando automaticamente dados maliciosos. Além disso, o PDO oferece **portabilidade**: se você precisar trocar o banco de dados de MySQL para PostgreSQL, por exemplo, o código das queries permanece praticamente o mesmo, mudando apenas a string de conexão.

Para o desenvolvedor, ele padroniza o tratamento de erros através de **Exceptions**, permitindo identificar falhas de forma muito mais profissional e clara. Em resumo, utilizar PDO é abandonar práticas obsoletas em favor de um desenvolvimento **robusto, seguro e escalável**, sendo um requisito indispensável para qualquer programador que deseja atuar no mercado de trabalho atual seguindo as melhores práticas da indústriaPDO (PHP Data Objects).

# CRUD

O termo **CRUD** é um acrônimo que representa as quatro operações fundamentais que realizamos em qualquer sistema que manipule dados. No dia a dia de um desenvolvedor, quase tudo o que fazemos — seja em uma rede social, um e-commerce ou uma agenda — gira em torno dessas quatro funções:

*   **C (Create):** É a criação de novos registros (ex: cadastrar um novo contato).
*   **R (Read):** É a leitura ou consulta dos dados (ex: listar seus contatos ou ver detalhes de um deles).
*   **U (Update):** É a atualização de informações já existentes (ex: editar o número de telefone de alguém).
*   **D (Delete):** É a remoção de dados do sistema (ex: apagar um contato da lista).

Dominar o CRUD é considerado o "primeiro grande degrau" para qualquer estudante de programação. É através dele que você entende como o **Front-end** (formulários HTML) se comunica com o **Back-end** (PHP) para persistir informações de forma organizada em um **Banco de Dados** (MySQL). Entender esse ciclo é a base para construir sistemas muito mais complexos no futuro.

# Exemplo de código

## inserir.php

```php
<?php
// 1. Conexão
    $dsn = "mysql:host=localhost;dbname=agenda_db;charset=utf8";
    $usuario = "root";
    $senha = "";
    
    // Conexão com o Banco de Dados
    try {
        // Criamos o objeto PDO
        $pdo = new PDO($dsn, $usuario, $senha);
    } catch (PDOException $e) { //Apenas será executado se acontecer algum erro
        die("Erro ao conectar: " . $e->getMessage());
    }


// Dados que viriam, por exemplo, de um formulário ($_POST)
$nomeNovo   = "Maria Souza";
$numeroNovo = "11 97777-6666";

// 2. PREPARAR (INSERT):
// Deixamos os "buracos" (:nome e :numero) para os dados entrarem depois
$sql = "INSERT INTO agenda (nome, numero) VALUES (:nome, :numero)";
$stmt = $pdo->prepare($sql);

// 3. EXECUTAR:
// O PDO pega os valores e os coloca no lugar dos "buracos" com segurança
$stmt->execute([
    ':nome'   => $nomeNovo,
    ':numero' => $numeroNovo
]);

// 4. CONFIRMAÇÃO:
// No INSERT, se o comando rodou, podemos pegar o ID gerado automaticamente
if ($pdo->lastInsertId()) {
    echo "Sucesso! O contato foi salvo com o ID: " . $pdo->lastInsertId();
}
?>

```
---

## visualizar.php

```php
<?php
// 1. Conexão
    $dsn = "mysql:host=localhost;dbname=agenda_db;charset=utf8";
    $usuario = "root";
    $senha = "";
    
    // Conexão com o Banco de Dados
    try {
        // Criamos o objeto PDO
        $pdo = new PDO($dsn, $usuario, $senha);
    } catch (PDOException $e) { //Apenas será executado se acontecer algum erro
        die("Erro ao conectar: " . $e->getMessage());
    }

// 2. PREPARAR e EXECUTAR:
// Como vamos listar tudo (sem filtros de usuário), podemos usar o query() direto
// Mas o prepare() continua sendo uma prática excelente por padrão
$sql = "SELECT * FROM agenda ORDER BY nome ASC";
$stmt = $pdo->prepare($sql);
$stmt->execute();


// 3. BUSCAR TODOS (fetchAll):
// O PDO::FETCH_ASSOC organiza cada linha como um array associativo ['campo' => 'valor']
$contatos = $stmt->fetchAll(PDO::FETCH_ASSOC);

// 4. EXIBIR (O laço de repetição):
echo "<h2>Lista de Contatos</h2>";

if ($contatos) {
    foreach ($contatos as $registro) {
        echo "ID: " . $registro['id'] . " | ";
        echo "Nome: " . $registro['nome'] . " | ";
        echo "Telefone: " . $registro['numero'] . "<br>";
        echo "-----------------------------------<br>";
    }
} else {
    echo "A agenda está vazia.";
}
?>

```
---

## procurar-por-id.php

```php
<?php
// 1. Conexão
    $dsn = "mysql:host=localhost;dbname=agenda_db;charset=utf8";
    $usuario = "root";
    $senha = "";
    
    // Conexão com o Banco de Dados
    try {
        // Criamos o objeto PDO
        $pdo = new PDO($dsn, $usuario, $senha);
    } catch (PDOException $e) { //Apenas será executado se acontecer algum erro
        die("Erro ao conectar: " . $e->getMessage());
    }

// O ID que queremos buscar
$idBuscado = 4;

// 2. PREPARAR: Note o uso do ":id" (um apelido/placeholder)
// Isso impede que alguém tente injetar códigos maliciosos no seu SQL
$sql = "SELECT * FROM agenda WHERE id = :id";
$stmt = $pdo->prepare($sql);

// 3. EXECUTAR: Passamos o valor real para o apelido :id
$stmt->execute([':id' => $idBuscado]);

// 4. BUSCAR: Como o ID é único, usamos fetch() em vez de fetchAll()
// O FETCH_ASSOC serve para que o resultado venha como um array ['campo' => 'valor']
$contato = $stmt->fetch(PDO::FETCH_ASSOC);

// 5. MOSTRAR OS DADOS
if ($contato) {
    echo "Nome: " . $contato['nome'] . "<br>";
    echo "Número: " . $contato['numero'];
} else {
    echo "Contato com ID $idBuscado não encontrado.";
}
?>

```
---

## alterar.php

```php
<?php
// 1. Conexão
    $dsn = "mysql:host=localhost;dbname=agenda_db;charset=utf8";
    $usuario = "root";
    $senha = "";
    
    // Conexão com o Banco de Dados
    try {
        // Criamos o objeto PDO
        $pdo = new PDO($dsn, $usuario, $senha);
    } catch (PDOException $e) { //Apenas será executado se acontecer algum erro
        die("Erro ao conectar: " . $e->getMessage());
    }

// Dados que queremos atualizar
$idParaAlterar = 4;
$novoNome = "Carlos Alberto (Etec)";
$novoNumero = "11 98888-7777";

// 2. PREPARAR (UPDATE): 
// Usamos "SET" para definir os novos valores onde o ID for igual ao selecionado
$sql = "UPDATE agenda SET nome = :novo_nome, numero = :novo_num WHERE id = :id";
$stmt = $pdo->prepare($sql);

// 3. EXECUTAR:
// Vinculamos os valores aos apelidos (:novo_nome, :novo_num, :id)
$sucesso = $stmt->execute([
    ':novo_nome' => $novoNome,
    ':novo_num'  => $novoNumero,
    ':id'         => $idParaAlterar
]);

// 4. FEEDBACK:
// É importante avisar ao usuário se deu certo
if ($sucesso) {
    // rowCount() conta quantas linhas foram afetadas no banco
    if ($stmt->rowCount() > 0) {
        echo "Sucesso! O contato ID $idParaAlterar foi atualizado.";
    } else {
        echo "O comando funcionou, mas os dados eram iguais ou o ID não existe.";
    }
} else {
    echo "Erro ao tentar atualizar.";
}
?>

```
---

## excluir.php

```php
<?php
// 1. Conexão
    $dsn = "mysql:host=localhost;dbname=agenda_db;charset=utf8";
    $usuario = "root";
    $senha = "";
    
    // Conexão com o Banco de Dados
    try {
        // Criamos o objeto PDO
        $pdo = new PDO($dsn, $usuario, $senha);
    } catch (PDOException $e) { //Apenas será executado se acontecer algum erro
        die("Erro ao conectar: " . $e->getMessage());
    }

// O ID que queremos apagar (geralmente viria de um link ou formulário)
$idParaExcluir = 4;

// 2. PREPARAR: 
// IMPORTANTE: Nunca esqueça o WHERE no DELETE, senão apaga a tabela toda!
$sql = "DELETE FROM agenda WHERE id = :id";
$stmt = $pdo->prepare($sql);

// 3. EXECUTAR:
$stmt->execute([':id' => $idParaExcluir]);

// 4. VERIFICAÇÃO:
// O rowCount nos diz se realmente alguma linha foi removida
if ($stmt->rowCount() > 0) {
    echo "Sucesso! O contato ID $idParaExcluir foi removido da agenda.";
} else {
    echo "Nenhum contato foi encontrado com o ID $idParaExcluir.";
}
?>

```
---

```sql
-- phpMyAdmin SQL Dump
-- version 5.2.1
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Tempo de geração: 06/05/2026 às 23:16
-- Versão do servidor: 10.4.32-MariaDB
-- Versão do PHP: 8.2.12

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Banco de dados: `agenda_db`
--

-- --------------------------------------------------------

--
-- Estrutura para tabela `agenda`
--

CREATE TABLE `agenda` (
  `id` int(11) NOT NULL,
  `nome` int(11) NOT NULL,
  `numero` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Índices para tabelas despejadas
--

--
-- Índices de tabela `agenda`
--
ALTER TABLE `agenda`
  ADD PRIMARY KEY (`id`);

--
-- AUTO_INCREMENT para tabelas despejadas
--

--
-- AUTO_INCREMENT de tabela `agenda`
--
ALTER TABLE `agenda`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;

```

---
