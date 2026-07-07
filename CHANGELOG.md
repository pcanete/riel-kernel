# Changelog — riel-kernel

Registro de cambios del kernel. Cada versión lleva tag de git (`vX.Y.Z`).
Regla: las instalaciones actualizan con `git pull` cuando lo deciden; nunca se les empuja un cambio.

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
