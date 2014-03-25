---
layout: docs
title: Docentes
prev_section: estudiantes
next_section: parientes
permalink: /docs/docentes/
---

Al ingresar en la opción *Docentes* en el menú se desplegará un listado de los docentes del sistema con la opción para ingresar al 
[expediente del docente](#expediente_del_docente):

![listado](/img/docs/docentes_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto se muestran únicamente los docentes *activos* del sistema, es decir, aquellos que se pueden asignar a materias y secciones. Por consiguiente,
  se cuenta con la opción *Mostrar todos* **(2)**, que quita dicha restricción y muestra todos los docentes del sistema.
- Un campo de texto **(4)** para filtrar los docentes por nombre y/o apellidos.
- Si se cuenta con el permiso *DOCENTE_CREATE*, se desbloquea la opción *Nuevo Docente* **(1)** para [ingresar un docente](#crear_docente) en el sistema.
- Si se cuenta con el permiso *DOCENTE_MANAGE*, se desbloquea la opción *Exportar*, lo cual exporta toda la información de los docentes activos en un archivo
  comprimido. El archivo comprimido contiene las fotos de los docentes y una hoja de cálculo de Excel con la información general de sus expedientes.
  Este procesamiento se lleva a cabo en una tarea de fondo del servidor, la cual una vez finalizada enviará una notificación al usuario con las indicaciones 
  para descargar el archivo y un log del procesamiento.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>DOCENTE_READ</i>.</p>
</div>

## Crear Docente

Al dar clic en la opción de crear docente se despliega el siguiente formulario:

![nuevo](/img/docs/docentes_new.png)

En dicho formulario es necesario llenar la información general y de contacto del docente. Al igual que en la [creación de estudiante](/docs/estudiantes/#crear_estudiante),
Se puede incluir una foto para el docente, ya sea seleccionando una imagen en la computadora actual, o se puede utilizar la opción *Tomar* para tomar una fotografía 
desde una cámara que se encuentre conectada a la computadora.

Adicionalmente, el formulario cuenta con una sección de *Asignaturas*, en el cual se deben agregar las asignaturas que el docente imparte:

![nuevo](/img/docs/docentes_new_asignaturas.png)

Las asignaturas que se vayan agregando al docente se listarán en esta sección. Al seleccionar la opción de *Agregar Asignatura* se desplegará el siguiente 
formulario:

![nuevo](/img/docs/docentes_new_asignaturas_2.png)

Si se checkea el campo *Jefe* el docente se convierte en jefe de asignatura, lo cual tiene [implicaciones en los accesos para este objeto](/docs/seguridad/#objetos).

Luego de enviar el formulario exitosamente, se podrá acceder al [expediente del docente](#expediente_del_docente).

<div class="note warning">
  <h5>Asignaturas del Docente</h5>
  <p>Agregarle asignaturas al docente es muy importante:</p>
  <ul>
    <li>No se puede <a href="/docs/secciones#crear_seccin">asignar un docente guía a una sección</a> a menos que el docente imparta al menos
      una asignatura para el nivel correspondiente a la clase.</li>
    <li>No se puede <a href="/docs/materias#crear_materia">asignar un docente a una materia</a> a menos que el docente imparta la asignatura
      correspondiente.</li>
  </ul>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>DOCENTE_CREATE</i>.</p>
</div>

## Expediente del Docente

![detalles](/img/docs/docentes_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(1)** privado a este docente.
- Opción para *Editar* los detalles del docente **(2)**, si se cuenta con el permiso *DOCENTE_UPDATE*, lo cual desplegará el formulario de actualización 
  del docente con los mismos campos del [formulario de creación](#crear_docente).
- Opción para *Eliminar* el docente **(3)**, si se cuenta con el permiso *DOCENTE_MANAGE* y el docente no tenga asignado ninguna sección o materia.

<div class="note">
  <h5>Eliminación de Docente</h5>
  <p>Si el docente tiene asignado alguna sección o materia, para eliminarlo se deberá primero modificar dichas secciones/materias y eliminar las asignaciones
    correspondientes. Sin embargo, esto no se puede hacer en periodos lectivos cerrados, en cuyo caso se recomienda desactivar el docente, de tal forma
    que el expediente del docente queda disponible como un histórico.</p>
</div>

Por su parte, los detalles del expediente del docente se visualizan en las siguientes pestañas:

### General

Información general y de contacto del docente. Al igual que en el [expediente del estudiante](/docs/estudiantes/#general), en la parte inferior se puede acceder a un 
registro de cambios **(4)** en el que se puede visualizar las modificaciones que ha sufrido la información a lo largo del tiempo.

### Asignaturas

En esta pestaña se listan las asignaturas del docente agrupadas por nivel. Las asignaturas para las cuales el docente es jefe se resaltan en negrita.

### Estudios y Experiencia

En estas pestañas se puede agregar información académica y laboral al expediente del docente:

![estudios](/img/docs/docentes_show_estudios.png)

Para agregar un nuevo registro al expediente se puede utilizar la opción *Agregar* **(3)**, siempre y cuando se cuente con el permiso 
*ESTUDIO_MANAGE* para la pestaña de estudios, o *EXPERIENCIA_MANAGE* para la pestaña de experiencia laboral. Esto desplegará el siguiente
formulario:

![estudios](/img/docs/docentes_show_estudios_new.png)

Luego de ingresar los campos y enviar el formulario, la información se desplegará en la pestaña correspondiente. Si se cuenta con el permiso *MANAGE*
correspondiente, se podrá *Editar* **(1)** la entrada, lo cual desplegará el mismo formulario anterior, o bien *Eliminar* **(2)** la entrada
directamente del expediente.

### Usuarios

Únicamente está disponible si se cuenta con el permiso *USUARIO_READ*. [Las funcionalidades de esta pestaña se describen en la sección de seguridad](/docs/seguridad/#objetos).
