# Instalación

Este es el esqueleto del sistema de coordinación. Es autocontenido: no hay nada que configurar.

## Pasos

1. **Copiar esta carpeta** a la ubicación que quieras en la PC (cualquier ruta sirve).
2. **Abrir Claude Code en esa carpeta** (la raíz, donde está este archivo).
3. **Invocar a `riel`** y decirle que es una instalación nueva. No hay formulario ni entrevista larga: Riel pregunta lo mínimo para arrancar (quién sos, qué hace la organización, qué te duele hoy) y el resto lo va aprendiendo durante el trabajo real.
4. **Primera victoria:** Riel propone un caso real y chico, crea su carpeta en `clients/` y hace un primer trabajo útil de punta a punta. El valor se ve en la primera sesión.
5. **Revisar y aprobar** los archivos que Riel genere o amplíe (`org/context.md` y `org/users/`). Nada queda como canon sin tu revisión.

## Lo que NO se hace el primer día

- No crear agentes especializados (nacen cuando una función se repite; ver `docs/04-nacimiento-agentes.md`)
- No conectar integraciones (primero operar con lo que hay)
- No automatizar nada (primero registrar lo que duele)

## Estructura

Ver `CLAUDE.md`. Para entender el modelo del sistema: `docs/capas-contexto.md`. Para las reglas del coordinador: `docs/19-riel-kernel.md`.
