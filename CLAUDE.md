# CLAUDE.md — Web Project Builder

## Workspace
Workspace central de desarrollo web. Cada proyecto vive en su propia carpeta con un `brief.md` que define su identidad y requisitos.

## Siempre hacer primero
- **Antes de escribir cualquier código frontend**, invocar la skill `frontend-design` usando la herramienta Skill. Sin excepciones.
- Esto aplica a cualquier tarea que implique HTML, CSS, JS, componentes UI, layouts, páginas, o cualquier archivo que se renderice en el navegador.
- No saltarse este paso aunque la tarea parezca pequeña (un botón, un color, un ajuste de spacing).

## Repositorio obligatorio
- **Al iniciar cualquier proyecto web nuevo**, crear inmediatamente un repositorio en GitHub (cuenta jjurado2026) con el nombre del proyecto.
- Hacer commit y push del estado inicial antes de avanzar con el desarrollo.
- Configurar GitHub Pages (rama gh-pages) para poder compartir prototipos con clientes.
- Nunca trabajar sin repositorio remoto — todo proyecto debe tener backup en GitHub desde el minuto cero.

## Diseño único por proyecto — NO repetir patrones
- **Cada web debe tener un diseño radicalmente diferente.** No reutilizar la misma estructura, layout, paleta ni estilo visual entre proyectos.
- Antes de diseñar, **investigar el sector del cliente**: ¿qué tipo de diseño funciona mejor para ese nicho? ¿Qué hacen las mejores webs del sector? ¿Qué esperan los usuarios de ese tipo de negocio?
- Adaptar la dirección estética al sector:
  - Salud/clínicas → transmitir confianza, limpieza, profesionalidad. Fotos reales, espacios blancos, tipografía legible.
  - Tech/startups → moderno, bold, dark modes, animaciones llamativas, gradientes.
  - Lujo/moda → editorial, mucho whitespace, tipografía serif grande, minimalismo elegante.
  - Hostelería/gastro → cálido, texturas, fotos a sangre, tipografía con personalidad.
  - Legal/finanzas → sobrio, serio, estructura clara, colores corporativos clásicos.
  - Creativo/diseño → experimental, layouts asimétricos, scroll horizontal, efectos visuales.
  - E-commerce → enfocado en producto, grid limpio, CTAs claros, velocidad.
- **Variar siempre**: diferente tipografía, diferente layout hero, diferente estructura de nav, diferente approach a cards/grids, diferente sistema de animaciones.
- Nunca converger en un "estilo por defecto". Si los últimos proyectos usaron Instrument Serif + split layouts, el siguiente debe usar algo completamente distinto.
- **Solo reutilizar estilos entre proyectos si el usuario lo pide expresamente.** Nunca asumir que un proyecto debe parecerse a otro.

## Flujo de trabajo
1. Análisis del sector → 2. Brief → 3. Copy (siempre primero) → 4. Diseño adaptado al sector → 5. Desarrollo (WordPress / Shopify / otro CMS)

## Convenciones generales
- Idioma principal: Español
- Archivos de copy en Markdown dentro de `copy/` de cada proyecto
- CMS principal: WordPress (PHP/HTML/CSS/JS puro, sin page builders)
- Alternativas: Shopify, otros CMS según brief del proyecto
- Mobile-first como convención responsive

## Brief de proyecto
Cada proyecto tiene un `brief.md` en su carpeta raíz con:
- Nombre y descripción del proyecto
- Sector y competencia (webs de referencia del nicho)
- Colores de marca (primario, secundario, acentos)
- Tono de comunicación
- Target / público objetivo
- Servicios o secciones
- CMS elegido
- Fase actual del proyecto
- Dirección estética elegida (justificada por el análisis del sector)

Siempre leer el `brief.md` antes de trabajar en cualquier archivo del proyecto.

## Reglas de diseño frontend

### Colores
- Nunca usar la paleta por defecto de Tailwind ni colores genéricos
- Usar siempre los colores definidos en el brief del proyecto
- Derivar variantes (hover, disabled, etc.) de los colores de marca

### Tipografía
- Elegir fuentes que encajen con el sector y tono del proyecto — NO repetir las mismas fuentes entre proyectos
- Tracking natural (no negativo) en headings
- Line-height generoso (1.7) en texto de cuerpo

### Sombras y profundidad
- Sombras con tinte del color de marca y baja opacidad (no shadow-md plano)
- Sistema de capas: base → elevado → flotante
- Espaciado consistente con tokens, no valores aleatorios

### Gradientes y texturas
- Gradientes multicapa para profundidad
- Textura con ruido SVG cuando aporte

### Animaciones
- Solo animar `transform` y `opacity`
- Nunca `transition-all`
- Easing tipo spring
- Variar el tipo de animaciones entre proyectos (no siempre scroll reveal + counters)

### Estados interactivos
- Todo elemento clicable: hover, focus-visible y active. Sin excepciones

### Imágenes
- Overlay degradado (from-black/60 o similar)
- Capa de color con mix-blend-multiply cuando aplique

## Referencia visual
- Si se proporciona imagen de referencia: replicar layout, spacing, tipografía y color exactos. No "mejorar" el diseño
- Si no hay referencia: diseñar desde cero investigando el sector y eligiendo una dirección estética única

## Estructura de carpetas por proyecto
```
proyecto/
  brief.md          # Identidad, sector y requisitos
  copy/             # Copys en markdown
  assets/           # Logos, imágenes, recursos
  prototype/        # Prototipos HTML (si aplica)
  theme/            # Tema WordPress/Shopify (cuando toque)
```
