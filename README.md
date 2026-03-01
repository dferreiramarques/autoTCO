# AUTO.TCO

Avaliador de TCO a 6 anos para carros usados em Portugal.  
Analisa anúncios do Standvirtual, OLX e CustoJusto com IA (Claude Haiku).

## Deploy no Railway

1. Cria conta em [railway.app](https://railway.app)
2. New Project → Deploy from GitHub repo
3. Faz push deste repositório para GitHub
4. Railway detecta o `package.json` automaticamente e faz deploy

Sem variáveis de ambiente necessárias — a API key é configurada pelo utilizador no browser.

## Estrutura

```
auto-tco-app/
├── server.js          Express server (serve /public)
├── package.json
└── public/
    └── index.html     App React completa (React + Babel via CDN)
```

## Desenvolvimento local

```bash
npm install
npm start
# → http://localhost:3000
```

## Como funciona

- O utilizador configura a sua própria API key Anthropic (guardada em localStorage)
- Cada análise usa o modelo Claude Haiku (~$0.001 por carro)
- A chave nunca passa pelo servidor — vai directamente do browser para a API Anthropic
- Sem base de dados, sem autenticação, sem custos de infraestrutura além do Railway
