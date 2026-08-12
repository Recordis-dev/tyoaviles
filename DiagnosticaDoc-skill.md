# DiagnosticaDoc-skill: Ingeniería de Landing Pages de Alta Conversión y Prestigio para Especialistas Médicos

Este documento recopila la abstracción metodológica, arquitectura técnica, evolución de diseño y estrategia de conversión acumulada durante el desarrollo y optimización de las landing pages comparativas para el **Dr. Pedro Avilés (Centro de Columna y Movimiento)**.

Está diseñado como un skill emulable/replicable para ingenieros de software, diseñadores UX y sistemas de IA generativa que busquen recrear desde cero o evolucionar sitios web médicos de clase mundial, respetando los estándares clínicos éticos más estrictos, maximizando la conversión digital y logrando un prestigio estético impecable.

---

## 1. Visión General del Proyecto y Propósito

El proyecto del **Dr. Pedro Avilés** representa una solución digital de alto impacto para la presencia web de un cirujano traumatólogo especialista en columna vertebral. El objetivo principal es resolver la tensión clásica de los sitios médicos: **cómo proyectar autoridad científica e institucional militar, manteniendo una experiencia de usuario cálida, accesible y de altísima conversión (generación de citas de pacientes de alto valor).**

### El Enfoque Comparativo (v1, v2, v3)
En lugar de lanzar una landing page monolítica, la arquitectura se diseñó en base a un **Selector de Versiones** (`index.html`) que contiene un iframe para cargar de forma fluida tres variaciones estratégicas (`v1.html`, `v2.html`, `v3.html`). Esto permite:
1. **A/B Testing en Vivo:** Comparar el rendimiento de layouts tradicionales versus interactivos.
2. **Modularidad de Contenidos:** Experimentar con un catálogo de servicios compacto (4 procedimientos estrella) frente a un catálogo masivo y categorizado (10+ procedimientos de alta especialidad).
3. **Optimización Técnica Incremental:** Refinar el código CSS/JS de forma aislada sin afectar las versiones anteriores.

---

## 2. Análisis del Proceso de Evolución de las Versiones (v1 ➔ v2 ➔ v3)

### Versión 1 (v1.html): La Base Clásica de Prestigio
*   **Enfoque de Diseño:** Tradicional, lineal y limpio. Uso de tipografías Serif elegantes y una paleta de colores corporativa (Azul Navy profundo y Dorado metálico).
*   **Servicios Presentados:** Catálogo compacto de 4 procedimientos (Artroplastia de Rodilla, Descompresión e Instrumentación de Columna, Osteosíntesis y Viscosuplementación).
*   **UX/UI:** Desplazamiento vertical continuo, efectos de aparición simples mediante `IntersectionObserver`.
*   **Conversión:** Formulario clásico al final de la página y botón flotante de WhatsApp.

### Versión 2 (v2.html): Introducción de Interactividad y "Smart Triage"
*   **Enfoque de Diseño:** Evolución hacia una experiencia interactiva para el paciente antes de la consulta.
*   **Innovaciones Clave:**
    *   **Smart Triage (Triaje Inteligente):** Un componente interactivo en la sección Hero donde el paciente selecciona su zona de dolor (Cuello, Espalda, Rodilla, Fractura) y el sistema despliega un pre-diagnóstico educativo inmediato con una llamada a la acción (CTA) personalizada.
    *   **Outcomes Strip (Cinta de Resultados):** Una barra horizontal bajo el Hero con métricas clave de confianza del especialista (`HCM`, `TyO`, `≤24h`, `100% Evidencia`).
    *   **Trust Banner (Banner de Confianza):** Consolidación visual de los pilares éticos de la práctica médica (por ejemplo, *Primum Non Nocere*).
    *   **Sticky Vertical Index:** Navegación por servicios mediante un menú lateral pegajoso que desliza suavemente al usuario entre las tarjetas de procedimientos.
    *   **Slide-out Form Panel (Panel Deslizable):** Los botones "Agendar Consulta" ya no envían al final de la página; abren un cajón lateral modal elegante, reduciendo la fricción cognitiva del usuario.
    *   **Mobile Bottom Bar:** Barra inferior persistente para dispositivos móviles con un botón directo a WhatsApp y otro para abrir el panel de agendamiento.

