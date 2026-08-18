## Leia tudo atentamente e **DEPOIS** teste os exemplos do texto.

# 🎨 Aula — Efeitos Avançados com HTML, CSS e Bootstrap

## Objetivo

Aprender a utilizar recursos visuais do CSS para melhorar a aparência e a interação de páginas web.

Nesta aula, vamos trabalhar com:

* sombras;
* transparência e mesclagem;
* filtros;
* transformações;
* transições;
* animações;
* efeitos de interação com `hover`;
* combinação com componentes do Bootstrap.

---

# 1. Preparando o projeto

Crie a seguinte estrutura:

```text
efeitos-css/
│
├── index.html
└── css/
    └── style.css
```

No arquivo `index.html`, adicione o Bootstrap:

```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1">

    <title>Efeitos CSS</title>

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

    <link rel="stylesheet" href="css/style.css">
</head>

<body>

    <div class="container py-5">

        <h1 class="mb-4">Efeitos avançados com CSS</h1>

    </div>

</body>

</html>
```

---

# 2. Sombras

O CSS possui duas propriedades bastante utilizadas para criar sombras:

```css
box-shadow
```

e:

```css
text-shadow
```

## Sombra em elementos

Adicione ao HTML:

```html
<div class="card shadow-example">
    <div class="card-body">
        <h2>Card com sombra</h2>

        <p>
            Este elemento utiliza a propriedade
            box-shadow.
        </p>
    </div>
</div>
```

No CSS:

```css
.shadow-example {
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
}
```

A estrutura é:

```text
box-shadow:
deslocamento-horizontal
deslocamento-vertical
desfoque
cor
```

Exemplo:

```css
box-shadow: 5px 5px 10px gray;
```

---

# 3. Sombra em textos

HTML:

```html
<h2 class="title-shadow">
    Desenvolvimento Web
</h2>
```

CSS:

```css
.title-shadow {
    font-size: 3rem;

    text-shadow: 3px 3px 5px rgba(0, 0, 0, 0.4);
}
```

Experimente modificar:

```css
3px 3px 5px
```

e observe o resultado.

---

# 4. Bootstrap também possui sombras

O Bootstrap possui classes prontas:

```html
<div class="p-4 shadow-sm">
    Sombra pequena
</div>

<div class="p-4 shadow">
    Sombra normal
</div>

<div class="p-4 shadow-lg">
    Sombra grande
</div>
```

Isso mostra uma diferença importante:

> O Bootstrap oferece efeitos prontos, enquanto o CSS permite personalizar os efeitos.

---

# 5. Transparência

Podemos modificar a transparência utilizando:

```css
opacity
```

HTML:

```html
<img
    src="https://picsum.photos/400/250"
    class="image-opacity"
    alt="Imagem de exemplo">
```

CSS:

```css
.image-opacity {
    opacity: 0.5;
}
```

O valor pode variar entre:

```text
0   → totalmente transparente

1   → totalmente visível
```

Exemplo:

```css
opacity: 0.8;
```

---

# 6. Transparência ao passar o mouse

Podemos utilizar:

```css
:hover
```

HTML:

```html
<img
    src="https://picsum.photos/401/250"
    class="image-hover"
    alt="Imagem de exemplo">
```

CSS:

```css
.image-hover {
    opacity: 0.6;
}

.image-hover:hover {
    opacity: 1;
}
```

Agora a imagem fica totalmente visível quando o usuário passa o mouse.

---

# 7. Filtros

A propriedade:

```css
filter
```

permite aplicar efeitos em imagens.

## Escala de cinza

```css
.gray-image {
    filter: grayscale(100%);
}
```

HTML:

```html
<img
    src="https://picsum.photos/402/250"
    class="gray-image"
    alt="Imagem">
```

---

# 8. Outros filtros

### Desfoque

```css
filter: blur(3px);
```

### Brilho

```css
filter: brightness(150%);
```

### Contraste

```css
filter: contrast(150%);
```

### Saturação

```css
filter: saturate(200%);
```

### Sépia

```css
filter: sepia(100%);
```

---

# 9. Combinando filtros

É possível aplicar mais de um filtro:

```css
.effect-image {
    filter:
        grayscale(40%)
        contrast(120%)
        brightness(110%);
}
```

---

# 10. Filtro com interação

Um efeito bastante utilizado em galerias:

```css
.photo-effect {
    filter: grayscale(100%);
}

.photo-effect:hover {
    filter: grayscale(0%);
}
```

HTML:

```html
<img
    src="https://picsum.photos/403/250"
    class="photo-effect"
    alt="Fotografia">
```

Ao passar o mouse, a cor da imagem retorna.

---

# 11. Transformações

A propriedade:

```css
transform
```

permite alterar visualmente um elemento.

Podemos:

* mover;
* girar;
* aumentar;
* diminuir;
* inclinar.

---

# 12. Aumentando um elemento

```css
.scale-example:hover {
    transform: scale(1.1);
}
```

HTML:

```html
<button class="btn btn-primary scale-example">
    Passe o mouse
</button>
```

`scale(1.1)` significa aumentar o elemento em aproximadamente 10%.

---

# 13. Rotação

```css
.rotate-example:hover {
    transform: rotate(10deg);
}
```

HTML:

```html
<div class="card p-4 rotate-example">
    Girar
</div>
```

Também podemos usar:

```css
rotate(-10deg)
```

para girar no sentido contrário.

---

# 14. Movimento

Utilizamos:

```css
translate()
```

Exemplo:

```css
.move-example:hover {
    transform: translateY(-10px);
}
```

O elemento se moverá:

```text
10 pixels para cima.
```

Outro exemplo:

```css
transform: translateX(20px);
```

move o elemento horizontalmente.

---

# 15. Inclinação

Podemos utilizar:

```css
transform: skew(10deg);
```

Exemplo:

```css
.skew-example:hover {
    transform: skew(-5deg);
}
```

---

# 16. O problema das mudanças instantâneas

Observe:

```css
.card-effect:hover {
    transform: scale(1.1);
}
```

A mudança acontece imediatamente.

Visualmente, pode parecer brusca.

É nesse momento que utilizamos:

```css
transition
```

---

# 17. Transições

A propriedade `transition` permite criar mudanças suaves.

```css
.card-effect {
    transition: 0.3s;
}

.card-effect:hover {
    transform: scale(1.05);
}
```

Agora o crescimento acontece gradualmente.

---

# 18. Transição de várias propriedades

Podemos utilizar:

```css
.card-effect {
    transition: all 0.3s ease;
}
```

Exemplo completo:

```css
.card-effect {
    transition: all 0.3s ease;
}

.card-effect:hover {
    transform: translateY(-8px);

    box-shadow:
        0 12px 25px
        rgba(0, 0, 0, 0.25);
}
```

---

# 19. Entendendo `ease`

Podemos modificar a velocidade da transição.

```css
transition: all 0.5s ease;
```

Algumas opções:

```text
linear
ease
ease-in
ease-out
ease-in-out
```

Experimente:

```css
transition: all 1s linear;
```

e depois:

```css
transition: all 1s ease-in-out;
```

Compare os resultados.

---

# 20. Botão com efeito

HTML:

```html
<button class="btn btn-primary button-effect">
    Saiba mais
</button>
```

CSS:

```css
.button-effect {
    transition: all 0.3s ease;
}

.button-effect:hover {
    transform: scale(1.08);

    box-shadow:
        0 6px 15px
        rgba(0, 0, 0, 0.25);
}
```

Neste exemplo temos:

```text
Bootstrap
+
Transformação
+
Transição
+
Sombra
```

---

# 21. Card interativo

HTML:

```html
<div class="card product-card">

    <img
        src="https://picsum.photos/500/300"
        class="card-img-top"
        alt="Produto">

    <div class="card-body">

        <h3 class="card-title">
            Produto
        </h3>

        <p class="card-text">
            Exemplo de card com efeito.
        </p>

        <button class="btn btn-primary">
            Ver detalhes
        </button>

    </div>

</div>
```

CSS:

```css
.product-card {
    overflow: hidden;

    transition: all 0.3s ease;
}

.product-card:hover {
    transform: translateY(-10px);

    box-shadow:
        0 15px 30px
        rgba(0, 0, 0, 0.2);
}
```

---

# 22. Criando efeito na imagem do Card

Agora:

```css
.product-card img {
    transition: transform 0.5s ease;
}

.product-card:hover img {
    transform: scale(1.1);
}
```

Ao passar o mouse sobre o card:

```text
Card sobe
+
Sombra aumenta
+
Imagem aumenta
```

---

# 23. Animações

Transições normalmente dependem de alguma alteração de estado, como:

