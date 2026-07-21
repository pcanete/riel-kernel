# Riel

**Riel es el sherpa que ayuda a las personas de una organización a trabajar con colaboradores agénticos.**

No piensa por la empresa ni reemplaza a sus responsables. Guía: ordena lo que entra, sostiene el contexto entre sesiones, registra las decisiones, cuida las fronteras entre quienes trabajan —humanos y agentes— y escala al humano cuando algo deja de ser reversible.

Este repositorio es el **kernel**: el esqueleto instalable, vacío de cualquier organización. Se clona, se abre con Claude Code y Riel aprende la organización trabajando con ella.

---

## El problema que resuelve

Un equipo empieza a usar IA y en pocas semanas tiene el mismo problema: **el trabajo vive en conversaciones**.

- Cada sesión arranca de cero y hay que volver a explicar el contexto.
- Las decisiones se toman en un chat y nadie recuerda por qué.
- Lo que hizo una persona con un asistente no lo puede retomar otra.
- Nadie sabe qué puede hacer un agente solo y qué tiene que aprobar un humano.
- Se agregan herramientas y agentes antes de que exista un dolor real que los justifique.

Riel no agrega otra herramienta encima. Ordena lo que ya pasa: **las conversaciones son contexto, el trabajo queda en archivos.**

## Las tres capas

Riel sirve solo si mantiene tres cosas separadas. Si se mezclan, el sistema deja de poder actualizarse y deja de poder transferirse a otra organización.

| Capa | Qué es | Dónde vive |
|---|---|---|
| **Esqueleto** | El kernel. Reglas de coordinación que valen en cualquier organización. | Este repositorio |
| **Organización** | Qué hace, cómo decide, qué riesgos no puede tomar, quiénes la operan. | `org/`, fuera del versionado |
| **Trabajo** | Clientes, productos, proyectos o áreas, según cómo esté organizada la empresa. | `clients/`, fuera del versionado |

**El kernel no contiene nada de ninguna organización.** Ni nombres, ni clientes, ni herramientas, ni cultura. La regla se verifica, no se declara: si alguien clona este repositorio sin conocer a nadie, no debe poder deducir de qué organización salió.

Por eso una instalación puede actualizarse con `git pull` sin riesgo de que le pisen su trabajo.

## Cómo funciona

**Archivos de texto, no base de datos.** Todo el sistema se lee con un editor. Si Riel desaparece mañana, el trabajo sigue siendo legible.

**Onboarding progresivo.** No hay formulario que llenar. Riel pregunta lo mínimo para arrancar —quién sos, qué hace la organización, qué te duele hoy—, va directo a un primer trabajo útil y completa el resto durante trabajo real. El valor se ve en la primera sesión.

**Los agentes nacen tarde.** El sistema arranca con un solo agente: el coordinador. Los demás aparecen cuando una función se repite lo suficiente como para justificar una frontera propia, y ninguno nace sin aprobación humana. No vienen agentes hechos: cada organización descubre los suyos.

**Tres niveles de aprobación.** Lo que el agente hace solo, lo que hace avisando, y lo que espera decisión humana: publicar, gastar, borrar, mandar mensajes afuera, cambiar permisos. Ante la duda, escala.

**Un bus append-only.** Los mensajes entre agentes son líneas JSON que nunca se editan ni se borran. Un mensaje se cierra agregando una línea nueva. El rastro queda.

**Conducta invariante.** El coordinador no valida ideas tibias para no incomodar ni elogia sin análisis. Dice el desacuerdo una vez, con motivo, y si el humano decide avanzar igual ejecuta y registra el desacuerdo. Esta parte no se personaliza por organización: un coordinador complaciente no coordina, registra deseos.

## Qué NO es

- **No es un framework ni una librería.** No hay código que ejecutar, dependencias que instalar ni runtime que mantener. Son archivos de texto y un contrato de agente.
- **No es una app ni un servicio.** Todo vive en la máquina de la organización. No hay cuenta que crear ni servidor al que conectarse.
- **No trae agentes hechos.** Trae el mecanismo para que nazcan los que esa organización necesite, con sus nombres y sus fronteras.
- **No reemplaza las herramientas que ya usás.** Primero entiende qué hay y se apoya en eso. Agregar piezas viene después, y solo si duele algo concreto.

## Instalación

Ver **[LEEME.md](LEEME.md)**. Resumen: crear una carpeta, abrir Claude Code ahí, pegar un mensaje. No hace falta saber git — Claude Code lo opera.

Después de instalar, invocar a **riel** y decirle que es una instalación nueva.

## Estructura

```
.claude/agents/riel.md   contrato del coordinador
CLAUDE.md                reglas del workspace
docs/                    documentación del sistema (entrar por docs/00-indice.md)
org/                     capa de la organización — no versionada
clients/                 capa de trabajo — no versionada
bus/                     mensajes entre agentes — no versionada
```

Lo versionado es el kernel. Lo que genera cada instalación vive fuera del repositorio y nunca sube.

## Actualizar

```bash
git pull
```

Solo trae mejoras del esqueleto. Las capas de la organización no se tocan. Qué cambió en cada versión: **[CHANGELOG.md](CHANGELOG.md)**.

Nadie empuja cambios a una instalación: cada organización actualiza cuando decide.

## Requisitos

[Claude Code](https://claude.com/claude-code). Git recomendado —es lo que permite actualizar—, pero el sistema también funciona copiando la carpeta a mano.

## Estado

En uso real y en evolución. La versión vigente es el último tag de este repositorio; qué cambió en cada una está en el [CHANGELOG](CHANGELOG.md). Los cambios que rompan compatibilidad se anuncian ahí.

## Licencia

[Apache-2.0](LICENSE). Podés usar, modificar y desplegar este kernel dentro de tu organización, incluso comercialmente, sin pedir permiso. Si lo redistribuís o publicás un trabajo derivado, conservá el archivo [NOTICE](NOTICE) y declará qué cambiaste.

Concepto original: Patricio Cañete.

Lo que genera cada instalación —el contexto de la organización, sus agentes locales y su trabajo— es de esa organización y no está cubierto por esta licencia.
