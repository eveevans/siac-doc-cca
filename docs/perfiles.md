---
layout: docs
title: Perfiles
prev_section: mensajes
next_section: usuarios
permalink: /docs/perfiles/
---

Los perfiles de usuario corresponden el primer nivel de control de acceso del sistema, puesto que agrupan una serie de permisos 
que son globales para todo el sistema.

Al ingresar en la opción de *Perfiles* del menú se muestra un listado de los perfiles del sistema:

![listado](/img/docs/perfiles_index.png)

Este muestra el nombre y descripción del perfil, así como también enlaces **(1)** para mostrar los [detalles del perfil](#detalles_del_perfil). 
Adicionalmente, se cuenta con la opción de [crear un nuevo perfil](#crear_perfil) **(2)**.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Se necesita el permiso <i>PERFIL_MANAGE</i> en el perfil del usuario para acceder a todas las opciones de perfiles de usuario.</p>
</div>

## Crear Perfil

Al dar clic en la opción de crear perfil se despliega un formulario en el que se debe ingresar el nombre y descripción del perfil, y seleccionar
todos los permisos globales del perfil:

![crear](/img/docs/perfiles_new.png)

Al enviar el formulario se habrá creado el perfil, el cual se podrá asignar a cualquier usuario.

Los permisos y el tema de la seguridad en general se verá con más detalle en la sección de [Seguridad](/docs/seguridad/).

## Detalles del perfil

Se muestran dos pestañas: la pestaña *General* muestra el nombre y descripción del perfil, así como también las fechas de ingreso 
y modificación; sin embargo, la pestaña de *Autorizaciones* es la realmente importante, puesto que lista cuáles son los permisos 
globales que tiene el perfil:

![detalles](/img/docs/perfil_show.png)

Al dar clic en la opción de *Editar* **(1)** se desplegará un formulario de modificación del perfil, el cual contiene los mismos campos
mostrados en la creación de perfil.

Por otro lado, la opción de *Eliminar* **(2)** únicamente estará disponible para los perfiles que no se hayan asociado a ningún usuario.
Por consiguiente, si se desea eliminar un perfil con usuarios asignados es preciso editar o eliminar dichos usuarios para que la opción
se desbloquee.