```text
:hover
```

Já as animações podem executar automaticamente.

Para isso utilizamos:

```css
@keyframes
```

---

# 24. Primeira animação

HTML:

```html
<div class="animation-box">
    Animação
</div>
```

CSS:

```css
.animation-box {
    animation: move 2s infinite alternate;
}

@keyframes move {

    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

O elemento ficará se movimentando.

---

# 25. Animação com porcentagens

Também podemos controlar várias etapas.

```css
@keyframes example {

    0% {
        transform: translateX(0);
    }

    50% {
        transform: translateX(100px);
    }

    100% {
        transform: translateX(0);
    }
}
```

---

# 26. Animação de entrada

Um efeito bastante utilizado é o `fade-in`.

```css
.fade-in {
    animation: fadeIn 1s ease;
}

@keyframes fadeIn {

    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

HTML:

```html
<h2 class="fade-in">
    Bem-vindo ao site
</h2>
```

---

# 27. Fade + movimento

Podemos melhorar:

```css
.fade-up {
    animation: fadeUp 0.8s ease;
}

@keyframes fadeUp {

    from {
        opacity: 0;

        transform:
            translateY(30px);
    }

    to {
        opacity: 1;

        transform:
            translateY(0);
    }
}
```

Agora o elemento:

```text
aparece
+
move-se para cima
```

---

# 28. Efeito pulsante

HTML:

```html
<button class="btn btn-danger pulse">
    Atenção
</button>
```

CSS:

```css
.pulse {
    animation: pulseEffect 1.5s infinite;
}

@keyframes pulseEffect {

    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.1);
    }

    100% {
        transform: scale(1);
    }
}
```

Esse tipo de efeito deve ser utilizado com cuidado.

Animações excessivas podem:

* distrair o usuário;
* prejudicar a leitura;
* tornar a página cansativa;
* causar problemas de acessibilidade.

---

# 29. Mesclagem de imagens e cores

O CSS possui propriedades como:

```css
mix-blend-mode
```

e:

```css
background-blend-mode
```

que permitem combinar cores e imagens.

Exemplo:

```html
<div class="blend-example">
    <h2>Desenvolvimento Web</h2>
</div>
```

CSS:

```css
.blend-example {
    min-height: 300px;

    background:
        rgba(0, 0, 255, 0.4)
        url("https://picsum.photos/700/400");

    background-size: cover;

    background-blend-mode: multiply;

    display: flex;

    align-items: center;

    justify-content: center;

    color: white;
}
```

O navegador combina:

```text
Imagem
+
Cor
+
Modo de mesclagem
```

---

# 30. Gradientes

Também podemos criar efeitos utilizando gradientes.

```css
.gradient-example {
    background:
        linear-gradient(
            135deg,
            #0d6efd,
            #6610f2
        );

    color: white;

    padding: 50px;
}
```

HTML:

```html
<div class="gradient-example">
    <h2>CSS + Bootstrap</h2>

    <p>
        Exemplo utilizando gradiente.
    </p>
</div>
```

---

# 31. Gradiente sobre imagem

Um efeito muito utilizado em banners:

```css
.hero {
    min-height: 400px;

    background:
        linear-gradient(
            rgba(0, 0, 0, 0.3),
            rgba(0, 0, 0, 0.8)
        ),
        url("https://picsum.photos/1000/500");

    background-size: cover;

    background-position: center;

    display: flex;

    align-items: center;

    color: white;
}
```

HTML:

```html
<section class="hero">

    <div class="container">

        <h1>
            Desenvolvimento Web
        </h1>

        <p>
            HTML, CSS e Bootstrap.
        </p>

    </div>

</section>
```

---

# 32. Exemplo completo: cards modernos

HTML:

```html
<div class="container py-5">

    <div class="row g-4">

        <div class="col-12 col-md-4">

            <div class="card modern-card">

                <img
                    src="https://picsum.photos/500/300?1"
                    class="card-img-top"
                    alt="Imagem">

                <div class="card-body">

                    <h3 class="card-title">
                        HTML
                    </h3>

                    <p class="card-text">
                        Estrutura das páginas Web.
                    </p>

                    <a
                        href="#"
                        class="btn btn-primary">
                        Saiba mais
                    </a>

                </div>

            </div>

        </div>

        <div class="col-12 col-md-4">

            <div class="card modern-card">

                <img
                    src="https://picsum.photos/500/300?2"
                    class="card-img-top"
                    alt="Imagem">

                <div class="card-body">

                    <h3 class="card-title">
                        CSS
                    </h3>

                    <p class="card-text">
                        Aparência e efeitos visuais.
                    </p>

                    <a
                        href="#"
                        class="btn btn-primary">
                        Saiba mais
                    </a>

                </div>

            </div>

        </div>

        <div class="col-12 col-md-4">

            <div class="card modern-card">

                <img
                    src="https://picsum.photos/500/300?3"
                    class="card-img-top"
                    alt="Imagem">

                <div class="card-body">

                    <h3 class="card-title">
                        Bootstrap
                    </h3>

                    <p class="card-text">
                        Desenvolvimento responsivo.
                    </p>

                    <a
                        href="#"
                        class="btn btn-primary">
                        Saiba mais
                    </a>

                </div>

            </div>

        </div>

    </div>

</div>
```

CSS:

```css
.modern-card {
    overflow: hidden;

    border: 0;

    transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
}

.modern-card img {
    transition:
        transform 0.5s ease,
        filter 0.5s ease;

    filter: saturate(80%);
}

.modern-card:hover {
    transform: translateY(-10px);

    box-shadow:
        0 15px 30px
        rgba(0, 0, 0, 0.2);
}

.modern-card:hover img {
    transform: scale(1.08);

    filter: saturate(120%);
}

.modern-card .btn {
    transition: transform 0.3s ease;
}

.modern-card .btn:hover {
    transform: scale(1.05);
}
```

Neste pequeno exemplo utilizamos:

* Bootstrap Grid;
* Bootstrap Card;
* sombra;
* filtro;
* transformação;
* transição;
* `hover`;
* responsividade.

---

# 33. Cuidado: efeitos não são decoração obrigatória

Um site com muitos efeitos não é necessariamente um site melhor.

Os efeitos devem ajudar:

* na navegação;
* na identificação de elementos interativos;
* na hierarquia visual;
* na compreensão das informações;
* no feedback das ações do usuário.

Evite:

* animações muito rápidas;
* elementos piscando;
* movimentos constantes;
* excesso de sombras;
* muitos efeitos diferentes na mesma página.

---

# 34. Acessibilidade e movimento

Algumas pessoas possuem sensibilidade a animações e movimentos.

O CSS possui:

```css
prefers-reduced-motion
```

Podemos escrever:

```css
@media (prefers-reduced-motion: reduce) {

    * {
        animation: none !important;

        transition: none !important;
    }

}
```

Isso permite respeitar usuários que configuraram o dispositivo para reduzir movimentos.

---

# 🧪 Atividade prática

Crie uma página utilizando **Bootstrap** contendo pelo menos três cards.

Cada card deve possuir:

* imagem;
* título;
* descrição;
* botão.

Implemente utilizando CSS externo:

1. sombra nos cards;
2. efeito de movimento ao passar o mouse;
3. transição suave;
4. efeito na imagem utilizando `filter`;
5. transformação utilizando `scale()`;
6. pelo menos uma animação utilizando `@keyframes`.

---

# ⭐ Desafio

Crie um banner contendo:

* imagem de fundo;
* gradiente;
* texto;
* botão Bootstrap;
* animação de entrada;
* efeito no botão ao passar o mouse.

---

# ✅ O que devemos compreender ao final da aula

| Recurso                 | Função                          |
| ----------------------- | ------------------------------- |
| `box-shadow`            | Sombra em elementos             |
| `text-shadow`           | Sombra em textos                |
| `opacity`               | Transparência                   |
| `filter`                | Efeitos visuais                 |
| `transform`             | Modifica forma ou posição       |
| `scale()`               | Aumenta ou diminui              |
| `rotate()`              | Rotaciona                       |
| `translate()`           | Move                            |
| `transition`            | Suaviza mudanças                |
| `@keyframes`            | Define animações                |
| `animation`             | Executa animações               |
| `linear-gradient()`     | Cria gradientes                 |
| `background-blend-mode` | Mescla fundo e cores            |
| `:hover`                | Aplica efeito durante interação |

---

## Ideia principal

Os efeitos avançados do CSS permitem criar interfaces mais agradáveis e interativas, mas devem ser utilizados com equilíbrio.

> **O objetivo de um efeito visual não é apenas chamar atenção, mas melhorar a experiência do usuário.**
