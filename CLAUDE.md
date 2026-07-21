# Workspace — Sistema de coordinación

Este workspace es la base operativa del sistema agéntico de la organización.

## Estructura

```
KERNEL — viaja con el sistema, se actualiza, no se edita
  .claude/agents/riel.md   contrato del coordinador
  docs/                    documentación del sistema
  CLAUDE.md, LEEME.md      reglas del workspace e instalación

ORGANIZACIÓN — lo genera esta instalación, nunca sube al repositorio
  org/context.md           capa 1: qué hace la organización, cómo decide
  org/users/               capa 2: quién opera el sistema y qué puede aprobar
  org/docs/                documentación propia de la organización
  .claude/agents/*.md      agentes locales (todos menos riel.md)
  clients/<unidad>/        capa 3: trabajo real
  bus/                     mensajes entre agentes (.ndjson, append-only)
```

**La línea entre los dos bloques es lo que permite actualizar sin riesgo.** Todo lo del segundo bloque está fuera del versionado: `git pull` no lo toca y nunca viaja a un repositorio público.

## Regla de paths

El único ancla es la raíz de este workspace: todo path del sistema es relativo a ella. No usar rutas absolutas de máquina en contratos ni docs.

## Reglas de escritura

- Todo trabajo de cliente/proyecto va en `clients/<unidad>/`
- Toda documentación propia de la organización va en `org/docs/`, nunca en `docs/`
- Todo agente local nace en `.claude/agents/` y no se versiona; el único versionado es `riel.md`
- Todo mensaje entre agentes va en `bus/queues/<agente>.ndjson` (append-only)
- Las conversaciones son contexto — el trabajo queda en archivos
- **Lo que la organización necesita ver no se queda solo en disco:** va a su superficie compartida, propuesto y aprobado (ver "Dónde vive el trabajo" en `docs/19-riel-kernel.md`)
- Prioridad de verdad: archivos canónicos > archivos del agente > conversaciones

## Kernel y actualizaciones

Este workspace se instaló clonando `https://github.com/pcanete/riel-kernel`. Eso implica dos reglas:

- **Actualizar el sistema = `git pull`.** Solo trae mejoras del kernel; las capas de la organización (`org/`, `clients/`, `bus/`) están fuera del versionado y no se tocan. Qué cambió: `CHANGELOG.md`.
- **Los archivos del kernel no se editan localmente** (contratos en `.claude/agents/` que vinieron con el kernel, `docs/` del kernel, este archivo, `LEEME.md`). Editarlos genera conflictos en la próxima actualización. Toda personalización va en las capas 1–3; si una regla del kernel parece mala, se reporta al mantenedor — no se parchea acá.

## Primer uso

Si `org/context.md` no existe todavía, invocar a **riel** con algo como "sistema recién instalado, empecemos". No hay formulario previo que llenar: riel pregunta lo mínimo indispensable, va directo a un primer trabajo útil y completa el contexto de la organización progresivamente durante el trabajo real, siempre con aprobación del responsable humano.

## Para retomar una unidad de trabajo

Leer siempre primero: `clients/<unidad>/shared/context.md` y `shared/open-loops.md`
