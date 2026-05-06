# PDO (PHP Data Objects)

### 📖 Explicando o `include`


Nos exemplos anteriores([php-crud-pdo.md](php-crud-pdo.md)), existe um conjunto de códigos que acaba se repetindo em vários arquivos, principalmente a parte responsável pela conexão com o banco de dados. Quando repetimos muito o mesmo código, o projeto fica mais difícil de organizar e manter.

Uma forma de resolver isso é criar um arquivo separado chamado `conexao.php`, contendo apenas a conexão com o banco. Depois, utilizamos o comando `include` para “importar” esse arquivo dentro de outros arquivos PHP, como `inserir.php`, `listar.php` ou `editar.php`.

O comando `include` funciona como uma forma de reaproveitar código. Assim, se for necessário alterar a conexão futuramente, basta modificar apenas o arquivo `conexao.php`, sem precisar alterar todos os outros arquivos do sistema. Isso deixa o código mais organizado, profissional e fácil de entender.

## Na prática:

*   **O que ele faz:** O comando `include` pega todo o conteúdo de um arquivo externo e o coloca exatamente naquela linha onde o comando foi escrito.
*   **Vantagem principal:** Manutenção. Se o nome do seu banco de dados mudar, você altera apenas o `conexao.php` e, magicamente, todos os outros arquivos (`inserir.php`, `listar.php` ou `editar.php`) já estarão atualizados, pois todos eles "leem" o mesmo arquivo de conexão.

**Dica extra:** Existe também o `require`. A diferença é que, se o arquivo não existir, o `include` apenas dá um aviso e tenta continuar, enquanto o `require` para tudo (é mais rigoroso, o que geralmente é melhor para conexões de banco de dados).

---

## Exemplo PDO usando include/require

## conexao.php

```php
<?php

$servidor = "localhost";
$banco = "agenda_db";
$usuario = "root";
$senha = "";

try {

    $conexao = new PDO(
        "mysql:host=$servidor;dbname=$banco",
        $usuario,
        $senha
    );

    echo "Conexão realizada com sucesso!";

} catch(PDOException $erro) {

    echo "Erro na conexão: " . $erro->getMessage();

}

?>
```


---

No exemplo a seguir (inserir.php), o `require "conexao.php";` faz com que o arquivo `inserir.php` utilize a conexão já criada anteriormente. Dessa forma, evitamos repetir código e tornamos o projeto mais organizado.

---

## inserir.php

```
<?php
// 1. Conexão

require 'conexao.php';


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
## 🚀 Dica de Ouro: `require_once`

- No mercado de trabalho, o mais comum é usar o `require_once`. Ele faz a mesma coisa que o `require`, mas com uma inteligência extra: ele verifica se o arquivo já foi puxado antes. Se você, por acidente, tentar dar `require` na conexão duas vezes, o PHP ignora a segunda tentativa, evitando erros de "variável já declarada".

- Uma das técnicas mais utilizadas por programadores profissionais para manter o site organizado, o `require_once` para blocos de HTML. Imagine que o seu site tem 10 páginas. Todas elas têm o mesmo **topo** (logotipo e menu) e o mesmo **rodapé** (contatos e redes sociais). Se você precisar mudar o telefone no rodapé, sem o `require`, você teria que abrir os 10 arquivos. Com o `require`, você muda em apenas **um**.

Aqui está como estruturamos isso de forma prática:

---

### 1. Crie o arquivo `cabecalho.php`
Este arquivo contém apenas a parte de cima do seu HTML.

```php
<!-- cabecalho.php -->
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Agenda Etec VAV</title>
    <style>
        body { font-family: Arial; background: #eee; }
        nav { background: #333; color: white; padding: 10px; }
        nav a { color: white; margin-right: 15px; text-decoration: none; }
    </style>
</head>
<body>
    <nav>
        <strong>Etec VAV</strong>
        <a href="index.php">Início</a>
        <a href="inserir.php">Novo Contato</a>
    </nav>
    <hr>
```

### 2. Crie o arquivo `rodape.php`
Este contém o fechamento das tags e informações finais.

```php
<!-- rodape.php -->
    <hr>
    <footer>
        <p>&copy; 2026 - Desenvolvido pela Turma de Informática - Etec Albert Einstein</p>
    </footer>
</body>
</html>
```

### 3. Como ficam suas páginas (ex: `index.php`)
Agora a página principal fica limpa e foca apenas no conteúdo dela.

```php
<?php 
  require 'conexao.php'; // Puxa o banco
  require 'cabecalho.php'; // Puxa o topo visual
?>

<h2>Bem-vindo à Agenda</h2>
<p>Aqui você pode gerenciar seus contatos de forma rápida.</p>

<?php 
  require 'rodape.php'; // Puxa o final do site
?>
```

---

### 🧠 Por que isso é bom?

*   **Padronização:** Você garante que todas as páginas do sistema tenham a mesma aparência. Se o cabeçalho estiver bonito na página inicial, estará bonito em todas.
*   **Organização de Código:** O arquivo `index.php` não fica com 200 linhas de HTML misturadas com PHP. Ele fica curto e fácil de ler.
*   **Escalabilidade:** Se o cliente pedir para adicionar uma página de "Sobre", você cria o arquivo, dá o `require` no cabeçalho e no rodapé, e em 30 segundos a página nova está com a cara do resto do site.

---