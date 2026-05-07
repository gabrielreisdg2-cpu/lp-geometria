# Megap+Lub — Landing de Geometria Veicular

Site estático pronto para deploy na Vercel.

## Como hospedar na Vercel

### Opção 1 — Drag & drop (mais rápido)
1. Acesse https://vercel.com/new
2. Clique em **"Deploy"** e arraste a pasta `vercel-build` (ou o conteúdo dela) para a área de upload.
3. Pronto. A Vercel detecta como **Other / Static** automaticamente.

### Opção 2 — Via Git
1. Suba o conteúdo desta pasta para um repositório no GitHub/GitLab/Bitbucket.
2. Em https://vercel.com/new clique **Import** e selecione o repositório.
3. Framework Preset: **Other**. Build Command: *(deixar em branco)*. Output Directory: *(deixar em branco)*.
4. Clique **Deploy**.

### Opção 3 — Vercel CLI
```bash
npm i -g vercel
cd vercel-build
vercel
```

## Estrutura
```
vercel-build/
├── index.html              # landing page
├── vercel.json             # config (cache de assets, headers)
├── assets/
│   ├── logo-megaplub-cropped.png   # logo usada no hero
│   └── logo-megaplub.png           # logo original (backup)
└── README.md
```

## Pixel da Meta
O Pixel `1526425278996802` já está embutido no `<head>` do `index.html`. Os eventos disparados:
- `PageView` — automático ao carregar
- `ViewContent` — quando o usuário rola até a seção de oferta
- `InitiateCheckout` — ao clicar em qualquer CTA verde de compra (`data-cta`)

> O Pixel só dispara em produção (domínio publicado). Em `localhost` ou preview interno fica silenciado para não poluir os dados.

## Conversions API (CAPI)
O **Access Token** já está no código junto ao Pixel. Se quiser ativar a CAPI server-side com mais segurança, mova o token para um endpoint serverless (`/api/capi.js`) ao invés de expor no front-end.

## Checkout
Todos os botões verdes apontam para: `https://pay.kiwify.com.br/DPnipGh`

## Domínio próprio
No painel da Vercel: **Settings → Domains → Add**. Aponte o CNAME do seu domínio para `cname.vercel-dns.com`.
