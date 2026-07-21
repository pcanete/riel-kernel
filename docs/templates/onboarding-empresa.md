# Onboarding de Empresa

> Checklist interno del coordinador para conocer a una organizacion nueva.
> NO es un formulario: el coordinador nunca lo entrega para llenar ni lo descarga como cuestionario.
> Es el mapa de lo que en algun momento va a necesitar saber. Lo pregunta progresivamente,
> durante trabajo real, y materializa las respuestas en las capas a medida que aparecen.
> El objetivo es que el coordinador entienda la empresa sin inventar cultura ni asumir modelos de negocio.

---

## Como se usa

- **Arranque minimo**: para empezar solo hace falta 1.1, 1.2 y un dolor concreto de la Parte 3. Con eso el coordinador materializa un `org/context.md` inicial (marcado como parcial) y va directo a un primer trabajo util.
- **El resto, cuando el trabajo lo pida**: cada seccion se pregunta en el momento en que su ausencia bloquea o arriesga algo, de a una cosa por vez. Ej: la Parte 5 (gobierno) aparece la primera vez que surge una accion que podria requerir aprobacion.
- Cuanto mas concreto, mejor. Ejemplos reales valen mas que descripciones abstractas.
- "Obligatorio" significa que el coordinador tiene que llegar a saberlo — no que se responde el primer dia.
- Si la empresa prefiere llenar este archivo a mano de una, puede — pero el camino por defecto es conversacional y progresivo.
- Las respuestas no viven en este archivo: viven en las capas (`org/context.md`, `org/users/`). Este documento es guia, no destino.

---

# Parte 1 — Identidad de la empresa (obligatorio)

## 1.1 Nombre y dominio

- Nombre legal o comercial:
- Dominio principal o identificador corto (se usara para nombrar carpetas):

> Hint: el identificador corto tiene que ser estable. Ej: `acme-logistics`, `clinica-rio`, `northwind`.

## 1.2 Que hace la empresa

Describir en 3 a 6 frases que hace la empresa, concretamente.

> Hint: evitar slogans. Decir que se produce, que se vende, que servicio se presta, como gana dinero.
> Ejemplo util: "Operamos una flota de 40 camiones y movemos carga refrigerada entre tres provincias. Facturamos por viaje. No tenemos app propia."
> Ejemplo poco util: "Somos lideres en soluciones integrales de movilidad."

## 1.3 Para quien trabaja

Describir quienes son los destinatarios reales del trabajo de la empresa.

> Hint: pueden ser clientes externos, pacientes, usuarios, alumnos, otras empresas, areas internas, etc.
> Si hay varios tipos de destinatario, listarlos por separado.

## 1.4 Tamano y forma del equipo

- Cantidad aproximada de personas que trabajan en la empresa:
- Areas o funciones principales (ej: operaciones, ventas, administracion, clinica, desarrollo, etc.):
- Persona o personas que van a interactuar directamente con los agentes:
- Nivel de uso de IA de cada una de esas personas (conversacional / asistentes / automatizaciones / agentes):
- Capacitacion previa en IA, si hubo (cual y cuando):

> Hint: el nivel de uso va al archivo de capa 2 de cada usuario. El coordinador lo lee para calibrar cuanto explica y que propone (ver el mapa del sistema agentico en `docs/`). Si no saben ubicarse, la escala es: solo chatean con IA = conversacional; usan asistentes para tareas concretas = asistentes; tienen flujos automatizados = automatizaciones; ya trabajan con agentes con objetivos y herramientas = agentes.

## 1.5 Idioma de trabajo

Idioma principal en el que se va a operar con los agentes (ej: espanol, ingles, portugues, mixto).

---

# Parte 2 — Modelo de trabajo (obligatorio)

## 2.1 Unidad de trabajo

Como se organiza el trabajo dentro de la empresa. Elegir la opcion que mejor describa la realidad y explicar brevemente.

- [ ] Por cliente externo (cada cliente es una carpeta separada)
- [ ] Por proyecto (cada proyecto es una carpeta separada)
- [ ] Por caso, expediente o paciente
- [ ] Por area interna (sin clientes ni proyectos explicitos)
- [ ] Por producto o linea de producto
- [ ] Otro:

Explicacion breve:

> Hint: esto define como se organiza el workspace. Una consultora trabaja por cliente. Una clinica por paciente o especialidad. Una startup de software por proyecto o feature. Una empresa de logistica puede trabajar por ruta, flota o contrato.

## 2.2 Ciclo tipico de una unidad de trabajo

Describir el recorrido de una unidad de trabajo de punta a punta, desde que aparece hasta que se cierra.

