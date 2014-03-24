---
layout: docs
title: Estudiantes
permalink: /docs/estudiantes/
---

Al ingresar en la opción *Estudiantes* en el menú se desplegará un listado de los estudiantes del sistema con la opción para ingresar al 
[expediente del estudiante](#expediente_del_estudiante):

![listado](/img/docs/estudiantes_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto, se muestran los estudiantes del periodo lectivo actual. Si se quiere visualizar información histórica, se debe *Mostrar filtros* **(1)**
  y seleccionar un periodo lectivo diferente.
- Si el número de estudiantes es demasiado extenso, se puede *Mostrar filtros* **(1)** y limitar los resultados por código, nombres y/o apellidos,
  periodo lectivo o clase.
- Si se cuenta con el permiso *ESTUDIANTE_CREATE*, se desbloquea la opción *Nuevo* **(2)** para [ingresar un estudiante](#crear_estudiante) sin ninguna ayuda,
  o alternativamente se puede *Importar* **(3)** la [información del estudiante](#importar_estudiante) desde el sistema administrativo.
- Si se cuenta con el permiso *ESTUDIANTE_MANAGE*, se desbloquea la opción *Importar fotos* **(4)** que nos permite 
  [actualizar las fotos de los estudiantes masivamente](#importar_fotos).

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita:</p>
  <ul>
    <li>Permiso <i>ESTUDIANTE_READ</i> para visualizar todos los estudiantes del sistema.</li>
    <li>Objeto tipo <i>Estudiante</i> o <i>Pariente</i> para visualizar los estudiantes que estén asignados al usuario.</li>
    <li>Objeto tipo <i>Docente</i> para visualizar todos los estudiantes que estén en una sección del cual el docente sea guía.</li>
    <li>Objeto tipo <i>Nivel</i> o <i>Clase</i> con el rol <i>ESTUDIANTE_READ</i> para visualizar todos los estudiantes del nivel o clase determinado.</li>
  </ul>
</div>

## Crear estudiante

Al dar clic en la opción de crear estudiante se despliega el siguiente formulario:

![nuevo](/img/docs/estudiantes_new.png)

El formulario está dividido en diferentes secciones:

- *Datos Generales*: Datos generales y de contacto del estudiante. Se puede incluir una foto para el estudiante, ya sea seleccionando una 
  imagen en la computadora actual **(1)**, o se puede utilizar la opción *Tomar* **(2)** para tomar una fotografía desde una cámara que se 
  encuentre conectada a la computadora.
- *Datos Académicos*: Se debe asociar al estudiante a una sección específica, y especificar la fecha de transferencia (para estudiantes que se transfieren
  de otros colegios) y si el estudiante es repitente.
- *Datos Médicos*: Información médica del estudiante. Todos los campos de esta sección son opcionales.

Luego de enviar el formulario exitosamente, se podrá acceder al [expediente del estudiante](#expediente_del_estudiante).

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>ESTUDIANTE_CREATE</i>.</p>
</div>

## Importar estudiante

Alternativamente, si el estudiante ya se ha ingresado en el sistema administrativo y ya cuenta con un código de estudiante, entonces se puede
importar dicha información utilizando esta funcionalidad:

![importar](/img/docs/estudiantes_importar.png)

Primeramente se debe introducir el *Código* del estudiante en el campo de texto y darle clic a la opción *Obtener datos*. En caso de éxito, se consultará
directamente la base de datos administrativa y se extraerá la información general, académica y de los padres de familia y responsables del estudiante, la
cual se desplegará en el mismo formulario para que el usuario la verifique antes de ingresar el estudiante:

![importar](/img/docs/estudiantes_importar_2.png)

En el caso de los pares de familia y responsables, se da la opción de ingresar o no individualmente cada uno de ellos:

![importar](/img/docs/estudiantes_importar_3.png)

<div class="note warning">
  <h5>Errores al importar estudiante</h5>
  <p>Para que esta funcionalidad funcione correctamente, la estructura académica debe ser igual en ambos sistemas, en particular:</p>
  <ul>
    <li>No debe haber un estudiante con el mismo código en el sistema.</li>
    <li>La información a importar es únicamente la del último periodo lectivo ingresado en el sistema administrativo. Por consiguiente, si en el sistema 
      administrativo ya están ingresadas las listas del próximo ciclo, no será posible importar la información de nuevos estudiantes del ciclo actual, incluso
      cuando este no haya terminado.</li>
    <li>El <i>ciclo</i> del sistema administrativo debe coincidir con el <i>nombre corto</i> del periodo lectivo actual, y este debe estar abierto.</li>
    <li>El <i>nivel</i> del sistema administrativo debe coincidir con el <i>nombre corto</i> del nivel en el sistema.</li>
    <li>El <i>grado</i> del sistema administrativo debe estar ingresado como una <i>clase</i> en el sistema para el nivel especificado.</li>
    <li>La <i>sección</i> del sistema administrativo debe estar ingresada en el sistema para la clase especificada.</li>
  </ul>
</div>

<div class="note">
  <h5>Importar estudiantes masivamente</h5>
  <p>Se puede hacer uso de la opción <i>Importar</i> del <a href="/docs/periodos_lectivos/#importar">periodo lectivo</a>, lo cual, además de importar las 
    listas de estudiantes del sistema administrativo, procederá a crear nuevos usuarios con el código del estudiante como login y con el estudiante ya 
    asignado al usuario.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>ESTUDIANTE_CREATE</i>.</p>
</div>

## Importar fotos

Se puede utilizar esta opción para actualizar de forma masiva las fotos de los estudiantes del sistema:

![importar_fotos](/img/docs/estudiantes_importar_fotos.png)

La importación se puede llevar a cabo de 2 maneras diferentes:

- Se puede subir un archivo comprimido al servidor, el cual deberá especificarse en el campo *Archivo a cargar*. Si se pretende utilizar esta opción, se
  recomienda que las fotos se suban ya comprimidas, para que de esta forma el archivo a cargar no sea demasiado grande. Una vez se suba el archivo,
  el sistema lo descomprimirá en una carpeta temporal.
- Alternativamente se pueden cargar las imágenes directamente en el servidor, para lo cual deberá ingresarse la dirección local de la carpeta o archivo 
  comprimido en el campo *Ruta archivo o directorio*. Si la ruta corresponde a un archivo comprimido, se procederá a descomprimirlo en una carpeta temporal.

En cualquiera de los dos casos, el sistema procesará las fotos en en una tarea de fondo del servidor, el cual una vez finalizado enviará una notificación
al usuario actual con un log del procesamiento, en el que se listarán todos los archivos procesados y cualquier error que se encontrase.

El sistema procesará todas las fotos que se encuentren en el directorio, no importa en qué subcarpeta estén. De esta forma, el usuario puede organizar
las fotos en cualquier estructura de directorio que le resulte más conveniente. El único requerimiento es que las fotos deben tener como nombre de archivo
el código del estudiante para que el sistema pueda identificar al estudiante en cuestión. De esta forma, el archivo *1234.jpg*, por ejemplo, se utilizará
para actualizar la foto del estudiante con el código *1234*, siempre que este existiese.

Las fotos subidas se guardarán con un tamaño de 768 pixeles de ancho por 1024 pixeles de alto. No importa que se ingresen fotos con mayores dimensiones,
siempre que se respete la proporción de 3 de ancho por 4 de alto. En caso contrario, la foto será recortada en la dirección de la dimensión en exceso.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>ESTUDIANTE_MANAGE</i>.</p>
</div>

## Expediente del estudiante

![detalles](/img/docs/estudiantes_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(1)** privado a este estudiante.
- Opción para *Editar* los detalles del estudiante **(2)**, si se cuenta con el permiso *ESTUDIANTE_UPDATE* y el periodo lectivo está abierto, 
  lo cual desplegará el formulario de actualización de estudiante con la mayoría de los campos del [formulario de creación](#crear_estudiante).
- Opción para *Eliminar* el estudiante **(3)**, si se cuenta con el permiso *ESTUDIANTE_MANAGE*, el periodo lectivo esté abierto y el estudiante
  no tenga calificaciones ingresadas.

Por su parte, los detalles del expediente del estudiante se visualizan en las siguientes pestañas:

### General

Información general del estudiante, la cual se mantiene estática o cambia muy esporádicamente. Contiene mayormente información básica y de contacto
del estudiante (código, nombres y apellidos, dirección, fecha y lugar de nacimiento, etc.).

En la parte inferior se puede acceder a un registro de cambios **(4)** en el que se puede visualizar las modificaciones que ha sufrido la 
información a lo largo del tiempo:

![historial](/img/docs/estudiante_historial.png)

Para las acciones de modificación se puede visualizar los detalles del expediente del estudiante antes de efectuarse la modificación:

![historial](/img/docs/estudiante_show_version.png)

- La opción *Restaurar* **(1)** se puede utilizar para revertir la información del estudiante, lo cual puede ser útil para revertir errores
  al modificar el expediente. Para esto se necesita el permiso *ESTUDIANTE_UPDATE*.
- La opción *Eliminar* **(2)** puede ser útil si se quiere limpiar el historial del estudiante si acaso se incurrió en algún error durante su
  modificación. Para esto se necesita el permiso *ESTUDIANTE_MANAGE*.

### Académico

Información académica del estudiante, la cual es diferente para cada periodo lectivo (periodo lectivo, nivel, grado, sección, docente guía, etc.).

![academico](/img/docs/estudiantes_show_academico.png)

- Se puede [visualizar la clase](/docs/clases/#detalles_de_la_clase) **(1)** del estudiante si se cuenta con el permiso *CLASE_READ*.
- Se puede [visualizar la sección](/docs/secciones/#detalles_de_la_seccion) **(2)** del estudiante si se cuenta con el permiso *SECCION_READ*. Adicionalmente, 
  si se cuenta con el permiso *ESTUDIANTE_CLASE_MANAGE*, se puede acceder a la opción para transferir al estudiante a una sección diferente.
- Se puede [visualizar el docente guía](/docs/docentes/#expediente_del_docente) **(3)** del estudiante si se cuenta con el permiso *DOCENTE_READ*.
  Adicionalmente, se cuenta con la opción para [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje).

Cabe mencionar que las pestañas de *Materias*, *Horarios*, *Médico* e *Incidencias* dependen de la información académica que se tenga seleccionada. Por esta razón,
en la parte inferior de esta pestaña se muestran enlaces **(4)** para visualizar el expediente y calificaciones del estudiante en dicho periodo lectivo.

<div class="note warning">
  <h5>Transferencia de estudiante</h5>
  <p>Al transferir al estudiante a mitad del periodo lectivo se debe ser cuidadoso con las calificaciones existentes, puesto que estas no serán eliminadas, 
    y puede con facilidad dar lugar al ingreso de calificaciones duplicadas para el estudiante, excediendo el porcentaje de acumulado definido para la materia.
    Queda a criterio del docente efectuar los ajustes necesarios en estos casos.</p>
</div>

### Materias

En esta pestaña se muestra un listado de las materias que cursa el estudiante para el periodo lectivo seleccionado en la pestaña *Académico*.

![academico](/img/docs/estudiantes_show_materias.png)

- Se puede [visualizar la materia](/docs/materias/#detalles_de_la_materia) **(1)** si se cuenta con el permiso *MATERIA_READ*.
- Se puede [visualizar el docente](/docs/docentes/#expediente_del_docente) **(2)** que imparte la materia si se cuenta con el permiso *DOCENTE_READ*. Adicionalmente,
  se cuenta con la opción para [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje).
- Se pueden visualizar todas evaluaciones, exámenes y consolidados de la materia, con sus respectivas descripciones y observaciones, al darle clic a la opción
  *Detalle* **(3)**:

![calificacion](/img/docs/estudiante_calificacion.png)

Alternativamente, se pueden visualizar las calificaciones del estudiante en su totalidad al acceder al enlace *Calificaciones* en la pestaña de *Materias* **(4)**, 
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

Alternativamente, se puede exportar la información de este reporte como una hoja de cálculo de Excel de dos formas diferentes:

- Si únicamente interesan los bloques consolidados, se puede utilizar la opción *Exportar todo* **(1)**, lo cual exporta las notas bimestrales, semestrales y finales
  y los despliega como un boletín de calificaciones
- Si se quiere visualizar el detalle de las evaluaciones, la opción **Exportar BLOQUE** **(2)** resulta más adecuada, puesto que exporta todas las calificaciones
  del bloque evaluativo que se seleccione, incluyendo los detalles de las evaluaciones y comentarios del docente

### Horario

Muestra el horario de clases del estudiante, si acaso estuviese disponible.

![horario](/img/docs/estudiantes_show_horario.png)

### Médico

Muestra el expediente médico del estudiante, con su información general (altura, peso, tipo de sangre, alergias, etc.), así como también una bitácora médica con
sucesos médicos propios del estudiante.

![medico](/img/docs/estudiantes_show_medico.png)

Si se cuenta con el permiso *ESTUDIANTE_MEDICO* y el periodo lectivo está abierto, se podrá tanto *Editar* **(1)** los datos básicos del expediente, como
*Agregar* **(2)** nuevos sucesos a la bitácora médica del estudiante, lo cual nos desplegará el siguiente formulario:

![medico](/img/docs/estudiantes_show_medico_create.png)

Una vez ingresado el suceso, se podrá [visualizar los detalles del suceso](/docs/registro_medicos/#detalles_del_suceso) **(3)**.

### Padres y Responsables

Muestra los nombres e información de contacto del padre, madre y responsable(s) del estudiante.

![responsables](/img/docs/estudiantes_show_responsables.png)

Si existen responsables asignados al estudiante, se presentan las siguientes opciones:

- Opción para *Eliminar* **(1)** la información del responsable, si se cuenta con el permiso *PARIENTE_MANAGE*. Si el responsable únicamente está asociado a este estudiante,
  entonces se eliminará; caso contrario, solamente se eliminará la asociación.
- Opción para *Editar* **(2)** la información del responsable, si se cuenta con el permiso *PARIENTE_UPDATE*.
- Opción para *Mostrar* **(3)** la [información del responsable](/docs/parientes/#detalles_del_pariente), si se cuenta con el permiso *PARIENTE_READ*.
- Al igual que el expediente de los estudiantes, se puede acceder a un registro de cambios **(4)** en el que se puede visualizar las modificaciones que ha sufrido la 
  información a lo largo del tiempo

Si el estudiante no tiene un padre o madre asignado, en su lugar aparecerá la opción para *Agregar* el responsable en cuestión, lo cual desplegará el 
[formulario de creación de pariente](/docs/parientes/#crear_pariente).

### Incidencias

Muestra los sucesos en los que se encuentra involucrado el estudiante, que pueden afectar ya sea a toda la clase, sección o al estudiante en particular.

![incidencias](/img/docs/estudiantes_show_incidencias.png)

Si se cuenta con el permiso *ESTUDIANTE_UPDATE* y el periodo lectivo está abierto, se contará con la opción *Nueva* para ingresar una incidencia, lo que desplegará
el siguiente formulario:

![incidencias](/img/docs/estudiantes_show_incidencias_new.png)

Una vez ingresada la incidencia, se podrá [visualizar los detalles del suceso](/docs/incidencias/#detalles_de_la_incidencia).

### Usuarios

Únicamente está disponible si se cuenta con el permiso *USUARIO_READ*. [Las funcionalidades de esta pestaña se describen en la sección de seguridad](/docs/seguridad/#objetos).
