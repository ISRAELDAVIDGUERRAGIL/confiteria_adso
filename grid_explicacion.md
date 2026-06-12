# CSS Grid - Explicacion para el Examen

## Que es Grid
Sistema de maquetacion en 2 dimensiones (filas Y columnas). Como una tabla pero mas flexible.

## Propiedades Clave

| Propiedad | Que hace | Ejemplo |
|-----------|----------|---------|
| `display: grid` | Activa el modo grid | `display: grid;` |
| `grid-template-columns` | Define el numero y ancho de columnas | `repeat(3, 550px)` = 3 columnas de 550px |
| `gap` | Espacio entre filas y columnas | `gap: 52px;` |
| `justify-content` | Centra las columnas horizontalmente | `justify-content: center;` |

## repeat()
Evita escribir lo mismo varias veces:
```css
/* Es lo mismo: */
grid-template-columns: 550px 550px 550px;
grid-template-columns: repeat(3, 550px);
```

## 1fr vs px
- **px** = tamaño fijo (no cambia)
- **1fr** = se reparte el espacio disponible (responsivo)

## Grid vs Flexbox

| | Grid | Flexbox |
|--|------|---------|
| Direccion | 2 (filas y columnas) | 1 (fila O columna) |
| Wrap | No, siempre respeta columnas | Si, puede envolver |
| Uso tipico | Cuadriculas, galerias, productos | Barras de nav, centrar items |

## Donde se usa en el proyecto

### Productos (Desktop)
```css
.tarjetas-productos {
    display: grid;
    gap: 52px;
    grid-template-columns: repeat(3, 550px);
    justify-content: center;
}
```
3 columnas fijas de 550px centradas en la pantalla.

### Videos (Desktop)
```css
.tarjetas-video {
    gap: 67px;
    grid-template-columns: repeat(3, 343px);
}
```
3 columnas de 343px para las tarjetas de video.

### Responsive (Tablet y Desktop mediano)
```css
/* Tablet ≤1024px y Desktop mediano 1025-1750px */
.tarjetas-productos {
    grid-template-columns: repeat(3, 1fr);
}
```
3 columnas flexibles que se reparten el espacio.

### Phone (≤767px)
```css
.tarjetas-productos {
    grid-template-columns: repeat(2, 1fr);
}
```
2 columnas en telefono.

### Iconos del Footer
```css
.iconos-footer {
    grid-template-columns: 1fr 1fr 1fr 1fr;
}
```
4 columnas iguales para los iconos de redes.

## Resumen para el examen
1. Grid = filas + columnas
2. `repeat(3, 550px)` = 3 columnas de 550px
3. `repeat(3, 1fr)` = 3 columnas flexibles
4. `gap` = espacio entre celdas
5. Se usa grid cuando quieres control exacto de columnas (ej: productos siempre en 3 columnas)
6. Se usa flexbox cuando solo necesitas alinear (ej: centrar items en una barra)
