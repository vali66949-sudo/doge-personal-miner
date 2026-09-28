# DOGE Personal Miner v3
1. Copia `.env.example` a `.env`.
2. Pon las claves de tu placement Offerwall.GG.
3. Ejecuta `node server.js`.
4. Abre `http://localhost:8787`.

El callback valida HMAC-SHA256 sobre `userId:transactionId:currencyAmount`, ignora tests y es idempotente por transacción/estado. `payoutUsd` se guarda como dato de conciliación porque la documentación del proveedor indica que no está cubierto por la firma; para producción, concilia ese importe con su API antes de tratarlo como dinero disponible.

La minería real no se ejecuta en el navegador. `MINER_START_COMMAND` y `MINER_STOP_COMMAND` son opcionales y están pensados para controlar un minero Scrypt externo que ya tengas.

No hay clicks automáticos, impresiones falsas ni generación ficticia de DOGE.