> Hint: 5 a 10 pasos concretos. Ej: "Llega un pedido por mail, se carga en la planilla, se asigna a un chofer, se hace el viaje, se factura, se cobra, se archiva."

## 2.3 Sistemas y herramientas en uso hoy

Listar las herramientas con las que ya trabaja la empresa y que no se van a reemplazar.

> Hint: planillas, mail, whatsapp, CRM, ERP, sistemas propios, carpetas compartidas, etc. No hace falta integrar todo: basta con saber que existe.

## 2.4 Donde queda visible el trabajo (superficie compartida)

De las herramientas de 2.3, cual es la que el equipo mira para saber que esta pasando.

- Herramienta o lugar:
- Quienes tienen acceso:
- Que se espera encontrar ahi (estado, decisiones, entregables, todo):

> Hint: esta es la respuesta mas importante de la Parte 2. Define donde queda visible el trabajo
> para el resto de la organizacion, no solo para quien lo hizo. Puede ser un gestor de proyectos,
> un wiki interno, los proyectos de cada cliente o una carpeta compartida.
>
> Si la respuesta es "no tenemos", no inventar una herramienta: nombrarlo como hallazgo. Un sistema
> donde el unico registro queda en el disco de una persona muere con esa maquina y deja afuera al
> resto del equipo. Ver "Donde vive el trabajo" en `19-riel-kernel.md`.
>
> El coordinador nunca escribe ahi por su cuenta: propone que registrar y espera aprobacion.

---

# Parte 3 — Dolores y oportunidades (obligatorio)

## 3.1 Que funciones consumen tiempo y no agregan criterio

Listar tareas repetitivas, administrativas o de seguimiento que hoy ocupan tiempo humano pero no requieren decisiones complejas.

> Hint: son las primeras candidatas a soporte de agentes. Ej: armar reportes semanales, mandar recordatorios, consolidar informacion de varias fuentes, responder preguntas frecuentes.

## 3.2 Que funciones exigen criterio experto y se podrian apoyar con un agente

Listar funciones donde si hay criterio, pero un agente podria sostener memoria, preparar material o dejar rastro.

> Hint: no se busca reemplazar al experto. Se busca que el experto no empiece de cero cada vez. Ej: revisar contratos, diagnosticar casos, auditar calidad, preparar propuestas.

## 3.3 Que informacion se pierde hoy entre sesiones, personas o herramientas

Describir donde hay perdida de memoria o contexto.

> Hint: conversaciones que no quedan registradas, decisiones que nadie recuerda por que se tomaron, archivos que viven en la cabeza de una persona.

## 3.4 Que decisiones NO deben automatizarse nunca

Listar decisiones que deben quedarse siempre en manos humanas, por riesgo, regulacion, o cultura.

> Hint: esto protege a la empresa de sobreautomatizar. Ej: diagnosticos medicos finales, decisiones de contratacion, cualquier accion con impacto legal o financiero alto.

---

# Parte 4 — Agentes propuestos (diferida — emerge del uso)

Esta seccion NO se pregunta durante el onboarding: los agentes emergen del trabajo real,
no de una lista inicial de deseos. El coordinador la retoma cuando una funcion se repite
lo suficiente como para justificar un agente con frontera propia.
Esta seccion no define los agentes finales, solo propone candidatos.
El coordinador va a revisar, consolidar y proponer el equipo final.

## 4.1 Funciones que se necesita cubrir con agentes

Listar 2 a 6 funciones que se cree que un agente podria sostener. Una funcion por bloque.

### Funcion A
- Nombre tentativo (opcional, la empresa puede elegir como llamarlo):
- Que resuelve:
- Cuando alguien escribiria a este agente:
- Que decisiones puede tomar solo:
- Que debe escalar:

### Funcion B
- Nombre tentativo:
- Que resuelve:
- Cuando alguien escribiria a este agente:
- Que decisiones puede tomar solo:
- Que debe escalar:

### Funcion C (si aplica)
- Nombre tentativo:
- Que resuelve:
- Cuando alguien escribiria a este agente:
- Que decisiones puede tomar solo:
- Que debe escalar:

> Hint: es mejor proponer pocos agentes con frontera clara que muchos con funciones solapadas. Si dos funciones compiten por el mismo trabajo, unirlas.

## 4.2 Estilo de los agentes

Describir brevemente el tono y la actitud que deberian tener los agentes de esta empresa.

> Hint: no es decoracion. Define como se comunican con el equipo humano. Ej: formal y cauto en una clinica, directo y operativo en logistica, exploratorio en una empresa creativa.