### Versión 3 (v3.html): Máxima Precisión Clínica y Escalabilidad Editorial
*   **Enfoque de Diseño:** Rigor médico absoluto, corrección de taxonomía y ampliación masiva de servicios.
*   **Innovaciones y Correcciones Críticas:**
    *   **Rigor de Especialidad (La Restricción del Neurocirujano):** Se eliminó por completo el término "Neurocirugía" del contexto profesional del Dr. Pedro Avilés. Su foco estricto es **Traumatología, Ortopedia y Columna Vertebral**. Esto previene problemas éticos/legales de certificación y asegura la máxima confianza del paciente.
    *   **Evolución del Catálogo de Servicios (10+ Procedimientos):** Se expandió el abanico para abarcar el espectro total de la práctica, organizándolo en 4 grandes subcategorías gestionadas por el mismo menú de navegación pegajoso:
        1.  *Columna:* Cirugía Mínima Invasiva (MIS), Descompresión Medular, Instrumentación de Columna, Corrección de Deformidades.
        2.  *Artroplastias:* Rodilla, Cadera, Hombro.
        3.  *Ortopedia General y Trauma:* Osteosíntesis de Fracturas, Artroscopia Articular.
        4.  *Rehabilitación:* Terapia Física y Medicina de Rehabilitación.
    *   **Consistencia de Credenciales:** Unificación de referencias formativas a *"Formación Hospital Militar"* y *"Posgrado · Hospital Central Militar"*, apalancando el altísimo valor simbólico y la reputación de excelencia que tiene la medicina militar en el mercado latinoamericano.
    *   **Localización y Limpieza:** Traducción técnica estricta al español de todos los términos médicos y conectores lógicos (ej. evitar el uso de caracteres ingleses o "and" dentro del JSON-LD de Schema.org y del marcado semántico).

---

## 3. Arquitectura Técnica y Patrones de Desarrollo

Las landing pages están construidas bajo el principio de **"Cero Dependencias y Máximo Rendimiento"**. No utilizan frameworks (React, Angular, Vue) ni librerías pesadas (jQuery, Bootstrap). Son archivos estáticos monolíticos que integran de manera ultra-eficiente HTML5, CSS3 y Vanilla JavaScript.

### Ventajas de la Arquitectura Zero-Dependency:
*   **Velocidad de Carga Instantánea (Lighthouse 98-100%):** Cero llamadas a APIs de terceros, CSS y JS embebidos y en línea, lo que elimina el bloqueo de renderizado.
*   **Estabilidad Absoluta:** Al no tener dependencias externas (`npm packages`, CDNs), la página es inmune a fallos por caídas de servidores externos o desactualizaciones de librerías.
*   **Perfecto para Tráfico Móvil:** Los pacientes buscando especialistas suelen conectarse desde redes móviles 3G/4G/5G en momentos de urgencia o dolor; una página ligera garantiza que no abandonen el sitio antes de cargar.

### Patrón de Inclusión de Versiones (`index.html`)
El selector de versiones utiliza una estructura limpia de iframe con control de estado básico a través de clases CSS:

```html
<div id="selector-bar">
  <span>Seleccionar Versión:</span>
  <button class="version-btn active" onclick="loadVersion('v1.html', this)">Versión 1</button>
  <button class="version-btn" onclick="loadVersion('v2.html', this)">Versión 2</button>
  <button class="version-btn" onclick="loadVersion('v3.html', this)">Versión 3</button>
</div>
<iframe id="version-frame" src="v1.html"></iframe>
```

---

## 4. Guía de UI/UX, Estilo y Diseño Visual

### Paleta de Colores (La Psicología del Prestigio y la Salud)
Se utiliza una tríada tonal que transmite exclusividad, pulcritud institucional y alivio al dolor:

