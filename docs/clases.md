---
layout: docs
title: Clases
permalink: /docs/clases/
---

Al ingresar en la opción *Clases* en el menú se desplegará un listado de las clases del sistema con la opción para ingresar a
los [detalles de la clase](#detalles_de_la_clase):

![listado](/img/docs/clases_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto, se muestran las clases del periodo lectivo actual. Si se quiere visualizar información histórica, se debe *Mostrar filtros* **(2)**
  y seleccionar un periodo lectivo diferente.
- Se puede *Mostrar filtros* **(2)** y limitar las clases mostradas por nivel.
- Si se cuenta con el permiso *CLASE_MANAGE*, se desbloquea la opción *Nueva Clase* **(1)** para [ingresar una clase](#crear_clase) en el sistema.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita:</p>
  <ul>
    <li>Permiso <i>CLASE_READ</i> para visualizar todas las clases del sistema.</li>
    <li>Objeto tipo <i>Nivel</i> o <i>Clase</i> con el rol <i>CLASE_READ</i> para limitar el listado por clase o nivel asignado.</li>
  </ul>
</div>

## Crear Clase

Al dar clic en la opción de crear clase se despliega el siguiente formulario:

![nuevo](/img/docs/clases_new.png)

Solamente se pueden crear clases para los periodos lectivos abiertos. Adicionalmente, la combinación de *Nivel* y *Grado* debe ser única 
para el periodo lectivo seleccionado.

<div class="note">
  <h5>Creación masiva de clases</h5>
  <p>Si la estructura académica suele cambiar poco entre un periodo lectivo y el siguiente, como es el caso casi siempre, se puede hacer uso de 
    la funcionalidad de <a href="/docs/periodo_lectivos/#copiar">copiar periodo lectivo</a> para duplicar esta estructura al periodo lectivo siguiente y 
    evitarse el trabajo de introducir manualmente las clases.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>CLASE_MANAGE</i>.</p>
</div>

## Detalles de la Clase

![detalles](/img/docs/clases_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(1)** a toda la clase. En el destinatario se podrá seleccionar si se quiere
  enviar a los estudiantes y padres de familia, a los docentes o a ambos.
- Opción para *Editar* los detalles de la case **(2)**, si se cuenta con el permiso *CLASE_MANAGE* y el periodo lectivo está abierto, 
  lo cual desplegará el formulario de actualización de la clase con los mismos campos del [formulario de creación](#crear_clase).
- Opción para *Eliminar* la clase **(3)**, si se cuenta con el permiso *CLASE_MANAGE*, el periodo lectivo está abierto y la clase no tiene
  ningún estudiante asignado.

Por su parte, los detalles de la clase se visualizan en las siguientes pestañas:

### General

Información general de la clase (periodo lectivo, clase, grado e información básica de auditoría).

### Materias

Esta pestaña muestra un listado de las materias que se cursan en la clase.

![materias](/img/docs/clases_show_materias.png)

- Se puede [crear una materia](/docs/materias/#crear_materia) **(1)** si se cuenta con el permiso *MATERIA_CREATE*.
- Se puede [visualizar el docente](/docs/docentes/#expediente_del_docente) **(2)** que imparte la materia si se cuenta con el permiso *DOCENTE_READ*. Adicionalmente,
  se cuenta con la opción para [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje).
- Se puede [visualizar la materia](/docs/materias/#detalles_de_la_materia) **(3)** si se cuenta con el permiso *MATERIA_READ*.

### Secciones

Esta pestaña muestra un listado de las secciones en las que se divide la clase.

![secciones](/img/docs/clases_show_secciones.png)

- Se puede [crear una sección](/docs/secciones/#crear_seccin) **(1)** si se cuenta con el permiso *SECCION_CREATE*.
- Se puede [visualizar el docente guía](/docs/docentes/#expediente_del_docente) **(2)** de la sección si se cuenta con el permiso *DOCENTE_READ*. Adicionalmente,
  se cuenta con la opción para [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje).
- Se puede [visualizar la sección](/docs/secciones/#detalles_de_la_seccin) **(3)** si se cuenta con el permiso *SECCION_READ*.

### Estudiantes

Esta pestaña muestra un listado de todos los estudiantes asignados a la clase.

![estudiantes](/img/docs/clases_show_estudiantes.png)

- Se puede [administrar la asignación de estudiantes a la clase](#asignar_estudiantes) **(1)** si se cuenta con el permiso *ESTUDIANTE_CLASE_MANAGE*.
- Se puede [visualizar un reporte de calificaciones](#calificaciones) **(2)** consolidado para todos los estudiantes de la clase.
- Para cada estudiante se cuenta con la opción de [enviarle un mensaje privado](/docs/mensajes/#crear_mensaje) **(3)**.
- Se puede [visualizar el expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante) **(4)** si se cuenta con el permiso *ESTUDIANTE_READ*.

#### Asignar Estudiantes

Esta opción contiene el siguiente formulario para asignar estudiantes ya existentes de años anteriores a la clase actual:

![estudiantes](/img/docs/clases_show_estudiantes_manage.png)

Para añadir estudiantes se debe ingresar un criterio de búsqueda en el campo *Buscar estudiante* **(1)**. Esto mostrará las posibles *coincidencias* **(3)**
de estudiantes no asignados, las cuales al darles clic se agregarán a la clase actual. Alternativamente, si se conoce el código del estudiante, se puede
introducir directamente en el campo *Código estudiante* **(2)** y enviar el formulario, con el mismo resultado.

En la parte inferior del formulario se incluye el listado de los estudiantes asignados a la clase:

![estudiantes](/img/docs/clases_show_estudiantes_manage_2.png)

- Se puede [visualizar el expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante) **(1)** si se cuenta con el permiso *ESTUDIANTE_READ*.
- Si el estudiante no tiene calificaciones ingresadas, se puede *Eliminar* **(3)** el estudiante de la clase actual. Si el estudiante tiene información histórica, 
  entonces únicamente se eliminará la relación, en caso contrario (el estudiante no está asignado a ninguna otra clase), entonces el expediente del 
  del estudiante también será eliminado.
- Si el estudiante está activo, se puede *Retirar* **(2)** de la clase, para lo cual se deberá introducir la fecha en la que se retira el estudiante. Un estudiante
  retirado no será incluido en las nuevas evaluaciones que se introduzcan y será excluido de los reportes de calificaciones, pero conservará cualquier
  calificación ya introducida en modo de visualización.
- Si el estudiante ya se ha retirado, se puede *Reintegrar* **(4)** a la clase, activando nuevamente al estudiante en las evaluaciones y los reportes.

<div class="note">
  <h5>Importar estudiantes masivamente</h5>
  <p>Se puede hacer uso de la opción <i>Importar</i> del <a href="/docs/periodos_lectivos/#importar">periodo lectivo</a>, lo cual, además de importar las 
    listas de estudiantes del sistema administrativo, procederá a crear nuevos usuarios con el código del estudiante como login y con el estudiante ya 
    asignado al usuario.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>ESTUDIANTE_CLASE_MANAGE</i>.</p>
</div>

#### Calificaciones

Con esta opción se muestran las calificaciones consolidadas por bimestres, semestres y finales:

![calificaciones](/img/docs/clases_show_estudiantes_calificaciones.png)

- Por defecto se muestra el último consolidado que esté disponible para la clase. Se puede cambiar seleccionando un consolidado diferente en la lista desplegable **(1)**.
- Se puede *Exportar* **(2)** el reporte como una hoja de cálculo de Excel con la misma estructura.
- Las calificaciones de los estudiantes retirados **(3)** son desplegadas si se encuentran disponibles, pero son ignoradas en el cálculo de los promedios globales
  en la parte inferior del listado.

<div class="note">
  <h5>Maximizar pantalla</h5>
  <p>Puesto que el área de la pantalla se encuentra reducida por el menú y estilo del sistema, se recomienda maximizar el área de contenido dando clic en el 
    ícono <i>Cambiar modo de pantalla</i> localizado en la esquina superior izquierda de la pantalla.</p>
</div>

### Incidencias

Se muestran los sucesos que involucran a los estudiantes de esta clase. El funcionamiento de esta pestaña es análogo al de su 
[homónimo en el expediente del estudiante](/docs/estudiantes/#incidencias). Para crear incidencias se requiere el permiso *CLASE_MANAGE*.

### Usuarios

Únicamente está disponible si se cuenta con el permiso *USUARIO_READ*. [Las funcionalidades de esta pestaña se describen en la sección de seguridad](/docs/seguridad/#objetos).
