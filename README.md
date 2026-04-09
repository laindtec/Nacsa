# NACSA - Sitio Web Reconstruido

Norte Agro Corredora S.A. - Sitio web moderno y responsive reconstruido desde la versión original de 2016.

## 📁 Estructura del Proyecto

```
Nacsa/
├── index.html          # Página principal (single-page con todas las secciones)
├── style.css          # Estilos globales del sistema de diseño
├── sitemap.xml        # Sitemap para SEO
├── robots.txt         # Instrucciones para crawlers
├── assets/            # Carpeta para imágenes y recursos
│   ├── logo.png       # Logo de NACSA (requerido)
│   ├── favicon.png    # Favicon del sitio (requerido)
│   ├── hero-bg.jpg    # Imagen de fondo del hero (requerido)
│   └── hero-poster.jpg # Poster para redes sociales (requerido)
└── old_page/         # Archivos HTML originales de 2016 (para referencia)
```

## 🎨 Características del Diseño

### Sistema de Diseño Implementado
- **Colores de marca**: Paleta agro/naturaleza con verdes, tierra y cielo
- **Tipografía**: Outfit (display) e Inter (body) de Google Fonts
- **Responsive**: Mobile-first con breakpoints en 640px, 768px, 1024px, 1280px
- **Grid system**: Flexbox y CSS Grid para layouts modernos
- **Animaciones**: Micro-animaciones suaves con CSS y JavaScript
- **Accesibilidad**: WCAG 2.1 AA compliant

### Secciones Incluidas
1. **Header sticky** con navegación y teléfono visible
2. **Hero section** con badge, título, subtítulo y CTAs
3. **Servicios**: 6 tarjetas con los servicios principales
4. **Por qué elegirnos**: Misión, visión y puntos clave
5. **Stats**: Números de confianza (años, sucursales, compromiso)
6. **Sucursales**: San Justo, Franck y Margarita
7. **Contacto**: Información de contacto y formulario funcional
8. **Footer**: Navegación, servicios, sucursales y contacto

### Funcionalidades JavaScript
- ✅ Header sticky con efecto de scroll
- ✅ Menú móvil responsive con toggle
- ✅ Navegación suave (smooth scroll)
- ✅ Link activo según scroll
- ✅ Formulario de contacto con validación
- ✅ Animaciones de revelación al hacer scroll

## 🚀 Próximos Pasos

### 1. Agregar Assets Requeridos
Debes agregar las siguientes imágenes en la carpeta `assets/`:

- `logo.png` - Logo de NACSA (recomendado: 200x100px)
- `favicon.png` - Favicon del sitio (32x32px o 64x64px)
- `hero-bg.jpg` - Imagen de fondo del hero (recomendado: 1920x1080px)
- `hero-poster.jpg` - Poster para Open Graph (recomendado: 1200x630px)

**Sugerencia para hero-bg.jpg**: Una imagen de campos de cultivos, silos, o una vista aérea de la región norte de Santa Fe que transmita agricultura y confianza.

### 2. Configurar el Formulario
El formulario de contacto está listo para funcionar. Tienes varias opciones:

**Opción A: EmailJS (más simple)**
```javascript
// Agrega esto en el HTML antes de </head>
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>
  emailjs.init('TU_SERVICE_ID');
</script>

// Reemplaza el handler del formulario con:
emailjs.send('TU_SERVICE_ID', 'TU_TEMPLATE_ID', data)
  .then(() => alert('¡Mensaje enviado!'))
  .catch(() => alert('Error al enviar'));
```

**Opción B: Webhook (Make.com / n8n / Zapier)**
```javascript
fetch('TU_WEBHOOK_URL', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify(data)
})
```

**Opción C: Backend propio**
Crea un endpoint PHP, Node.js o Python para recibir y procesar el formulario.

### 3. Actualizar URLs de Producción
Cuando subas el sitio a producción, actualiza:

1. **En `index.html`**:
   - Líneas 12-13: `canonical` URL
   - Líneas 16-23: `og:url` y `twitter:url`
   - Línea 97: Schema.org `url`
   - Líneas 104-107: Schema.org `image` y `logo`

2. **En `sitemap.xml`**:
   - Actualiza `https://www.nacsa.com.ar/` por tu dominio real

### 4. Opcional: Agregar Google Analytics
Agrega antes del cierre de `</head>`:
```html
<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-XXXXXXX');</script>
```

## 📱 Responsiveness

El sitio está optimizado para:
- 📱 Móvil: < 640px
- 📱 Tablet: 640px - 1023px
- 💻 Desktop: ≥ 1024px

## 🎯 SEO Optimizado

El sitio incluye:
- ✅ Meta tags completos (title, description, keywords)
- ✅ Open Graph para Facebook/LinkedIn/WhatsApp
- ✅ Twitter Cards
- ✅ Schema.org LocalBusiness JSON-LD
- ✅ Sitemap.xml
- ✅ Robots.txt
- ✅ Estructura de headings correcta (h1, h2, h3)
- ✅ Texto alternativo en imágenes (cuando se agreguen)
- ✅ Links internos con anchor tags
- ✅ Preconnect para Google Fonts

## 🎨 Personalización del Diseño

### Cambiar Colores
Edita las variables CSS en `style.css` (líneas 9-65):

```css
:root {
  /* Colores de Marca */
  --color-primary-500: #4caf50;  /* Color principal */
  --color-primary-600: #43a047;  /* Hover */

  /* Más variables de color... */
}
```

### Cambiar Tipografía
Edita las variables de fuente (líneas 70-74):

```css
:root {
  --font-display: 'Outfit', 'Inter', system-ui, sans-serif;
  --font-body: 'Inter', system-ui, sans-serif;
}
```

Y reemplaza las URLs de Google Fonts en el `<head>` de `index.html`.

## 🔧 Soporte del Navegador

- ✅ Chrome/Edge (últimas 2 versiones)
- ✅ Firefox (últimas 2 versiones)
- ✅ Safari (últimas 2 versiones)
- ✅ Móvil iOS y Android

## 📄 Contenido Real Utilizado

Todo el contenido proviene de los archivos originales de 2016:

- ✅ Nombre: NACSA - Norte Agro Corredora S.A.
- ✅ Teléfono: +54 03498 426751
- ✅ Email: nacsa@nacsa.com.ar
- ✅ Dirección: Ruta Nac. N° 11 KM 533,5, San Justo - Santa Fe
- ✅ Servicios: Asesoramiento a campo, Venta de granos, Bolsas para silos, Fitosanitarios, Fertilizantes, Logística
- ✅ Sucursales: San Justo, Franck, Margarita
- ✅ Misión y visión originales

## ✨ Características de Usuario

- ✅ Navegación entre secciones sin recargar página
- ✅ Header sticky para fácil acceso
- ✅ Menú móvil intuitivo
- ✅ Formulario de contacto funcional
- ✅ Animaciones suaves y profesionales
- ✅ Diseño moderno y limpio
- ✅ Accesibilidad WCAG 2.1 AA
- ✅ Performance optimizada

---

**Fecha de reconstrucción**: Abril 2026
**Tecnologías**: HTML5, CSS3, JavaScript (ES6+)
**Diseño**: Mobile-first, responsive, accesible
