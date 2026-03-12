# 1BIM-M1 — Introdução à Web e seus padrões

## 1. Introdução

A Web é uma das principais plataformas de comunicação e distribuição de informação do mundo. Ela permite que usuários acessem páginas, aplicações e serviços por meio da internet utilizando navegadores.

Para que esse funcionamento seja possível, existem diversos **padrões e tecnologias**, como protocolos de comunicação, servidores, navegadores e sistemas de nomes de domínio.

Nesta atividade, vamos explorar alguns conceitos fundamentais da Web e compreender como eles são utilizados no desenvolvimento e acesso a aplicações web.

---

# 2. Conceitos fundamentais

## Tecnologias da Web

As tecnologias da Web são o conjunto de linguagens, protocolos e ferramentas que permitem criar e acessar páginas e aplicações na internet.

Entre as principais tecnologias estão:

* **HTML**
* **CSS**
* **JavaScript**
* **HTTP**

### Exemplo simples em HTML

```html
<!DOCTYPE html>
<html>
<head>
<title>Minha primeira página</title>
</head>
<body>

<h1>Olá Web!</h1>
<p>Esta é minha primeira página.</p>

</body>
</html>
```

Esse código pode ser aberto em qualquer navegador para exibir uma página web simples.

---

## HTTP e HTTPS

O **HTTP (HyperText Transfer Protocol)** é o protocolo responsável pela comunicação entre o navegador do usuário e o servidor web.

O **HTTPS** é a versão segura do HTTP. Ele utiliza criptografia (**SSL/TLS**) para proteger os dados transmitidos entre o navegador e o servidor.

### Exemplos de URLs

```
http://example.com
https://github.com
```

Quando um site utiliza **HTTPS**, os dados trafegam de forma criptografada, aumentando a segurança da comunicação.

---

## Navegadores e servidores web

O **navegador web** é o software utilizado para acessar páginas da internet. Ele interpreta códigos HTML, CSS e JavaScript e exibe o conteúdo para o usuário.

### Exemplos de navegadores

* Google Chrome
* Mozilla Firefox
* Microsoft Edge
* Safari

O **servidor web** é o sistema responsável por armazenar e disponibilizar páginas e arquivos para os usuários que acessam o site.

### Fluxo simplificado de funcionamento

```
Usuário abre o navegador
        ↓
Navegador faz uma requisição HTTP ao servidor
        ↓
Servidor responde enviando o conteúdo da página (HTML, CSS, JS)
        ↓
Navegador interpreta e exibe a página
```

---

## URLs, domínios e DNS

Uma **URL (Uniform Resource Locator)** é o endereço utilizado para acessar um recurso na internet.

Uma URL geralmente possui três partes principais:

* protocolo
* domínio
* caminho do recurso

### Exemplo de URL

```
https://developer.mozilla.org/pt-BR/docs/Web
```

Nesse exemplo:

* `https` → protocolo
* `developer.mozilla.org` → domínio
* `/pt-BR/docs/Web` → caminho do recurso

O **DNS (Domain Name System)** é o sistema que traduz nomes de domínio em endereços IP.

### Exemplo

```
google.com → 142.250.218.14
```

Isso permite que as pessoas utilizem **nomes fáceis de lembrar**, em vez de números.

---

## IDEs e Ferramentas de Desenvolvedor

Uma **IDE (Integrated Development Environment)** é um ambiente que facilita o desenvolvimento de software, oferecendo recursos como edição de código, sugestões automáticas e integração com ferramentas.

### Exemplos de IDEs e editores

* Visual Studio Code
* WebStorm
* Sublime Text

Além disso, os navegadores possuem **Ferramentas de Desenvolvedor (DevTools)** que permitem analisar e inspecionar páginas web.

Com essas ferramentas é possível:

* visualizar o código HTML da página
* analisar estilos CSS
* verificar requisições de rede
* depurar código JavaScript

### Exemplo de como acessar

```
Clique com o botão direito na página → Inspecionar
```

Ou pressione:

```
F12
```

---

# 3. Exercícios

## 1 — Pergunta conceitual

Explique com suas próprias palavras:

* O que é **HTTP**
* Qual é a diferença entre **HTTP e HTTPS**

Explique também por que o **HTTPS é importante para a segurança na Web**.

---

## 2 — Pergunta de aplicação

Imagine que uma empresa precisa criar um **site institucional**.

Explique:

* qual é o papel do **navegador**
* qual é o papel do **servidor web**
* como ocorre a comunicação entre eles quando um usuário acessa o site.

Utilize exemplos para ilustrar sua explicação.

---

## 3 — Pergunta de investigação (atividade prática)

Utilizando um navegador (**Chrome, Firefox ou Edge**):

1. Acesse o site:

```
https://developer.mozilla.org
```

2. Abra as **Ferramentas de Desenvolvedor**.

3. Inspecione a página e responda:

* Qual é a **URL completa da página acessada**?
* Qual protocolo está sendo utilizado (**HTTP ou HTTPS**)?
* Encontre um elemento HTML da página (por exemplo `<h1>`, `<p>` ou `<div>`).
* Copie um pequeno trecho do HTML encontrado.

Por fim, explique brevemente **o que você observou ao analisar a estrutura da página**.

---

## 4 — Pergunta de reflexão

Os padrões da Web permitem que sistemas diferentes consigam se comunicar na internet.

Explique:

* Por que padrões como **HTTP, HTML e DNS** são importantes.
* Como esses padrões ajudam a garantir que **diferentes navegadores e servidores funcionem corretamente**.

Apresente exemplos para apoiar sua explicação.

---

# 4. Instruções para os alunos

* Esta atividade deve ser realizada **em grupo**.
* Cada aluno deve **escolher apenas uma das questões** para responder.
* As respostas devem ser **claras, objetivas e bem organizadas**.
* Sempre que necessário, utilize **exemplos ou referências pesquisadas**.

Organize o documento utilizando **formatação adequada em Markdown**, com títulos, listas e blocos de código quando necessário.

---

# 5. Entrega

A atividade deve ser entregue no **repositório GitHub do grupo**.

### Formato do arquivo

```
Markdown (.md)
```

### Nome do arquivo

```
1BIM-M1-introducao-web.md
```

Certifique-se de que o arquivo está **corretamente organizado antes de enviar**.

---

# 6. Critérios de avaliação

Serão avaliados os seguintes aspectos:

* clareza e organização das respostas
* qualidade da pesquisa realizada
* aplicação correta dos conceitos estudados
* capacidade de explicação e argumentação
* organização e formatação do documento Markdown
