---
layout: default
title: "App Registration"
nav_order: 2
---

# ¿Cómo crear una App Registration en Azure y vincularla a Power BI? 

En los pasos siguientes vamos a ver como registrar una App en Azure Active Directory la cual nos permitirá que la plataforma de identidad de Microsoft nos provea servicios de autenticación y autorización para PiBi. 
1. Como primer paso ingresamos al portal de [Azure](https://portal.azure.com/) y una vez dentro pulsamos en el menú ubicado en el margen superior izquierdo.   
![app1](Media/App%20registration/menu%20azure.PNG)
2. Se desplegará un menú en donde buscamos y seleccionamos la opción *Azure Active Directory*. 
3. En la sección *Administrar*, seleccionamos la opción *Registro de Aplicaciones*.
4. En la nueva pantalla pulsamos en *Nuevo registro*.  
![app2](Media/App%20registration/nueva%20app.PNG)
5. Definimos un nombre a la aplicación. Recordemos que este será el nombre que se muestra al momento de pedir permisos de acceso a nuestra información básica, por lo que tenemos que ingresar un nombre significativo y acorde a la empresa. También en este paso tenemos la posibilidad de seleccionar quiénes se podrán autenticar a través de esta aplicación. Una vez completado pulsamos en *Registrar*.  
![app3](Media/App%20registration/Registrar%20app.PNG)
6. En este momento ya podemos ver el *Id de la aplicación* (Copiar y conservar este valor).  
![app4](Media/App%20registration/app%20id.PNG)
7. El próximo paso es generar la *Secret Key*. Para eso, ubicamos la sección de *Credenciales de cliente*, y pulsamos en Agregar un certificado o secreto. Tengamos en cuenta que este paso es necesario para configurar la conexión con *Service Principal*. 
![app5](Media/App%20registration/agregar%20secreto.PNG)
8. Una vez dentro de *Certificados y secretos*, vamos a la sección de Secretos de cliente, donde pulsamos en el botón *Nuevo Secreto de Cliente*. 
![app6](Media/App%20registration/nuevo%20secreto.PNG)
9. Luego, simplemente completamos la descripción a nuestro secreto, ingresamos un tiempo de caducidad y pulsamos en *Agregar*.  
![app7](Media/App%20registration/datos%20secreto.PNG)
10. En este momento vamos a copiar el contenido del campo valor. Este se va a ver mientras permanezcamos en la página, una vez que cerremos o cambiemos no lo volveremos a ver, por lo que es muy importante que guardemos este valor para utilizarlo como *Secret Key* en la configuración de PiBi:  
![app8](Media/App%20registration/secret%20key.PNG)
11. Para poder acceder a informes de Power BI con orígenes de *Azure Analysis Services* es necesario contar con el valor del campo ObjectId. Este valor lo copiamos ingresando en *Managed application in local directory* 
![app9](Media/App%20registration/objectId1.png)

     Luego copiamos el valor del campo Object Id de Properties

     ![app10](Media/App%20registration/objectId2.png)
12. Tengamos en cuenta que, si vamos a conectar PiBi con un conector *Master User*, debemos realizar una configuración adicional en la App. Tenemos que ir a la sección *Autenticación* y activar la opción *Permitir flujos de clientes públicos*.
![app11](Media/App%20registration/app%20auth.PNG)
13. Para poder comunicarnos con Power BI tenemos que configurar los permisos de la aplicación que acabamos de registrar. Para eso en el panel de la izquierda buscamos Permisos de Api, pulsamos en *Agregar un Permiso*, y en la lista de los servicios seleccionamos *Power Bi Services*.  
![app12](Media/App%20registration/permisos%20de%20api.PNG)
14. Una vez seleccionada esa opción se nos va a desplegar una ventana donde debemos elegir el tipo de permiso que va a necesitar la aplicación creada. Seleccionamos *Permisos de la aplicación*, luego seleccionamos los permisos *Read.All y Read.WriteAll* sobre el Tenant, y por último aplicamos los cambios en *Agregar Permisos*.  
![app13](Media/App%20registration/agregar%20permisos.PNG)
15. Una vez hecho todo esto, si lo realizamos con un usuario administrador, con solo aplicar el consentimiento en *Permisos de Api*, vamos a aplicar todo lo visto anteriormente. Caso contrario, debemos solicitar al administrador su consentimiento en la aplicación creada.
En nuestro lo realizamos con un usuario común y por ello vemos la opción desactivada.  
![app14](Media/App%20registration/permisos%20admin.PNG)
16. Por último, para poder comunicarnos por completo con los servicios de *Power Bi*, debemos acceder al portal de [*Power Bi*](https://app.powerbi.com/), ingresar a *Configuración, Portal de Administración* y en la ventana que nos aparece habilitar *“Embed content in apps”* bajo la sección *Opciones de desarrollador*.  
![app15](Media/App%20registration/PBI%20embed%20content.png)
17. Para el caso de conectarnos a Power BI por medio de un Service Principal necesitamos realizar una configuración adicional. Tenemos que ingresar a *Perfil, Configuración, Portal de Administración* y en la ventana que nos aparece habilitar el *“allow service principals to use Power BI APIs”*.  
![app16](Media/App%20registration/PBI%20service%20principal.png)
18. Tengamos en cuenta que para que poder realizar esto, anteriormente se tiene que habilitar el servicio de autenticación por Api en el portal de Azure. En el siguiente enlace se describe como llevar a cabo esto, [Enable service principal authentication for read-only admin APIs](https://docs.microsoft.com/en-us/power-bi/admin/read-only-apis-service-principal-authentication).

Se puede obtener más información ingresando a: [Inicio rápido: registrar una aplicación en la plataforma de identidad de Microsoft | Documentos de Microsoft](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app?source=docs)