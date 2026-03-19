# Fundamentos de HTML — Parte 1: Estrutura e Texto

> **Observação:** este material utiliza **apenas HTML** (sem CSS).  
> Alguns elementos/atributos apresentados (ex.: `align`, `bgcolor`, `font`) são **legados** e hoje costumam ser substituídos por CSS — mas aqui são mantidos por serem úteis para praticar HTML puro.

---

## 1) Estrutura básica de uma página HTML

**Para que serve:** define o “esqueleto” do documento: idioma, codificação, título da aba e o conteúdo visível.

### Exemplo mínimo
```html
<!DOCTYPE html>
<html lang="pt-br">
  <meta charset="UTF-8">

  <head>
    <title>Título a ser exibido na aba</title>
  </head>

  <body>
    Conteúdo a ser exibido na página
  </body>
</html>
```

**Explicando:**
- `<!DOCTYPE html>`: informa ao navegador que é um documento HTML5.
- `<html lang="pt-br">`: define o idioma principal do conteúdo.
- `<meta charset="UTF-8">`: permite acentuação correta.
- `<title>`: texto que aparece na aba do navegador.
- `<body>`: tudo que aparece para o usuário fica aqui.

---

## 2) Títulos (`h1` a `h6`)

**Para que serve:** criar hierarquia de títulos e subtítulos (do maior para o menor).

```html
<h1>Título em h1</h1>
<h2>Título em h2</h2>
<h3>Título em h3</h3>
<h4>Título em h4</h4>
<h5>Título em h5</h5>
<h6>Título em h6</h6>
```

---

## 3) Parágrafos e alinhamento (`p`)

**Para que serve:** organizar texto em blocos (parágrafos).  
No HTML “antigo”, é comum ver `align` para alinhar o texto.

Valores comuns:
- `center` (centralizado)
- `right` (direita)
- `left` (esquerda)
- `justify` (justificado)

```html
<p align="center">Parágrafo centralizado.</p>
<p align="right">Parágrafo à direita.</p>
<p align="left">Parágrafo à esquerda.</p>
<p align="justify">Parágrafo justificado.</p>
```

---

## 4) Quebra de linha (`br`) e linha horizontal (`hr`)

### `<br>`
**Para que serve:** quebra de linha (pula para a próxima linha) dentro de um texto.

```html
<p>
  Linha 1<br>
  Linha 2
</p>
```

### `<hr>`
**Para que serve:** inserir uma linha horizontal (separador visual).

```html
<hr size="9" color="red" width="50%" align="center">
```

**Explicando atributos (legados):**
- `size`: espessura da linha
- `color`: cor
- `width`: largura (pode ser em %)
- `align`: alinhamento

---

## 5) “Formatando” títulos com alinhamento (legado)

```html
<h1 align="center">Título em h1 centralizado</h1>
<h2 align="left">Título em h2 à esquerda</h2>
<h3 align="justify">Título em h3 justificado</h3>
<h6 align="right">Título em h6 à direita</h6>
<hr color="red" width="50%">
```

---

## 6) Corpo da página (`body`) com cores (legado)

**Para que serve:** definir cor de fundo e cor do texto usando atributos (sem CSS).

```html
<body bgcolor="#ADD8E6" text="#800000">
  A página terá fundo azul claro e letras em vermelho escuro.
</body>
```

> Dica: para encontrar códigos de cores em hexadecimal, use uma tabela de cores HTML.

---

## 7) Fontes com a tag `<font>` (legado)

**Para que serve:** alterar tamanho, cor e tipo de fonte (sem CSS).

```html
<font size="12pt" color="#800000" face="Arial">
  Texto com fonte, tamanho e cor definidos.
</font>
```

> Observação: em projetos atuais, a formatação é feita com CSS. Aqui usamos `<font>` apenas para treinar HTML puro.

---

## 8) Imagens (`img`) e plano de fundo (legado)

**Para que serve:** mostrar imagens no site.

Formatos comuns: `gif`, `jpg`, `jpeg`, `bmp`.

```html
<img src="imagem.gif" align="middle">
```

**Explicando `align` (legado):**
- `top`: texto alinhado ao topo da imagem
- `middle`: texto alinhado ao meio
- `bottom`: texto alinhado à base

Plano de fundo (legado):
```html
<body background="imagem.gif">
  Conteúdo da página...
</body>
```

---

## 9) Links (âncoras) com `<a>`

**Para que serve:** criar links para páginas do site ou para sites externos.

### Link para outra página do projeto
```html
<a href="pagina.html">Ir para outra página</a>
```

### Link para um site externo
```html
<a href="https://exemplo.com">Abrir site</a>
```

### Link em imagem
```html
<a href="pagina.html">
  <img src="botao.png" align="middle">
</a>
```

---

## 10) Link para a mesma página (âncora interna)

**Para que serve:** pular para uma seção do mesmo documento (útil para FAQ / sumário).

1) Crie o link com `href="#id"`  
2) Marque a seção de destino com `id="..."`

```html
<a href="#duvidas">Ir para Dúvidas Frequentes</a>

<h2 id="duvidas">Dúvidas Frequentes</h2>
<p>Conteúdo da seção...</p>
```

> O uso do `#` é obrigatório no `href`.

---

## 11) Exemplo completo (HTML puro)

```html
<!DOCTYPE html>
<html lang="pt-br">
  <meta charset="UTF-8">

  <head>
    <title>Primeira página</title>
  </head>

  <body bgcolor="#ADD8E6" text="#800000">
    <h1 align="center">Título em h1</h1>
    <h2 align="left">Título em h2</h2>
    <h3>Título em h3</h3>
    <h4>Título em h4</h4>
    <h5>Título em h5</h5>
    <h6 align="right">Título em h6</h6>

    <hr color="red" width="50%">

    <p>
      Formatação de parágrafo com quebra de<br>
      linha
    </p>
  </body>
</html>
```
