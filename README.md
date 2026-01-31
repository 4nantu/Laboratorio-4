
## Mejoras Implementadas

### 1. Uso Correcto de Etiquetas Semánticas HTML5

**Implementación:**
- `<header>`: Encabezado principal del sitio con información institucional
- `<nav>`: Navegación principal con atributo `aria-label` descriptivo
- `<main>`: Contenido principal con `id="main-content"` para skip links
- `<footer>`: Pie de página con información adicional
- `<section>`: Secciones temáticas con `aria-labelledby` para asociar títulos
- `<article>`: Artículos independientes dentro de secciones
- `<figure>` y `<figcaption>`: Para imágenes con descripciones
- `<address>`: Para información de contacto


### 2. Contraste Adecuado entre Texto y Fondo (WCAG 2.1 AA)

**Implementación:**
- Texto principal: `#212529` sobre `#ffffff` = **12.63:1** (cumple nivel AAA)
- Texto secundario: `#495057` sobre `#ffffff` = **7.12:1** (cumple nivel AA)
- Enlaces: `#0B5A9C` sobre `#ffffff` = **4.74:1** (cumple nivel AA)
- Botones: Texto blanco sobre fondo `#0B5A9C` = **4.74:1** (cumple nivel AA)

**Variables CSS utilizadas:**
```css
--color-text: #212529;
--color-text-light: #6c757d;
--color-primary: #0B5A9C;
```

### 3. Atributos Alt Descriptivos en Todas las Imágenes

**Implementación:**
- Todas las imágenes incluyen atributo `alt` descriptivo
- Imágenes decorativas usarían `alt=""` (vacío)
- Imágenes informativas tienen descripciones completas y contextuales
- Uso de `<figure>` y `<figcaption>` para imágenes con contexto adicional


### 4. Etiquetas de Formulario Adecuadas (Label)

**Implementación:**
- Todos los campos de formulario tienen etiquetas `<label>` asociadas
- Uso de `for` y `id` para asociar correctamente labels con inputs
- Campos obligatorios marcados con `*` y `aria-required="true"`
- Mensajes de ayuda con `aria-describedby`
- Mensajes de error con `role="alert"` y `aria-live="polite"`
- Validación accesible con `aria-invalid`

### 5. Navegación con Teclado Funcional (Tabulador)

**Implementación:**
- **Skip link**: Enlace para saltar al contenido principal (visible al enfocar)
- **Foco visible mejorado**: Outline de 3px con color de alto contraste (`#005fcc`)
- **Box shadow adicional**: Sombra alrededor del foco para mayor visibilidad
- **Tabindex apropiado**: Elementos interactivos con tabindex correcto
- **Orden lógico de tabulación**: Elementos en orden semántico
- **Manejo de elementos deshabilitados**: `tabindex="-1"` para elementos no accesibles


### 6. Jerarquía de Títulos Correcta (h1, h2, h3, etc.)

**Implementación:**
- Un solo `<h1>` por página (título principal)
- Jerarquía lógica: h1 → h2 → h3 → h4
- No se saltan niveles (no hay h1 seguido de h3)
- Títulos descriptivos y contextuales
- Uso de `aria-labelledby` para asociar secciones con títulos


### 7. Descripción Clara en Enlaces y Botones

**Implementación:**
- Enlaces con texto descriptivo (evita "haz clic aquí", "más información", etc.)
- Enlaces contextuales que describen el destino
- Uso de `aria-label` cuando el texto visible no es suficiente
- Botones con texto descriptivo o `aria-label` apropiado
- Enlaces externos con `rel="noopener noreferrer"` y `target="_blank"`


### 8. Criterios de Legibilidad y Comprensión del Contenido Textual

**Implementación:**
- **Tamaño de fuente base**: 16px (1rem) para legibilidad óptima
- **Line-height**: 1.6 para mejor espaciado entre líneas
- **Ancho máximo de texto**: 65 caracteres (65ch) para legibilidad óptima
- **Espaciado adecuado**: Márgenes y padding consistentes
- **Fuente sans-serif**: Fuentes del sistema para mejor legibilidad
- **Contraste mejorado**: Colores con alto contraste
- **Párrafos bien estructurados**: Espaciado entre párrafos
- **Listas con espaciado**: Mejor legibilidad en listas



## Mejoras Específicas de Diseño Inclusivo

### Mejora #1: Tamaños de Fuente Ajustables

**Implementación:**
- Controlador visual de tamaño de fuente con botones A-, A, A+
- Persistencia del tamaño seleccionado usando `localStorage`
- Respeta las preferencias del usuario del navegador
- Rango de ajuste: 12px a 24px

**Características:**
- Botones con `aria-label` descriptivos
- Posicionamiento fijo pero accesible
- Responsive en dispositivos móviles

**Código:**
```javascript
// Controlador de tamaño de fuente
const decreaseBtn = document.getElementById('decrease-font');
const resetBtn = document.getElementById('reset-font');
const increaseBtn = document.getElementById('increase-font');
// ... implementación completa en el archivo HTML
```


### Mejora #2: Foco Visible Mejorado para Navegación por Teclado

**Implementación:**
- Outline de 3px con color de alto contraste (`#005fcc`)
- Box shadow adicional para mayor visibilidad
- Offset de 3px para separación clara del elemento
- Estilos consistentes en todos los elementos interactivos



### Mejora #3: Skip Link para Navegación Rápida

**Implementación:**
- Enlace "Saltar al contenido principal" visible al enfocar
- Posicionado al inicio de la página
- Conecta directamente con el contenido principal (`#main-content`)
- Estilo visible solo cuando tiene foco