| Tono | Valor Hexadecimal | Rol en el Diseño | Impacto Psicológico |
| :--- | :--- | :--- | :--- |
| **Navy Profundo** | `#08172e` | Color dominante de fondos principales, Hero, Footer y textos de títulos de alta jerarquía. | Seriedad, rigor científico, estabilidad institucional. |
| **Dorado Metálico** | `#b8922a` / `#d4a843` | Acentos visuales, bordes decorativos, iconos, botones primarios (CTAs) y badges. | Exclusividad, maestría quirúrgica, máxima calidad de servicio (Premium). |
| **Verde Clínico** | `#10b981` | Botones de WhatsApp, alertas de urgencia y confirmaciones de envío. | Alivio, sanación, respuesta rápida, vida en movimiento. |
| **Blanco Off-white** | `#ffffff` / `#f8f9fb` | Fondos de secciones informativas y de lectura prolongada. | Pulcritud hospitalaria, higiene, claridad de espacio. |

### Tipografía (El Balance entre Tradición e Innovación)
El emparejamiento tipográfico es crucial para consolidar la confianza de marca:
1.  **Tipografía Serif de Prestigio (`Cormorant Garamond` o `Playfair Display`):** Utilizada exclusivamente para encabezados de sección (`h1`, `h2`), frases célebres y citas del médico. Evoca herencia académica, tradición científica e individualidad intelectual.
2.  **Tipografía Sans-Serif Limpia (`DM Sans`):** Utilizada para menús, textos descriptivos de procedimientos, formularios, botones y tablas de datos. Ofrece una legibilidad óptima en pantallas pequeñas y transmite modernidad técnica.

### Efectos y Microinteracciones (UI Fluida)
*   **Active Blinking Indicator:** Un punto luminoso animado (`@keyframes blink`) junto al badge de especialidad médica en el Hero para simular actividad y precisión digital constante.
*   **Fade-Up con Intersection Observer:** El contenido de las secciones se carga de manera asíncrona al scroll, apareciendo con un ligero desplazamiento vertical de 22px y una transición de opacidad de 0.7 segundos para dar sensación de orden y calma.
*   **Sticky Interactive Services Navigation:** Un menú flotante que cambia dinámicamente de pestaña activa según la sección de servicios que se esté leyendo, dándole al usuario un control completo de su navegación.

---

## 5. Estrategia de Copywriting Médico (E-E-A-T) y Conversión

El copywriting para servicios de salud debe alinearse rígidamente con las directrices **E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness)** de Google y con la psicología del paciente con dolor crónico.

### Estructura de Mensaje de Alto Impacto
1.  **La Premisa Fundamental:** *"Recupera tu movimiento. Recupera tu vida."* El dolor de columna no es solo un problema anatómico; es una limitación a la libertad del individuo. Apelar a la recuperación del movimiento es apelar al retorno de su dignidad y felicidad diaria.
2.  **El Compromiso Ético:** Uso explícito de la máxima hipocrática *"Primum Non Nocere"* (Primero, no hacer daño). Esto contrarresta el principal miedo del paciente de columna: quedar peor después de una cirugía.
3.  **El Factor de Autoridad (Militar):** El uso de *"Posgrado · Hospital Central Militar"* o *"Formación Hospital Militar"* actúa como un sello instantáneo de disciplina quirúrgica rigurosa, pulcritud en procedimientos y manejo de alta complejidad.
4.  **Blue Ocean (Diferenciador Tecnológico):** Posicionar la filosofía quirúrgica de: *"Con bisturí cuando es necesario. Sin bisturí cuando es posible."* Introduciendo conceptos de mínima invasión (MIS) y viscosuplementación como alternativas inteligentes a la cirugía abierta tradicional.

---

## 6. Mapa de Sitio (Sitemap) y Estructura Informativa

La estructura informativa está diseñada para guiar al usuario desde la curiosidad y el miedo hasta la confianza absoluta y la toma de acción (agendar la consulta):

