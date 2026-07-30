# O que é WAI-ARIA?

**WAI-ARIA** significa:

> **W**eb **A**ccessibility **I**nitiative – **A**ccessible **R**ich **I**nternet **A**pplications

É um conjunto de atributos criado pelo **W3C** para tornar páginas web mais acessíveis às pessoas com deficiência, especialmente usuários que utilizam:

* leitores de tela;
* navegação por teclado;
* dispositivos de acessibilidade;
* comandos de voz.

Em outras palavras:

> **O WAI-ARIA fornece informações extras para que tecnologias assistivas consigam entender corretamente os elementos da página.**

---

# Por que ele foi criado?

Nem todo elemento HTML informa claramente sua função.

Imagine este botão:

```html
<div onclick="abrirMenu()">
    Menu
</div>
```

Visualmente ele parece um botão.

Mas para um leitor de tela ele é apenas uma `<div>`.

Resultado:

O usuário cego não sabe que aquilo pode ser clicado.

Com WAI-ARIA:

```html
<div
    role="button"
    tabindex="0"
    onclick="abrirMenu()">
    Menu
</div>
```

Agora o leitor de tela entende:

> "Botão Menu"

---

# O Bootstrap utiliza WAI-ARIA?

Sim.

Grande parte dos componentes do Bootstrap já possui atributos ARIA.

Por exemplo, um menu responsivo.

```html
<button
    class="navbar-toggler"
    type="button"
    data-bs-toggle="collapse"
    data-bs-target="#menu">

    <span class="navbar-toggler-icon"></span>

</button>
```

Na documentação oficial ele aparece assim:

```html
<button
    class="navbar-toggler"
    type="button"
    data-bs-toggle="collapse"
    data-bs-target="#menu"

    aria-controls="menu"
    aria-expanded="false"
    aria-label="Abrir menu">

    <span class="navbar-toggler-icon"></span>

</button>
```

Observe os atributos:

```text
aria-controls
aria-expanded
aria-label
```

Eles não mudam o visual da página.

Servem apenas para acessibilidade.

---

# O que significa ARIA?

ARIA utiliza atributos iniciados por:

```text
aria-
```

Exemplos:

```text
aria-label
aria-hidden
aria-expanded
aria-controls
aria-current
aria-live
aria-describedby
aria-labelledby
```

---

# aria-label

É um dos mais usados.

Serve para dar um nome ao elemento.

Exemplo:

```html
<button aria-label="Fechar janela">
    X
</button>
```

O usuário enxerga:

```text
X
```

O leitor de tela anuncia:

> "Fechar janela"

---

Outro exemplo:

```html
<input
type="search"
aria-label="Pesquisar produtos">
```

---

# aria-expanded

Indica se um menu está aberto ou fechado.

```html
<button
aria-expanded="false">
```

Quando abrir:

```html
aria-expanded="true"
```

Muito utilizado em:

* menus;
* acordeões;
* dropdowns;
* navbar.

---

# aria-controls

Informa qual elemento será controlado.

```html
<button
aria-controls="menuPrincipal">
```

Depois existe:

```html
<div id="menuPrincipal">
```

Assim o leitor de tela entende a relação entre os dois elementos.

---

# aria-current

Indica qual item representa a página atual.

Exemplo:

```html
<a
href="index.html"
aria-current="page">
Início
</a>
```

O leitor anuncia:

> "Página atual: Início"

Bootstrap usa isso na Navbar.

---

# aria-hidden

Esconde um elemento das tecnologias assistivas.

Exemplo:

```html
<i
class="bi bi-house"
aria-hidden="true">
</i>
```

O ícone é apenas decorativo.

Não há necessidade do leitor dizer:

> "Casa"

---

# aria-labelledby

Liga um elemento ao título dele.

Exemplo:

```html
<h2 id="titulo">
Cadastro
</h2>

<form
aria-labelledby="titulo">
```

Assim o leitor sabe que aquele formulário pertence ao título "Cadastro".

---

# aria-describedby

Adiciona uma descrição.

```html
<input
type="password"
aria-describedby="senhaInfo">

<p id="senhaInfo">
Mínimo de oito caracteres.
</p>
```

O leitor informa essa descrição quando o campo recebe foco.

---

# role

Embora não comece com `aria-`, o atributo `role` faz parte do conjunto WAI-ARIA.

Ele informa qual é a função do elemento.

Exemplo:

```html
<div role="button">
```

Outros exemplos:

```text
role="button"

role="navigation"

role="dialog"

role="menu"

role="alert"

role="banner"

role="main"

role="search"
```

---

# Bootstrap e ARIA

Bootstrap já implementa diversos atributos automaticamente em seus exemplos.

Navbar:

```html
<button
aria-controls="navbarNav"
aria-expanded="false"
aria-label="Alternar navegação">
```

Accordion:

```html
aria-expanded="true"

aria-controls="collapseOne"
```

Collapse:

```html
aria-labelledby="headingOne"
```

Modal:

```html
aria-hidden="true"
```

---

# O que o ARIA NÃO faz?

É importante lembrar que o WAI-ARIA **não substitui o HTML semântico**.

Por exemplo, não faça isso:

```html
<div role="button">
Salvar
</div>
```

Se você pode usar:

```html
<button>
Salvar
</button>
```

O HTML semântico já possui significado próprio, suporte nativo ao teclado e comportamento esperado pelos navegadores e tecnologias assistivas. O WAI-ARIA deve ser usado para complementar a semântica quando ela não for suficiente, especialmente em componentes dinâmicos.

---

# Boas práticas

* ✅ Utilize elementos HTML semânticos (`<button>`, `<nav>`, `<main>`, `<header>`, `<footer>`) sempre que possível.
* ✅ Adicione atributos ARIA apenas quando realmente agregarem informações de acessibilidade.
* ✅ Forneça textos descritivos em `aria-label`.
* ✅ Mantenha `aria-expanded` sincronizado com o estado real do componente.
* ✅ Teste a navegação usando apenas o teclado (`Tab`, `Shift + Tab`, `Enter` e `Espaço`).

---

# Resumo

O **WAI-ARIA (Web Accessibility Initiative – Accessible Rich Internet Applications)** é um conjunto de atributos desenvolvido pelo W3C para melhorar a acessibilidade de páginas e aplicações web. Esses atributos fornecem informações adicionais às tecnologias assistivas, permitindo que leitores de tela e outros recursos de acessibilidade compreendam corretamente a função, o estado e o relacionamento entre os elementos da interface. Frameworks como o Bootstrap já utilizam diversos atributos WAI-ARIA em componentes como menus, acordeões e modais, contribuindo para a criação de sites mais inclusivos e acessíveis.
