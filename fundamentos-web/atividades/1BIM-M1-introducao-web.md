# Introdução à Web e seus Padrões

## Introdução

A Web é um dos principais sistemas de comunicação da internet. Ela permite acessar páginas, aplicações, imagens, vídeos e diversos serviços online por meio de navegadores. Para que tudo funcione corretamente, existem padrões e tecnologias que definem como computadores se comunicam, como endereços são organizados e como os desenvolvedores criam e analisam sites.

Nesta atividade vamos conhecer alguns dos principais conceitos que fazem a Web funcionar.

---

# Conceitos Fundamentais da Web

## HTTP

**HTTP (HyperText Transfer Protocol)** é o protocolo utilizado para transferir páginas web entre o navegador e o servidor. Ele define como as requisições e respostas devem acontecer quando um usuário acessa um site.

Quando você digita um endereço no navegador, ele envia uma **requisição HTTP** para um servidor solicitando a página.

**Exemplo:**


http://example.com


O navegador envia uma requisição HTTP e o servidor responde com o conteúdo da página (HTML, imagens, etc.).

---

## HTTPS

**HTTPS (HyperText Transfer Protocol Secure)** é uma versão segura do HTTP. Ele utiliza criptografia para proteger os dados transmitidos entre o navegador e o servidor.

Isso evita que informações sensíveis (como senhas ou dados pessoais) sejam interceptadas.

**Exemplo:**


https://www.google.com


O cadeado no navegador indica que a conexão está protegida.

---

## Navegador Web

Um **navegador web** é o programa utilizado para acessar páginas da internet. Ele interpreta arquivos HTML, CSS e JavaScript e os apresenta de forma visual ao usuário.

Os navegadores também permitem inspecionar elementos, executar scripts e analisar o funcionamento das páginas.

**Exemplos de navegadores:**

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

---

## Servidor Web

Um **servidor web** é um computador ou software responsável por armazenar e entregar páginas web para os navegadores.

Quando um usuário acessa um site, o navegador faz uma requisição ao servidor, que envia os arquivos necessários para exibir a página.

**Exemplo de fluxo:**


Usuário → Navegador → Servidor → Página HTML


Exemplo de servidores web populares:

- Apache
- Nginx

---

## URL

**URL (Uniform Resource Locator)** é o endereço utilizado para acessar um recurso na internet, como uma página web, imagem ou arquivo.

Ela indica **o protocolo**, **o domínio** e **o caminho do recurso**.

**Exemplo:**


https://www.wikipedia.org/wiki/Internet


Partes principais:

- `https` → protocolo
- `wikipedia.org` → domínio
- `/wiki/Internet` → caminho do recurso

---

## Domínio

O **domínio** é o nome que identifica um site na internet. Ele facilita o acesso, pois seria difícil lembrar endereços numéricos (IP).

Os domínios são registrados e associados ao endereço real do servidor.

**Exemplos:**


google.com
github.com
gov.br


---

## DNS

O **DNS (Domain Name System)** funciona como uma espécie de **agenda telefônica da internet**. Ele converte nomes de domínio em endereços IP.

Quando você acessa um site, o DNS descobre qual é o servidor correspondente.

**Exemplo:**


google.com → 142.250.190.78


O usuário digita o domínio e o DNS encontra o endereço real do servidor.

---

## IDE

Uma **IDE (Integrated Development Environment)** é um software que reúne ferramentas para desenvolvimento de programas ou sites.

Ela normalmente inclui editor de código, ferramentas de depuração e integração com sistemas de controle de versão.

**Exemplos:**

- Visual Studio Code
- IntelliJ IDEA
- Eclipse

Exemplo de código HTML em uma IDE:

```html
<!DOCTYPE html>
<html>
<head>
<title>Minha Página</title>
</head>
<body>
<h1>Olá Web!</h1>
</body>
</html>
```
## Ferramentas de Desenvolvedor

As ferramentas de desenvolvedor (DevTools) são recursos presentes nos navegadores que permitem analisar e testar páginas web.

Com elas é possível:

- visualizar o HTML da página

- analisar requisições HTTP

- modificar estilos CSS

- verificar erros de JavaScript

Como abrir no Chrome ou Edge:

- F12

- Ou clique com o botão direito na página → Inspecionar.

# Exercícios

1. Como a Web funciona?

Explique, com suas próprias palavras, o que acontece desde o momento em que um usuário digita um endereço como:

https://www.wikipedia.org

até a página aparecer no navegador.

Em sua resposta, relacione pelo menos três dos conceitos estudados (por exemplo: DNS, servidor web, HTTP, navegador).

---

2. Analisando uma URL

Observe a seguinte URL:

https://developer.mozilla.org/pt-BR/docs/Web/HTML

Explique:

- qual é o protocolo

- qual é o domínio

- qual é o caminho do recurso

Depois pesquise e explique qual é a função desse site para desenvolvedores web.

---

3. Investigação com Ferramentas de Desenvolvedor

Acesse o site:

https://example.com

- Abra as Ferramentas de Desenvolvedor (F12).

- Na aba Elements (Elementos):

- encontre a tag ``` <h1> ``` da página

- altere temporariamente o texto para outro de sua escolha

Responda:

- O que aconteceu com a página após a alteração?

- Essa mudança altera o site para todos os usuários ou apenas para você? Explique por quê.

---

4. Pesquisa sobre ferramentas de desenvolvimento

Pesquise sobre duas IDEs usadas para desenvolvimento web.

Para cada uma delas, responda:

- nome da IDE

- empresa ou organização responsável

- principais recursos

- por que ela é útil para desenvolvedores web

- Apresente também um link oficial da ferramenta.

---

## Sobre os exercícios

- **Modalidade:** em Grupo
- **Entrega:** Github do grupo 
- **Nome do arquivo:** 1BIM-M1-introducao-web.md  
- **Data da Entrega:** Verifique o cronograma de entrega 


