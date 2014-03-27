---
layout: docs
title: Seguridad
prev_section: usuarios
next_section: estudiantes
permalink: /docs/seguridad/
---

El tema de la seguridad en el sistema es relativamente complejo, puesto que existen muchas funcionalidades en el sistema, las cuales
son accedidas desde diversos tipos de usuarios, y cada uno de estos usuarios debería tener acceso únicamente a la información que
le compete. Por esta razón se concibió un sistema de seguridad basado en dos niveles:

## Perfiles de usuario

Al [crear un usuario](/docs/usuarios/#crear_usuario) se le debe asignar un único perfil. Este perfil puede contener un conjunto de permisos
que le dan acceso global a ciertas funciones del sistema. A continuación se da un listado de los permisos del sistema:

- *PERFIL_MANAGE*: Administrar perfiles de usuarios
- *USUARIO_READ*: Listar usuarios
- *USUARIO_CREATE*: Crear usuarios
- *USUARIO_MESSAGE*: Enviar mensajes a usuarios
- *USUARIO_MANAGE*: Administrar usuarios
- *NIVEL_READ*: Listar niveles
- *NIVEL_MESSAGE*: Envío de anuncions a niveles
- *NIVEL_MANAGE*: Administrar niveles
- *ASIGNATURA_MANAGE*: Administrar asignaturas
- *CATALOGO_MANAGE*: Administrar tablas estáticas
- *ESCALA_MANAGE*: Administrar escalas literales
- *CONFIGURACION_MANAGE*: Administrar configuraciones globales
- *PERIODO_LECTIVO_MESSAGE*: Envío de anuncios globales
- *PERIODO_LECTIVO_MANAGE*: Administrar períodos lectivos
- *TIPO_NOTA_MANAGE*: Administrar tipos de notas
- *RECORRIDO_MANAGE*: Administrar recorridos
- *DOCENTE_READ*: Listar docentes
- *DOCENTE_MESSAGE*: Enviar mensajes a docentes
- *DOCENTE_CREATE*: Crear docentes
- *DOCENTE_UPDATE*: Actualizar docentes
- *DOCENTE_MANAGE*: Administrar docentes
- *ESTUDIO_MANAGE*: Administración información académica de docentes
- *EXPERIENCIA_MANAGE*: Administración experiencia laboral de docentes
- *ESTUDIANTE_READ*: Listar estudiantes
- *ESTUDIANTE_MESSAGE*: Enviar mensajes a estudiantes
- *ESTUDIANTE_CREATE*: Crear estudiantes
- *ESTUDIANTE_UPDATE*: Actualizar estudiantes
- *ESTUDIANTE_MEDICAR*: Actualizar expediente médico de estudiantes
- *ESTUDIANTE_MANAGE*: Administrar estudianets
- *PARIENTE_READ*: Listar responsables
- *PARIENTE_MESSAGE*: Enviar mensajes a responsables
- *PARIENTE_CREATE*: Crear responsables
- *PARIENTE_UPDATE*: Actualizar responsables
- *PARIENTE_MANAGE*: Administrar responsables
- *CLASE_READ*: Listar clases
- *CLASE_MESSAGE*: Enviar mensajes a clases
- *CLASE_MANAGE*: Administrar clases
- *ESTUDIANTE_CLASE_MANAGE*: Administrar asignación de estudiantes y clases
- *SECCION_READ*: Listar secciones
- *SECCION_MESSAGE*: Enviar mensajes a secciones
- *SECCION_BOLETIN*: Exportar boletines de calificaciones
- *SECCION_MANAGE*: Administrar secciones
- *MATERIA_READ*: Listar materias
- *MATERIA_EVALUAR*: Evaluar materias
- *MATERIA_MANAGE*: Administrar materias
- *EVALUACION_READ*: Listar evaluaciones
- *EVALUACION_MANAGE*: Administrar evaluaciones
- *MENSAJE_READ*: Listar mensajes
- *MENSAJE_MESSAGE*: Responder mensajes
- *MENSAJE_ADJUNTO_CREATE*: Adjuntar archivos a los mensajes
- *INCIDENCIA_READ*: Listar incidencias
- *INCIDENCIA_MANAGE*: Administrar incidencias
- *REGISTRO_MEDICO_READ*: Listar registros médicos
- *REGISTRO_MEDICO_MANAGE*: Administrar registros médicos
- *SUCESO_READ*: Visualizar registros de auditoría del sistema
- *REPORTES_NUEVOS_ESTUDIANTES*: Generar reporte de nuevos estudiantes
- *REPORTES_ESTADISTICAS_BLOQUES*: Generar reporte de estadísticas de bloques
- *REPORTES_LISTADO_ESTUDIANTES*: Generar reporte de listado de estudiantes
- *REPORTES_RESUMEN_DOCENTES*: Generar reporte de resumen de docentes

Puesto que resulta difícil explicar exactamente a qué funcionalidades le da acceso cada permiso, solamente se da la descripción del permiso.
En consecuencia, para cada funcionalidad que se explique en la presente guía se listan los permisos necesarios para poder acceder a estas.

<div class="note">
  <h5>Permisos Administrativos</h5>
  <p>Los permisos administrativos son los que terminan en <i>_MANAGE</i> y otorgan el acceso más elevado sobre la funcionalidad en cuestión.
    Por ejemplo, si se otorga el permiso <i>USUARIO_MANAGE</i> ya no es necesario otorgarle <i>USUARIO_READ</i> o <i>USUARIO_CREATE</i>, 
    puesto que ya se encuentran incluidos en el primero.</p>
</div>

Si bien los perfiles de usuario ofrecen una amplia variedad de permisos, se tiene la deventaja de que estos permisos son *globales* al 
sistema. Por lo tanto, si se quiere otorgar acceso a los expedientes de estudiantes de una clase en particular, por ejemplo, no se le 
debería asignar el permiso *ESTUDIANTE_READ* perfil, puesto que ello le daría autorización para visualizar *todos* los expedientes
de los estudiantes. Para lograr el resultado deseado se deberá asignar objetos al usuario.

## Objetos

Para darle accesos limitados al usuario se le puede asignar un objeto determinado, lo cual le otorgará diversos permisos dependiendo del 
tipo de objeto que se le asigne:

- **Estudiante**: Permite visualizar el expediente del estudiante, siempre y cuando estén solventes.
- **Pariente**: Permite visualizar los expedientes de los estudiantes solventes de los cuales el pariente es responsable (esto se puede visualizar
  en el expediente del estudiante en cuestión, en la pestaña *Responsables*).
- **Docente**: Le otorga varios accesos al docente, dependiendo de la forma en la que esté configurado:
  - Permite visualizar y evaluar todas las materias que el docente imparta.
  - Permite visualizar las secciones (incluyendo expedientes de estudiantes, materias y evaluaciones) de los cuales esté configurado como docente guía.
  - Permite visualizar las materias (incluyendo evaluaciones) para los cuales el docente esté configurado como jefe de asignatura.
- **Nivel**: Le otorga permisos sobre un nivel determinado (*Primaria*, por ejemplo), los cuales pueden variar dependiendo de qué roles se le asignen al objeto. 
  Estos roles corresponden a un subconjunto de los permisos que se listaron anteriormente, de tal forma que al asignarle el rol *ESTUDIANTE_READ* al objeto, 
  por ejemplo, el usuario podrá visualizar los expedientes de los estudiantes de igual forma que si se le hubiese asignado el permiso homónimo, pero *limitado* a los
  estudiantes del nivel especificado.
- **Clase**: Le otorga permisos para una clase determinada (*Primer Grado*, por ejemplo), los cuales, al igual que para un nivel, dependen de los roles que
  se le asignen al objeto.

En la pantalla de visualización del objeto se pueden administrar sus asignaciones de usuarios, siempre que se cuente con el permiso *USUARIO_CREATE*,
en cuyo caso se mostrará la pestaña adicional *Usuarios*, a como se ilustra en la siguiente captura:

![objeto](/img/docs/seguridad_objetos.png)

En dicha pestaña se listan los usuarios que tienen asignados el objeto actual, con las opciones para *Eliminar* **(1)** la asignación, modificar los *Roles* **(2)**
del objeto (para *Nivel* o *Clase*) o *Mostrar* **(3)** directamente los detalles del usuario.

También se cuenta con la opción de *Nuevo* **(4)**, lo cual nos permite [crear un usuario](/docs/usuarios/#crear_usuario) con el objeto asignado, o 
alternativamente se cuenta con la opción de *Agregar* **(5)** el objeto a un usuario existente.

Se puede agregar cualquier cantidad de objetos a un usuario, lo cual permite una mayor flexibilidad al momento de definir los accesos
permitidos para el usuario en cuestión.

<div class="note">
  <h5>Crear usuarios de estudiantes masivamente</h5>
  <p>Para evitarse el trabajo de crear usuarios para cada uno de los estudiantes del sistema, se puede hacer uso de la opción <i>Importar</i> 
    del <a href="/docs/periodo_lectivos/#importar">periodo lectivo</a>, lo cual, además de importar las listas de estudiantes del sistema administrativo,
    procederá a crear nuevos usuarios con el código del estudiante como login y con el estudiante ya asignado al usuario.</p>
</div>
