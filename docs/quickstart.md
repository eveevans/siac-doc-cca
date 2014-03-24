---
layout: docs
title: Estudiantes
permalink: /docs/quickstart/
---

Los usuarios de los estudiantes y padres de familia conforman la mayoría de los usuarios del sistema. 
Para estos usuarios, luego de [iniciar sesión](/docs/login/) se mostrará en el área de contenido de la la [pantalla de inicio](/docs/login/#pantalla_de_inicio) 
una pestaña en la que se muestran los estudiantes a los que el usuario tiene acceso:

![estudiante](/img/docs/estudiante_snippet.png)

A como se muestra en la imagen, aparece un resumen del estudiante, su foto y un enlace al expediente.

<div class="note warning">
  <h5>Insolvencia</h5>
  <p>En caso de que no se haya cancelado el mes anterior aparecerá un mensaje de <i>INSOLVENTE</i> en lugar del enlace y no se
    podrá acceder al expediente de estudiante.</p>
</div>

## Expediente del Estudiante

En el expediente del estudiante se muestra toda su información, la cual para mayor facilidad se encuentra organizada en diversas pestañas, 
tal y como se muestra a continuación:

### General

![general](/img/docs/estudiante_general.png)

Información general del estudiante, la cual se mantiene estática o cambia muy esporádicamente. Contiene mayormente información básica y de contacto
del estudiante (código, nombres y apellidos, dirección, fecha y lugar de nacimiento, etc.).

En la parte inferior se puede acceder a un registro de cambios en el que se puede visualizar las modificaciones que ha sufrido la información a lo largo del tiempo:

![historial](/img/docs/estudiante_historial.png)

### Académico

![academico](/img/docs/estudiante_academico.png)

Información académica del estudiante, la cual es diferente para cada periodo lectivo (periodo lectivo, nivel, grado, sección, docente guía, etc.).

Al lado de la información del docente aparece un enlace **(1)** para [enviar un mensaje privado](/docs/mensajes/#crear_mensaje) al docente en cuestión.

Cabe mencionar que las pestañas de *Materias*, *Horarios*, *Médico* e *Incidencias* dependen de la información académica que se tenga seleccionada. Por esta razón,
en la parte inferior de esta pestaña se muestran enlaces **(2)** para visualizar el expediente y calificaciones del estudiante en dicho periodo lectivo.

### Materias

![materias](/img/docs/estudiante_materias.png)

En esta pestaña se muestra un listado de las materias que se encuentra cursando el estudiante, el docente que la imparte (con un enlace **(1)** para 
[enviar un mensaje](/docs/mensajes/#crear_mensaje)), la calificación parcial y un enlace **(2)** para visualizar el detalle de la calificación:

![calificacion](/img/docs/estudiante_calificacion.png)

En esta pantalla se despliegan todas las evaluaciones, exámenes y consolidados de la materia, con sus respectivas descripciones, así como también cualquier observación
del docente sobre la calificación en cuestión.

Alternativamente, se pueden visualizar las calificaciones del estudiante en su totalidad al acceder al enlace *Calificaciones* en la pestaña de *Materias* **(3)**, 
la cual se muestra de la siguiente manera:

![calificacion](/img/docs/estudiante_calificaciones.png)

La hoja de calificaciones contiene en forma tabular todas las calificaciones del estudiante para todas las materias que se encuentra cursando. Esta información se 
encuentra organizada en los diferentes bloques evaluativos o bimestres que conforman el periodo lectivo

<div class="note">
  <h5>Opciones de visualización de la hoja de calificaciones</h5>
  <ul>
    <li>Las evaluaciones se encuentran ocultas por defecto y solo se muestra la columna del <i>Total Acumulado</i>. Para desplegarlas, dar clic en la cabecera del
      bloque evaluativo <b>(3)</b></li>
    <li>Puesto que el área de la pantalla se encuentra reducida por el menú y estilo del sistema, se recomienda maximizar el área de contenido dando clic en el 
      ícono <i>Cambiar modo de pantalla</i> localizado en la esquina superior izquierda de la pantalla. Adicionalmente, el reporte cuenta con una barra de desplazamiento
      horizontal en la parte inferior de la pantalla <b>(5)</b> para facilitar su visualización</li>
    <li>Al situar el cursor encima de cualquier evaluación o examen se visualizará una burbuja mostrando el porcentaje de la evaluación en el total de la calificación.
      Si la calificación se encuentra subrayada <b>(4)</b>, se le mostrarán adicionalmente los comentarios del docente</li>
  </ul>
</div>

Alternativamente, se puede exportar la información de este reporte en formato Excel de dos formas diferentes:

- Si únicamente interesan los bloques consolidados, se puede utilizar la opción *Exportar todo* **(1)**, lo cual exporta las notas bimestrales, semestrales y finales
  y los despliega como un boletín de calificaciones
- Si se quiere visualizar el detalle de las evaluaciones, la opción **Exportar BLOQUE** **(2)** resulta más adecuada, puesto que exporta todas las calificaciones
  del bloque evaluativo que se seleccione, incluyendo los detalles de las evaluaciones y comentarios del docente

### Horario

Muestra el horario de clases del estudiante, si acaso estuviese disponible.

### Médico

Muestra el expediente médico del estudiante, con su información general (altura, peso, tipo de sangre, alergias, etc.), así como también una bitácora médica con
sucesos médicos propios del estudiante.

### Padres y Responsables

Muestra los nombres e información de contacto del padre, madre y responsable(s) del estudiante.

### Incidencias

Muestra los sucesos en los que se encuentra involucrado el estudiante, que pueden afectar ya sea a toda la clase, sección o al estudiante en particular.
