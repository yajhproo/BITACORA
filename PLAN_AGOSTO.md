# PLAN DE AGOSTO — ACTUALIZADO

## Objetivo del mes

Construir y publicar mi primera página web con `HTML`, `CSS` y `JavaScript` separados, usando IA como apoyo pero tomando decisiones propias sobre diseño, funcionamiento y correcciones.

## Plan que me propuse y resultado real

- [x] **Dom 16** — Leer el plan completo, entender el flujo de trabajo con archivos `.md` y organizar mentalmente lo que iba a hacer. **(Listo el 16)**
- [x] **Lun 17** — Investigar lo básico de vibecoding, HTML y CSS, y comenzar una página sencilla. **(Iniciado el 17)**
- [x] **Vie 21** — Mejorar la parte visual y empezar a convertir la página en algo aplicable a SATPHONE. **(Quedó consolidado el 23)**
- [x] **Sab 22** — Revisar opciones para manejar inventario/datos sin obligar al dueño a modificar código. **(La idea quedó planteada, pero se decidió dejar base de datos/panel administrativo para una versión futura)**
- [x] **Dom 23** — Primera entrega de la página y reporte. **(Entregado el 23)**
- [x] **Vie 28** — Revisar las correcciones recibidas y decidir cómo resolverlas. **(Revisado entre el 28 y el 30)**
- [x] **Sab 29** — Hacer pruebas de funcionamiento, móvil y navegación. **(Terminado el 30)**
- [x] **Dom 30** — Aplicar correcciones, instalar/configurar Git, subir el proyecto a GitHub y preparar la publicación. **(Listo el 30)**

## Diferencias entre lo planeado y lo real

La idea inicial era hacer una página más sencilla y dedicar una parte del tiempo a investigar una base de datos. Durante el desarrollo decidí priorizar primero una versión estática funcional y dejar el panel administrativo, base de datos, integración con Instagram y cuestionario de repuestos como mejoras futuras.

También subestimé el tiempo que tomaría entender Git y resolver errores de configuración. La instalación, identidad de Git, correo privado de GitHub y primer `push` me tomaron más tiempo de lo esperado.

## Lo que aprendí sobre estimación

Para el próximo mes quiero separar mejor tres tipos de tiempo:

1. Tiempo de construcción.
2. Tiempo de pruebas y correcciones.
3. Tiempo de publicación/configuración.

# REPORTE — AGOSTO

## Proyecto: WEB.SATPHONE

## 1. Qué había que hacer

El objetivo de agosto era construir y publicar mi primera página web usando `index.html`, `styles.css` y `script.js` separados. La página debía servirme para practicar diseño web, trabajar con IA de forma dirigida y empezar a desarrollar criterio para detectar problemas de interfaz y funcionamiento.

Decidí aplicar el ejercicio a SATPHONE, negocio de mi hermano. SATPHONE significa **Servicio Técnico, Accesorios y Tecnología**.

El proyecto evolucionó desde una página informativa sencilla hasta un prototipo con:

- Inicio informativo.
- Catálogo de productos.
- Catálogo de repuestos.
- Buscadores y filtros.
- Cesta.
- Generación de solicitudes por WhatsApp.
- Información sobre servicios.
- Novedades.
- Enlaces a Instagram y reseñas.
- Diseño responsive.
- Navegación directa a las secciones principales.

---

## 2. Qué caminos tenía

### Una sola página larga o varias vistas

Al principio podía dejar todos los productos, servicios e información en una sola página vertical. Después de probarla consideré que mezclar todo iba a hacer más difícil navegar cuando creciera el inventario.

Por eso separé Inicio, Productos y Repuestos.

### Servicios y repuestos juntos o separados

Primero utilicé una pantalla de Servicio Técnico. Después noté que servicios como software, diagnóstico o microelectrónica necesitan asesoramiento, mientras que una batería o pantalla sí puede manejarse como un repuesto visible.

Decidí dejar la explicación de servicios en Inicio y usar la tercera vista para Repuestos.

### Inventario escrito en código o administrable

Para el prototipo guardé productos y repuestos en arrays dentro de JavaScript. Esto fue práctico para aprender y construir rápido, pero no es realista como solución final porque el dueño no debería modificar código para agregar un producto.

Consideré Excel, una base de datos y un panel privado de administración. Dejé esta decisión para una etapa futura porque todavía no era parte de agosto.

### Cesta solo en memoria o persistente

Inicialmente la cesta vivía únicamente en una variable de JavaScript. Eso funcionaba hasta que el usuario recargaba la página.

Consideré `sessionStorage`, cookies, base de datos y `localStorage`. Elegí `localStorage` porque permite conservar la cesta al recargar o cerrar la pestaña sin necesitar todavía un backend.

