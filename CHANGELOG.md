# Changelog — riel-kernel

Registro de cambios del kernel. Cada versión lleva tag de git (`vX.Y.Z`).
Regla: las instalaciones actualizan con `git pull` cuando lo deciden; nunca se les empuja un cambio.

## v1.2.0 — 2026-07-07

Correcciones de auditoría + reglas de convivencia con git.

- Corregido: `04-nacimiento-agentes.md` mandaba a registrar agentes en docs que no existen en el kernel; el registro vive en `org/context.md` (capa 1)
- Corregido: referencia rota a `26-riel-capas-contexto.md` y mención a herramientas de una organización específica en `templates/onboarding-empresa.md`
- Nuevo en `CLAUDE.md`: sección "Kernel y actualizaciones" — actualizar = `git pull`; los archivos del kernel no se editan localmente (la personalización va en capas 1–3)
- Nuevo: formato de mensaje del bus especificado en `bus/queues/LEEME.md` (esquema JSON mínimo + regla de cierre append-only)

## v1.1.0 — 2026-07-07

Repo público. Instalación sin cuenta de GitHub ni credenciales.

- `LEEME.md` reescrito: instalación por `git clone` operada por Claude Code (el usuario solo pega un mensaje), sección "Actualizar", copia manual como alternativa
- `.gitignore` nuevo: protege las capas de instancia (`org/`, `clients/`, `bus/`) para que el Claude de una instalación no pueda commitear datos privados por accidente

## v1.0.0 — 2026-07-07

Primera versión en repo. Contenido equivalente al zip `riel-kernel-v1-20260702` (2026-07-02):

- Agente coordinador `riel` (contrato de capa 0)
- Docs del kernel: reglas invariantes, capas de contexto, nacimiento de agentes, mapa del sistema
- Estructura plantilla: `org/`, `clients/`, `bus/` con LEEME por carpeta
- Instalación por copia de carpeta (`LEEME.md`) — ahora también por `git clone`
