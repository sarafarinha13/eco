# ECO · El proyecto y su estética

> **Todo tiene un eco.**
> ECO no escribe tu historia. Te ayuda a escuchar su eco.

---

## 1. Qué es ECO

**ECO** es una aplicación de journaling digital con IA, desarrollada como proyecto de DAM.

Una aplicación de notas que convierte tus escritos en un diario personal organizado, y que usa la IA para ayudarte a descubrir temas, patrones y evolución **sin quitarte el protagonismo de tu propia escritura**.

- **No es un chatbot.** El usuario escribe; la IA es una capa de análisis y apoyo.
- **Idea del nombre:** las experiencias y los pensamientos siguen resonando con el tiempo. «Lo que pasó sigue resonando.» «Algo que nos preocupa hoy puede haber empezado mucho antes.»
- **Frase de cierre:** «La IA está detrás; la historia sigue siendo del usuario.»

### Vocabulario propio

| Palabra | Significa |
|---|---|
| **Entrada** | Lo que escribes (un texto del diario). |
| **Eco** | Un tema detectado en tus entradas. |
| **Resonancia del eco** | La evolución de un tema a lo largo del tiempo. |
| **Nueva entrada** | Acción principal: escribir. |

---

## 2. Qué permite hacer (objetivo)

1. Escribir libremente, sin estructura obligatoria.
2. Guardar y consultar entradas.
3. Organizarlas por fecha y por ecos (temas).
4. Identificar temas automáticamente.
5. Detectar temas recurrentes.
6. Ver la evolución de cada eco (Resonancia).
7. Recuperar entradas antiguas relevantes.
8. Ofrecer preguntas opcionales para empezar a escribir.
9. Mostrar conexiones entre momentos distintos.
10. Mantener al usuario como protagonista.

### MVP (pequeño a propósito)

- Crear, editar y guardar entradas
- Organización temporal
- Búsqueda
- Clasificación automática por ecos
- Visualización de ecos y su Resonancia
- Preguntas opcionales
- Recuperación de entradas antiguas

**Futuro:** análisis emocional, recuerdos destacados, conexiones entre entradas, personas/lugares, fotografías, transcripción de notas manuscritas, «hace un año escribiste esto», importar diarios.

---

## 3. Para quién

- **España, 18–34 años**, familiarizados con herramientas digitales.
- Personas que **ya escriben o han escrito un diario**, pero les cuesta mantenerlo, organizarlo o sacar conclusiones.

Tres perfiles: quien ya escribe (quiere patrones), quien es irregular (necesita hábito y saber qué escribir) y quien busca bienestar/autoconocimiento (quiere ver su evolución).

---

## 4. Principios de producto y UX

| Principio | En la práctica |
|---|---|
| **Libre** | Se escribe sin formularios ni estructura obligatoria. |
| **Visual** | La evolución se entiende con ecos, tarjetas, calendario, línea de tiempo y gráficos sencillos. |
| **No chat** | La IA analiza, no conversa. |
| **Personal** | Todo parte del historial real; ECO no le dice al usuario quién es. |
| **Cozy** | Cálida, íntima, sencilla y moderna. Nada médico, corporativo ni «techie». |

Las preguntas de ayuda son opcionales y suenan a **un amigo** («¿Qué ha sido lo mejor y lo más raro del día?»), no a un tema impuesto.

### Qué NO es ECO

Ni terapia, ni psicólogo virtual, ni diagnóstico, ni chatbot terapéutico, ni app de meditación, ni red social, ni tracker de hábitos, ni simple app de notas.

---

## 5. Diferencial

La IA histórica ya existe (Day One, Aksha, MindLens, Three), así que **«tener IA» no es el diferencial**. Lo es la **experiencia**: escritura libre, visual, sin chat, personal y centrada en el historial del usuario.

Quejas reales que ECO quiere resolver:
- «Nunca termino revisando las entradas antiguas ni encontrando patrones.» (Day One)
- «Acaba siendo un montón de datos con los que no sé qué hacer.» (Daylio)
- «Demasiados menús y pestañas.» (Day One)
- «Muy pocas funciones sin pagar.» (Grid Diary)

---

## 6. Validación (encuesta exploratoria, 13 respuestas)

No es representativa de España; sirve para orientar decisiones.

- 61,5 % escribe actualmente; 84,6 % escribe al menos semanalmente.
- Dificultades: olvidarse de escribir (38,5 %), mantener el hábito (23,1 %), no saber qué escribir (15,4 %).
- Funciones más deseadas: recordar entradas antiguas (76,9 %), ver evolución (61,5 %), recibir preguntas (61,5 %).
- Precio: 61,5 % prefiere freemium.

---

## 7. Modelo de negocio (hipótesis)

**Freemium.** En la primera versión solo existe la opción gratuita.

- **Gratis:** escribir, guardar, consultar, organización temporal, búsqueda básica.
- **Premium (futuro):** análisis IA, Resonancia de ecos, patrones históricos, preguntas personalizadas, recordatorios inteligentes, análisis de periodos.

