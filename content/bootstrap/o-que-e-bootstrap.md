



# Bootstrap — Teoria

## O que é Bootstrap?

O **Bootstrap** é um framework front-end gratuito e de código aberto utilizado para desenvolver sites e aplicações web de forma rápida, organizada e responsiva.

Ele fornece uma coleção de componentes prontos, estilos CSS e funcionalidades JavaScript que reduzem o tempo de desenvolvimento e ajudam a manter um padrão visual.

Foi criado pelo Twitter (atualmente X) e hoje é um dos frameworks mais utilizados no desenvolvimento web.

---

# Por que utilizar Bootstrap?

Sem Bootstrap, o desenvolvedor precisa criar praticamente todo o CSS do projeto.

Com Bootstrap, diversos elementos já possuem estilos prontos, permitindo focar mais na lógica e no conteúdo da aplicação.

### Principais vantagens

- Desenvolvimento mais rápido.
- Layout responsivo.
- Padronização visual.
- Grande quantidade de componentes prontos.
- Fácil integração com HTML, CSS e JavaScript.
- Ampla documentação e comunidade.

---

# O que significa "Responsivo"?

Um site responsivo adapta automaticamente seu layout conforme o tamanho da tela.

Por exemplo:

- computador;
- notebook;
- tablet;
- smartphone.

Bootstrap utiliza um sistema chamado **Grid System**, baseado em 12 colunas, para organizar o conteúdo.

---

# Estrutura básica de um projeto Bootstrap

Para utilizar Bootstrap basta incluir seus arquivos CSS e JavaScript.

Exemplo:

```html
<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/css/bootstrap.min.css"
        rel="stylesheet">
</head>

<body>

    Conteúdo

    <script
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/js/bootstrap.bundle.min.js">
    </script>

</body>
</html>
```

---

# Classes

Bootstrap funciona através de **classes CSS**.

Exemplo:

```html
<p class="text-primary">
    Texto azul
</p>
```

A classe:

```text
text-primary
```

faz o texto assumir a cor principal do tema.

Outro exemplo:

```html
<div class="bg-success text-white">
    Conteúdo
</div>
```

Resultado:

- fundo verde;
- texto branco.

---

# Containers

O **Container** organiza todo o conteúdo da página.

Existem três tipos principais.

## Container fixo

```html
<div class="container">
```

Possui largura máxima definida conforme o tamanho da tela.

---

## Container fluido

```html
<div class="container-fluid">
```

Ocupa 100% da largura da janela.

---

## Container por breakpoint

```html
<div class="container-lg">
```

Só muda de largura após determinado tamanho de tela.

---

# Sistema de Grid

Bootstrap divide a tela em **12 colunas**.

Exemplo:

```html
<div class="row">

    <div class="col-6">
        Coluna 1
    </div>

    <div class="col-6">
        Coluna 2
    </div>

</div>
```

Cada coluna ocupa:

```
6 + 6 = 12
```

Logo, as duas ocupam toda a largura.

---

Outro exemplo:

```html
<div class="col-4"></div>

<div class="col-8"></div>
```

Resultado:

```
4 + 8 = 12
```

---

# Breakpoints

Bootstrap utiliza tamanhos de tela chamados **breakpoints**.

| Classe | Dispositivo aproximado |
|---------|------------------------|
| `col-` | Extra pequeno |
| `col-sm-` | ≥ 576 px |
| `col-md-` | ≥ 768 px |
| `col-lg-` | ≥ 992 px |
| `col-xl-` | ≥ 1200 px |
| `col-xxl-` | ≥ 1400 px |

Exemplo:

```html
<div class="col-12 col-md-6 col-lg-4">
```

Significa:

- celular → ocupa toda a linha;
- tablet → metade;
- computador → um terço.

---

# Componentes

Bootstrap possui diversos componentes prontos.

## Botões

```html
<button class="btn btn-primary">
    Salvar
</button>
```

