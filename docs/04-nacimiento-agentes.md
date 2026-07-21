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

Un agente local es un unico archivo `.md` en `.claude/agents/` dentro del workspace.

**Pertenece a la organizacion, no al kernel: no se versiona.** El `.gitignore` deja fuera todo `.claude/agents/` salvo el contrato del coordinador, que es lo unico que viaja con el esqueleto. Asi la instalacion puede actualizarse sin que los agentes de la organizacion entren al repositorio ni se pisen con una version nueva.

Estructura del archivo:

```
---
name: <id>
description: <cuando invocar / cuando NO — una linea>
model: <capacidad requerida — ver abajo>
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

**Sobre el modelo: elegir por capacidad, no por nombre.** Este documento no enumera modelos concretos a proposito — caducan, y la regla anti-obsolescencia del kernel vale tambien para el kernel. Lo que se define acá es qué capacidad necesita el rol: razonamiento largo y criterio para agentes que deciden o critican, respuesta rápida y barata para agentes que ejecutan tareas acotadas. Qué modelo cumple hoy esa capacidad se verifica en el momento y se declara en la capa 1 de cada organizacion, no en esta plantilla.

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

Retirar tiene dos partes, y las dos hacen falta:

1. **Registro:** mover el agente a la seccion "Retirados" del registro en `org/context.md`, con el motivo. No se pierde la historia.
2. **Operacion:** mover el archivo fuera de `.claude/agents/` — a `org/agentes-retirados/` — para que deje de ser invocable. No se borra.

Si solo se hace lo primero, el agente figura como retirado pero el sistema lo sigue descubriendo y alguien lo va a invocar por error. Reactivarlo exige revision y aprobacion nuevas, igual que un nacimiento.

## Regla de autonomia

La autonomia no es licencia para invadir otros dominios.
Significa: decidir bien dentro de la frontera, escalar cuando corresponde, dejar rastro.
