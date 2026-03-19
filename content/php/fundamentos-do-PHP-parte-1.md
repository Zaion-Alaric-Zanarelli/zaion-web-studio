# 📘 PHP Básico --- Soma de Dois Números (GET e POST)

## 🎯 Objetivo

Explicar comandos básicos do **PHP** e como ele **recebe** e
**dá saída** (mostra na tela) de informações.

Você vai criar dois arquivos:

- `index.php` → página com **HTML + formulário**

- `calcula.php` → página que **recebe os números**, faz a
**soma** e mostra o resultado

---

# ✅ Parte 1 --- Método GET

## 📄 1) Arquivo `index.php` (GET)

```php
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Soma com PHP (GET)</title>
</head>
<body>

  <h1>Soma de dois números (GET)</h1>

  <form action="calcula.php" method="get">
    <label>Primeiro número:</label>
    <input type="number" name="n1" step="any" required>
    <br><br>

    <label>Segundo número:</label>
    <input type="number" name="n2" step="any" required>
    <br><br>

    <input type="submit" value="Calcular soma">
  </form>

</body>
</html>
```

### 🧠 Explicação linha a linha --- index.php

-   ```<!DOCTYPE html>``` → define que o documento é **HTML5**.

-   ```<html lang="pt-br">``` → define o idioma da página.

-   ```<head>``` → parte de configurações (não aparece na página).

-   ```<meta charset="UTF-8">``` → permite acentuação correta.

-   ```<title>...</title>``` → título que aparece na aba do navegador.

-   ```<body>``` → conteúdo visível na página.

-   ```<h1>...</h1>``` → título principal exibido ao usuário.

**Formulário:**

-   ```<form action="calcula.php" method="get">```

    -   action="calcula.php" → envia os dados para o arquivo calcula.php.

    -   method="get" → envia os dados pela **URL**.

**Campos:**

-   ```<label>...</label>``` → texto explicando o campo.

-   ```<input type="number" ...>``` → campo para digitar número.

-   name="n1" e name="n2" → nomes que o PHP usa para pegar os
    > valores.

-   step="any" → permite números com decimais (ex.: 2.5).

-   required → obriga preencher antes de enviar.

-   ```<br><br>``` → quebra linha e dá espaço.

-   ```<input type="submit" ...>``` → botão que envia o formulário.

## 📄 2) Arquivo calcula.php (GET)
```
<?php

$n1 = $_GET["n1"];

$n2 = $_GET["n2"];

$soma = $n1 + $n2;

?>

<!DOCTYPE html>

<html lang="pt-br">

<head>

<meta charset="UTF-8">

<title>Resultado (GET)</title>

</head>

<body>

<h1>Resultado da Soma (GET)</h1>

<p>Primeiro número: <?php echo $n1; ?></p>

<p>Segundo número: <?php echo $n2; ?></p>

<p><strong>Soma: <?php echo $soma; ?></strong></p>

<a href="index.php">Voltar</a>

</body>

</html>
```
### 🧠 Explicação linha a linha --- calcula.php

-  ``` <?php``` → início do código PHP.

-   $n1 = $_GET["n1"];

    -   cria a variável $n1

    -   pega o valor enviado pelo formulário com o nome n1 usando
        > **GET**.

-   $n2 = $_GET["n2"]; → faz o mesmo com o segundo número.

-   $soma = $n1 + $n2; → soma os dois valores.

-   ?> → final do trecho PHP (voltamos para HTML).

**Saída na tela:**

-   ```<?php echo $n1; ?>``` → mostra o valor de $n1.

-   echo → comando do PHP para **imprimir na tela**.

-   ```<?php echo $soma; ?>``` → mostra a soma calculada.

-   ```<a href="index.php">Voltar</a>``` → link para voltar ao
    > formulário.

# ✅ Parte 2 --- Método POST (explicar apenas o que mudou)

## 🔁 O que muda no index.php

Troque apenas o método do formulário:

**Antes (GET):**

```<form action="calcula.php" method="get">```

Agora (POST):

```<form action="calcula.php" method="post">```

## 🔁 O que muda no calcula.php

Troque apenas $_GET por $_POST:

**Antes (GET):**

`$n1 = $_GET["n1"];`

`$n2 = $_GET["n2"];`

Agora (POST):

`$n1 = $_POST["n1"];`

`$n2 = $_POST["n2"];`

O resto do arquivo permanece igual.

# 🔍 Diferença entre GET e POST (explicação simples)

## ✅ GET

-   Envia os dados pela **URL**.

-   Exemplo de URL:

    -   calcula.php?n1=10&n2=5

-   Bom para:

    -   buscas

    -   filtros

    -   páginas onde faz sentido "ver" os parâmetros

-   Não é recomendado para:

    -   senha

    -   dados pessoais

## ✅ POST

-   Envia os dados "por dentro" da requisição (não aparece na URL).

-   Bom para:

    -   formulários com muitos dados

    -   informações mais sensíveis (como senha)

    -   envio de textos maiores

-   Mais adequado quando:

    -   você não quer que os valores fiquem visíveis na URL

# ✅ Resumo Final

-   GET → dados aparecem na URL → usa $_GET

-   POST → dados não aparecem na URL → usa $_POST

-   PHP recebe dados do formulário usando $_GET ou $_POST

-   PHP mostra dados na tela usando echo

## 📌 Lembre-se

| Característica | GET | POST |
|---------------|------|------|
| Dados aparecem na URL? | Sim | Não |
| Segurança | Menor | Maior |
| Indicado para | Buscas e filtros | Cadastros e formulários |

---

# 🧠 Conclusão

- HTML cria o formulário.
- PHP recebe os dados.
- `$_GET` e `$_POST` capturam os valores enviados.
- `echo` exibe os resultados.
- GET e POST fazem praticamente a mesma coisa, mas diferem na forma como enviam os dados.

✅ Com isso, você aprendeu como o PHP recebe dados de um formulário e
exibe resultados na tela.

---   
