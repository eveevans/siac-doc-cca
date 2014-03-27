---
layout: docs
title: Parientes
prev_section: docentes
next_section: clases
permalink: /docs/parientes/
---

Al ingresar en la opción *Parientes* en el menú se desplegará un listado de los parientes (padres de familia y responsables) del sistema con la opción para ingresar a los 
[detalles del pariente](#detalles_del_pariente):

![listado](/img/docs/parientes_index.png)

Adicionalmente, el listado cuenta con las siguientes opciones:

- Un campo de texto **(2)** para filtrar los parientes por nombre y/o apellidos.
- Si se cuenta con el permiso *PARIENTE_CREATE*, se desbloquea la opción *Nuevo Pariente* **(1)** para [ingresar un pariente](#crear_pariente) en el sistema.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>PARIENTE_READ</i>.</p>
</div>

## Crear Pariente

Al dar clic en la opción de crear pariente se despliega el siguiente formulario:

![nuevo](/img/docs/parientes_new.png)

En dicho formulario es necesario llenar la información general y de contacto del pariente. Luego de enviar el formulario exitosamente, 
se podrá acceder a los [detalles del pariente](#detalles_del_pariente).

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>PARIENTE_CREATE</i>.</p>
</div>

## Detalles del Pariente

![detalles](/img/docs/parientes_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(1)** privado a este pariente, si se cuenta con el permiso *PARIENTE_MESSAGE*.
- Opción para *Editar* los detalles del pariente **(2)**, si se cuenta con el permiso *PARIENTE_UPDATE*, lo cual desplegará el formulario de actualización 
  del pariente con los mismos campos del [formulario de creación](#crear_pariente).
- Opción para *Eliminar* el pariente **(3)**, si se cuenta con el permiso *PARIENTE_MANAGE* y el pariente no tenga asignado ningún estudiante como hijo o dependiente.
  Esta opción no resulta muy útil puesto que el pariente ya se elimina desde la [pestaña de padres y responsables](/docs/estudiantes/#padres_y_responsables) del 
  estudiante.

Por su parte, los detalles del detalles del pariente se visualizan en las siguientes pestañas:

### General

Información general y de contacto del pariente. Al igual que en el [expediente del estudiante](/docs/estudiantes/#general), en la parte inferior se puede acceder a un 
registro de cambios **(4)** en el que se puede visualizar las modificaciones que ha sufrido la información a lo largo del tiempo.

### Hijos y Dependientes

En estas pestañas se muestran los estudiantes que están relacionados a este pariente, junto a un enlace al [expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante)
si se cuenta con el permiso *ESTUDIANTE_READ*:

![hijos](/img/docs/parientes_show_hijos.png)

### Usuarios

Únicamente está disponible si se cuenta con el permiso *USUARIO_READ*. [Las funcionalidades de esta pestaña se describen en la sección de seguridad](/docs/seguridad/#objetos).
