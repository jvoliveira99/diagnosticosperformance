# Agente de Diagnóstico — Setup

## Estrutura do projeto

```
agente-diagnostico/
├── api/
│   └── chat.js          # Backend: proxy para a API da Anthropic
├── public/
│   └── index.html       # Frontend: interface do agente
├── vercel.json          # Configuração de rotas
├── package.json
└── README.md
```

---

## Deploy em 5 passos

### 1. Criar repositório no GitHub

1. Acesse [github.com](https://github.com) e clique em **New repository**
2. Nome sugerido: `agente-diagnostico`
3. Deixe como **Private**
4. Clique em **Create repository**

### 2. Subir os arquivos

Opção A — pela interface do GitHub (sem precisar de Git):
1. Clique em **uploading an existing file**
2. Suba toda a pasta do projeto mantendo a estrutura de pastas
3. Commit com a mensagem `initial commit`

Opção B — pelo terminal:
```bash
git init
git add .
git commit -m "initial commit"
git remote add origin https://github.com/SEU_USUARIO/agente-diagnostico.git
git push -u origin main
```

### 3. Conectar à Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login com sua conta GitHub
2. Clique em **Add New → Project**
3. Selecione o repositório `agente-diagnostico`
4. Clique em **Deploy** (as configurações padrão já funcionam)

### 4. Configurar a variável de ambiente

1. No painel da Vercel, acesse seu projeto
2. Vá em **Settings → Environment Variables**
3. Adicione:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sua-chave-anthropic-aqui` ← cole a nova chave gerada
4. Clique em **Save**

### 5. Fazer redeploy

1. Vá em **Deployments**
2. Clique nos três pontos do último deploy
3. Clique em **Redeploy**

Pronto. A URL gerada pela Vercel (ex: `agente-diagnostico.vercel.app`) é o link de acesso à ferramenta.

---

## Credenciais de acesso

- **Usuário:** adminperformance
- **Senha:** leadqualificado

---

## Atualizações futuras

Para atualizar a ferramenta, basta atualizar os arquivos no GitHub. A Vercel faz o redeploy automaticamente.

---

## Segurança recomendada

- [ ] Revogar e regenerar a `service_role` key do Supabase
- [ ] Revogar e regenerar a API Key da Anthropic exposta no chat
- [ ] Considerar autenticação mais robusta para uso em produção