### Tarjetas con alturas diferentes o estructura estable

Las descripciones tenían longitudes diferentes y eso movía el precio y los botones de cada tarjeta.

Podía limitar todos los textos manualmente, pero eso no resolvería el problema cuando el inventario real tenga información desigual.

Elegí Flexbox para que la tarjeta soporte contenido variable y mantenga alineada su parte inferior. Además añadí mi idea de mostrar una descripción corta con `...` y una ventana **Ver detalles...** para consultar el contenido completo sin ocupar toda la pantalla.

### Tres bloques ocultos o navegación con dirección

Al principio Inicio, Productos y Repuestos eran bloques mostrados/ocultados con JavaScript, pero compartían la misma URL.

Podía crear tres HTML separados, usar parámetros, History API o hashes.

Elegí `#inicio`, `#productos` y `#repuestos` porque solucionan enlace directo, recarga y navegación Atrás/Adelante sin necesitar framework ni cambiar la estructura completa.

---

## 3. Cuál escogí y por qué

Escogí mantener SATPHONE como una página estática por ahora, pero haciendo que se comporte de forma más sólida.

### `localStorage`

La cesta se guarda en el navegador cada vez que cambia. Cuando la página vuelve a abrirse, se leen esos datos y se reconstruye.

Lo escogí porque resuelve el problema actual con poca complejidad y funciona en una página publicada estáticamente.

### Flexbox + detalles ampliados

Las tarjetas usan Flexbox para mantener precio, stock y botón alineados. La descripción visible queda resumida y puede terminar en `...`, mientras que **Ver detalles...** abre una tarjeta ampliada predeterminada con la información completa.

Esto permite que el contenido real sea desigual sin desordenar el catálogo.

### Navegación por hash

La dirección refleja la sección actual:

- `#inicio`
- `#productos`
- `#repuestos`

Así es posible compartir directamente Productos o Repuestos, recargar conservando la vista y utilizar Atrás/Adelante.

### Git y GitHub

Instalé Git para Windows, inicialicé el repositorio local y publiqué el proyecto mediante Git desde la terminal.

Durante el primer `push` tuve que resolver dos problemas que no esperaba:

1. Git no tenía configurada mi identidad y no podía crear correctamente el primer commit.
2. GitHub rechazó el push porque el commit estaba utilizando un correo privado.

Configuré el correo `noreply` de GitHub, corregí el autor del commit y repetí el `push`.

Esto me ayudó a entender mejor que un commit no es solamente “subir archivos”: tiene autor, historial y metadatos.

---

## 4. Qué quedó pendiente o dudoso

El proyecto publicado sigue siendo un prototipo.

### Inventario real

Los productos, precios y cantidades son datos de demostración. Mi hermana Sara ofreció hacer el inventario del negocio de Juanse, y mi idea es reutilizar ese trabajo como base para cargar los datos reales en lugar de crear un inventario aparte para la web.

### Panel privado

La solución final no debería obligar al dueño a modificar JavaScript. Quiero estudiar un panel restringido donde el encargado pueda agregar imagen, nombre, descripción, precio, cantidad y categoría mediante un formulario.

### Base de datos

Una base de datos es una opción, pero todavía no he elegido tecnología. Primero quiero definir la forma más sencilla de administrar la información y después decidir dónde debe almacenarse.

### Cuestionario de repuestos

Quedó planteada una interfaz que haga preguntas al cliente sobre equipo, daño, repuesto, causa, tiempo que puede esperar y descripción libre. Al finalizar debería generar un mensaje organizado para WhatsApp.

### Instagram

Existe un espacio para una futura integración de publicaciones recientes, pero no la implementé todavía porque requiere estudiar la conexión correcta con Instagram/Meta.

### Fotografías reales

Los iconos y emojis son temporales. La versión real debería usar fotografías de productos, repuestos, máquinas y trabajos.

### Reserva real

`localStorage` conserva la cesta solamente en el navegador del cliente. No sincroniza dispositivos ni descuenta inventario real. Para una reserva real habría que desarrollar un sistema del lado del servidor.

---

## Cierre

La parte más importante que me llevo de agosto es que una página no está terminada solamente porque “se ve” o porque los botones responden.

Ahora también reviso:

- dónde viven los datos;
- qué ocurre al recargar;
- cómo se comporta contenido de diferente tamaño;
- qué pasa en celular;
- si se puede compartir una sección;
- si Atrás/Adelante funcionan;
- y si una persona que no programa podría utilizar el sistema en una versión real.

La página fue construida con apoyo fuerte de IA, pero mi objetivo para los siguientes proyectos es seguir aumentando mi capacidad de entender, probar y decidir sobre lo que la IA genera.

