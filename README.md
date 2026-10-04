# FuelControl — Local-first + Firebase opcional

## Objetivo
A aplicação funciona completamente sem qualquer serviço de sincronização. Os dados principais ficam no dispositivo, em localStorage, e a PWA continua utilizável offline.

O Firebase é uma camada opcional para login e cópia/sincronização entre dispositivos. Se estiver desligado, não é necessário Firebase nem Internet para usar as funções principais.

## Funcionalidades
- Combustível, histórico, gráficos, garagem, manutenção e despesas.
- Backup/restauro JSON e exportação CSV.
- Firebase Authentication (email/password), opcional.
- Cloud Firestore por utilizador, opcional.
- Sincronização manual e automática quando o Firebase está ativo.
- Dados locais preservados mesmo quando a nuvem falha ou a sessão termina.

## Configurar Firebase
1. Criar um projeto no Firebase.
2. Ativar Authentication > Sign-in method > Email/Password.
3. Criar Firestore Database.
4. Registar uma Web App e copiar a configuração `firebaseConfig`.
5. No FuelControl > Setup, preencher os campos Firebase e guardar.
6. Ativar a sincronização e criar/iniciar sessão.

### Regras de segurança recomendadas
Cada utilizador deve poder ler/escrever apenas o seu próprio caminho `users/{uid}/...`. Não usar regras abertas em produção.

## Importante
- Nunca colocar uma service account ou chave privada no frontend.
- A configuração Web do Firebase é pública; a segurança deve ser feita pelas Authentication Rules e Firestore Security Rules.
- O backup JSON continua independente da nuvem.
- A sincronização atual usa `updatedAt` e mantém os dados locais. Para uma futura versão multi-dispositivo avançada, podemos acrescentar resolução explícita de conflitos e tombstones mais sofisticados.


## v17 — sincronização manual
A sincronização Firebase é exclusivamente manual: os dados locais não são enviados automaticamente ao iniciar sessão, ao voltar online ou ao voltar à aplicação. O envio ocorre apenas através do botão **Sincronizar**.
