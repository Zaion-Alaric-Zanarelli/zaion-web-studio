# Fundamentos de HTML — Parte 2: Listas, Tabelas e Formulários

> **Observação:** este material utiliza **apenas HTML** (sem CSS).  
> Alguns atributos são **legados** (ex.: `bordercolor`, `bgcolor`, `align`) e hoje costumam ser substituídos por CSS — mas aqui são mantidos para prática.

---

## 1) Listas

### 1.1 Lista ordenada (`ol`)
**Para que serve:** criar uma lista numerada (1, 2, 3...) ou com outros formatos.

```html
<ol type="1">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

> O atributo `type` pode variar o estilo de numeração conforme a tabela do material da aula.

---

### 1.2 Lista ordenada encadeada (lista dentro de lista)
**Para que serve:** criar subitens (itens “dependentes” de outro item).

```html
<ol type="1">
  <li>Software Aplicativo
    <ol>
      <li>Word</li>
      <li>Excel</li>
      <li>PowerPoint</li>
    </ol>
  </li>

  <li>Programação
    <ol>
      <li>Java</li>
      <li>C#</li>
      <li>PHP</li>
    </ol>
  </li>
</ol>
```

---

### 1.3 Lista não ordenada (`ul`)
**Para que serve:** criar uma lista com marcadores (bolinhas).

Tipos de marcador (legado): `disc`, `circle`, `square`.

```html
<ul type="square">
  <li>Item A</li>
  <li>Item B</li>
  <li>Item C</li>
</ul>
```

---

### 1.4 Lista de definição (`dl`)
**Para que serve:** apresentar termos e suas definições (glossário).

```html
<dl>
  <dt>HTML</dt>
  <dd>Linguagem de marcação para páginas web.</dd>

  <dt>CSS</dt>
  <dd>Linguagem usada para estilos (não usada neste material).</dd>
</dl>
```

---

## 2) Tabelas

### 2.1 Estrutura básica (`table`, `tr`, `td`, `th`, `caption`)
**Para que serve:** organizar dados em linhas e colunas.

- `<table>`: cria a tabela
- `<tr>`: cria uma linha
- `<td>`: célula comum
- `<th>`: célula de cabeçalho (destaque)
- `<caption>`: título da tabela

Exemplo simples:
```html
<table>
  <tr>
    <td>Linha 1, coluna 1</td>
    <td>Linha 1, coluna 2</td>
  </tr>

  <tr>
    <td>Linha 2, coluna 1</td>
    <td>Linha 2, coluna 2</td>
  </tr>
</table>
```

---

### 2.2 Borda e cor (legado)
**Para que serve:** mostrar bordas e definir cor de borda/fundo sem CSS.

```html
<table border="2" bordercolor="blue" width="80%" height="80%" bgcolor="green">
  <tr>
    <td>Linha 1, Coluna 1</td>
    <td>Linha 1, Coluna 2</td>
  </tr>
  <tr>
    <td>Linha 2, Coluna 1</td>
    <td>Linha 2, Coluna 2</td>
  </tr>
</table>
```

---

### 2.3 Exemplo com `caption` e cabeçalho (`th`)
```html
<table border>
  <caption>Notas da primeira avaliação</caption>

  <tr>
    <th>Notas/Alunos</th>
    <th>Ana</th>
    <th>João</th>
    <th>Pedro</th>
  </tr>

  <tr>
    <th>Notas</th>
    <td>8.5</td>
    <td>9.0</td>
    <td>8.3</td>
  </tr>

  <tr>
    <th>Nº Inscrição</th>
    <td>12345</td>
    <td>98765</td>
    <td>56789</td>
  </tr>
</table>
```

---

### 2.4 Mesclar células (`colspan` e `rowspan`)
**Para que serve:** unir células de colunas ou linhas para organizar melhor a tabela.

- `colspan`: mescla **colunas**
- `rowspan`: mescla **linhas**

Exemplo (contatos):
```html
<table border>
  <caption align="top">Lista de contatos</caption>

  <tr>
    <th>Nome</th>
    <th>Fones</th>
    <th>Niver</th>
  </tr>

  <tr>
    <td rowspan="2">Ana</td>
    <td>4521-1234</td>
    <td rowspan="2">06/04</td>
  </tr>

  <tr>
    <td>4522-4321</td>
  </tr>

  <tr>
    <td>João</td>
    <td>4586-7890</td>
    <td>10/05</td>
  </tr>
</table>
```

---

## 3) Formulários (`form`)

**Para que serve:** coletar dados do usuário (login, senha, escolhas, mensagens etc.).

Um formulário é criado com a tag `<form>`, e dentro dele colocamos campos como `<input>`, `<textarea>` e `<select>`.

---

### 3.1 Exemplo básico de formulário
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Trabalhando com forms</title>
  </head>

  <body>
    <p>Clientes de e-mail</p>

    <form>
      Login: <input type="text" name="login"><br>
      Senha: <input type="password" name="password">
    </form>
  </body>
</html>
```

---

### 3.2 Tipos comuns de `<input type="...">`

**`text`**: entrada de texto (nome, usuário, etc.)  
```html
<input type="text" name="nome">
```

**`password`**: texto oculto (senha)  
```html
<input type="password" name="senha">
```

**`radio`**: escolher **uma opção** entre poucas  
```html
<input type="radio" name="plano" value="basico"> Básico
<input type="radio" name="plano" value="pro"> Pro
```

**`checkbox`**: escolher **várias opções**  
```html
<input type="checkbox" name="interesse" value="web"> Web
<input type="checkbox" name="interesse" value="mobile"> Mobile
```

---

### 3.3 Área de texto (`textarea`)
**Para que serve:** campo maior para mensagens/descrições.

```html
<textarea name="descricao" cols="20" rows="5">texto</textarea>
```

---

### 3.4 Lista suspensa (`select` + `option`)
**Para que serve:** menu “drop-down” com opções.

```html
<select name="servico">
  <option value="email">E-mail</option>
  <option value="agenda">Agenda</option>
  <option value="noticias">Notícias</option>
  <option value="jogos">Jogos</option>
</select>
```

---

### 3.5 Botões: `submit`, `reset` e `button`

**`button`**: botão comum (não envia automaticamente)  
```html
<input type="button" value="Oi, eu sou um botão">
```

**`submit`**: envia o formulário  
```html
<input type="submit" value="Enviar">
```

**`reset`**: limpa os campos preenchidos  
```html
<input type="reset" value="Apagar">
```

---

### 3.6 `action` do formulário
**Para que serve:** define para onde os dados do formulário serão enviados quando o usuário clicar em **Enviar** (`submit`).

```html
<form name="entrada" action="nova_pagina.html">
  <input type="text" name="login">
  <input type="submit" value="Enviar">
</form>
```

> O `action` está ligado ao envio do formulário. Em projetos reais, ele normalmente aponta para um arquivo/rota que processa os dados (ex.: PHP).
