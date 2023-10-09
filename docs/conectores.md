---
layout: default
title: "Conectores"
nav_order: 5
---

# ¿Qué es un conector en PiBi? 

Un conector es una configuración que nos va a permitir acceder a los reportes de Power BI. En PiBi debemos completar la información del conector para indicar en qué Tenant se encuentran dichos reportes. 

Para validar nuestros permisos de acceso a estos informes podemos elegir entre dos tipos de conexión. 

Uno de ellos se llama Service Principal y consiste en indicarle al conector el *Id de la aplicación* y el *Secret Key*. Estos códigos los obtenemos creando una *App Registration en Azure*. El campo *ObjectId* es el Object Id de Managed Identity del Service Principal y es un campo no requerido pero si obligatorio para informes con orígenes de *Azure Analysis Services*.

![conectores1](Media/Conectores/conectores1.png)

La otra opción de acceso es *Master User* en la cual debemos ingresar un usuario y contraseña. Lo particular es que este usuario debe tener permisos de administrador en Power BI al que nos estamos conectando y permisos sobre la App registrada. 

![conectores2](Media/Conectores/conectores2.png)

Cuando completamos los datos y pulsamos en el botón *Aplicar* se guardará  el conector con los datos ingresados.

# Sincronizar Informes 

Luego de tener configurado nuestro conector vamos a poder sincronizar la lista de informes de PiBi con los datos que se encuentran compartidos en los espacios de trabajo de Power BI. 

Cuando pulsemos en *Sincronizar Informes*, PiBi buscará los informes en las áreas de trabajo compartidas en Power Bi y actualizará su base de informes. Luego se aplicará el rol de seguridad *Administrador* para todos los usuarios administradores de PiBi y para todos los informes recientemente sincronizados. De manera que los usuarios administradores de PiBi siempre podrán consultar la información de los informes. 

![conectores3](Media/Conectores/conectores3.png)

Además, PiBi cuenta con dos sincronizaciones automáticas por día las cuales mantienen actualizados los informes. 

# Cambiar conector existente

Puede ocurrir que por vencimiento de una key o cambios en nuestra organización tengamos que cambiar el conector de PiBi. En este escenario es **muy importante** hacer el cambio en un orden determinado puesto que si configuramos un conector sin ningún acceso en PowerBi, la sincronización de PiBi resolverá que hemos eliminado workspaces y dejaremos de ver asignaciones.
**¿Cómo lo hacemos correctamente?**
1. Registrar nueva App en Azure o Service Principal para la conexión con los permisos como nos guía la documentación.
2. Ingresar a Power Bi Service para agregar la aplicación registrada como Administrador de las Áreas de Trabajo que teníamos configuradas.
3. Ingresar a PiBi y cambiar los valores en menú Conectores.
4. Sincronizar informes en menú de Conectores.
Tengamos presente que no hacer este orden exacto puede provocar la pérdida de asignaciones puesto que si sincronizamos un conector que no tiene permisos en Áreas de Trabajo, asumirá que las quitamos y no queremos verlas.