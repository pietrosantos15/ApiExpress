# ApiExpress

API REST simples desenvolvida com **Node.js** e **Express**, que retorna a data e a hora atuais do servidor em formato JSON. O projeto foi feito para a disciplina **Frameworks Front-end** (SENAI) e é consumido por uma aplicação front-end publicada na Vercel.

## 👤 Autor

**Pietro Freire Rezende dos Santos**

---

## 🔗 Links

- **API (Render):** https://apiexpress-k65o.onrender.com
- **Front-end que consome a API (Vercel):** https://frontapiexpress.vercel.app/

> A API está no plano gratuito do Render, então a primeira requisição pode demorar alguns segundos enquanto o serviço "acorda".

---

## 🚀 Tecnologias

| Tecnologia | Uso |
|------------|-----|
| [Node.js](https://nodejs.org/) | Ambiente de execução JavaScript no servidor |
| [Express](https://expressjs.com/) | Framework para criação de rotas e do servidor HTTP |
| [CORS](https://www.npmjs.com/package/cors) | Libera o acesso à API a partir de outros domínios (o front-end) |
| [Render](https://render.com/) | Hospedagem da API como Web Service |

---

## 📌 Endpoint

### `GET /`

Retorna a data/hora atual do servidor (formato `pt-BR`), o status e uma mensagem de boas-vindas.

**Exemplo de resposta:**

```json
{
  "date": "19/11/2026, 14:32:10",
  "status": "API rodando",
  "mensagem": "Bem-vindo à minha API!"
}
```

| Código | Significado |
|--------|-------------|
| `200 OK` | Requisição realizada com sucesso |

---

## 📁 Estrutura do Projeto

```
ApiExpress/
├── api.js              # Servidor Express e definição da rota
├── package.json        # Dependências do projeto
└── package-lock.json   # Versões exatas das dependências
```

---

## ⚙️ Como Executar Localmente

**Pré-requisito:** [Node.js](https://nodejs.org/) instalado (versão 22 ou superior, que entende a sintaxe `import` do `api.js`).

```bash
# 1. Clonar o repositório
git clone https://github.com/pietrosantos15/ApiExpress.git

# 2. Entrar na pasta
cd ApiExpress

# 3. Instalar as dependências
npm install

# 4. Iniciar o servidor
node api.js
```

O servidor sobe em `http://localhost:3000` (ou na porta definida pela variável de ambiente `PORT`).

---

## ☁️ Deploy no Render

1. Publicar o projeto no GitHub.
2. Em [dashboard.render.com](https://dashboard.render.com), criar um novo **Web Service** e conectar este repositório.
3. Definir o **Build Command** como `npm install` e o **Start Command** como `node api.js`.
4. Após o deploy, a API fica disponível em `https://<nome-do-projeto>.onrender.com`.

O Render define automaticamente a variável `PORT`, que o `api.js` já utiliza.

---

## 💻 Consumindo a API no Front-end

```js
fetch("https://apiexpress-k65o.onrender.com/")
  .then((resposta) => resposta.json())
  .then((dados) => {
    console.log(dados.date);     // data e hora
    console.log(dados.mensagem); // mensagem de boas-vindas
  });
```

---

## 📚 Conceitos Aplicados

- Criação de API REST com Express
- Rota `GET` com resposta em JSON
- Middleware de CORS
- Uso de variável de ambiente para a porta (`process.env.PORT`)
- Deploy de back-end no Render e integração com front-end na Vercel
