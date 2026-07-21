# Changelog — riel-kernel

Registro de cambios del kernel. Cada versión lleva tag de git (`vX.Y.Z`).
Regla: las instalaciones actualizan con `git pull` cuando lo deciden; nunca se les empuja un cambio.

## v1.5.0 — 2026-07-21

Puerta de entrada y licencia.

- Nuevo `README.md`: hasta ahora el repositorio no tenía ninguno y quien entraba veía solo una lista de archivos. Explica qué es Riel, qué problema resuelve, las tres capas, cómo funciona y —sobre todo— qué NO es. La instalación sigue en `LEEME.md`; el README no la duplica
- Nueva licencia **Apache-2.0** (`LICENSE` + `NOTICE`). Hasta ahora el repositorio no declaraba licencia, con lo cual el default legal era "todos los derechos reservados": nadie que lo clonara tenía derecho a usarlo. Apache-2.0 permite uso, modificación y despliegue comercial dentro de la organización que instala, y conserva la atribución como obligación de la licencia
- El `NOTICE` aclara que lo que genera cada instalación —contexto, agentes locales y trabajo— pertenece a esa organización y no queda cubierto por la atribución del kernel
- La versión dejó de estar escrita a mano en el README: la fuente es el último tag y el CHANGELOG, para que no haya dos números que puedan discrepar

## v1.4.0 — 2026-07-21

Kernel limpio de su organización de origen.

- `19-riel-kernel.md` reescrito sin una sola referencia a la organización que creó el kernel: se eliminaron nombres propios, clientes, nombres de agentes locales, herramientas concretas y la sección de onboarding específica de esa organización. Ese contenido es capa 1 y vive en el workspace de cada instalación, no en el producto distribuible
- Nueva regla verificable en "Lo que NO viaja": si alguien clona el kernel sin conocer a nadie, no debe poder deducir de qué organización salió. Se comprueba con un barrido sobre los archivos versionados, no se declara
- Nueva sección "Para qué existe": Riel es el sherpa que ayuda a las personas de una organización a trabajar con colaboradores agénticos — guía, no reemplaza
- Nueva sección "Las tres garantías": esqueleto independiente, contexto de la organización como capa aparte, y el trabajo de cada persona en sus propias capas (clientes, productos, proyectos o áreas)
- El segundo modo de traslado dejó de ser específico de una organización: ahora es "kernel + addon", y el addon se declara explícitamente contenido de capa 1
- Redacción de la conducta invariante ajustada: sostener la evaluación ante un empuje sin evidencia no significa buscar ni exhibir el desacuerdo (hallazgo de auditoría externa cruzada)

## v1.3.0 — 2026-07-08

Conducta invariante: anti-complacencia como regla de capa 0.

- Nueva sección "Conducta invariante" en el contrato de riel y en `19-riel-kernel.md`: la evaluación solo cambia con evidencia nueva; prohibido validar ideas tibias y el elogio vacío; el desacuerdo se dice una vez y queda registrado en decisiones si el humano avanza igual; vale en ambos sentidos (el contrarianismo performático es el mismo defecto); los primeros desacuerdos con un usuario nuevo fundan la cultura
- Registrado también en "Lo que viaja en el kernel": la franqueza del coordinador no se personaliza por organización

## v1.2.1 — 2026-07-08

- Mensaje de instalación del `LEEME.md` robustecido con el caso de carpeta no vacía (aprendizaje de la primera instalación real): `git clone` fallaba si había trabajo previo; ahora la instrucción indica integrar el repo sin pisar nada y dejar que riel revise los archivos existentes con su dueño

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