---

# Parte 5 — Gobierno y limites (obligatorio)

## 5.1 Quien aprueba que

Definir que tipo de acciones requieren aprobacion humana explicita.

- Acciones que los agentes pueden ejecutar solos:
- Acciones que requieren aviso pero no bloquean:
- Acciones que requieren aprobacion previa:

> Hint: publicar algo hacia afuera, gastar dinero, borrar trabajo, enviar mensajes a terceros y cambiar permisos suelen requerir aprobacion previa.

## 5.2 Persona humana de referencia

Quien es la persona humana que toma las decisiones irreversibles y a quien escalan los agentes cuando hay conflicto.

- Nombre:
- Rol dentro de la empresa:

## 5.3 Datos sensibles

Listar tipos de datos que la empresa considera sensibles y que los agentes deben tratar con cuidado especial (o no tocar).

> Hint: datos de salud, datos financieros, datos personales de empleados, informacion confidencial de clientes, propiedad intelectual.

---

# Parte 6 — Contexto adicional (opcional)

## 6.1 Metodologia o forma de trabajar propia

Si la empresa tiene una metodologia, filosofia o forma de trabajo que quiere preservar en los agentes, describirla aqui.

> Hint: no es obligatorio. Muchas empresas no tienen una metodologia nombrada y esta bien.

## 6.2 Restricciones regulatorias o de industria

Si la empresa opera en una industria regulada, listar las restricciones relevantes.

> Hint: salud, finanzas, legal, educacion, alimentos, etc.

## 6.3 Historia breve y momento actual

Dos o tres frases sobre el momento que atraviesa la empresa.

> Hint: esta creciendo, esta reestructurando, esta entrando en un mercado nuevo, esta estabilizando operaciones, etc. Ayuda a calibrar el tono y la prioridad.

## 6.4 Que NO se espera del sistema de agentes

Listar expectativas que la empresa quiere descartar desde el principio.

> Hint: evita malentendidos. Ej: "no esperamos que los agentes reemplacen al equipo comercial", "no buscamos una IA conversacional con clientes finales".

---

# Parte 7 — Notas adicionales (opcional)

Espacio libre para cualquier cosa que no haya entrado en las secciones anteriores y que el coordinador deberia saber antes de disenar el equipo de agentes.

---

## Que materializa este template (modelo de capas)

> Ligada al modelo de capas: `docs/capas-contexto.md`.
> Este template no es un cuestionario suelto: es el flujo que llena las capas de contexto del coordinador.

| Parte del template | Capa que llena | Archivo resultante |
|--------------------|----------------|--------------------|
| 1 (identidad), 2 (modelo de trabajo), 3 (dolores), 5.1 y 5.3 (gobierno y datos sensibles), 6 (contexto adicional) | **Capa 1 — organizacion** | `org/context.md` |
| 1.4 (quienes interactuan) + 5.2 (persona de referencia) | **Capa 2 — usuarios** | `org/users/<nombre>.md`, uno por persona, con su autoridad de aprobacion |
| 2.1 (unidad de trabajo) | **Capa 3 — engagements** | define la forma de las carpetas de trabajo dentro de `clients/`, con el tipo declarado en el contexto de cada unidad |
| 2.3 y 2.4 (herramientas y visibilidad) | Capa 1 — superficie compartida | que herramienta existente materializa el registro visible; se documenta en `org/docs/<herramienta>-map.md`, fuera del versionado |
| 4 (agentes propuestos) | Capa 1 — equipo local | candidatos para el registro de agentes; ninguno nace sin aprobacion |

La capa 0 (kernel) no se llena nunca: viaja identica a toda instalacion.

## Cierre

No hace falta que este checklist este completo para que el sistema opere: el arranque minimo
(1.1, 1.2 y un dolor concreto) alcanza para materializar las capas iniciales y empezar a trabajar.
A medida que las secciones se van cubriendo durante trabajo real, el coordinador:

1. **Materializa las capas**: crea o amplia `org/context.md` y `org/users/<nombre>.md` con lo nuevo (ver tabla de arriba), siempre con visto bueno humano antes de canonizar.
2. Propone la estructura del workspace (como se organizan las carpetas de trabajo) cuando la unidad de trabajo queda clara.
3. Propone el flujo de aprobaciones y escalamiento (con el mapeo `territorio → quien aprueba` si hay mas de un usuario) la primera vez que hace falta.
4. Consolida funciones repetidas en candidatos a agentes y redacta sus contratos de nacimiento — recien cuando el uso real lo justifica.

Ningun agente se crea sin aprobacion de la persona humana de referencia.
