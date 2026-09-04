# CHECKLIST PERSONAL — ¿CÓMO SÉ QUE UNA PÁGINA ESTÁ BIEN TERMINADA?

Esta lista sale de lo que aprendí construyendo SATPHONE y de las correcciones de agosto.

## Estructura y contenido

- [ ] La página tiene una función clara y sé explicar para quién está hecha.
- [ ] HTML, CSS y JavaScript están separados y cada archivo cumple su función.
- [ ] Los textos principales se entienden sin tener que adivinar qué hace cada sección.
- [ ] No hay funciones o secciones repetidas que puedan confundir al usuario.
- [ ] Lo que todavía no está terminado se identifica como pendiente y no se presenta como funcional.

## Diseño

- [ ] Hay jerarquía visual: sé qué debería mirar primero el usuario.
- [ ] Los colores, tipografía y espaciados son coherentes.
- [ ] Las tarjetas de una misma fila mantienen precio, stock y botones alineados aunque tengan textos de diferente longitud.
- [ ] El contenido largo no destruye el diseño de la tarjeta.
- [ ] Si oculto parte de una descripción con `...`, existe una forma clara de ver la información completa.
- [ ] Los botones importantes se distinguen de los secundarios.

## Celular / responsive

- [ ] Probé la página aproximadamente en 360–390 px de ancho.
- [ ] No aparece desplazamiento horizontal inesperado.
- [ ] Ningún texto se sale de su contenedor.
- [ ] Los botones siguen siendo fáciles de pulsar.
- [ ] Las tarjetas se acomodan correctamente en móvil.
- [ ] La cesta y las ventanas de detalles se pueden usar en pantalla vertical.

## Funcionalidad

- [ ] Probé todos los botones y enlaces.
- [ ] Probé buscadores y filtros.
- [ ] Probé agregar, aumentar, disminuir y eliminar artículos de la cesta.
- [ ] La cesta no permite superar el stock disponible.
- [ ] La cesta conserva sus datos al recargar la página.
- [ ] La cesta sigue existiendo si cierro y vuelvo a abrir la página en el mismo navegador.
- [ ] El contador de la cesta aparece correcto desde que carga la página.
- [ ] El mensaje de WhatsApp contiene los productos y cantidades correctas.

## Navegación

- [ ] Inicio, Productos y Repuestos tienen una dirección identificable con `#inicio`, `#productos` y `#repuestos`.
- [ ] Puedo copiar un enlace terminado en `#productos` o `#repuestos` y abre directamente esa sección.
- [ ] El botón Atrás del navegador vuelve a la vista anterior.
- [ ] El botón Adelante vuelve a funcionar correctamente.
- [ ] Si recargo en Productos o Repuestos, permanezco en esa vista.

## Pruebas finales

- [ ] Probé la página desde cero y no solamente desde el estado en el que estaba trabajando.
- [ ] Recargué varias veces para buscar errores.
- [ ] Probé al menos una ruta diferente a la “normal”.
- [ ] Revisé la consola del navegador si algo se comportó raro.
- [ ] Confirmé que los tres archivos guardados son los mismos que voy a subir.
- [ ] Ejecuté `git status` antes de publicar.
- [ ] Hice un `commit` con un mensaje que explica el cambio.
- [ ] Hice `push` y confirmé que GitHub tiene la versión correcta.
- [ ] Abrí el enlace publicado y lo probé nuevamente.

## Regla que quiero conservar para los siguientes proyectos

Una corrección que ya aprendí en un proyecto debería entrar automáticamente a este checklist para no repetirla en el siguiente.
