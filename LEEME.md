# Instalación

Este es el esqueleto del sistema de coordinación. Es autocontenido: no hay nada que configurar.

## Instalar (recomendado: con git)

No hace falta saber git — Claude Code lo opera por vos.

1. **Crear una carpeta vacía** donde quieras tener el sistema (ej: `Documentos\sistema`).
2. **Abrir Claude Code en esa carpeta**.
3. **Pegar este mensaje:**

   > Instalá en esta carpeta el sistema del repo público
   > https://github.com/pcanete/riel-kernel — si falta git, instalalo primero.
   > Los archivos del repo van en la raíz de esta carpeta, no en una subcarpeta.
   > Si la carpeta no está vacía, integrá el repo sin pisar nada
   > (git init + remote add + fetch + checkout) y no muevas los archivos
   > existentes: riel los revisa con su dueño.
   > Cuando termine, leé el LEEME.md e invocá a riel: es una instalación nueva.

4. **Riel arranca solo.** No hay formulario ni entrevista larga: pregunta lo mínimo (quién sos, qué hace la organización, qué te duele hoy) y el resto lo aprende durante el trabajo real.
5. **Primera victoria:** Riel propone un caso real y chico, crea su carpeta en `clients/` y hace un primer trabajo útil de punta a punta. El valor se ve en la primera sesión.
6. **Revisar y aprobar** los archivos que Riel genere (`org/context.md` y `org/users/`). Nada queda como canon sin tu revisión.

## Instalar sin git (alternativa)

Copiar esta carpeta completa a cualquier ruta de la PC y seguir desde el paso 2. Funciona igual, pero sin git no hay actualizaciones automáticas: cada versión nueva hay que copiarla a mano.

## Actualizar

Cuando haya una versión nueva del kernel, pegale esto a Claude Code en la carpeta del sistema:

> Actualizá el sistema: hacé git pull del kernel y contame qué cambió (mirá el CHANGELOG.md).

Nada de lo tuyo se toca: tu contexto (`org/`, incluida tu documentación en `org/docs/`), tu trabajo (`clients/`), tus mensajes (`bus/`) y los agentes que hayas creado están fuera del versionado. La actualización solo trae mejoras del esqueleto. Nadie te empuja cambios — actualizás cuando vos querés.

## Lo que NO se hace el primer día

- No crear agentes especializados (nacen cuando una función se repite; ver `docs/04-nacimiento-agentes.md`)
- No conectar integraciones (primero operar con lo que hay)
- No automatizar nada (primero registrar lo que duele)

## Estructura

Ver `CLAUDE.md`. Para entender el modelo del sistema: `docs/capas-contexto.md`. Para las reglas del coordinador: `docs/19-riel-kernel.md`.
