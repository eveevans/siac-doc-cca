---
layout: docs
title: Tipos de Notas
prev_section: periodo_lectivos
next_section: niveles
permalink: /docs/tipo_notas/
---

Los tipos de notas definen la estructura de las calificaciones consolidadas para el periodo lectivo. Al ingresar en la opción de 
*Tipos de Notas* del menú se muestra el listado siguiente:

![listado](/img/docs/tipo_notas_index.png)

Por defecto se muestran los tipos de notas para el periodo lectivo actual. Si se quiere visualizar información histórica, se debe *Mostrar filtros*
y seleccionar un periodo lectivo diferente.

<div class="note info">
  <h5>Seguridad</h5>
  <p>Se necesita el permiso <i>TIPO_NOTA_MANAGE</i> en el perfil del usuario para acceder a todas las opciones de los tipos de notas.</p>
</div>

## Crear Tipo de Nota

Al seleccionar la opción *Nuevo tipo* se despliega el siguiente formulario:

![crear](/img/docs/tipo_notas_new.png)

Los tipos de notas pueden variar entre periodos lectivos diferentes, de tal forma que en un ciclo se califiquen *4 BIMESTRES, 2 SEMESTRES y FINAL*,
mientras que en otro sean *3 CUATRIMESTRES y FINAL*.

Por consiguiente, debe seleccionarse el *Periodo lectivo* al momento de crear un tipo de nota, indicar un *Nombre*, un *Nombre corto* (se recomienda
una inicial) y opcionalmente las *Observaciones*.

Los campos *Consolidado* y *Número consolidados* requieren especial atención, puesto que son los que definen la estructura de las calificaciones
consolidadas. Los tipos de nota guardan una relación jerárquica, por lo tanto el campo *Consolidado* seleccionará automáticamente la rama inferior
de la jerarquía, y en caso de existir, debe colocarse el **número de consolidados necesarios para consolidar el siguiente elemento de la jerarquía**.
Por consiguiente, la jerarquía debe crearse desde la calificación más general hasta la más específica, y el número de bloques evaluativos
del periodo lectivo se calculará multiplicando progresivamente el número de consolidados de cada rama de la jerarquía.

Para ilustrar, considérese el ejemplo anterior: *4 BIMESTRES, 2 SEMESTRES y FINAL*. Para crear esta estructura, se deben seguir los siguientes pasos:

- Ingresar *FINAL*, consolidado ninguno.
- Ingresar *SEMESTRE*, consolidado *FINAL*, número de consolidados *2*.
- Ingresar *BIMESTRE*, consolidado *SEMESTRE*, número de consolidados *2*.

Y el número resultante de bloques evaluativos para el periodo lectivo será: *2 BIMESTRES x 2 SEMESTRES = 4*.

## Detalles del Tipo de Nota

En esta pantalla se muestran los detalles del tipo de nota:

![detalles](/img/docs/tipo_notas_show.png)

Adicionalmente se cuenta con la opción de *Editar* el tipo de nota, lo cual desplegará el formulario de modificación con los mismos campos
que el [formulario de creación](#crear_tipo_de_nota), así como también con la opción de *Eliminar* el tipo de nota del sistema,
siempre y cuando el periodo lectivo esté abierto, el tipo de nota no tenga calificaciones consolidadas y el tipo de nota sea el último
elemento de la jerarquía.

<div class="note warning">
  <h5>Modificar tipos de notas con consolidados ya efectuados</h5>
  <p>Se recomienda encarecidamente que no se modifique la estructura de los tipos de notas si ya se han consolidado materias para el periodo
    lectivo. Esto incorporará inconsistencias en el sistema.</p>
</div>
