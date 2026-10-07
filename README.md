# FuelControl — Local Database
## Objetivo
A aplicação funciona completamente sem qualquer serviço de sincronização. Os dados principais ficam no dispositivo, em localStorage, e a PWA continua utilizável offline.

Tem um viatura como exemplo ( Golf GTE ) cria a sua e pode apagar a de exemplo.

O Firebase (opcional) para login e cópia/sincronização entre dispositivos. Se estiver desligado, não é necessário Firebase nem Internet para usar as funções principais.

## Funcionalidades
- Combustível, histórico, gráficos, garagem, manutenção e despesas.
- Backup/restauro JSON e exportação CSV.
- Firebase Authentication (email/password), opcional.
- Cloud Firestore por utilizador, opcional.
- Sincronização manual e automática quando o Firebase está ativo.
- Dados locais preservados mesmo quando a nuvem falha ou a sessão termina.
