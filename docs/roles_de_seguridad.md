# ¿Qué son y cómo configuramos los Roles de Seguridad? 

En PiBi los *Roles de Seguridad* son configuraciones de permisos para poder acceder a un informe. Están vinculados al concepto de RLS en Power BI y *deben tener el mismo nombre en PiBi.* 

Por defecto PiBi crea dos Roles de Seguridad:
- *Rol de Seguridad Admin*: Es el rol administrador y nos permite acceder a todos los informes de PiBi. Los administradores pueden acceder a informes con o sin RLS configurado en Power BI. 
- *Rol de Seguridad Ninguno*: Es el rol para acceder a informes que no tengan configurado el RLS en Power BI. 

![conectores1](Media/Roles/roles%20defecto.png)

Como administradores siempre tenemos asignado el rol *Admin* para todos los informes de PiBi, gracias a la sincronización automática de informes. Con este rol podemos acceder a informes con o sin RLS configurado en Power BI. 

Como administradores podemos crear roles de seguridad y luego asignarlos a los usuarios. 

Para crear un nuevo *Rol de seguridad* pulsamos en el botón *Añadir* de la sección *Roles*. 

![conectores1](Media/Roles/roles%20a%C3%B1adir.png)

Definimos el nombre del rol que estamos por crear. *Este nombre del rol debe ser el mismo que la configuración RLS del conjunto de datos del informe en Power BI que queremos aplicar.*

![conectores1](Media/Roles/Rol%20nombre.PNG)

¡Listo! Acabamos de crear el rol y lo tenemos disponible para crear asignaciones de rol.

![conectores1](Media/Roles/rol%20nuevo%20tabla.PNG)

Además, podemos modificar o eliminar el rol desde las acciones disponibles en la tabla.

