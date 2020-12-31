# css-grid-layout-course

Profe: Leonidas Esteban
---

* Grid Container: va a ser el elemento padre que va a tener puesto un nuevo tipo de display: grid. Nos permite colocar otras propiedades para manipular nuestro layaout.
* Grid Item: Son nuestro componentes, contenido, lo que vamos a manejar. Nuestras filas o columnas que vamos a mover a nuestro gusto. Son hijos directos de grid
* Grid Line: Lineas divisorias horizontales y verticales
* Grid Track: Espacio entre dos líneas adyacentes. Filas y columnas.
* Grid Cell: Celdas, espacio en dos filas adyacentes y 2 columnas adyacentes.
* Grid Area: Espacio rodeado por 4 grid lines

https://css-tricks.com/snippets/css/complete-guide-grid/

Emmet command:
.item{contenido #$}*12

Run server:
```
python -m http.server 8000
```

# Definiendo columnas

Podríamos usar la función **repeat **en grid-template-columns para por ejemplo indicar que se desean 4 columnas de 200px cada una:
```
<style>
    .container{
        display: grid;
        grid-template-columns: repeat(4,200px);
    }
</style>
```

# Definiendo filas

Grid explicito (explicit grid) es cuando nosotros definimos el numero de filas o columnas.
Grid implicito (implicit grid) es cuando tenemos filas o columnas que no definimos pero son parte de nuestro grid.

Aqui dejo un enlace donde se explica mas a detalle:
Implicit/Explicit Grid: https://www.quackit.com/css/grid/tutorial/explicit_vs_implicit_grid.cfm


# Grids identados y tipos de displays

Display subgrid para heredar la configuración del grid padre (cuando se esten anidando grids).
```
display: subgrid;
```

Display inline-grid muestra el grid en una sola linea:
```
display: inline-grid;
```

# Espaciado entre filas y columnas
```
grid-column-gap: 30px;
grid-row-gap: 30px;
grid-gap: rows/columns;
grid-gap: 30px / 30px;
```


# Repetidores, unidades de medida y funciones

Unidad de medida: fracciones fr distrubuye el espacio disponible en formas iguales.

Funciones:
repeat(cantidad, valor) para usar el mismo valor varias veces
minmax(min, max) agregar un valor minimo y maximo para el tamaño al hacer responsive

# Definiendo areas de contenido

grid-template-areas: "header header"
                           "left content"
                           "footer footer";

.header {
  grid-area: header;
}


# Definir el tamaño de las columnas dentro de un grid:

```
grid-column-start: 1;
grid-column-end: 3;
```

Para escribir esto en una sola linea:

```
grid-column: inicio / final;
```

Para usar por espacios: span #
Para usar el espacio de toda la columna usamos -1 al final Ejemplo: grid-column: 1/ -1;


# Definiendo el nombre de lineas

Para nombrar lineas colocamos el nombre entre [ ]. Ejemplo:

```
grid-template-columns: [inicio] 1fr [linea2] 1fr [final];
```

En estos casos no podemos usar la función repeat()


# Manejando el grid implícito

Para cambiar el flujo automático de mi grid:
```
grid-auto-flow: column;
```

Por defecto viene grid-auto-flow: row;
Para asignar el valor por defecto de el espacio de las columnas o filas que no han sido asignadas:
```
grid-auto-columns: valores;
grid-auto-rows: valores;
```

# Alineación de contenido

Para alinear contenido:
justify-items: valor; para alineación horizontal
align-items: valor; para alineación vertical
Los valores que toman por defecto es stretch el cual hace que tomen todo el valor asignado en la fila o columna.

Para asignar la alineación de un solo elemento podemos usar:
```
align-self: valor;
justify-self: valor;
```

# Alineación de filas y columnas

http://cssgridgarden.com/
http://flexboxfroggy.com/

Alineación de filas y columnas

En la clase pasada aprendimos de las propiedades de justify-items (HORIZONTAL) y align-items (VERTICAL). Estas nos sirvieron para alinear los grids dentro del container y también aprendimos las propiedades: justify-self y align-self , que permiten alinear el contenido que tuviesen dentro de estos grids.
En esta clase aprendemos a alinear las columnas y filas; para el caso de las columnas utilizamos: justify-content que organiza las columnas de manera desplagadas horizontalmente.

Por parte de las filas tenemos align-content que organiza las filas de manera desplegadas de forma vertical.
Nota: En este curso hacemos uso de display: grid ; pero si hubieramos utilizado flex el uso de las propiedades se invierte.