Precio definitivo por validar. Distribución: Google Play, App Store y web. Captación: TikTok e Instagram.

---

## 8. Arquitectura técnica (especificación P1)

Tecnología aún no cerrada; la elección prioriza MVP, facilidad, seguridad, privacidad, coste y despliegue.

- **Cliente:** web + pantalla nativa Kotlin (Nueva entrada).
- **Backend** + **PostgreSQL**: Usuario, Entrada (versión y estado de ecos), Tema (eco), EntradaTema (relevancia/confianza).
- **Servicio de IA externo** para detectar ecos.
- **Odoo (ERP):** solo Contactos. **Los textos del diario nunca van a Odoo.**
- **Sección crítica:** edición de una entrada con *bloqueo optimista* (por versión) para no pisar cambios.
- **Tarea en segundo plano** con reintentos para el análisis de ecos.

---

## 9. Privacidad y seguridad

La privacidad es una característica central, no un añadido.

- Recoger solo los datos necesarios.
- Explicar qué analiza la IA y permitir controlarla.
- Conexiones seguras; credenciales protegidas.
- Textos personales fuera de los logs.
- Poder eliminar los datos.
- Nunca usar diarios reales para pruebas sin consentimiento.

---

## 10. Tono de voz

Cercano, sencillo, humano, tranquilo, **no clínico**.

| Evitar | Preferir |
|---|---|
| «ECO sabe cómo te sientes.» | «ECO te ayuda a observar tus escritos.» |
| «ECO descubre tus problemas.» | «ECO encuentra ecos que aparecen en tu historial.» |
| «ECO te diagnostica.» | «Puedes ver cómo cambian tus ecos con el tiempo.» |
| «ECO sabe quién eres.» | «La IA analiza; tú decides qué hacer con esa información.» |

---

## 11. Estética · Guía de estilo

Estética: **suave, minimalista, cálida, personal, moderna y visual**. Evitar dashboards corporativos, estética médica, interfaces recargadas y estética de chatbot.

### Colores (5, con su rol)

| Rol | Hex | Para qué sirve | Para qué NO |
|---|---|---|---|
| **Base** | `#FDFFE1` | Fondo de todas las pantallas. | Texto, iconos ni bordes. |
| **Acción** | `#224870` | Botón principal, enlaces y texto principal sobre el crema. | Fondos grandes; más de una acción destacada a la vez. |
| **Apoyo** | `#7A9CC6` | Línea y puntos del gráfico de Resonancia, bordes, ilustración. | Texto ni botones. |
| **Superficie** | `#9FBBCC` | Tarjetas, campos y etiquetas de ecos, siempre con texto `#224870`. | Texto en claro encima; color de texto sobre el crema. |
| **Error** | `#7B0828` | Mensajes de error, siempre con icono y texto. | Decoración o énfasis normal. |

Contrastes sobre la base `#FDFFE1` (aprox.): Acción ≈ 9,2 : 1 · Error ≈ 10,8 : 1 · Apoyo ≈ 2,8 : 1 (por eso **no** se usa para texto) · Superficie ≈ 2,0 : 1 (por eso el texto sobre ella es siempre `#224870`, ≈ 4,7 : 1).

### Tipografía

- **Nunito** para todo el texto de la app.
- **Hind Siliguri** solo en el logotipo «eco».
- Tres tamaños: **título 24 px** (Nunito 800), **texto 16 px** (Nunito 400), **secundario 14 px** (Nunito 400). Nada baja de 14 px.

### Estados

**Nunca solo por color:** cada estado lleva icono + texto + color. (Se retiró el color de aviso de la paleta; la rúbrica de la actividad pide uno, decisión pendiente.)

### Pantalla principal · «Nueva entrada»

Una sola acción principal: **escribir**. De arriba abajo:
logotipo «eco» · título «Nueva entrada» · fecha · nombre opcional · 2 preguntas de ayuda opcionales · área de texto grande · «+ ecos» · estado de guardado (icono + texto) · botón **Guardar entrada** · navegación inferior **Escribir / Escritos / Ecos**.

### Nota sobre las paletas

Existen tres paletas en el material del proyecto:
1. La de referencia inicial (cálida: crema `#FFFDF9`, salvia `#B1C4AE`, rosa `#E8C7C2`, beige `#EFD7BA`, lavanda `#D0C7DE`, azul claro `#BED3DA`, verde `#688268`).
2. La de la presentación.
3. **La guía de estilo de Desarrollo de Interfaces (la de arriba), que es la vigente para la app.**

Conviene unificarlas antes de la entrega final.

---

## 12. Riesgos

Privacidad de textos personales · abandono del hábito · alternativas gratuitas · competencia · falta de confianza en la IA · costes de IA, almacenamiento y APIs.

---

## 13. Regla para decidir cualquier función

¿Ayuda de verdad al usuario? ¿Encaja con journaling? ¿Mantiene al usuario como protagonista? ¿Necesita IA de verdad? ¿Complica la experiencia? ¿Aumenta el valor del historial? ¿Respeta la privacidad? ¿Cabe en el MVP?

*No añadir funciones solo porque sean técnicamente posibles.*
