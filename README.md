# AceleraBrands — Landing Page

Site institucional/landing page de conversão da AceleraBrands. É um único arquivo `index.html` estático (HTML + CSS + JS, com as imagens embutidas), sem necessidade de build.

## Antes de publicar

1. **Formulário (importante):** o formulário envia os dados (nome, telefone, e-mail, empresa, faturamento, setor) para um endpoint. Abra `index.html`, busque por `FORM_ENDPOINT` e troque `https://formspree.io/f/SEU_ID` pelo endpoint real:
   - **Caminho fácil (Formspree):** crie uma conta grátis em https://formspree.io, crie um formulário, copie o endpoint (`https://formspree.io/f/xxxxxx`) e cole no lugar. Funciona direto com os campos atuais.
   - **Ou** use o endpoint do seu CRM/automação que aceite POST com `FormData`.
   - Enquanto não configurar, o formulário mostrará uma mensagem de erro ao enviar.
2. **Conferir conteúdo:** confirme os números dos selos/certificações e dos cases, e se a AceleraBrands realmente possui as parcerias (Meta/Google) exibidas.

---

## Opção A — Deploy via GitHub + Vercel (recomendado: gera deploy automático a cada alteração)

### 1. Criar o repositório no GitHub
- Acesse https://github.com/new
- Nome sugerido: `acelerabrands-site` → Create repository

### 2. Subir os arquivos
**Pelo navegador (mais simples):** na página do repo recém-criado, clique em "uploading an existing file" e arraste `index.html` (e este `README.md`). Commit.

**Ou pelo terminal (git):**
```bash
cd pasta-do-projeto
git init
git add index.html README.md
git commit -m "AceleraBrands landing page"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/acelerabrands-site.git
git push -u origin main
```

### 3. Publicar na Vercel
- Acesse https://vercel.com e faça login com o GitHub
- "Add New..." → "Project" → importe o repositório `acelerabrands-site`
- Framework Preset: **Other** (é estático, sem build)
- Build Command: deixe vazio | Output Directory: deixe vazio (raiz)
- Clique em **Deploy**
- Em segundos a Vercel devolve a URL (ex.: `acelerabrands-site.vercel.app`)

A cada `git push`, a Vercel republica sozinha.

---

## Opção B — Deploy direto na Vercel (mais rápido, sem GitHub)

**Pelo CLI:**
```bash
npm i -g vercel
cd pasta-do-projeto
vercel
```
Siga as perguntas (aceite os padrões). Para publicar em produção: `vercel --prod`.

---

## Domínio próprio
No projeto da Vercel: **Settings → Domains → Add** e informe `acelerabrands.com.br` (ou o domínio desejado). A Vercel mostra os registros de DNS para apontar no seu provedor de domínio.

## Estrutura
```
/
├── index.html   (a página completa, autossuficiente)
└── README.md
```
