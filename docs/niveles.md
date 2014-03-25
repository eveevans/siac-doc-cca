---
layout: docs
title: Niveles
prev_section: tipo_notas
next_section: catalogos
permalink: /docs/niveles/
---

Al ingresar en la opción *Niveles* en el menú se desplegará un listado de los niveles del sistema con la opción para ingresar a
los [detalles del nivel](#detalles_del_nivel):

![listado](/img/docs/niveles_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Por defecto se muestran únicamente los niveles *activos* del sistema, es decir, aquellos que se pueden asignar a clases y asignaturas. Por consiguiente,
  se cuenta con la opción *Mostrar todos* **(2)**, que quita dicha restricción y muestra todos los niveles del sistema.
- Si se cuenta con el permiso *NIVEL_MANAGE*, se desbloquea la opción *Nuevo Nivel* **(1)** para [ingresar un nivel](#crear_nivel) en el sistema.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>NIVEL_READ</i>.</p>
</div>

## Crear Nivel

Al dar clic en la opción de crear nivel se despliega el siguiente formulario:

![nuevo](/img/docs/niveles_new.png)

- Se debe ingresar un *Nombre* para el nivel.
- Se debe ingresar un *Nombre corto* para el nivel, el cual, para que la [importación de estudiante](/docs/estudiantes/#importar_estudiante)
  funcione correctamente, debe coincidir con la inicial que se ocupa para el *nivel* en el sistema administrativo.
- El campo *Orden* se utiliza para ordenar los niveles en los diferentes reportes del sistema.
- Se debe ingresar el *Número de grados* que tiene este nivel. Por ejemplo, el nivel de *PRIMARIA* tiene *6* grados.
- Si se especifica un valor en *Inicio grado*, este se utilizará para nombrar las diferentes clases del nivel. Por ejemplo,
  los grados del nivel de *SECUNDARIA* se numeran del *7* en adelante.
- Se debe ingresar el *Nombre del grado*, el cual se utilizará para nombrar las diferentes clases del nivel. Por ejemplo, 
  para el nivel de *PREESCOLAR* los grados se denominan como *nivel*.
- Se debe especificar si el nivel está *Habilitado*, checkeando el campo homónimo. Los niveles que no estén habilitados no pueden
  utilizarse para crear nuevos clases o asignaturas.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>NIVEL_MANAGE</i>.</p>
</div>

## Detalles del Nivel

En esta pantalla se muestran los detalles del nivel en la pestaña *General*. Adicionalmente, si se cuenta con el permiso *USUARIO_READ*, 
estará disponible la pestaña de *Usuarios*, [cuyas funcionalidades se describen en la sección de seguridad](/docs/seguridad/#objetos).

![detalles](/img/docs/niveles_show.png)

Si se cuenta con el permiso *NIVEL_MANAGE* se tienen las siguientes opciones disponibles:

- Se puede *Editar* **(1)** el nivel, lo cual nos despliega el formulario de modificación con los mismos campos que el 
  [formulario de creación](#crear_nivel).
- Se puede *Eliminar* **(2)** el nivel siempre y cuando no tenga ninguna clase ni asignatura asignada.
