---
layout: docs
title: Materias
permalink: /docs/materias/
---

Al ingresar en la opción *Materias* en el menú se desplegará un listado de las materias del sistema con la opción para ingresar a
los [detalles de la materia](#detalles_de_la_materia):

![listado](/img/docs/materias_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto, se muestran las materias del periodo lectivo actual. Si se quiere visualizar información histórica, se debe *Mostrar filtros* **(2)**
  y seleccionar un periodo lectivo diferente.
- Se puede *Mostrar filtros* **(2)** y limitar las materias mostradas por nivel, clase y asignatura.
- Si se cuenta con el permiso *MATERIA_MANAGE*, se desbloquea la opción *Nueva Materia* **(1)** para [ingresar una materia](#crear_materia) en el sistema.

<div class="note">
  <h5>Materia vs Asignatura</h5>
  <p>Aunque en el idioma español los términos pueden utilizarse como sinónimos, el sistema hace distinción entre ellos. Por un lado, la <i>asignatura</i>
    es una entidad que depende únicamente del nivel (por ejemplo <i>MATEMÁTICAS del nivel PRIMARIA</i>), mientras que la <i>materia</i> es la forma 
    concreta de la asignatura aplicada a una clase en un periodo lectivo determinado (por ejemplo, <i>MATEMÁTICAS del CUARTO GRADO de PRIMARIA del PERIODO 2014</i>).
    En consecuencia, las asignaturas deben ingresarse una única vez, mientras que las materias deben definirse nuevamente para cada periodo lectivo.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita:</p>
  <ul>
    <li>Permiso <i>MATERIA_READ</i> para visualizar todas las clases del sistema.</li>
    <li>Objeto tipo <i>Docente</i>, en cuyo se listarán las materias que el usuario imparta con el mismo acceso que el permiso <i>MATERIA_EVALUAR</i>,
      y las materias de las secciones de las cuales el docente es guía en modo de visualización.</li>
    <li>Objeto tipo <i>Nivel</i> o <i>Clase</i> con el rol <i>MATERIA_READ</i> para visualizar las secciones que pertenezcan a la clase o nivel correspondiente.</li>
  </ul>
</div>

## Crear Materia

Al dar clic en la opción de crear materia se despliega el siguiente formulario:

![nuevo](/img/docs/materias_new.png)

Solamente se pueden crear materias para los periodos lectivos abiertos. Adicionalmente, la combinación de *Clase* y *Asignatura* debe ser única 
para el periodo lectivo seleccionado.

Si un único docente imparte la asignatura para todas las secciones de la clase, entonces se puede seleccionar en el campo *Docente*. En caso contrario, se pueden
[asignar docentes diferentes](#asignar_docentes) para cada sección luego de ingresar la materia. El docente que se seleccione debe 
[impartir la asignatura](/docs/docentes/#crear_docente).

<div class="note">
  <h5>Creación masiva de materias</h5>
  <p>Si la estructura académica suele cambiar poco entre un periodo lectivo y el siguiente, como es el caso casi siempre, se puede hacer uso de 
    la funcionalidad de <a href="/docs/periodo_lectivos/#copiar">copiar periodo lectivo</a> para duplicar esta estructura al periodo lectivo siguiente y 
    evitarse el trabajo de introducir manualmente las materias.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>MATERIA_MANAGE</i>.</p>
</div>

### Configuraciones de la Materia

Existen diversas opciones de configuración para modificar el comportamiento de las materias:

- **Nota mínima**: Nota mínima considerada como *aprobada* para la materia.
  - Si la calificación de una evaluación es inferior a este valor, entonces se resaltará en color rojo en todos los reportes del sistema.
  - Si el valor de la evaluación es menor al 100 %, entonces este valor es ponderado (por ejemplo, si la evaluación vale 10 puntos y el 
    valor de la nota mínima es 60, entonces cualquier valor menor a 10).
- **Tipo materia**: Controla los [tipos de evaluaciones que se pueden crear](/docs/evaluaciones/#crear_evaluacin) para esta materia:
  - *Solo acumulado*: Únicamente se pueden crear evaluaciones acumulativas.
  - *Acumulado y examen*: Se pueden crear tanto evaluaciones acumulativas como un examen.
  - *Solo examen*: Únicamente se puede crear una evaluación de tipo examen por bloque.
- **Porcentaje examen**: Únicamente se toma en consideración si el tipo de materia es *Acumulado y examen*, y corresponde al porcentaje que
  tendrá el examen sobre la calificación del bloque.
  - Si el valor es mayor a 0, entonces la materia *debe* contener una evaluación tipo examen (el cual tendrá este porcentaje independientemente del valor
    que se introduzca al momento de crear la evaluación) para que la calificación del bloque pueda consolidarse.
    Adicionalmente, se restringirán las evaluaciones acumulativas para que no sobrepasen el porcentaje restante. En consecuencia, un valor de 100 en este
    campo es funcionalmente equivalente a una materia de tipo *Solo examen*.
  - Si el valor es 0, entonces el docente podrá calificar la materia de la forma que estime conveniente: podrá crear únicamente evaluaciones acumulativas, 
    crear un examen y asignarle el porcentaje que desee y el resto de acumulado, o incluso ingresar un único examen con un peso del 100 % de la nota
    del bloque si así lo desea.
- **Exámenes reparación**: Número máximo de exámenes de reparación permitidos para los estudiantes reprobados. Un número de 0 deshabilita
  los exámenes de reparación para la materia.
- **Escala literal**: Utilizar una [escala literal](/docs/escalas/) para la materia, de tal forma que las calificaciones se visualizarán
  como letras en todos los reportes del sistema para esta materia, así como también las [evaluaciones deberán ser calificadas](/docs/evaluaciones/#calificar_evaluacin)
  con sus correspondientes valores literales.
- **Excluir promedio**: Si se activa el check en este campo, la materia se excluirá del cálculo del promedio del estudiante. Se recomienda que
  se active esta opción si se selecciona una *escala literal* para la materia, a menos que todas las materias de la clase se califiquen de forma literal.
- **Excluir reprobadas**: Si se activa el check en este campo, la materia no se tomará en cuenta para el cálculo de asignaturas reprobadas en el
  [reporte de estadísticas de bloque](/docs/reportes/#estadsticas_de_bloque).
- **Periodo inicio** y **Periodo fin**: Para las materias cuya duración no abarca la totalidad del periodo lectivo, debe indicarse el bloque inicial
  y el bloque final que se evalúan, de tal forma que al consolidar el bloque final se calculará la nota final de la materia. De esta forma, para las
  materias semestrales debe introducirse una duración del periodo 1 al 2 para el primer semestre, y del 3 al 4 para el segundo semestre.

<div class="note info">
  <h5>Configuración heredada del periodo lectivo</h5>
  <p>Los valores iniciales de varias de las configuraciones se copian directamente del <a href="/docs/periodo_lectivos#crear_periodo_lectivo">periodo lectivo</a>
    seleccionado, y en caso de no modificarse, quedarán enlazadas, de tal forma que cualquier modificación en las configuraciones del periodo lectivo
    se replicará en la materia.</p>
</div>

<div class="note warning">
  <h5>Configurar materia con calificaciones ingresadas</h5>
  <p>Puesto que todas estas configuraciones modifican el comportamiento de la materia al momento de introducir evaluaciones y calificaciones,
    se recomienda que no se cambie la configuración para materias con calificaciones ingresadas <b>a menos que se esté seguro de lo que se está
    haciendo</b>. Efectuar modificaciones de forma descuidada puede introducir inconsistencias en las calificaciones ya ingresadas en el sistema.</p>
</div>

## Detalles de la Materia

![detalles](/img/docs/materias_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para filtrar las pestañas de [estudiantes](#estudiantes) y [evaluaciones](#evaluaciones) por sección **(1)**. Esta opción se oculta si
  el docente no imparte la materia para más de una sección en el grado especificado.
- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(2)** a toda la clase o sección. En el destinatario se podrá seleccionar si se quiere
  enviar a los estudiantes y padres de familia, a los docentes o a ambos.
- Opción para *Editar* los detalles de la materia **(3)**, si se cuenta con el permiso *MATERIA_MANAGE* y el periodo lectivo está abierto, 
  lo cual desplegará el formulario de actualización de la materia con los mismos campos del [formulario de creación](#crear_materia).
- Opción para *Eliminar* la materia **(4)**, si se cuenta con el permiso *MATERIA_MANAGE*, el periodo lectivo está abierto y la materia no tiene
  ninguna calificación introducida.

Por su parte, los detalles de la materia se visualizan en las siguientes pestañas:

### General

Información general de la sección (periodo lectivo, nivel, grado, docente guía e información básica de auditoría).

- Se puede [visualizar la clase](/docs/clases/#detalles_de_la_clase) **(5)** si se cuenta con el permiso *CLASE_READ*.
- Se puede [visualizar el docente](/docs/docentes/#expediente_del_docente) que imparte la clase **(6)** si se cuenta con el permiso *DOCENTE_READ*. Adicionalmente,
  se cuenta con la opción para [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje).
- Si docentes diferentes imparten la asignatura en las diferentes secciones, entonces luego de los datos generales aparece una sección de *Docentes* en la 
  que se listan los docentes por cada sección.
- Se puede [modificar la asignación de docentes](#asignar_docentes) **(7)** si se cuenta con el permiso *MATERIA_MANAGE*.

#### Asignar Docentes

Se puede modificar la asignación de docentes a la materia con el siguiente formulario:

![docentes](/img/docs/materias_show_docentes.png)

- Para poder seleccionar un docente, este debe impartir la asignatura de la materia.
- Se puede dejar sin seleccionar el docente, en cuyo caso se interpretará como que el docente guía de la sección es el que imparte la materia en
  su sección.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>MATERIA_MANAGE</i>.</p>
</div>

### Configuraciones

En esta pestaña se muestran todas las [configuraciones de la materia](#configuraciones_de_la_materia).

![configuraciones](/img/docs/materias_show_configuraciones.png)

### Estudiantes

Esta pestaña muestra un listado de todos los estudiantes que reciben la materia en las secciones a las cuales el usuario tiene acceso.

![estudiantes](/img/docs/materias_show_estudiantes.png)

- Se puede [visualizar un reporte de calificaciones](#calificaciones) **(1)** de la materia para todos los estudiantes.
- Se puede [visualizar el expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante) **(2)** si se cuenta con el permiso *ESTUDIANTE_READ*.
- Para cada estudiante se cuenta con la opción de [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje) **(3)**.
- Se puede [visualizar el detalle de calificaciones específico para el estudiante](#detalle_de_calificaciones) **(4)**.

#### Calificaciones

Con esta opción se pueden visualizar las calificaciones de la materia en su totalidad, organizada en los diferentes bloques evaluativos o 
bimestres que conforman el periodo lectivo.

![calificaciones](/img/docs/materias_show_estudiantes_calificaciones.png)

- Se puede *Exportar* **(2)** el reporte como una hoja de cálculo de Excel con la misma estructura. También se incluyen las evaluaciones 
  acumulativas, pero al igual que en el formato web, las columnas se encuentran ocultas en la hoja de cálculo.
- Las calificaciones de los estudiantes retirados son desplegadas si se encuentran disponibles, pero son ignoradas en el cálculo del promedio
  global de la clase/sección.

<div class="note">
  <h5>Opciones de visualización de la hoja de calificaciones</h5>
  <ul>
    <li>Al igual que en los <a href="#detalles_de_la_materia">detalles de la materia</a>, se pueden filtrar los estudiantes por sección <b>(1)</b>.</li>
    <li>Las evaluaciones se encuentran ocultas por defecto y solo se muestra la columna del <i>Total Acumulado</i>. Para desplegarlas, dar clic en la cabecera del
      bloque evaluativo <b>(3)</b>.</li>
    <li>Puesto que el área de la pantalla se encuentra reducida por el menú y estilo del sistema, se recomienda maximizar el área de contenido dando clic en el 
      ícono <i>Cambiar modo de pantalla</i> localizado en la esquina superior izquierda de la pantalla. Adicionalmente, el reporte cuenta con una barra de desplazamiento
      horizontal en la parte inferior de la pantalla para facilitar su visualización.</li>
    <li>Al situar el cursor encima de cualquier evaluación o examen se visualizará una burbuja mostrando el porcentaje de la evaluación en el total de la calificación.
      Si la calificación se encuentra subrayada, se le mostrarán adicionalmente los comentarios del docente.</li>
  </ul>
</div>

#### Detalle de Calificaciones

En esta pantalla se despliegan todas las evaluaciones, exámenes y consolidados de la materia, con sus respectivas descripciones, así como también cualquier observación
del docente sobre la calificación en cuestión.

![calificacion](/img/docs/materias_show_estudiantes_calificacion.png)

- Se puede [visualizar la clase](/docs/clases/#detalles_de_la_clase) **(1)** si se cuenta con el permiso *CLASE_READ*.
- Se puede [visualizar el expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante) **(2)** si se cuenta con el permiso *ESTUDIANTE_READ*.
- Se puede [visualizar la materia](#detalles_de_la_materia) **(3)**.
- Se puede visualizar la descripción de la evaluación **(4)** o las observaciones de las calificaciones. Se puede identificar la presencia de comentarios
  cuando el campo está subrayado, y se desplegará al momento de situar el cursor sobre el campo en cuestión.

### Evaluaciones

Esta pestaña muestra un listado de todas las evaluaciones ingresadas para la materia para las secciones a las cuales el usuario tiene acceso.

![evaluaciones](/img/docs/materias_show_evaluaciones.png)

- Se puede *Agregar* **(1)** una nueva evaluación a la materia si el periodo lectivo está abierto y se cuenta con el permiso *MATERIA_EVALUAR*.
- Se puede *Consolidar* o *Reaperturar* **(2)** si el periodo lectivo está abierto, [la materia está lista para la operación](#consolidar_y_reaperturar_materia),
  **se tiene seleccionada una sección en el filtro de secciones** y se cuenta con el permiso *MATERIA_EVALUAR*.
- Se puede visualizar la descripción de las evaluaciones **(3)** si existiese.
- Se puede [visualizar la evaluación](/docs/evaluaciones/#detalles_de_la_evaluacin) **(4)** si se cuenta con el permiso *EVALUACION_READ*.
- Se puede [calificar la evaluación](/docs/evaluaciones/#calificar_evaluacin) **(5)** si se cuenta con el permiso *MATERIA_EVALUAR*.

La creación y calificación de evaluaciones se verán con más detalle en la sección de [evaluaciones](/docs/evaluaciones/).

#### Consolidar y Reaperturar Materia

Una vez que se ha completado la nota del bloque para una materia determinada no se podrá [crear nuevas evaluaciones](/docs/evaluaciones/#crear_evaluacin). Para
esto, primeramente se deberá *Consolidar* el bloque en cuestión, lo cual tiene las siguientes consecuencias:

- Se aumenta el periodo actual de la materia, lo cual permitirá [ingresar evaluaciones](/docs/evaluaciones/#crear_evaluacin) para el nuevo bloque.
- Las evaluaciones del bloque consolidado ya no pueden modificarse o eliminarse (aunque sí podrán [calificarse](/docs/evaluaciones/#calificar_evaluacin)).
- Se crearán calificaciones consolidadas para el bloque en cuestión, de acuerdo a la configuración establecida en los [tipos de nota](/docs/tipo_notas/) 
  (por ejemplo, notas bimestrales, semestrales y finales). Dichos consolidados se mostrarán en la mayoría de reportes de calificaciones del sistema.

Por otro lado, la operación de *Reaperturar* hace exactamente lo contrario, lo cual permite modificar las evaluaciones del bloque reaperturado. Cabe mencionar 
que para poder reaperturar un bloque este no debe tener ninguna evaluación ingresada para dicho bloque.

<div class="note">
  <h5>Seleccionar filtro de sección</h5>
  <p>Estas operaciones se deben aplicar por sección, de tal forma que cuando se cargue la materia, al no estar seleccionada una sección específica, la opción 
    de consolidar/reaperturar no estará visible aún cuando todas las secciones estén listas para la operación, lo cual puede ocasionar cierta confusión.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>MATERIA_EVALUAR</i>.</p>
</div>

### Incidencias

Se muestran los sucesos que involucran a los estudiantes de esta clase. El funcionamiento de esta pestaña es análogo al de su 
[homónimo en el expediente del estudiante](/docs/estudiantes/#incidencias). Para crear incidencias se requiere el permiso *MATERIA_MANAGE* o un
objeto tipo *Docente* que imparta la materia en cuestión.
