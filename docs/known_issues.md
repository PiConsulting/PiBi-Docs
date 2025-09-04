---
layout: default
title: "Known Issues"
nav_order: 15
---

# ¿Qué problemas conocidos tenemos en PiBi? 

En PiBi, como cualquier aplicativo, tenemos defectos conocidos, de menor prioridad, que pueden ocurrir y estamos trabajando en resolver. Como aún no fueron resueltos, queremos transparentarlos para que puedan saber de ante mano que experiencia de la app puede provocarlos. 
A continuación se listan ejemplos de problemas que pueden encontrarse.

- v1.0 y v1.1: Cuando utilizamos el apartado de filtros para una asignación, la interfaz dispone múltiples condiciones. Hoy PiBi solo ejecuta una condición *Tabla[Columna] IS "Valor"*. De modo que, aunque elijamos una condición ">=", el filtro de PowerBi será un "IS" sin importar la selección.
- v2.0: Actualmente existe un error en los componentes de tipo Tabla, contamos con un delimitador de items por página de la tabla pero al modificarlo el número de páginas no se modifica.