Outros estilos:

```text
btn-success
btn-danger
btn-warning
btn-secondary
btn-dark
btn-light
```

---

## Alertas

```html
<div class="alert alert-success">
    Cadastro realizado com sucesso!
</div>
```

---

## Cards

```html
<div class="card">

    <div class="card-body">

        Conteúdo

    </div>

</div>
```

Muito utilizado para produtos, notícias e perfis.

---

## Navbar

Permite criar menus responsivos.

```html
<nav class="navbar navbar-expand-lg">
```

---

## Formulários

Bootstrap possui estilos para:

- caixas de texto;
- senha;
- e-mail;
- checkbox;
- radio;
- select;
- textarea;
- validação.

Exemplo:

```html
<input
type="text"
class="form-control">
```

---

# Espaçamentos

Bootstrap possui classes prontas para margem e preenchimento.

## Margin

```
m-0
m-1
m-2
m-3
m-4
m-5
```

Exemplo:

```html
<div class="m-3">
```

---

## Padding

```
p-0
p-1
p-2
p-3
p-4
p-5
```

---

Também existem:

```
mt-3
mb-3
ms-3
me-3
mx-3
my-3
```

Onde:

- **t** → top (superior)
- **b** → bottom (inferior)
- **s** → start (esquerda em idiomas LTR)
- **e** → end (direita em idiomas LTR)
- **x** → horizontal
- **y** → vertical

---

# Cores

Bootstrap possui uma paleta pronta.

| Classe | Cor |
|---------|-----|
| primary | Azul |
| secondary | Cinza |
| success | Verde |
| danger | Vermelho |
| warning | Amarelo |
| info | Azul-claro |
| light | Claro |
| dark | Escuro |

Exemplo:

```html
<div class="bg-danger text-white">
```

---

# Utilitários

Bootstrap oferece centenas de classes utilitárias.

Exemplos:

Centralizar texto:

```html
text-center
```

Negrito:

```html
fw-bold
```

Flexbox:

```html
d-flex
```

Ocultar elemento:

```html
d-none
```

Centralizar horizontalmente:

```html
mx-auto
```

---

# Ícones

Bootstrap não inclui ícones por padrão, mas disponibiliza a biblioteca **Bootstrap Icons**.

Exemplo:

```html
<i class="bi bi-house"></i>
```

---

# JavaScript no Bootstrap

Alguns componentes precisam do JavaScript do Bootstrap, como:

- Modal;
- Carousel;
- Collapse;
- Dropdown;
- Tooltip;
- Offcanvas.

Esses componentes funcionam ao incluir o arquivo:

```html
bootstrap.bundle.min.js
```

---

# Bootstrap × CSS puro

| CSS puro | Bootstrap |
|-----------|-----------|
| Todo o estilo é criado manualmente | Muitos estilos já estão prontos |
| Maior liberdade | Maior produtividade |
| Mais trabalho | Desenvolvimento mais rápido |
| Responsividade manual | Responsividade integrada |

---

# Boas práticas

- Utilize o Grid para organizar o layout.
- Prefira componentes prontos antes de criar novos estilos.
- Evite alterar diretamente os arquivos do Bootstrap.
- Crie um arquivo CSS próprio para personalizações.
- Use apenas as classes necessárias para manter o código limpo.
- Consulte a documentação oficial sempre que possível.

---

# Resumo

Bootstrap é um framework front-end que acelera o desenvolvimento de interfaces web por meio de componentes prontos, um sistema de grid responsivo e diversas classes utilitárias. Ele permite criar páginas modernas, organizadas e adaptáveis a diferentes dispositivos com menos código CSS, tornando-se uma ferramenta muito utilizada tanto em projetos acadêmicos quanto profissionais. Para estudantes, aprender Bootstrap é um passo importante para compreender conceitos de responsividade, organização de layouts e boas práticas no desenvolvimento web.