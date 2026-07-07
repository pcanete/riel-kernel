Mensajes entre agentes: un archivo `<agente>.ndjson` por destinatario, append-only. Se crean cuando hace falta el primer mensaje.

## Formato

Una línea JSON por mensaje. Campos mínimos:

```json
{"id":"msg_<fecha>_<nro>","ts":"<ISO 8601>","from":"<agente|usuario>","to":"<agente>","type":"task|decision|handoff|bloqueo|aprobacion","summary":"<una línea>","status":"open"}
```

Opcionales según el caso: `priority`, `client`, `relates_to`, `resolution`, `resolution_ref` (puntero a detalle en `bus/events/`).

**Cierre:** nunca se edita ni se borra una línea. Un mensaje se cierra agregando una línea nueva con el mismo `id`, `type: "close"`, `closed_by` y `resolution`. El estado vigente de un mensaje es el de su última línea.
