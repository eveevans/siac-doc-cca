---
layout: docs
title: Secciones
prev_section: clases
next_section: materias
permalink: /docs/secciones/
---

Al ingresar en la opción *Secciones* en el menú se desplegará un listado de las secciones del sistema con la opción para ingresar a
los [detalles de la sección](#detalles_de_la_seccin):

![listado](/img/docs/secciones_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto, se muestran las secciones del periodo lectivo actual. Si se quiere visualizar información histórica, se debe *Mostrar filtros* **(2)**
  y seleccionar un periodo lectivo diferente.
- Se puede *Mostrar filtros* **(2)** y limitar las secciones mostradas por nivel y clase.
- Si se cuenta con el permiso *SECCION_MANAGE*, se desbloquea la opción *Nueva Sección* **(1)** para [ingresar una sección](#crear_seccin) en el sistema.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita:</p>
  <ul>
    <li>Permiso <i>SECCION_READ</i> para visualizar todas las clases del sistema.</li>
    <li>Objeto tipo <i>Docente</i> que sea guía de al menos una sección.</li>
    <li>Objeto tipo <i>Nivel</i> o <i>Clase</i> con el rol <i>SECCION_READ</i> para visualizar las secciones que pertenezcan a la clase o nivel correspondiente.</li>
  </ul>
</div>

## Crear Sección

Al dar clic en la opción de crear sección se despliega el siguiente formulario:

![nuevo](/img/docs/secciones_new.png)

Solamente se pueden crear secciones para los periodos lectivos abiertos. Adicionalmente, la combinación de *Clase* y *Nombre* debe ser única 
para el periodo lectivo seleccionado.

El docente que se designe como guía de la sección debe tener [asignada al menos una asignatura](/docs/docentes/#crear_docente) para el nivel especificado.

<div class="note">
  <h5>Creación masiva de secciones</h5>
  <p>Si la estructura académica suele cambiar poco entre un periodo lectivo y el siguiente, como es el caso casi siempre, se puede hacer uso de 
    la funcionalidad de <a href="/docs/periodo_lectivos/#copiar">copiar periodo lectivo</a> para duplicar esta estructura al periodo lectivo siguiente y 
    evitarse el trabajo de introducir manualmente las secciones.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>SECCION_MANAGE</i>.</p>
</div>

## Detalles de la Sección

![detalles](/img/docs/secciones_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(1)** a toda la sección. En el destinatario se podrá seleccionar si se quiere
  enviar a los estudiantes y padres de familia, a los docentes o a ambos.
- Opción para *Editar* los detalles de la sección **(2)**, si se cuenta con el permiso *SECCION_MANAGE* y el periodo lectivo está abierto, 
  lo cual desplegará el formulario de actualización de la sección con los mismos campos del [formulario de creación](#crear_seccin).
- Opción para *Eliminar* la sección **(3)**, si se cuenta con el permiso *SECCION_MANAGE*, el periodo lectivo está abierto y la sección no tiene
  ningún estudiante asignado.

Por su parte, los detalles de la sección se visualizan en las siguientes pestañas:

### General

Información general de la sección (periodo lectivo, nivel, grado, docente guía e información básica de auditoría).

- Se puede [visualizar la clase](/docs/clases/#detalles_de_la_clase) **(4)** si se cuenta con el permiso *CLASE_READ*.
- Se puede [visualizar el docente guía](/docs/docentes/#expediente_del_docente) **(5)** si se cuenta con el permiso *DOCENTE_READ*. Adicionalmente,
  se cuenta con la opción para [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje).

### Materias

Esta pestaña muestra un listado de las materias que se cursan en la sección. El listado se muestra de la misma forma que en la 
[pestaña homónima de la clase](/docs/clases/#materias), con la excepción de que no hay ninguna opción disponible para crear materias.

### Estudiantes

Esta pestaña muestra un listado de todos los estudiantes asignados a la sección.

![estudiantes](/img/docs/secciones_show_estudiantes.png)

- Se puede [administrar la asignación de estudiantes a la sección](/docs/clases/#asignar_estudiantes) **(1)** si se cuenta con el permiso *ESTUDIANTE_CLASE_MANAGE*.
- Se puede exportar el listado de estudiantes **(2)** a una hoja de cálculo de Excel con 2 hojas: una para registrar las asistencias y otroas para las notas.
- Se pueden exportar los boletines de todos los estudiantes **(3)** en una hoja de cálculo de Excel si se cuenta con el permiso *SECCION_BOLETIN*.
- Se puede [visualizar un reporte de calificaciones](/docs/clases/#calificaciones) **(4)** consolidado para todos los estudiantes de la sección.
- Para cada estudiante se cuenta con la opción de [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje) **(5)**.
- Se puede [visualizar el expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante) **(6)** si se cuenta con el permiso *ESTUDIANTE_READ*.

### Horario

Esta pestaña muestra el horario de clases de la sección.

![horario](/img/docs/secciones_show_horarios.png)

Adicionalmente, si se cuenta con el permiso *SECCION_MANAGE* o con un objeto tipo *Docente* el cual es guía de esta sección, se desbloquea la opción
para administrar el horario de clases de la sección. Esto muestra el siguiente formulario:

![horario](/img/docs/secciones_show_horarios_manage.png)

Se debe seleccionar una materia (o alternativamente para periodos de receso por ejemplo, introducir una descripción) y llenar el resto de campos obligatorios
para agregar una entrada en el horario de clases.

Debajo del formulario se listan todas las entradas del horario de clases con una opción para *Eliminar* la entrada en caso de que sea necesaria alguna correción.

### Incidencias

Se muestran los sucesos que involucran a los estudiantes de esta sección. El funcionamiento de esta pestaña es análogo al de su 
[homónimo en el expediente del estudiante](/docs/estudiantes/#incidencias). Para crear incidencias se requiere el permiso *SECCION_MANAGE* o un objeto
tipo *Docente* el cual es guía de esta sección.
