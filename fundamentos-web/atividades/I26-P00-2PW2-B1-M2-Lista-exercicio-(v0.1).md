# Introdução a Cookies e Sessions no PHP

## 1. Introdução

Em aplicações web, cada requisição HTTP é **independente**. Isso significa que, por padrão, o servidor não "lembra" das informações de uma requisição anterior.

Por exemplo:

- um usuário faz login
- navega para outra página
- o servidor precisa reconhecer que ele já está autenticado

Para resolver esse problema utilizamos **mecanismos de persistência de dados**, como:

- **Cookies**
- **Sessions**

Esses mecanismos permitem que aplicações web mantenham informações entre diferentes requisições, possibilitando funcionalidades como:

- login de usuários
- carrinhos de compras
- preferências do usuário
- personalização da aplicação

Neste material, vamos explorar como utilizar **cookies e sessions no PHP**.

---

# 2. Conceitos fundamentais

## setcookie()

A função `setcookie()` é utilizada para **criar ou modificar um cookie** no navegador do usuário.

Cookies são pequenos dados armazenados **no navegador do cliente**, e são enviados automaticamente ao servidor em cada requisição HTTP para o mesmo domínio.

Eles podem ser usados para:

- guardar preferências do usuário
- identificar visitantes
- armazenar pequenas informações de sessão

Exemplo simples:

```php
<?php

setcookie("usuario", "Ana", time() + 3600);

echo "Cookie criado!";
?>
```

Neste exemplo:

- o cookie se chama **usuario**
- o valor é **Ana**
- ele expira em **1 hora**

---

## $_COOKIE

`$_COOKIE` é uma **variável superglobal do PHP** utilizada para acessar cookies enviados pelo navegador.

Quando um cookie já existe no navegador, ele pode ser acessado usando esse array.

Exemplo:

```php
<?php

if(isset($_COOKIE["usuario"])) {
    echo "Usuário: " . $_COOKIE["usuario"];
} else {
    echo "Cookie não encontrado.";
}

?>
```

Esse código verifica se o cookie existe antes de utilizá-lo.

---

## session_start()

`session_start()` inicia ou continua uma **sessão no PHP**.

Sessions são utilizadas para armazenar informações **no servidor**, enquanto apenas um identificador da sessão é enviado ao navegador.

Isso torna as sessions mais seguras para armazenar informações sensíveis.

A função `session_start()` deve ser chamada **antes de qualquer saída HTML**.

Exemplo:

```php
<?php

session_start();

$_SESSION["usuario"] = "Ana";

echo "Sessão iniciada.";

?>
```

---

## $_SESSION

`$_SESSION` é um array superglobal usado para **armazenar dados da sessão**.

Esses dados permanecem disponíveis enquanto a sessão estiver ativa.

Exemplo:

```php
<?php

session_start();

$_SESSION["visitas"] = 1;

echo "Visitas: " . $_SESSION["visitas"];

?>
```

Cada página que usar a sessão precisa executar `session_start()`.

---

## session_destroy()

A função `session_destroy()` é utilizada para **encerrar uma sessão** e remover seus dados do servidor.

Ela é muito usada em sistemas de **logout**.

Exemplo:

```php
<?php

session_start();

session_destroy();

echo "Sessão encerrada.";

?>
```

Após destruir a sessão, as variáveis de `$_SESSION` deixam de existir.

---

## Comparação entre Cookies e Sessions

Cookies e sessions possuem objetivos semelhantes, mas funcionam de formas diferentes.

**Cookies**

- armazenados no **navegador do usuário**
- possuem tamanho limitado
- podem ser manipulados pelo usuário
- permanecem mesmo após fechar o navegador (se tiverem tempo de expiração)

**Sessions**

- dados armazenados **no servidor**
- mais seguras
- usadas frequentemente para autenticação
- normalmente terminam quando o navegador é fechado ou quando o logout ocorre

Em muitas aplicações, cookies e sessions são utilizados **juntos**.

---

# 3. Exemplo prático

A seguir está um pequeno sistema demonstrando o uso de **cookies e sessions**.

## login.php