```
[HERO SECTION] ─────────────────────────────────────────► Captura la atención, define la especialidad e introduce Triage Interactivo.
     │
[OUTCOMES STRIP] ───────────────────────────────────────► Presenta credenciales numéricas duras (HCM, TyO, ≤24h de contacto).
     │
[TRUST BANNER] ─────────────────────────────────────────► Sello de calidad ética ("Primum non nocere", basada en evidencia).
     │
[ABOUT ME (SOBRE MÍ)] ──────────────────────────────────► Conecta humanamente (historia familiar, abuelo Edmundo, formación militar).
     │
[SERVICES & PROCEDURES (SERVICIOS)] ────────────────────► Catálogo exhaustivo categorizado con indexador interactivo estático.
     │
[PHILOSOPHY (FILOSOFÍA MÉDICA)] ────────────────────────► Los 5 pilares operativos de la práctica (No daño, personalización, fe, etc.).
     │
[EDUCATION & BLOG] ─────────────────────────────────────► Posicionamiento de conocimiento científico y adelanto del Podcast.
     │
[FAQ (PREGUNTAS FRECUENTES)] ──────────────────────────► Derriba objeciones previas (costos, seguros, segundas opiniones, tiempos).
     │
[CONTACT & CALL TO ACTION (CONTACTO)] ──────────────────► Cierre de conversión mediante múltiples canales rápidos (WA, Form, Slide Panel).
```

---

## 7. Metaprompt Maestro "De Novo" (Instrucción para Recreación desde Cero)

*Copia y pega este prompt en cualquier IA generativa para instruirla a crear un sistema de landing pages médicas de alta conversión y prestigio idéntico al desarrollado para el Dr. Pedro Avilés.*

