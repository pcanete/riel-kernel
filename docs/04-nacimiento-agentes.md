# Nacimiento de Agentes

## Principio

Un agente nace cuando tiene necesidad clara, frontera definida y aprobacion humana.
No nace por entusiasmo ni por utilidad teorica.

## Proceso

### 1. Propuesta (Riel o el humano principal)

Definir en pocas lineas:
- para que existe
- que problema resuelve que otro agente no resuelve
- que no va a hacer
- que riesgos introduce

### 2. Construccion del archivo

Un agente es un unico archivo `.md` en `.claude/agents/` dentro del workspace, con esta estructura:

```
---
name: <id>
description: <cuando invocar / cuando NO — una linea>
model: <opus | sonnet>
tools: [lista]
---

## Identidad
## Contexto del sistema
## Equipo
## Como operas
## Workspace canonico
## Lo que NO haces
## Niveles de aprobacion
```

No hay soul.md, runbook.md, inbox.md, outbox.md ni status.json por agente.
El estado del agente vive en el bus. La identidad vive en el archivo.

### 3. Entrevista

Antes de aprobarse, el agente debe poder responder:
- quien soy
- para que existo
- que no hare
- cuando escalo

### 4. Aprobacion

Estados posibles: `aprobado`, `revisar`, `rechazado`.
Si `revisar`: ajusta y vuelve.

Si aprobado: agregar al registro de agentes de la organizacion en `org/context.md` (capa 1).

## Retiro de agentes

Si un agente no recibe trabajo en varios ciclos, Riel propone retirarlo.
Retiro = mover a la seccion "Retirados" del registro en `org/context.md`. No se borra el archivo.

## Regla de autonomia

La autonomia no es licencia para invadir otros dominios.
Significa: decidir bien dentro de la frontera, escalar cuando corresponde, dejar rastro.
