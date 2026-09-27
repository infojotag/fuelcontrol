# FuelControl Pro v13 — API + PostgreSQL

A v13 mantém a aplicação local e acrescenta uma camada de nuvem preparada para PostgreSQL.

## Estrutura
- `frontend/index.html` — aplicação PWA completa
- `backend/server.js` — API REST + autenticação JWT
- `database/schema.sql` — estrutura PostgreSQL
- `manifest-final-v13.json` / `sw-final-v13.js` — PWA

## Arranque local
1. Criar uma base PostgreSQL chamada `fuelcontrol`.
2. Executar `database/schema.sql`.
3. Entrar em `backend/` e executar `npm install`.
4. Copiar `.env.example` para `.env` e configurar `DATABASE_URL` e `JWT_SECRET`.
5. Executar `npm start`.
6. Abrir `http://localhost:3000`.

## Sincronização
Os dados continuam em `localStorage` até o utilizador escolher no Setup:
- **Enviar dados locais para a nuvem** — substitui o conteúdo da conta pelos dados deste dispositivo.
- **Baixar dados da nuvem** — substitui os dados locais pelo conteúdo online.

Esta primeira fase é deliberadamente explícita para evitar perda acidental. A próxima fase pode acrescentar sincronização automática e resolução de conflitos entre dispositivos.
