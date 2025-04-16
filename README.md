# Tracker

# 🚀 Projeto com CI/CD no GitHub Actions

Este é um projeto Vue com um pipeline de **CI/CD automatizado** usando **GitHub Actions**. Ideal para testes, estudos ou demonstrações de DevOps moderno com **deploy contínuo no GitHub Pages**!

## 📦 Instalação do Projeto Vue

``` bash
npm install
```

## 🔄 Executar em modo desenvolvimento

``` bash
npm run serve
```

## 🏗️ Gerar build para produção

``` bash
npm run build
```

## 🧹 Verificar e corrigir problemas de lint

``` bash
npm run lint
```

### ⚙️ Personalizar configurações

Confira a documentação oficial do Vue CLI. [Configuration Reference](https://cli.vuejs.org/config/).
---

## 📂 Estrutura do Projeto

```
.
├── .github/
    └── workflows/
        └── main.yml
├── .browserslistrc
├── .eslintrc.js
├── .gitignore
├── README.md
├── babel.config.js
├── package-lock.json
├── package.json
├── public
    ├── favicon.ico
    └── index.html
├── src
    ├── App.vue
    ├── assets
    │   └── logo.png
    ├── components
    │   ├── BarraLateral.vue
    │   ├── Botao.vue
    │   ├── Box.vue
    │   ├── Cronometro.vue
    │   ├── Formulario.vue
    │   ├── Tarefa.vue
    │   └── Temporizador.vue
    ├── interfaces
    │   ├── IProjeto.ts
    │   └── ITarefa.ts
    ├── main.ts
    ├── roteador
    │   └── index.ts
    ├── shims-vue.d.ts
    └── views
    │   ├── Projetos.vue
    │   └── Tarefas.vue
├── tsconfig.json
└── vue.config.js

```

---

## ⚙️ Pipeline de CI/CD

Cada push ou pull request na branch main dispara automaticamente o pipeline com 3 etapas principais:

### ✅ 1️⃣ Verificar arquivos no repositório

📋 Lista os arquivos do projeto, útil para validar o conteúdo presente.

```bash
ls -la
```

---

### 🔍 2️⃣ Análise estática com ESLint

🧹 Executa o ESLint para detectar problemas de estilo e sintaxe no código.  
Mesmo com erro, o pipeline continua (|| true).

---

### 🚀 3️⃣ Deploy no GitHub Pages

📦 Gera a build da aplicação Vue 
🌐 Faz o deploy automático no GitHub Pages com base nos arquivos gerados.

---

## 🔄 Quando o pipeline é executado?

O CI/CD roda automaticamente:

- ao fazer **push para a branch `main`** 🟢  
- ao abrir um **pull request para `main`** 🔁  
- ou de forma **manual via GitHub Actions → Run workflow** ⚙️

---

## 🌍 Acessar a aplicação

Após o deploy, sua aplicação estará disponível em:  
🔗 `https://github.com/MatheusFreitas54/Tracker`

---

## 🛠 Pré-requisitos para o Deploy corretamento

1. O arquivo `.github/workflows/main.yml` deve estar na branch `main`
2. Habilitar o GitHub Pages::
   - Vá em **Settings > Pages**
   - Em **Build and deployment**, selecione **GitHub Actions**
3. Commitar qualquer mudança e observar o CI rodando automaticamente 🎉

---

## 📘 Dica Extra

Você pode personalizar o pipeline para incluir:

- Testes automatizados
- Deploy para outros ambientes (Vercel, Netlify, etc)
- Integrações com Slack, Discord ou e-mail

---

## Autor

Desenvolvido por Matheus Freitas ™