---
layout: docs
title: Configuración
prev_section: catalogos
permalink: /docs/configuracion/
---

En esta pantalla se permiten actualizar configuraciones globales para el sistema.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Para acceder a esta funcionalidad se necesita el permiso <i>CONFIGURACION_MANAGE</i>.</p>
</div>

## Perfil Estudiante, Docente y Pariente

Si se utiliza esta opción, se bloqueará el campo de *Perfil* cuando se [ingrese un nuevo usuario](/docs/usuarios/#crear_usuario)
desde la pestaña de *Usuarios* del objeto correspondiente.

Adicionalmente, si no se especifica un perfil de estudiante por defecto no se podrán crear usuarios en masa al
[importar los listados en masa](/docs/periodo_lectivos/#importar).

## Excepciones Solvencia

Para que un usuario con un objeto de tipo *Estudiante* pueda visualizar el [expediente del estudiante](/docs/estudiantes/#expediente_del_estudiante),
es necesario esté solvente en el sistema administrativo. Para efectuar esta verificación, se utiliza el código del estudiante y se
consulta su información en el sistema administrativo.

Si se desea que el usuario tenga acceso al estudiante incluso cuando no esté solvente, se debe agregar el código del estudiante
en este campo (múltiples códigos se deben separar por espacios, comas o enters), lo cual agrega una excepción en la verificación de
solvencia.

## Acumular Redondeo de Consolidados

Esta opción modifica la forma en la que se redondean las calificaciones consolidadas a medida que van subiendo en la jerarquía.
Si la opción está desactivada, entonces los consolidados se calculan promediando las calificaciones del nivel *más bajo*, mientras
que si está activada, se promedian las calificaciones del nivel *inmediato inferior*.

Para ilustrar este comportamiento, considérese un escenario con las siguientes notas *BIMESTRALES*: *90*, *91*, *91* y *92*.

Si la opción está desactivada, los consolidados superiores se calcularán de la siguiente manera:

- *PRIMER SEMESTRE* = *(1B + 2B)/2* = *(90 + 91)/2* = *90.5* = **91**.
- *SEGUNDO SEMESTRE* = *(3B + 4B)/2* = *(91 + 92)/2* = *91.5* = **92**.
- *FINAL* = *(1B + 2B + 3B + 4B)/4* = *(90 + 91 + 91 + 92)/4* = **91**.

En cambio, si la opción está habilitada, el cálculo sería de la siguiente manera:

- *PRIMER SEMESTRE* = *(1B + 2B)/2* = *(90 + 91)/2* = *90.5* = **91**.
- *SEGUNDO SEMESTRE* = *(3B + 4B)/2* = *(91 + 92)/2* = *91.5* = **92**.
- *FINAL* = *(1S + 2S)/2* = *(91 + 92)/2* = *91.5* = **92**.
