---
layout: default
title: "Solución de problemas"
nav_order: 12
---

# ¿Qué problemas podemos encontrar al ver un informe? 

En PiBi las Asignaciones nos permitirán indicar los permisos de un usuario para acceder a los informes. A la hora de configurar las asignaciones podemos cometer errores que no permitirán visualizar los informes. 
A continuación se listan ejemplos de problemas que pueden encontrarse.

1. Cuando no coinciden el Rol de Seguridad configurado en PIBI con el existente en Power BI

![problemas1](Media/Problemas/roles_no_coinciden.png)

El nombre del Rol de Seguridad en PIBI debe coincidir con el nombre del RLS configurado en Power BI. El resultado e sun mensaje de error al intentar acceder a los datos del reporte.

2. Cuando el valor del filtro no existe en el reporte

![problemas2](Media/Problemas/filtros_1.png)

El valor que se configuró en la asignación de filtro no existe entre las opciones del reporte de Power BI. El resultado es que se aplica el filtro con un valor inexistente por lo cual el reporte puede aparece sin datos.

3. La tabla y/o columna del filtro son erróneas

![problemas3](Media/Problemas/filtros_2.png)

La tabla y/o columna del filtro de PIBI no coincide con los valores configurados en el reporte de Power BI. El resultado es que no se aplica el filtro en el reporte.



