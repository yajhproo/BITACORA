# TRES BLOQUES DE `script.js` EXPLICADOS CON MIS PALABRAS

## 1. La cesta

La cesta es la parte que guarda qué productos o repuestos eligió el cliente y cuántas unidades quiere de cada uno.

Cada artículo de la cesta no necesita copiar toda la información del producto. Principalmente guarda su tipo, su `id` y la cantidad. Con ese `id`, el programa puede volver a buscar el nombre, precio, stock y demás información dentro de los arrays de productos o repuestos.

Cuando agrego un artículo, el código primero revisa si ya existe en la cesta. Si ya existe aumenta la cantidad, pero solamente mientras no supere el stock. Si no existe, crea una nueva entrada con cantidad 1.

Después `renderizarCesta()` vuelve a construir visualmente la cesta: muestra los artículos, calcula cuántas unidades hay y suma el total aproximado.

La corrección importante fue entender que antes la cesta solamente estaba en una variable de JavaScript. Al recargar, esa memoria desaparecía. Ahora se guarda también en `localStorage`. Cuando cambia la cesta se vuelve a guardar, y cuando se abre la página se lee el contenido guardado y se reconstruye.

Mi forma de verlo es:

`cesta en JavaScript → guardar en localStorage → recargar → leer localStorage → reconstruir cesta`

Esto me ayudó a entender por primera vez el concepto de **estado**: no solamente importa qué dato tengo, también importa dónde vive y cuánto tiempo debe durar.

---

## 2. Navegación con `hash`

Antes Inicio, Productos y Repuestos parecían pantallas diferentes, pero para el navegador todas eran la misma dirección. JavaScript solamente ocultaba una parte y mostraba otra.

La corrección fue usar el texto que aparece después de `#` en la URL.

Ejemplos:

- `#inicio`
- `#productos`
- `#repuestos`

Cuando hago clic en Productos, en lugar de limitarme a ocultar y mostrar bloques, se cambia la dirección a `#productos`.

El evento `hashchange` detecta ese cambio. Después una función lee el hash y decide cuál vista debe mostrarse.

Así entiendo el flujo:

`clic → cambia el # de la URL → hashchange → JavaScript lee la dirección → muestra la vista correcta`

Esto hace que pueda enviar un enlace directo a Repuestos, recargar sin volver al Inicio y usar los botones Atrás y Adelante del navegador.

---

## 3. Creación de tarjetas y detalles

Los productos y repuestos no están escritos uno por uno en el HTML. JavaScript recorre los arrays y crea una tarjeta para cada objeto.

Cada objeto contiene información como:

- `id`
- nombre
- categoría
- descripción
- detalle
- precio
- stock
- icono

La función que crea las tarjetas utiliza esos valores para construir el HTML que ve el usuario.

Separé mentalmente dos tipos de información:

- `descripcion`: texto corto para la tarjeta.
- `detalle`: información más larga para la ventana ampliada.

En la tarjeta normal la descripción ocupa un espacio limitado y, si es más larga, aparecen `...`. El usuario puede pulsar **Ver detalles...** y JavaScript busca nuevamente el artículo por su `id` para abrir una tarjeta ampliada con la información completa.

Además, con Flexbox la zona inferior de cada tarjeta se empuja hacia el fondo, por lo que precio, stock y botón permanecen alineados aunque el contenido superior sea diferente.

---

# UNA COSA QUE ROMPÍ A PROPÓSITO

Para comprobar que entendía la navegación por hash, cambié temporalmente uno de los valores de una vista para que no coincidiera con los valores válidos que espera el código.

Por ejemplo, cambié temporalmente:

`data-vista="productos"`

por un nombre que el programa no reconocía.

Al pulsar el botón, la navegación dejó de poder mostrar correctamente esa vista. Al devolver el mismo nombre en el botón, el hash y el objeto de vistas, volvió a funcionar.

Con eso comprobé que el nombre no es decorativo: es la referencia que conecta el botón, la URL y la vista que JavaScript debe mostrar.

> Nota para mí antes de entregar: si finalmente hago otra prueba intencional diferente, reemplazar este ejemplo por la prueba que realmente hice.
