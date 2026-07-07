# Workspace — Sistema de coordinación

Este workspace es la base operativa del sistema agéntico de la organización.

## Estructura

```
.claude/agents/    → agentes del sistema (arranca solo con riel)
org/               → capa 1 (context.md) y capa 2 (users/)
clients/           → trabajo real por unidad (cliente, proyecto o caso)
bus/queues/        → mensajes entre agentes (.ndjson, append-only)
bus/events/        → detalle de eventos registrados
docs/              → documentación del sistema
```

## Regla de paths

El único ancla es la raíz de este workspace: todo path del sistema es relativo a ella. No usar rutas absolutas de máquina en contratos ni docs.

## Reglas de escritura

- Todo trabajo de cliente/proyecto va en `clients/<unidad>/`
- Todo mensaje entre agentes va en `bus/queues/<agente>.ndjson` (append-only)
- Las conversaciones son contexto — el trabajo queda en archivos
- Prioridad de verdad: archivos canónicos > archivos del agente > conversaciones

## Primer uso

Si `org/context.md` no existe todavía, invocar a **riel** con algo como "sistema recién instalado, empecemos". No hay formulario previo que llenar: riel pregunta lo mínimo indispensable, va directo a un primer trabajo útil y completa el contexto de la organización progresivamente durante el trabajo real, siempre con aprobación del responsable humano.

## Para retomar una unidad de trabajo

Leer siempre primero: `clients/<unidad>/shared/context.md` y `shared/open-loops.md`
