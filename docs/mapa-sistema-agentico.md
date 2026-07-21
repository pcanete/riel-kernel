# Mapa del sistema agéntico — de alumno a usuario

> Para qué existe: cuando una persona entra al sistema después de una capacitación en IA (o sin ella), este mapa conecta los conceptos que aprendió con las piezas concretas que va a tocar. El coordinador lo usa para guiar; el usuario lo usa para ubicarse.

## Regla anti-obsolescencia (leer primero)

Este doc mapea conceptos a estructura del sistema. Deliberadamente **no** contiene estado del arte: ni modelos vigentes, ni herramientas de moda, ni "mejores prácticas" con fecha de vencimiento.

- **Lo estructural** (roles, contratos, aprobaciones, memoria, canales) cambia solo cuando el sistema cambia → vive acá.
- **Lo volátil** (qué modelo conviene, qué herramienta apareció, cómo se compara X con Y) no se responde nunca desde memoria embebida → el coordinador lo verifica en fuentes vivas en el momento, o lo delega a la función de research.

El principio de fondo: **el modelo es reemplazable; el sistema permanece.**

## El mapa: concepto → dónde vive acá

| Concepto (de la capacitación) | Dónde vive en este sistema |
|---|---|
| El cerebro: modelos de lenguaje | El modelo que corre cada agente (configurable en su contrato, reemplazable) |
| Roles, objetivos y grados de libertad | El contrato `.md` de cada agente en `.claude/agents/` |
| Instrucciones y habilidades (skills) | Contratos + skills externas que se invocan cuando hacen falta |
| Herramientas, conectores y aplicaciones | Los tools de cada contrato y los conectores (MCP) de la instalación |
| Canales de entrada y salida | El bus (`bus/queues/`) y la superficie compartida de la organización |
| Autonomía y puntos de control humano | Los niveles de aprobación 0 / 1 / 2 |
| Contexto, dossiers y playbooks | Las capas 0–3: `org/` (organización y su documentación) y `clients/` (trabajo) |
| Memoria y aprendizaje operativo | `context.md`, `open-loops.md` y `session-log.md` de cada engagement |

## La escala de adopción (dónde está cada usuario)

`conversacional → asistentes → automatizaciones → agentes`

El archivo de capa 2 de cada usuario registra su nivel actual y el próximo razonable. El coordinador lee eso al arrancar y calibra: cuánto explica, cuánto delega, qué propone. La meta no es que el usuario "sepa de IA": es que pueda **pedir, aprobar y leer el rastro** sin ayuda.

## Cómo guía el coordinador (modo transición)

- Si al usuario le falta un concepto necesario para avanzar, explicarlo primero con el vocabulario de este mapa, señalando la pieza concreta que está actuando ("esto que acabo de hacer es un handoff; quedó registrado acá").
- Una pieza por vez, sobre trabajo real. Nunca explicar por adelantado ni en bloque.
- El modo se apaga solo: cuando el usuario deja de necesitar la traducción, dejar de traducir.
- Registrar en capa 2 los conceptos que costaron: es evidencia de qué le falta al equipo.
- Cuando el mismo hueco se repite, proponerle al usuario pedir una capacitación puntual sobre eso — mostrando la evidencia registrada, no como venta. El sistema prescribe; el humano decide.

## Criterios de diseño que este sistema asume

Criterios durables, no noticias:

1. El arnés importa más que el caballo: contexto, herramientas, memoria y verificación valen más que el modelo.
2. Un agente no trabaja mejor porque sabe todo: trabaja mejor cuando sabe exactamente qué parte le toca.
3. Agregar herramientas puede empeorar al agente; diseñar también es quitar.
4. Un archivo de instrucciones es un contrato de trabajo.
5. Las reglas vagas son decoración; las reglas útiles pueden comprobarse.
6. Lo irreversible no puede depender de que el agente recuerde: por eso existen los niveles de aprobación.
7. La memoria no es acumular documentos: es evitar pagar dos veces por el mismo aprendizaje.
8. Un agente es confiable no por lo que logra cuando todo sale bien, sino por lo que registra, avisa y puede revertir cuando algo falla.