```php
<?php
session_start();

if(isset($_POST["nome"])) {

    $nome = $_POST["nome"];

    $_SESSION["usuario"] = $nome;

    setcookie("ultimo_login", date("H:i:s"), time()+3600);

    header("Location: painel.php");
}

?>

<form method="post">
Nome:
<input type="text" name="nome">
<button type="submit">Entrar</button>
</form>
```

---

## painel.php

```php
<?php
session_start();

if(!isset($_SESSION["usuario"])) {
    header("Location: login.php");
}

echo "Bem-vindo, " . $_SESSION["usuario"] . "<br>";

if(isset($_COOKIE["ultimo_login"])) {
    echo "Último login: " . $_COOKIE["ultimo_login"];
}

echo "<br><a href='logout.php'>Sair</a>";
?>
```

---

## logout.php

```php
<?php
session_start();

session_destroy();

echo "Logout realizado.<br>";

echo "<a href='login.php'>Voltar ao login</a>";
?>
```

---

# 4. Exercícios

## Exercício 1 — Pergunta conceitual

Explique a diferença entre **cookies e sessions** no PHP.

Em sua resposta, considere:

- onde os dados são armazenados
- quais são mais seguros
- em quais situações cada um pode ser mais adequado.

---

## Exercício 2 — Pergunta de aplicação

Imagine que você está desenvolvendo um sistema de **loja virtual**.

Explique como cookies e sessions poderiam ser utilizados para:

- manter o usuário logado
- armazenar itens temporários no carrinho
- registrar preferências do usuário.

Justifique suas escolhas.

---

## Exercício 3 — Pergunta de investigação

Crie um arquivo chamado `teste.php` com o seguinte código:

```php
<?php

setcookie("contador", "1", time()+3600);

if(isset($_COOKIE["contador"])) {
    echo "Valor do cookie: " . $_COOKIE["contador"];
} else {
    echo "Cookie ainda não disponível.";
}

?>
```

Agora realize os seguintes passos:

1. Execute o arquivo no navegador.
2. Atualize a página.
3. Abra as ferramentas do navegador e visualize os cookies.
4. Limpe os cookies do site e atualize novamente.

Descreva:

- o que aconteceu em cada etapa
- por que o cookie não aparece imediatamente na primeira execução.

---

## Exercício 4 — Pergunta de reflexão

Por que **sessions são geralmente preferidas para autenticação de usuários** em sistemas web?

Discuta:

- segurança
- manipulação de dados
- possíveis riscos ao utilizar apenas cookies.

---

# 5. Instruções para os alunos

Esta atividade será realizada **em grupo**.

### Regras da atividade

- Modalidade: **em grupo**
- Local da entrega: **repositório GitHub do grupo**
- Formato da entrega: **arquivo Markdown**
- Nome do arquivo: **1BIM-M3-cookie-session.md**

### Organização das respostas

Cada aluno do grupo deverá:

- escolher **uma questão**
- responder **apenas uma questão**

Cada resposta deve:

- ter entre **5 e 10 linhas**
- ser clara
- apresentar explicação organizada

### Regras do repositório

O repositório deve demonstrar participação de todos.

Cada aluno deve:

- realizar **seus próprios commits**
- contribuir com suas alterações no arquivo
- evitar apenas **um commit final**

O histórico de commits deve mostrar a contribuição de cada integrante.

Caso utilizem fontes externas:

- incluir os **links das referências utilizadas**.

---

# 6. Critérios de avaliação

Serão observados os seguintes critérios:

- clareza e organização das respostas
- qualidade da pesquisa realizada
- aplicação correta dos conceitos estudados
- capacidade de explicação e argumentação
- organização do documento Markdown
- participação no repositório GitHub

---

# 7. Referências

Documentação oficial PHP:

https://www.php.net/manual/pt_BR/

Cookies no PHP:

https://www.php.net/manual/pt_BR/function.setcookie.php

Sessions no PHP:

https://www.php.net/manual/pt_BR/book.session.php

MDN Web Docs — HTTP Cookies:

https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Cookies

Livro recomendado:

- **PHP e MySQL: Desenvolvimento Web**
