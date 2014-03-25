---
layout: docs
title: Mensajes
prev_section: quickstart
next_section: perfiles
permalink: /docs/mensajes/
---

El sistema cuenta con un módulo de mensajería privada entre los usuarios. Para acceder a la bandeja de entrada, debe dar clic
al ícono de correo que se encuentra en la esquina superior derecha de la pantalla del sistema. Esto desplegará un listado de
los mensajes recibidos:

![inbox](/img/docs/mensajes_index.png)

En el listado se muestra el remitente del mensaje, el asunto y la fecha y hora en la que fue enviado, así como también un enlace **(1)** para 
mostrar el [contenido del mensaje](#detalles_de_mensaje). Los mensajes no leídos se muestran resaltados, y se muestra su número al lado del ícono de correo.
Adicionalmente, se cuenta un campo de texto **(2)** que permite filtrar los mensajes por remitente y/o asunto.

También se puede acceder a los mensajes a los que el usuario ha enviado (bandeja de salida) al dar clic en el enlace *Enviados* **(3)**, en cuyo 
caso la columna de remitente es reemplazada por la de destinatario.

## Detalles de mensaje

![detalles](/img/docs/mensaje_show.png)

Al acceder al mensaje se puede visualizar la fecha en la que fue enviado, el destinatario (puede ser una persona específica o un grupo de personas,
como una sección, clase o nivel), remitente, asunto, archivos adjuntos (si existieran) y contenido del mensaje.

Al lado del remitente se encuentra un enlace **(1)** para enviarle un mensaje al remitente. De igual manera, entre las opciones del mensaje se
incluye la opción *Responder* **(1)**, lo cual abre el formulario de creación de mensaje de la misma forma que la opción anterior, pero citando
el asunto y contenido del mensaje actual; por otra parte, la opción *Eliminar* remueve al mensaje de la bandeja de entrada (o salida) del usuario, aunque 
*no elimina físicamente el mensaje de la base de datos del sistema* por razones de auditoría.

## Crear mensaje

No existe una opción directa en la bandeja de entrada o salida para crear un nuevo mensaje y enviarlo a cualquier destinatario. 
Por consiguiente, para enviar un mensaje debe de darse clic en cualquiera de los íconos de envío de mensajes que se encuentran en las diversas pantallas
del sistema. Por ejemplo, si se desea enviar un mensaje al docente guía, se deberá ingresar a la [pestaña académica](/docs/quickstart/#acadmico) del
expediente del estudiante y darle clic a la opción de enviar mensaje, lo cual desplegará el siguiente formulario:

![crear](/img/docs/mensajes_new.png)

Como se puede ver, únicamente es necesario ingresar el asunto y contenido del mensaje, puesto que el destinatario se detecta automáticamente.
En el caso de los mensajes a grupos (clase o sección por ejemplo), se permitirá seleccionar si se quiere enviar el mensaje únicamente a los
estudiantes y padres de familia, a los docentes o a todos.

Una vez que se envía el formulario se crea un nuevo mensaje, por lo cual se puede visualizar en nuestra bandeja de salida, así como también
en la bandeja de entrada del destinatario. De igual forma, se le enviará un email el correo electrónico del destinatario notificándole que 
se le ha enviado un mensaje en el sistema académico.
