# Modelo de capas de contexto

El sistema separa su núcleo invariante del contexto que cambia según dónde esté instalado. Cada capa es algo que el coordinador **lee al arrancar en frío**, no un concepto.

## Las cuatro capas

| Capa | Qué contiene | Dónde vive |
|------|-------------|------------|
| **0 — Kernel** | Reglas invariantes de coordinación: clasificación de pedidos, niveles de aprobación, prioridad de verdad, criterio de simplicidad | `docs/19-riel-kernel.md` + contrato de riel |
| **1 — Organización** | Qué hace la organización, cómo decide, riesgos, herramientas, adapter de registro, equipo de agentes locales | `org/context.md` |
| **2 — Usuarios** | Quién opera el sistema, qué puede aprobar, cómo prefiere trabajar, feedback acumulado | `org/users/<nombre>.md` (uno por persona) |
| **3 — Engagements** | Clientes, proyectos o casos: contexto retomable, decisiones, loops abiertos, lo producido | `clients/<unidad>/` |

**Regla dura: la capa 0 nunca se personaliza.** Si una organización necesita cambiar una regla del kernel, o la regla estaba mal (se corrige para todos) o no era kernel (baja a capa 1).

## Regla del ancla (paths)

El único ancla del sistema es la raíz del workspace. Todo path de contratos, docs y capas es relativo a ella. Rutas absolutas de máquina solo pueden existir en capa 3 (punteros a insumos externos) y en infraestructura local.

Consecuencia: el workspace es autocontenido — copiar la carpeta = instalar el sistema.

## El bucle de aprendizaje

Cada capa tiene su registro de aprendizaje y una regla de promoción hacia arriba:

| Aprendizaje sobre... | Se escribe en... | Sube cuando... |
|----------------------|------------------|----------------|
| un engagement | capa 3 (su carpeta) | el patrón se repite en otros → capa 1 |
| cómo trabaja la organización | capa 1 (bitácora de la org) | la regla sirve a cualquier organización sin nombres propios → capa 0 |
| un usuario | capa 2 (su archivo) | nunca sube solo — el feedback personal no generaliza automáticamente |

**Un aprendizaje sube de capa solo cuando se abstrae: pierde nombres propios y sigue siendo verdad.**

## Skills: capacidad, no contexto

Las capas son **conocimiento** (dónde estoy, con quién hablo); las skills son **capacidad** (qué sabe hacer el sistema cuando hace falta). El kernel define el mecanismo de invocación; el catálogo de skills instaladas pertenece a la capa 1. Nada de conocimiento especializado se escribe dentro de los contratos: se empaqueta como skill y se invoca.

## Identidad de usuario no portable

La capa 2 es **por organización**. La misma persona operando en dos organizaciones tiene dos archivos de usuario distintos, con autoridades distintas. Solo el kernel viaja entre organizaciones.

## Onboarding = instalación de capas

El template `docs/templates/onboarding-empresa.md` es el flujo que llena las capas 1 y 2 en una instalación nueva. Llenarlo *es* instalar el sistema. La capa 0 no se llena nunca: viaja idéntica.
