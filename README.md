# Prática de DOM — Criação, Estilo, Atributos e Eventos

## 1. Criando Elementos com JavaScript

### Exercício 1 — Criar elementos e inserir na página

```js
const conteudo = document.getElementById("conteudo");

const p = document.createElement("p");
p.innerText = "Primeiro parágrafo criado via JavaScript.";
conteudo.appendChild(p);

const botao = document.createElement("button");
botao.innerText = "Adicionar Parágrafo";
conteudo.appendChild(botao);

botao.addEventListener("click", function () {
  const novo = document.createElement("p");
  novo.innerText = "Parágrafo criado ao clicar.";
  conteudo.appendChild(novo);
});
````

---

## 2. Manipulando Estilos

### Exercício 2 — Alterar estilo usando .style

```js
const botaoFonte = document.createElement("button");
botaoFonte.innerText = "Aumentar Fonte";
conteudo.appendChild(botaoFonte);

botaoFonte.addEventListener("click", function () {
  p.style.fontSize = "24px";
  p.style.color = "blue";
});
```

---

## 3. Manipulando Atributos

### Exercício 3 — Criar imagem e trocar o atributo src

```js
const img = document.createElement("img");
img.setAttribute("src", "https://via.placeholder.com/200");
img.setAttribute("alt", "Imagem inicial");
conteudo.appendChild(img);

const trocarImg = document.createElement("button");
trocarImg.innerText = "Trocar Imagem";
conteudo.appendChild(trocarImg);

trocarImg.addEventListener("click", function () {
  img.setAttribute("src", "https://via.placeholder.com/300x200");
});
```

---

## 4. Eventos Simples (click e input)

### Exercício 4 — Mostrar o texto digitado no mesmo momento

```js
const input = document.createElement("input");
input.setAttribute("placeholder", "Digite algo...");
conteudo.appendChild(input);

const exibicao = document.createElement("p");
exibicao.innerText = "Texto digitado aparecerá aqui.";
conteudo.appendChild(exibicao);

input.addEventListener("input", function () {
  exibicao.innerText = input.value;
});
```

---

## 5. Evento de Scroll

### Exercício 5 — Mudar a cor do header ao descer a página

```js
const header = document.getElementById("topo");

window.addEventListener("scroll", function () {
  if (window.scrollY > 50) {
    header.style.background = "#880000";
  } else {
    header.style.background = "#333";
  }
});
```

---

## Estrutura HTML para os exercícios

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <title>Prática DOM</title>
  <style>
    body {
      margin: 0;
      padding: 20px;
      font-family: Arial, sans-serif;
    }

    header {
      background: #333;
      color: white;
      padding: 20px;
      position: fixed;
      top: 0;
      width: 100%;
      transition: background 0.3s ease;
    }

    main {
      margin-top: 100px;
    }
  </style>
</head>
<body>
  <header id="topo">Meu Header</header>
  <main id="conteudo"></main>
  <script src="script.js"></script>
</body>
</html>
```
