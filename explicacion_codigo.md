# Explicacion del Codigo - Confiteria ADSO

## Estructura General
Pagina e-commerce de confiteria. Diseño desktop fijo que se vuelve responsive con media queries.

---

### 1. Header
**Clase:** `.header`
**Sirve para:** Mostrar logo, buscador e iconos de perfil/carrito
**Como funciona:** `display: flex` + `justify-content: space-between` separa logo (izquierda), buscador (centro), iconos (derecha)

### 2. Botones DULCES / REGALOS
**Clase:** `.botones`, `.dulces`, `.regalos`
**Sirve para:** Navegacion principal de categorias
**Como funciona:** Cada boton ocupa `width: 50%` con flexbox centrando el texto a 36px

### 3. Carrusel Hero
**Clase:** `.hero-carousel`, `.carousel-track`, `.carousel-slide`
**Sirve para:** 3 banners que rotan solos
**Como funciona:** Track al 300% de ancho (3 slides al 33.333% cada uno). `animation: slide 12s infinite` mueve el track con keyframes. Pausa ~30% en cada slide

### 4. Navegacion (Categorias)
**Clase:** `.navegacion`, `.btn-categorias`, `.btn-nav`
**Sirve para:** Botones de filtro "Todas las Categorias", "Preferencial", "Mis Pedidos", "Quienes somos"
**Como funciona:** Flexbox con `gap: 46px`. `.btn-categorias` tiene texto y flecha con `position: absolute`

### 5. Tarjetas de Productos
**Clase:** `.tarjetas-productos`, `.tarjeta1`
**Sirve para:** Cuadricula de productos con imagen, nombre, precio y boton
**Como funciona:** `display: grid` con `grid-template-columns: repeat(3, 550px)`. Cada tarjeta mide 550px. `margin-top: auto` en el boton lo empuja al fondo

### 6. Video
**Clase:** `.video-section`, `.video-container`
**Sirve para:** Video principal con autoplay
**Como funciona:** Contenedor de 1734px con border-radius y box-shadow

### 7. Tarjetas de Video
**Clase:** `.tarjetas-video`, `.tarjeta-video`
**Sirve para:** 3 selectores de video
**Como funciona:** Sobrescribe el grid con `repeat(3, 343px)`. Tarjetas mas angostas que las de producto

### 8. Banners
**Clase:** `.banners`, `.banner-link`
**Sirve para:** 3 banners verticales promocionales
**Como funciona:** `display: flex; flex-direction: column`. Cada banner 1497x499px

### 9. Footer Desktop
**Clase:** `.footer`
**Sirve para:** Pie con logo, navegacion, contacto y redes sociales
**Como funciona:** `width: 100%` + `aspect-ratio: 1920/602`. Todos los elementos usan `position: absolute` con porcentajes para escalar proporcionalmente. A menos de 1024px se oculta y muestra el footer mobile

### 10. Footer Mobile
**Clase:** `.footer-mobile`
**Sirve para:** Version responsive del footer
**Como funciona:** `display: none` por defecto. En tablet/phone (≤1024px) se muestra con `display: flex; flex-direction: column`. Contenido apilado verticalmente

---

## Responsive Design (Media Queries)

### Desktop Mediano (1025px - 1750px)
- Grid productos: `repeat(3, 1fr)` en vez de 550px fijos
- Banners: 100% de ancho
- Navegacion: se envuelve si no cabe

### Tablet / iPad Mini (768px - 1024px)
- Header, botones, carrusel reducidos
- Grid: `repeat(3, 1fr)`
- Footer desktop se oculta, se muestra footer mobile

### Phone (≤767px)
- Header se envuelve, buscador abajo
- Productos en **2 columnas**: `repeat(2, 1fr)`
- Navegacion en columna
- Video cards en 1 columna
- Footer mobile

---

## Conceptos Clave

| Concepto | Donde se usa | Para que sirve |
|----------|-------------|----------------|
| Flexbox | Header, navegacion, banners | Alinear elementos en una direccion |
| Grid | Tarjetas productos/videos | Crear columnas exactas sin wrap |
| Position Absolute | Footer, boton categorias | Colocar elementos en posiciones exactas |
| CSS Animation | Carrusel | Mover 3 imagenes automaticamente |
| @media queries | Todo el responsive | Cambiar estilos segun el ancho de pantalla |
| aspect-ratio | Footer | Escalar altura proporcional al ancho |
| overflow: hidden | Carrusel, footer | Ocultar lo que se sale del contenedor |
