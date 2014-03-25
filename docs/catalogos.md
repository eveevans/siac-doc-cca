---
layout: docs
title: Catálogos
prev_section: niveles
next_section: configuracion
permalink: /docs/catalogos/
---

Los catálogos son tablas estáticas del sistema que sufren cambios muy esporádicamente. Los catálogos del sistema son:

- [Niveles](/docs/niveles/).
- Asignaturas.
- Religiones.
- Estados Civiles.
- Escolaridades.
- Recorridos.

A excepción de los [niveles](/docs/niveles), la administración de estos catálogos es bastante similar, y puesto que no tienen mayor impacto en
el funcionamiento del sistema, se abordarán conjuntamente, utilizando las asignaturas como ejemplo.

Al seleccionar la opción correspondiente en el menú se despliega un listado con los elementos:

![listado](/img/docs/catalogos_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Se cuenta con la opción para ingresar un *Nuevo elemento* **(1)** en el sistema.
- Para las asignaturas y recorridos, por defecto se muestran únicamente los elementos *activos* del sistema, es decir, 
  aquellos que se pueden asignarse a otras entidades. Por consiguiente, se cuenta con la opción *Mostrar todos* **(2)**, que quita dicha restricción y 
  muestra todos los elmentos del sistema.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a todas las opciones de administración del catálogo se necesita:</p>
  <ul>
    <li>Para <i>Asignaturas</i>, el permiso <i>ASIGNATURA_MANAGE</i>.</li>
    <li>Para <i>Recorridos</i>, el permiso <i>RECORRIDO_MANAGE</i>.</li>
    <li>Para el resto de catálogos, el permiso <i>CATALOGO_MANAGE</i>.</li>
  </ul>
</div>

## Crear Elemento

Al dar clic en la opción de ingresar nuevo se despliega el formulario de creación, en el cual deberán llenarse los campos correspondientes:

![nuevo](/img/docs/catalogos_new.png)

En el caso particular de las asignaturas, cabe mencionar que deben asignarse a un [nivel](/docs/niveles/). De esta forma, la asignatura de
*MATEMÁTICAS* para *PRIMARIA* se considera diferente que su homónimo en *SECUNDARIA*, con asignaciones de docentes y materias diferentes.

## Detalles del Elemento

En esta pantalla se muestran los detalles del elemento. En el caso particular de las asignaturas, se muestra una pestaña adicional en la
que se listan los *Docentes* asignados (los jefes de asignatura se resaltan en negrita).

![detalles](/img/docs/catalogos_show.png)

- Se puede *Editar* **(1)** el elemento, lo cual nos despliega el formulario de modificación con los mismos campos que el 
  [formulario de creación](#crear_elemento).
- Se puede *Eliminar* **(2)** el elemento siempre y cuando no tenga relación.
