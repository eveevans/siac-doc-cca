---
layout: docs
title: Escalas
prev_section: evaluaciones
next_section: periodo_lectivos
permalink: /docs/escalas/
---

El sistema soporta la introducción de calificaciones literales. Al ingresar en la opción de *Escalas* del menú se muestra un listado con las escalas
existentes:

![listado](/img/docs/escalas_index.png)

<div class="note info">
  <h5>Seguridad</h5>
  <p>Se necesita el permiso <i>ESCALA_MANAGE</i> en el perfil del usuario para acceder a todas las opciones de las escalas literales.</p>
</div>

## Crear Escala

Al seleccionar la opción *Nueva escala* se despliega el siguiente formulario:

![crear](/img/docs/escalas_new.png)

Se debe ingresar un *Nombre* para la escala. Adicionalmente, si se checkea el campo *Mostrar leyenda*, entonces la escala se mostrará como 
leyenda al pie de los reportes de calificaciones de los padres de familia.

Internamente, las calificaciones siempre se representan de forma numérica en el sistema. Por consiguiente, la escala literal debe estar compuesta
por diferentes intérvalos, a los cuales le será asignada letra correspondiente. Los campos a introducir en los intérvalos son:

- *Límite*: Límite superior del intérvalo (el límite inferior se calcula automáticamente). Cabe mencionar que el límite superior es excluido 
  del intérvalo.
- *Valor*: Valor del literal al momento de introducir las calificaciones. Este valor debe estar contenido dentro del intérvalo del literal.
- *Nombre*: Literal utilizado para representar la calificación, el cual será utilizado en todos los reportes del sistema, de tal forma que 
  las calificaciones numéricas nunca son expuestas al usuario.
- *Descripción*: Descripción del literal, el cual únicamente es mostrado como leyenda en los reportes si se checkea la opción *Mostrar leyenda*.

Para ilustrar el funcionamiento de la escala, tómese como ejemplo los valores introducidos en la imagen anterior, para el cual los intervalos
resultantes quedarían de la siguiente manera:

- **D**: De 0 a 59.9
- **R**: De 60 a 69.9
- **B**: De 70 a 79.9
- **MB**: De 80 a 89.9
- **E**: De 90 a 100 (el último intérvalo es el único que incluye el extremo superior)

Una vez ingresada la escala, esta podrá asignarse en la [configuración de la materia](/docs/materias/#configuraciones_de_la_materia).

<div class="note">
  <h5>Consistencia en los intérvalos</h5>
  <p>Se recomienda que se tome el tiempo necesario en la definición de la escala para hacerla lo más consistente posible. Siguiendo el ejemplo 
    con los valores de la imagen, si un bloque se califica con <b>E</b> y el siguiente se califica con <b>MB</b>, entonces el consolidado
    semestral será: <b>(95 + 85)/2 = 90 = E</b>. Se recomienda que se efectúen más ejercicios como el anterior para asegurarse que el 
    comportamiento de la escala sea el deseado, puesto que dependiendo de los requerimientos tal vez sea deseable que el promedio entre
    <b>E</b> y <b>MB</b> sea <b>MB</b> en lugar de <b>E</b>.</p>
</div>

## Detalles de la Escala

Al visualizar los detalles de la escala, se muestran todos los campos y el detalle de los intervalos de la misma:

![detalles](/img/docs/escalas_show.png)

Adicionalmente se cuenta con la opción de *Editar* la escala, lo cual desplegará el formulario de modificación con los mismos campos
que el [formulario de creación](#crear_escala), así como también con la opción de *Eliminar* la escala del sistema.

<div class="note warning">
  <h5>Modificar escala en uso</h5>
  <p>Se recomienda que no se modifiquen los valores de los intérvalos de una escala que ya esté en uso y tenga evaluaciones calificadas,
    puesto que si bien los literales podrían no cambiar, se debe recordar que internamente las calificaciones se guardan en su forma numérica,
    y los cambio en la escala <b>no son replicados</b> en las calificaciones, y pueden ocasionar inconsistencias especialmente al momento
    de calcular promedios.</p>
</div>

<div class="note warning">
  <h5>Cuidado al eliminar escala</h5>
  <p>Una escala puede eliminarse incluso si existen materias que la utilicen. Queda a responsabilidad del usuario validar
    que la escala no tenga materias relacionadas.</p>
</div>
