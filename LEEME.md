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
   > Si la carpeta ya tiene trabajo previo, seguí el procedimiento del LEEME
   > para carpetas no vacías antes de integrar nada.
   > Cuando termine, leé el LEEME.md e invocá a riel: es una instalación nueva.

4. **Riel arranca solo.** No hay formulario ni entrevista larga: pregunta lo mínimo (quién sos, qué hace la organización, qué te duele hoy) y el resto lo aprende durante el trabajo real.
5. **Primera victoria:** Riel propone un caso real y chico, crea su carpeta en `clients/` y hace un primer trabajo útil de punta a punta. El valor se ve en la primera sesión.
6. **Revisar y aprobar** los archivos que Riel genere (`org/context.md` y `org/users/`). Nada queda como canon sin tu revisión.

## Instalar en una carpeta que ya tiene trabajo

El kernel reclama un conjunto acotado de archivos. Todo lo demás que haya en la carpeta se queda donde está y sale intacto. El problema aparece solo cuando un archivo tuyo **se llama igual** que uno del kernel.

Procedimiento, en este orden:

1. **Hacer una copia de seguridad de la carpeta entera.** Es el paso que nadie quiere hacer y el único que no se puede improvisar después.
2. **Ver qué colisiona.** Los archivos que trae el kernel están en `git ls-files` del repositorio: comparar contra lo que ya existe. Suelen colisionar `CLAUDE.md`, `docs/` y `.claude/agents/riel.md` si ya había un sistema previo.
3. **Mover lo tuyo antes de integrar.** Lo que colisiona es documentación de tu organización, no del kernel: va a `org/docs/`, que está fuera del versionado. Es una mudanza, no un borrado.
4. **Recién ahí integrar el repositorio** (`git init`, `remote add`, `fetch`, `checkout`).
5. **Arreglar las referencias** que apuntaban a los archivos que moviste.

**Si el checkout aborta diciendo que sobrescribiría archivos, está funcionando bien: te está protegiendo.** Volvé al paso 3 y mové lo que nombra. **Nunca uses `git checkout -f` ni `--force` para salir del paso** — eso sí destruye trabajo, y es la única forma real de perder algo en este procedimiento.

## Exclusiones propias de tu instalación

`.gitignore` viene con el kernel y se actualiza con él: **si lo editás, tus cambios entran en conflicto en la próxima actualización.**

Para que git ignore carpetas propias de tu instalación —herramientas, materiales de trabajo, lo que sea— usá `.git/info/exclude`, que es local, no se versiona y nunca genera conflicto:

```
# .git/info/exclude
mis-herramientas/
material-de-trabajo/
```

Misma idea que el resto del sistema: lo del kernel no se toca, lo tuyo va a un lugar propio.

## Instalar sin git (alternativa)

Copiar esta carpeta completa a cualquier ruta de la PC y seguir desde el paso 2. Funciona igual, pero sin git no hay actualizaciones automáticas: cada versión nueva hay que copiarla a mano.

## Actualizar

Cuando haya una versión nueva del kernel, pegale esto a Claude Code en la carpeta del sistema:

> Actualizá el sistema: verificá antes que no haya cambios locales sin guardar,
> hacé `git pull --ff-only`, y contame qué cambió (mirá el CHANGELOG.md).
> Si el pull no puede ser fast-forward, pará y explicame por qué antes de tocar nada.

`--ff-only` es deliberado: si la actualización no puede aplicarse limpiamente, se detiene en vez de fusionar a ciegas. Que se detenga es información, no un error.

Nada de lo tuyo se toca: tu contexto (`org/`, incluida tu documentación en `org/docs/`), tu trabajo (`clients/`), tus mensajes (`bus/`), tus skills y los agentes que hayas creado están fuera del versionado. La actualización solo trae mejoras del esqueleto. Nadie te empuja cambios — actualizás cuando vos querés.

**Si algo sale mal:** el kernel vive en git, así que `git status` te dice exactamente qué cambió y `git checkout -- <archivo>` restaura un archivo del kernel a su estado publicado. Tus capas no están en git, así que ningún comando de git las toca. Por eso el paso 1 de la instalación es la copia de seguridad: es lo único que git no puede devolverte.

## Lo que NO se hace el primer día

- No crear agentes especializados (nacen cuando una función se repite; ver `docs/04-nacimiento-agentes.md`)
- No conectar integraciones (primero operar con lo que hay)
- No automatizar nada (primero registrar lo que duele)

## Estructura

Ver `CLAUDE.md`. Para entender el modelo del sistema: `docs/capas-contexto.md`. Para las reglas del coordinador: `docs/19-riel-kernel.md`.
