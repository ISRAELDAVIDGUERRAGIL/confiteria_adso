# Explicacion del Codigo - Confiteria ADSO

## Estructura General

La pagina tiene un diseño desktop de 1920px. Todas las medidas son fijas (pixeles exactos) para que se vea igual en cualquier pantalla grande.

## Elementos Principales

### 1. Header (Encabezado)
- **Clase:** `.header`
- **Funcion:** Barra superior con logo, buscador e iconos
- **Porque:** Usa `display: flex` con `justify-content: space-between` para separar el logo (izquierda), buscador (centro) e iconos (derecha)
- **Color:** `#332f2e` (gris oscuro) para contrastar con el contenido blanco

### 2. Botones "DULCES" y "REGALOS"
- **Clase:** `.botones`, `.dulces`, `.regalos`
- **Funcion:** Navegacion principal de la tienda
- **Porque:** Cada boton ocupa el 50% del ancho (`width: 50%`) con flexbox para centrar el texto

### 3. Carrusel Hero
- **Clase:** `.hero-carousel`, `.carousel-track`, `.carousel-slide`
- **Funcion:** 3 banners que rotan automaticamente
- **Porque:** 
  - El track mide 300% de ancho (3 slides de 33.333% cada uno)
  - Usa `animation: slide 12s infinite` con keyframes que mueven el track
  - Pausa ~30% del tiempo en cada slide antes de avanzar

### 4. Botones de Navegacion (Categorias)
- **Clase:** `.navegacion`, `.btn-categorias`, `.btn-nav`
- **Funcion:** Filtros de productos
- **Porque:** 
  - `.navegacion` usa flexbox con `gap: 46px` para separar los botones
  - `.btn-categorias` tiene texto a la izquierda y flecha a la derecha con `position: absolute`

### 5. Tarjetas de Productos
- **Clase:** `.tarjetas-productos`, `.tarjeta1`
- **Funcion:** Mostrar productos en una cuadricula
- **Porque:** 
  - `display: grid` con `grid-template-columns: repeat(3, 550px)` crea 3 columnas exactas
  - Cada tarjeta mide 550x632px fijos
  - Usa `margin-top: auto` en el boton para que siempre quede al fondo

### 6. Seccion de Video
- **Clase:** `.video-section`, `.video-container`
- **Funcion:** Video principal con reproduccion automatica
- **Porque:** El contenedor tiene `max-width: 1734px` con bordes redondeados y sombra

### 7. Tarjetas de Video
- **Clase:** `.tarjetas-video`, `.tarjeta-video`
- **Funcion:** Selectores de videos (3 miniaturas)
- **Porque:** Sobrescribe el grid de productos con `grid-template-columns: repeat(3, 343px)` para tarjetas mas angostas

### 8. Banners
- **Clase:** `.banners`, `.banner-link`
- **Funcion:** 3 banners verticales promocionales
- **Porque:** `display: flex` con `flex-direction: column` para apilarlos, cada uno de 1497x499px

### 9. Footer
- **Clase:** `.footer`
- **Funcion:** Pie de pagina con informacion de contacto y navegacion
- **Porque:** 
  - Mide 1920x602px fijos con fondo `#332f2e`
  - Todos los elementos usan `position: absolute` para colocacion exacta por pixeles
  - El logo mide 291x291px, los textos estan en blanco
  - Separadores (lineas) decorativas con colores naranja y gris
  - Iconos de redes sociales con fondo blanco detras (`.fondo_icono`)

## Conceptos Claves Usados

| Concepto | Donde se usa | Porque |
|----------|-------------|--------|
| Flexbox | Header, botones DULCES/REGALOS, navegacion, banners | Para alinear elementos en una sola direccion |
| Grid | Tarjetas de productos y videos | Para crear columnas exactas sin que se envuelvan |
| Position Absolute | Footer, iconos, texto del boton categorias | Para colocar elementos en pixeles exactos |
| CSS Animation | Carrusel | Para mover automaticamente las 3 imagenes |
| Overflow hidden | Carrusel, imagen de fondo | Para ocultar lo que se sale del contenedor |