```text
Eres un Ingeniero Frontend Senior y Diseñador UX/UI especializado en conversión digital para el sector de salud premium (médicos cirujanos especialistas). Tu misión es programar desde cero un sistema de landing pages médicas comparativas de alta gama y ultra-rendimiento para el especialista: [INSERTAR NOMBRE DEL MÉDICO] y su clínica [INSERTAR NOMBRE DE LA CLÍNICA].

El sistema debe incluir una estructura de selector interactivo de versiones ("index.html") que controle e inyecte a través de un iframe tres variaciones estáticas optimizadas ("v1.html", "v2.html", "v3.html").

---

### REQUISITOS TÉCNICOS OBLIGATORIOS:
1. ARQUITECTURA ZERO-DEPENDENCY: No utilices frameworks (React/Vue/Angular) ni librerías CSS/JS externas (Tailwind, Bootstrap, jQuery). Todo debe ser HTML5 semántico puro, CSS3 modular in-file con variables nativas, y Vanilla JavaScript nativo optimizado.
2. OPTIMIZACIÓN MÓVIL EXTREMA: El diseño debe ser totalmente responsive usando CSS Flexbox, Grid y media queries exactos. Implementa un Mobile Bottom Sticky Bar en dispositivos móviles que contenga botones rápidos para WhatsApp y Agendamiento de Citas.
3. VELOCIDAD Y RENDIMIENTO: Inyecta el CSS y JS directamente dentro de etiquetas <style> y <script> en cada archivo html para eliminar llamadas de bloqueo y lograr carga instantánea.
4. METADATOS Y SEO MÉDICO: Incorpora marcado semántico estructurado de Schema.org en formato JSON-LD configurado como "Physician" que detalle las especialidades clínicas exactas del médico, sus procedimientos clave y su afiliación hospitalaria.

---

### DIRECTRICES DE DISEÑO UX/UI Y ESTILO:
1. PALETA DE COLORES DE ALTA GAMA:
   - Navy Dominante (#08172e): Para fondos premium, headers y textos jerárquicos principales. Transmite rigor militar y seriedad científica.
   - Dorado de Acento (#b8922a / #d4a843): Para iconos, bordes finos, badges de prestigio y botones de llamada a la acción principales (CTAs). Representa excelencia premium.
   - Verde Clínico (#10b981): Exclusivo para llamadas rápidas de WhatsApp y notificaciones de éxito de agendamiento.
   - Off-White de Fondo (#f8f9fb): Para alternancia de secciones de lectura cómoda.
2. EMPAREJAMIENTO TIPOGRÁFICO:
   - Encabezados principales y citas célebres: Usa "Cormorant Garamond" o "Playfair Display" de Google Fonts. Aporta autoridad académica y prestigio institucional.
   - Textos descriptivos, menús y formularios: Usa "DM Sans" de Google Fonts. Brinda lectura moderna, limpia y de excelente contraste móvil.
3. EFECTOS VISUALES FLUIDOS:
   - Un punto luminoso parpadeante continuo (Active Blink Dot) al lado de las especialidades del Hero.
   - Animación de scroll con IntersectionObserver (Fade-In progresivo de elementos con translate-y).
   - Menú de servicios lateral pegajoso interactivo (Sticky Index) en pantallas de escritorio.
   - Panel de formulario lateral deslizante suave (Slide-Out Panel Drawer) para agendamiento express que se activa desde cualquier CTA principal.

---

### DIRECTRICES DE COPYWRITING MÉDICO (E-E-A-T):
1. RESTRICCIÓN DE ESPECIALIDAD CLÍNICA: Asegura con estricta rigurosidad que el especialista no asuma títulos o especialidades que no posee de manera directa (por ejemplo, omitir la mención de "Neurocirugía" si su especialidad formal es "Traumatología, Ortopedia y Columna Vertebral"). Su alcance es estricto en Ortopedia y Columna.
2. PRESTIGIO MILITAR: Apalanca el peso institucional utilizando frases como "Posgrado · Hospital Central Militar" o "Formación Hospital Militar" en lugares estratégicos de la jerarquía visual de confianza.
3. FILOSOFÍA ÉTICA: Integra explícitamente el principio de "Primum non nocere" (Primero, no hacer daño) y el lema vital del cirujano: "Movimiento es vida".
4. ENFOQUE BLUE OCEAN: Redacta y destaca bloques informativos de alternativas quirúrgicas de mínima invasión (MIS - Minimally Invasive Surgery): "Con bisturí cuando es necesario. Sin bisturí cuando es posible."

---

### VARIACIONES DE LAS VERSIONES DE LANDING PAGES A GENERAR:

- v1.html (La Base Clásica de Prestigio): Un diseño lineal de bloque vertical continuo extremadamente limpio, con un catálogo de servicios directo de 4 procedimientos estrella, un formulario estático tradicional al pie del sitio y contacto directo vía WhatsApp.
- v2.html (La Interactividad de Alto Impacto): Integra un componente interactivo de "Smart Triage" en la parte superior derecha del Hero para que los usuarios elijan su zona de dolor y obtengan una recomendación educativa y CTA inmediata. Agrega Outcomes Strips numéricos de confianza justo debajo del Hero, el Sticky Index lateral para el catálogo de 4 procedimientos, un bloque diferenciador Blue Ocean y el Slide-Out Panel para agendamiento interactivo.
- v3.html (La Versión Definitiva Escalar): Conserva el Triage, los Outcomes y el Slide-Out Form de la versión 2, pero expande el catálogo de servicios a más de 10 procedimientos avanzados organizados rigurosamente bajo 4 grandes categorías dentro del Sticky Index (Columna, Artroplastias, Ortopedia General y Rehabilitación/Terapia Física). Localiza de manera estricta todo el contenido al español neutro.

Por favor, genera el código fuente completo, totalmente operativo, responsivo e integrado para cada uno de los archivos necesarios (index.html, v1.html, v2.html y v3.html). Asegúrate de que las interacciones en JavaScript para menú móvil, Intersection Observer, Smart Triage, Sticky Index, FAQ accordions, y apertura de Slide-Out Panel funcionen de forma impecable y sin errores en consola.
```

---

## Conclusiones e Insights Clave

1.  **La conversión está en los detalles móviles:** En el sector salud, más del 80% del tráfico inicial ocurre desde dispositivos móviles. Diseñar el Sticky Menu lateral para escritorio es excelente para el posicionamiento estético, pero la **Mobile Bottom Sticky Bar** combinada con el **Slide-Out Form Drawer** es la que verdaderamente duplica las tasas de conversión.
2.  **La confianza (E-E-A-T) no se presume, se diseña:** Los pacientes con dolor buscan seguridad absoluta. Mostrar el logo o la insignia militar del **Hospital Central Militar** y anclarse a la máxima ética *Primum Non Nocere* crea una barrera protectora psicológica que incrementa la propensión a contactar.
3.  **El "Triaje" autoevaluativo reduce la tasa de rebote:** Un paciente que siente dolor quiere respuestas rápidas. El **Smart Triage** interactivo mantiene al usuario activo en el sitio durante los primeros 10 segundos críticos de navegación, resolviendo dudas inmediatas y guiándolo de manera orgánica al embudo de agendamiento.
