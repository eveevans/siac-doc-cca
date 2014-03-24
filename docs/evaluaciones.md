---
layout: docs
title: Evaluaciones
permalink: /docs/evaluaciones/
---

Al ingresar en la opción *Evaluaciones* en el menú se desplegará un listado de las evaluaciones del sistema con la opción para ingresar a
los [detalles de la evaluación](#detalles_de_la_evaluacin):

![listado](/img/docs/evaluaciones_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto, se muestran las evaluaciones del periodo lectivo actual. Si se quiere visualizar información histórica, se debe *Mostrar filtros*
  y seleccionar un periodo lectivo diferente.
- Se puede *Mostrar filtros* y limitar las evaluaciones mostradas por nivel, clase y asignatura.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita:</p>
  <ul>
    <li>Permiso <i>EVALUACION_READ</i> para visualizar todas las clases del sistema.</li>
    <li>Objeto tipo <i>Docente</i>, en cuyo se listarán las evaluaciones de materias que el usuario imparta con el mismo con opción para calificar,
      y las materias de las secciones de las cuales el docente es guía en modo de visualización.</li>
    <li>Objeto tipo <i>Nivel</i> o <i>Clase</i> con el rol <i>EVALUACION_READ</i> para visualizar las evaluaciones que pertenezcan a la clase o 
      nivel correspondiente.</li>
  </ul>
</div>

## Crear Evaluación

No existe ninguna opción desde el listado de evaluaciones que se mostró anteriormente para crear una evaluación. Por consiguiente, 
para crear una evaluación, se debe dar clic en la opción *Agregar* en la pestaña de [evaluaciones de la materia](/docs/materias/#evaluaciones),
lo cual desplegará el siguiente formulario:

![nuevo](/img/docs/evaluaciones_new.png)

- Se debe seleccionar una *Sección* para la evaluación. No se pueden crear evaluaciones globales para una clase.
- Se debe seleccionar un *Tipo* de evaluación. Los tipos permitidos dependen de la [configuración de la materia](/docs/materias/#configuraciones_de_la_materia),
  y pueden ser cualquiera de los siguientes:
  - *Acumulado*: Pueden ingresarse cualquier número de evaluaciones acumulativas. El campo de *Porcentaje* siempre es requerido para este tipo.
  - *Examen*: Solo puede ingresarse un examen por bloque. El campo de *Porcentaje* requerido si el porcentaje del examen es variable.
  - *Reparación*: Solo se pueden ingresar cuando estén consolidados todos los bloques evaluativos.
- Se debe especificar una *Fecha* de la evaluación, la cual debe ser única para la sección. Opcionalmente se puede especificar la *Hora*.
- Se debe seleccionar el *Porcentaje* de la evaluación solo si es requerido, en caso contrario el valor será ignorado y se determinará automáticamente.
- Aunque no es requerido, se recomienda ingresar *Observaciones* breves, puesto que se muestran en diversos reportes de calificaciones del sistema,
  y puede serle de interés a los padres de familia.

Al enviar el formulario, automáticamente se agregarán los estudiantes que son evaluados, los cuales comprenden todos los estudiantes para acumulado y examen, y 
los estudiantes reprobados para reparación.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>MATERIA_EVALUAR</i>.</p>
</div>

## Detalles de la Evaluación

Se muestran dos pestañas: la pestaña *General* muestra la información general y de auditoría de la evaluación, y la pestaña *Calificaciones* lista
todos los estudiantes evaluados con sus calificaciones correspondientes (si se muestra un guión significa que la calificación todavía no se ha introducido).

![detalles](/img/docs/evaluaciones_show.png)

- Se puede *Calificar* **(1)** la evaluación si el periodo lectivo y el bloque están abiertos están abiertos, y se cuenta con el permiso *MATERIA_EVALUAR*, lo cual desplegará
  el [formulario ingreso de calificaciones](#calificar_evaluacin).
- Se puede *Editar* **(2)** la evaluación si el periodo lectivo y el bloque están abiertos, y se cuenta con el permiso *EVALUACION_MANAGE*, lo cual desplegará 
  el formulario de modificación con los mismos campos que el [formulario de creación](#crear_evaluacin).
- Se puede *Eliminar* **(2)** la evaluación si el periodo lectivo y el bloque están abiertos, y se cuenta con el permiso *EVALUACION_MANAGE*.

## Calificar Evaluación

El formulario permite introducir todas las calificaciones de la evaluación en una sola pantalla:

![calificar](/img/docs/evaluaciones_calificar.png)

- Para los estudiantes evaluados cuya calificación no se haya introducido, se habilitarán los campos para ingresar la calificación **(1)** y opcionalmente
  una observación, la cual se recomienda utilizar cuando se desee comunicarle información sobre la calificación al padre de familia.
- Si la calificación ya está ingresada, no podrá modificarse a menos que se cuente con el permiso *EVALUACION_MANAGE*. Adicionalmente, se habilitará también
  una opción para eliminar al estudiante de la evaluación **(2)**, en cuyo caso se puede interpretar que el estudiante no formó parte de dicha evaluación (esta opción
  puede ser útil para corregir las calificaciones de los [estudiantes transferidos](/docs/estudiantes/#acadmico) o cuando un estudiante no pueda presentarse
  a un sistemático por motivos de fuerza mayor, por citar un ejemplo).
- Para los estudiantes que no son evaluados, se tiene la opción de *Agregar*, lo cual al igual que la opción anterior, puede ser útil para corregir
  las calificaciones de los [estudiantes transferidos](/docs/estudiantes/#acadmico).
- En el caso de que la materia tenga configurada una [escala literal](/docs/materias/#configuraciones_de_la_materia), en lugar de los campos para introducir
  las calificaciones numéricas se mostrarán listas desplegables para seleccionar el literal correspondiente.
- Si la calificación es numérica, esta puede ser mayor que la nota máxima de la evaluación, en cuyo caso únicamente se dará una advertencia al usuario. Esta opción puede
  ser útil para otorgar puntos extras, o también para reponer evaluaciones a las que el estudiante no pudo presentarse, por ejemplo.

<div class="note warning">
  <h5>Estudiantes Transferidos</h5>
  <p>Cuando se <a href="/docs/estudiantes/#acadmico">transfiere un estudiante entre secciones</a> las calificaciones ya introducidas para el estudiante
    permanecen en el sistema. Sin embargo, este comportamiento puede generar confusiones, puesto que puede asumirse que la calificación fue borrada ya que las 
    evaluaciones pertenecen a otra sección y al calificar las evaluaciones de esta sección aparece la opción de <i>Agregar</i> la calificación. Al hacer esto,
    se crearán inconsistencias en las calificaciones del estudiante, pudiendo ocasionar por ejemplo que la suma de las calificaciones del bloque
    sobrepase el 100 %. Por consiguiente, se recomienda revisar en los reportes de <a href="/docs/materias/#calificaciones">calificaciones de la materia</a>
    que el número y porcentaje de los acumulados sea consistente.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>MATERIA_EVALUAR</i>.</p>
</div>
