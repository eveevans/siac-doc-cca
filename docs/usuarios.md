---
layout: docs
title: Usuarios
prev_section: perfiles
next_section: seguridad
permalink: /docs/usuarios/
---

Para poder ingresar al sistema se debe estar registrado primero como un usuario habilitado. A continuación se muestran las diversas opciones
de administración de los usuarios del sistema.

Al ingresar a la opción de *Usuarios* del menú se muestra un listado de los usuarios del sistema:

![listado](/img/docs/usuarios_index.png)

En este se muestran los campos principales del usuario (login, nombre, email, perfil, habilitado), y enlaces **(1)** para mostrar los
[detalles del usuario](#detalles_del_usuario).

Las opciones adicionales que comprende esta pantalla son: 

- Un campo de texto **(2)** para filtrar los usuarios por nombre, email y/o perfil.
- Opción para [crear un nuevo usuario](#crear_usuario) **(3)**, si se cuenta con el permiso *USUARIO_CREATE*.
- Por defecto se muestran únicamente los usuarios *habilitados* del sistema, es decir, aquellos que pueden iniciar sesión. Por consiguiente,
  se cuenta con la opción *Mostrar todos* **(4)**, que quita dicha restricción y muestra todos los usuarios del sistema.

<div class="note">
  <h5>Filtro avanzado</h5>
  <p>Por opciones de rendimiento, la opción para filtrar únicamente busca coincidencias por el inicio del campo. Sin embargo, este comportamiento
    se puede modificar si se le antepone un símbolo de porcentaje <b>%</b> al inicio de la cadena. Por ejemplo, la cadena <b>%@</b> nos filtrará
    todos los usuarios con correo electrónico.</p>
</div>

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>USUARIO_READ</i>.</p>
</div>

## Crear Usuario

Al dar clic en la opción de crear usuario se despliega el siguiente formulario:

![crear](/img/docs/usuarios_new.png)

- Los campos obligatorios son *perfil*, *login* y *nombre*.
- A pesar de que el email no es obligatorio, se recomienda ingresarlo puesto que los detalles de la nueva cuenta se envían por correo electrónico;
  de igual manera, si cuenta con un email podrá hacer uso de las [opciones de recuperación de contraseña](/docs/login/#olvido_de_contrasea).
- La contraseña puede dejarse vacía, en cuyo caso se generará una contraseña automáticamente.
- Si se ingresa una nueva contraseña, deberá repetirse en el campo de *Password confirmation* para confirmar que se introdujo correctmente.
- Si se le da check el campo *Expired password*, el usuario deberá cambiar su contraseña en el próximo inicio de sesión.
- Si se le quita el check en el campo *Habilitado* la cuenta de usuario se bloqueará y no podrá utilizarse para ingresar al sistema.

Una vez que se envíe el formulario se creará un usuario en el sistema, y se enviará un correo electrónico al usuario con los detalles de la
nueva cuenta creada, en caso de que se haya especificado un email válido.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>USUARIO_CREATE</i>.</p>
</div>

## Detalles del usuario

![detalles](/img/docs/usuario_show.png)

Las opciones de esta pantalla son las siguientes:

- Opción para [enviar un mensaje](/docs/mensajes/#crear_mensaje) **(1)** privado a este usuario, si se cuenta con el permiso *USUARIO_MESSAGE*.
- Opción para *Editar* detalles del usuario **(2)**, si se cuenta con el permiso *USUARIO_ADMIN*, lo cual desplegará el formulario de modificación
  de usuario con los mismos campos que la creación de usuario.
- Opción para *Eliminar* el usuario **(3)**, si se cuenta con el permiso *USUARIO_ADMIN*.

Por su parte, los detalles del usuario se visualizan en 2 pestañas: la pestaña *General* contiene la información general del usuario, así como 
también información básica de auditoría; la pestaña *Objetos* contiene todos los objetos que están asignados al usuario:

![objetos](/img/docs/usuarios_show_objetos.png)

Esta pestaña, a su vez, puede contener las siguientes opciones para cada uno de los objetos listados:

- Opción para *Eliminar* **(1)** la asignación, lo cual elimina la relación entre el objeto y el usuario y de esta forma revoca al usuario cualquier permiso
  obtenido de dicha asignación. Para esta opción se requiere el permiso *USUARIO_ADMIN*.
- Opción para *Mostrar* **(2)** los detalles del objeto en cuestión.
- Si el objeto admite roles, estos se mostrarán en el listado, y adicionalmente, si se cuenta con el permiso *USUARIO_ADMIN*, se contará con la opción
  *Roles* **(3)** para modificar dicha asignación.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para todas estas opciones se requiere al menos el permiso <i>READ</i> sobre el objeto especificado, el cual dependerá del tipo de objeto; por ejemplo,
    para un objeto tipo <i>Clase</i> se requerirá el permiso <i>CLASE_READ</i>.</p>
</div>

Los objetos y el tema de la seguridad en general se verá con más detalle en la sección de [Seguridad](/docs/seguridad/).
