# CSS Grid y Columns - Explicacion Facil

## ¿Que es CSS Grid?

Grid es un sistema de maquetacion que divide la pantalla en **filas** y **columnas** como si fuera una tabla, pero mas flexible.

## Analogia del Ajedrez

Imagina un tablero de ajedrez:
- Las **columnas** van de arriba a abajo (vertical)
- Las **filas** van de izquierda a derecha (horizontal)
- Cada cuadrito es una **celda**

Grid te permite colocar elementos en esas celdas.

## Como se usa en el Proyecto

### Grid de Productos (style.css linea 267)

```css
.tarjetas-productos {
    display: grid;
    gap: 52px;
    grid-template-columns: repeat(3, 550px);
    justify-content: center;
}
```

**Traduccion:**
- `display: grid` → Activo el modo grid
- `grid-template-columns: repeat(3, 550px)` → Creo 3 columnas de 550px cada una
- `gap: 52px` → Espacio de 52px entre cada tarjeta
- `justify-content: center` → Las columnas se centran en la pantalla

### ¿Por que GRID y no FLEXBOX?

Flexbox solo trabaja en UNA direccion (fila O columna). Si usas flexbox con 6 productos y la pantalla se achica, los productos se **envuelven** a la siguiente fila.

Grid te asegura que SIEMPRE sean 3 columnas exactas, sin importar nada. Eso es clave para un diseño desktop fijo.

## Las Propiedades Clave

### 1. `grid-template-columns`
Define cuantas columnas hay y su tamaño.

```css
/* 3 columnas de 550px cada una */
grid-template-columns: 550px 550px 550px;

/* Lo mismo pero mas corto */
grid-template-columns: repeat(3, 550px);

/* 4 columnas que se reparten el espacio disponible */
grid-template-columns: 1fr 1fr 1fr 1fr;
```

### 2. `gap`
El espacio entre celdas (funciona como margin entre elementos del grid).

```css
gap: 52px;  /* 52px entre cada tarjeta */
```

### 3. `repeat()`
Funcion para no escribir lo mismo varias veces.

```css
/* Esto: */
grid-template-columns: repeat(3, 550px);

/* Es igual a: */
grid-template-columns: 550px 550px 550px;
```

## Ejemplo Visual

```
Pantalla completa:
┌──────────┐ ┌──────────┐ ┌──────────┐
│ Tarjeta 1 │ │ Tarjeta 2 │ │ Tarjeta 3 │
│  550px    │ │  550px    │ │  550px    │
└──────────┘ └──────────┘ └──────────┘
←── gap 52px ──→←── gap 52px ──→

┌──────────┐ ┌──────────┐ ┌──────────┐
│ Tarjeta 4 │ │ Tarjeta 5 │ │ Tarjeta 6 │
│  550px    │ │  550px    │ │  550px    │
└──────────┘ └──────────┘ └──────────┘
```

## Diferencia con Flexbox

| Flexbox | Grid |
|---------|------|
| Trabaja en 1 direccion (fila O columna) | Trabaja en 2 direcciones (filas Y columnas) |
| Los elementos se envuelven si no caben | Los elementos siempre respetan las columnas |
| Ideal para barras de navegacion, centrar items | Ideal para cuadriculas de productos, galerias |

## En Nuestro Codigo

1. **Productos:** `grid-template-columns: repeat(3, 550px)` → 3 columnas fijas de 550px
2. **Videos:** `grid-template-columns: repeat(3, 343px)` → 3 columnas fijas de 343px
3. **Iconos footer:** `grid-template-columns: 1fr 1fr 1fr 1fr` → 4 columnas que se reparten el espacio

## Resumen para el Examen

1. Grid = tabla flexible de filas y columnas
2. `grid-template-columns` define el ancho y numero de columnas
3. `gap` define el espacio entre elementos
4. `repeat(3, 550px)` = 3 columnas de 550px
5. Usamos grid cuando queremos control exacto de columnas (como en productos)
6. Usamos flexbox cuando solo necesitamos alinear en una direccion
