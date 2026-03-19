# 📘 Atividade – Origens da Internet e do HTML

## 🎯 Tema
**Origens da Internet e do HTML**

---

## 👥 Modalidade
Atividade em **dupla**.

---
ACT-HTML-001-introducao-web-e-seus-padroes
ACT-HTML-002-const-site-origens-internt-html
ACT-HTML-003-const-site-origens-internt-html-revisao
## 📝 Objetivo da Atividade

Compreender a origem da Internet e do HTML, aplicando os conceitos estudados na construção de um site estruturado utilizando apenas HTML.

---

## 💻 O que deve ser feito

📌 Ver o planejamento no final deste arquivo.

Todas as páginas devem conter a estrutura completa de um documento HTML:

- `<!DOCTYPE html>`
- `<html>`
- `<head>`
- `<body>`

---

## 📂 Organização dos Arquivos

Todos os arquivos `.html` e as imagens utilizadas devem estar dentro de uma pasta chamada:
site
│ index.html
│ sobre.html
│ pagina1.html
│ pagina2.html
│ imagem1.jpg
│ imagem2.png


---

## 📚 Conteúdo Obrigatório

O site deve abordar:

- A origem da Internet
- A criação do HTML
- O primeiro site da história
- O primeiro navegador web
- Pessoas importantes para o desenvolvimento da Internet
- Empresas relevantes nesse processo

O site deve conter:

- Texto explicativo
- Imagens relacionadas ao tema
- Pelo menos uma tabela

Procurem manter equilíbrio entre texto e imagens.

---

## 📄 Página obrigatória: sobre.html

A página `sobre.html` deve conter:

- Nome completo dos desenvolvedores (alunos)
- Nome da instituição
- Nome do professor
- Referências utilizadas

📌 As referências devem estar no formato **ABNT**.

---

## 🛠 Regras Técnicas

- Utilizar **somente HTML**
- Não utilizar CSS
- Não utilizar os atributos:
  - `id`
  - `class`
  - `style`

- Manter a proporção adequada das imagens
- Utilizar diferentes tamanhos de fonte
- Buscar equilíbrio visual entre cores e conteúdo

---

## 📅 Entrega

Consultar o arquivo **"cronograma-entregas"** para verificar:

- Data de entrega
- Forma de envio
- Plataforma de envio

---

# 📊 Critérios de Avaliação

Serão avaliados:

- Aplicação correta dos conceitos estudados
- Clareza na organização das ideias
- Qualidade do texto (coerência e organização)
- Estrutura correta do HTML
- Organização da pasta e dos arquivos
- Uso adequado de imagens e tabelas
- Documentação na página `sobre.html`
- Cumprimento do prazo
- Capacidade de relacionar informações históricas e técnicas

---

## ✅ Observação Final

Este exercício tem como objetivo reforçar a base estrutural do HTML e desenvolver organização, pesquisa e apresentação de conteúdo.

---
# 📘 1. Planejamento do Site

## 🎯 Tema:
Origens da Internet e do HTML

## 👥 Público-alvo:
Alunos do ensino médio (linguagem simples, visual organizado)

## 📌 Objetivo:
Explicar de forma clara:

- Como surgiu a Internet  
- Como surgiu o HTML  
- Qual foi o primeiro navegador  
- Qual foi o primeiro site  

# 📁 2. Estrutura de Diretórios (Simples)

```
/meu-site/
│
├── index.html
├── internet.html
├── html.html
├── navegador.html
├── primeiro-site.html
│
├── /imagens/
│   ├── internet.jpg
│   ├── html.jpg
│   ├── navegador.jpg
│   └── site.jpg
│
└── /css/   (opcional para depois)
```
# 📄 3. Organização das Páginas

## 🏠 index.html (Página inicial)
- Introdução ao tema  
- Menu de navegação  

## 🌐 internet.html
- O que é a Internet  
- Surgimento (ARPANET)  

## 🧩 html.html
- O que é HTML  
- Criador: Tim Berners-Lee  
- Para que serve  

## 🧭 navegador.html
- Primeiro navegador: WorldWideWeb  
- Função dos navegadores  

## 🖥️ primeiro-site.html
- Primeiro site da história  
- Link e explicação  

# 🧱 4. Sugestão de Layout (Simples)

Usando HTML 4 + tabelas:

```
---------------------------------
|        TÍTULO DO SITE         |
---------------------------------
| MENU |       CONTEÚDO         |
|      |                        |
|      |                        |
---------------------------------
|           RODAPÉ              |
---------------------------------
```





# 💻 5. Exemplo de Layout em HTML 4

👉 Estrutura simples com tabela + imagens

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html>
<head>
    <title>Origens da Internet</title>
</head>

<body>

<table border="1" width="100%" cellpadding="10">

    <!-- Cabeçalho -->
    <tr>
        <td colspan="2" align="center">
            <h1>Origens da Internet e do HTML</h1>
        </td>
    </tr>

    <!-- Menu + Conteúdo -->
    <tr>

        <!-- Menu -->
        <td width="20%" valign="top">
            <b>Menu</b><br><br>

            <a href="index.html">Home</a><br>
            <a href="internet.html">Internet</a><br>
            <a href="html.html">HTML</a><br>
            <a href="navegador.html">Navegador</a><br>
            <a href="primeiro-site.html">Primeiro Site</a><br>
        </td>

        <!-- Conteúdo -->
        <td width="80%" valign="top">

            <h2>O que é a Internet?</h2>

            <p>
            A Internet é uma rede mundial de computadores que permite a troca de informações.
            Ela surgiu a partir de um projeto militar chamado ARPANET nos anos 1960.
            </p>

            <img src="imagens/internet.jpg" width="300" alt="Internet">

            <h3>Curiosidade</h3>
            <p>
            Hoje a Internet conecta bilhões de pessoas no mundo todo.
            </p>

        </td>

    </tr>

    <!-- Rodapé -->
    <tr>
        <td colspan="2" align="center">
            <p>Site educativo - Ensino Médio</p>
        </td>
    </tr>

</table>

</body>
</html>

```
# ✅ 6. Dicas para o Aluno

- Sempre organize arquivos em pastas  
- Use nomes simples (sem espaço)  
- Teste cada página no navegador  
- Comece simples, depois evolua (CSS futuramente)  
