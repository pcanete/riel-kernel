# Changelog — riel-kernel

Registro de cambios del kernel. Cada versión lleva tag de git (`vX.Y.Z`).
Regla: las instalaciones actualizan con `git pull` cuando lo deciden; nunca se les empuja un cambio.

## v1.6.0 — 2026-07-21

Separación real entre kernel e instalación, y doctrina de dónde vive el trabajo.

**Lo que la instalación genera deja de mezclarse con el esqueleto**

- `.gitignore`: los agentes locales dejan de versionarse. Nacen en `.claude/agents/` y pertenecen a la organización; el único contrato que viaja con el kernel es `riel.md`. Hasta ahora un agente creado durante el trabajo aparecía como archivo del repositorio
- La documentación propia de la organización se muda de `docs/` a `org/docs/`, fuera del versionado. `docs/` pasa a ser explícitamente del kernel: `00-indice.md` ahora lo dice y advierte que escribir ahí se pisa en la próxima actualización
- `CLAUDE.md` reescribió su mapa de estructura en dos bloques —lo que viaja y lo que genera la instalación— porque esa línea es exactamente lo que permite actualizar sin riesgo
- Eliminada del `.gitignore` una entrada residual de la organización que creó el kernel, que ignoraba una carpeta inexistente en el repositorio
- El retiro de agentes pasó a tener dos partes obligatorias: registro en `org/context.md` y **retiro operativo** moviendo el archivo a `org/agentes-retirados/`. Antes el agente figuraba como retirado pero el sistema lo seguía descubriendo, y alguien lo iba a invocar por error

**Nueva doctrina: "Dónde vive el trabajo"**

- Sección nueva en `19-riel-kernel.md` y en el contrato del coordinador. La separación: **local se ejecuta, compartido se ve.** Código, contenidos y borradores viven en disco; contexto, decisiones, estado y resultados van a la superficie compartida de la organización para servir de fuente unificada
- Criterio operativo: si otra persona necesita eso para trabajar o para retomar, va a la superficie compartida; si solo esta máquina lo necesita para ejecutar, se queda local
- El kernel no impone herramienta — exige que exista una y que el coordinador sepa cuál es. Nuevo punto 2.4 en el checklist de onboarding para declararla, con instrucción de nombrarlo como hallazgo si la organización no tiene ninguna
- **Destino no es automatismo:** el coordinador nunca escribe solo en la superficie compartida. Propone qué va a registrar y espera aprobación. Lo que no se negocia es el destino. Esto reemplaza el "no registrar por defecto" del cierre de sesión, que empujaba en la dirección contraria
- El coordinador además le explica esto al usuario: es la diferencia entre usar agentes para acelerar tareas propias y montar un sistema del que el equipo entero puede trabajar

**Nota para instalaciones existentes:** `.gitignore` no deja de rastrear lo que ya estaba rastreado. Si una instalación ya había commiteado agentes locales o documentación propia, hay que sacarlos del índice con `git rm --cached <archivo>` una sola vez. Las instalaciones nuevas no necesitan hacer nada.

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
