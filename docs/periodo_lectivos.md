---
layout: docs
title: Períodos Lectivos
permalink: /docs/periodo_lectivos/
---

Al ingresar en la opción *Períodos Lectivos* en el menú se desplegará un listado con todos los ciclos evaluativos ingresados en el sistema:

![listado](/img/docs/periodo_lectivos_index.png)

<div class="note info">
  <h5>Seguridad</h5>
  <p>Se necesita el permiso <i>PERIODO_LECTIVO_MANAGE</i> en el perfil del usuario para acceder a todas las opciones de los periodos lectivos.</p>
</div>

## Crear Periodo Lectivo

Al seleccionar la opción *Nuevo periodo* se despliega el siguiente formulario:

![listado](/img/docs/periodo_lectivos_new.png)

- Se debe ingresar un *Nombre* para el periodo lectivo.
- Se debe ingresar un *Nombre corto* para el periodo lectivo, el cual, para que la [importación de estudiante](/docs/estudiantes/#importar_estudiante)
  funcione correctamente, debe contener el *año* correspondiente al cliclo evaluativo (2013, 2014 por ejemplo).
- Se debe ingresar una fecha de *Inicio* y *Fin*, el cual no podrá traslaparse con otros periodos lectivos.
- Se debe especificar si el periodo lectivo está *Abierto* checkeando el campo homónimo. Si el periodo lectivo no está abierto (es decir, está
  cerrado), entonces no se pueden efectuar ninguna modificación sobre la información académica de dicho periodo, lo cual incluye: 
  [expedientes de estudiantes](/docs/estudiantes/), [clases](/docs/clases/), [secciones](/docs/secciones/), [materias](/docs/materias/),
  [evaluaciones](/docs/evaluaciones/), [tipos de notas](/docs/tipo_notas/), incidencias y bitácora médica.

En la parte inferior del formulario se muestran las opciones de configuración del periodo lectivo:

![listado](/img/docs/periodo_lectivos_new_2.png)

Estas configuraciones representan la configuración por defecto de las materias que se introduzcan al periodo lectivo. Adicionalmente, si se quiere
que un determinado nivel tenga una configuración diferente, se puede seleccionar la opción de *Conf. independiente* para ello.

Las configuraciones *Nota mínima* y *Escala literal* son las únicas configuraciones del periodo lectivo que se utilizan directamente para
mostrar los promedios globales de los estudiantes, puestos que estos no están limitados a una materia en particular.

<div class="note">
  <h5>Finalización del periodo lectivo</h5>
  <p>En lugar de crear el periodo lectivo desde cero, se recomienda el siguiente procedimiento para aperturar un nuevo periodo lectivo:</p>
  <ul>
    <li><a href="#copiar">Copiar</a> el periodo lectivo actual, lo cual duplicará toda la estructura del ciclo (clases, secciones y materias).</li>
    <li><a href="#crear_periodo_lectivo">Cerrar</a> el periodo lectivo actual para prevenir cualquier modificación.</li>
    <li>Asegurarse que las listas finales ya estén cargadas en el sistema administrativo.</li>
    <li>Efectuar cualquier modificación en la estructura del nuevo periodo lectivo, de tal forma que sea congruente con la información del sistema 
      administrativo. Esto incluye verificar el ciclo, letras de los niveles, grados y secciones. De ser posible 
      <a href="/docs/estudiantes/#importar_estudiante">importar un nuevo estudiante cualquiera</a> para validar el enlace con el sistema administrativo.</li>
    <li><a href="#importar">Importar</a> el periodo lectivo para cargar las listas y crear los nuevos usuarios en el sistema.</li>
  </ul>
</div>

## Detalles del Periodo Lectivo

Se muestran los detalles del periodo lectivo en dos pestañas: una para la información *General* y en la que listan las *Configuraciones*:

![detalles](/img/docs/periodo_lectivos_show.png)

- Se puede *Editar* **(1)** el periodo lectivo, lo cual nos despliega el formulario de modificación con los mismos campos que el 
  [formulario de creación](#crear_periodo_lectivo).
- Se puede *Eliminar* **(2)** el periodo lectivo siempre y cuando no tenga estudiantes asignados.
- Se puede *Copiar* **(3)** [la estructura el periodo lectivo](#copiar) si el periodo en cuestión corresponde al ciclo actual.
- Se puede *Importar* **(4)** [las listas de estudiantes del sistema administrativo](#importar).
- Se puede *Exportar* **(5)** toda la información de los expedientes de los estudiantes en un archivo comprimido. El archivo comprimido contiene las fotos de los 
  estudiantes y una hoja de cálculo de Excel con la información general de sus expedientes. Este procesamiento se lleva a cabo en una tarea de fondo del
  servidor, la cual una vez finalizada enviará una notificación al usuario con las indicaciones para descargar el archivo y un log del procesamiento.

### Copiar

Al seleccionar la opción *Copiar* se creará un nuevo periodo lectivo para el siguiente año con toda la estructura académica duplicada. Esto incluye:

- [Tipos de nota](/docs/tipo_notas/).
- [Clases](/docs/clases/).
- [Secciones](/docs/secciones/), con sus respectivas asignaciones de docente guía.
- [Materias](/docs/materias/), con sus respectivos docentes asignados.

### Importar

Al seleccionar la opción *Importar* se iniciará una tarea de fondo en el servidor la cual procederá a importar las listas de todos los estudiantes
registrados en el sistema administrativo.

Los estudiantes de nuevo ingreso serán [importados](/docs/estudiantes/#importar_estudiante) al sistema (por lo tanto hay que tener en cuenta las mismas 
consideraciones para que se lleve acabo correctamente). Adicionalmente, si se tiene [configurado un perfil por defecto para los usuarios de estudiantes](/docs/configuracion/), 
se crearán masivamente sus usuarios correspondientes, utilizando el código del estudiante como login para el usuario.

Una vez finalizada la tarea de fondo, se enviará una notificación al usuario con las contraseñas generadas para los nuevos usuarios, así como también
se incluirá un log con los resultados del procesamiento.
