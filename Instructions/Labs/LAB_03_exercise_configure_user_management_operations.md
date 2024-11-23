---
lab:
  title: 'Ejercicio: Configuración de operaciones de administración de usuarios '
  module: Guided Project – Administer Active Directory Domain Services
---
En este ejercicio, realizará operaciones de administración de usuarios.

## Crear unidades organizativas

En esta tarea, crearás tres unidades organizativas: Sydney, Melbourne y Brisbane. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory desde el menú Herramientas de la consola Administrador de servidores.
2.  Haz clic con el botón derecho en el dominio **tailwindtraders.internal**.
3.  Selecciona **Nuevo** y después **Unidad organizativa**.
4.  En el cuadro de diálogo Nuevo objeto: unidad organizativa, establece el nombre `Sydney` y haz clic en **Aceptar**.
5.  Repite este proceso para crear la unidad organizativa `Melbourne` y la unidad organizativa `Brisbane`.

## Creación de usuarios

En esta tarea, crearás un usuario y configurarás propiedades de cuenta como Fecha de expiración de la cuenta. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory (o Centro de administración).
2.  Haz clic con el botón derecho en la unidad organizativa Sydney.
3.  Selecciona **Nuevo** y después **Usuario**.
4.  Escribe `SydneyContractor` en los campos Nombre completo y Nombre de inicio de sesión de usuario y haz clic en **Siguiente**.
5.  Especifica una contraseña, como `Pa55w.rdPa55w.rd`, y confírmala.
6.  Haz clic en **Siguiente** y **Finalizar**.
7.  Selecciona la unidad organizativa Sydney. En la unidad organizativa Sydney, haz doble clic en la cuenta de usuario SydneyContractor.
8.  En la pestaña Cuenta, en la sección **La cuenta expira**, selecciona **Fin de:** y establece la fecha en **1 de enero de 2030**. Haga clic en **OK**.
9.  Haz clic con el botón derecho del ratón en el usuario SydneyContractor y selecciona **Copiar**.
10. Escribe `MelbourneContractor` en los campos Nombre completo y Nombre de inicio de sesión de usuario. Haga clic en **Next**.
11. Especifica una contraseña, como `Pa55w.rdPa55w.rd` y después confírmala.
12. Haz clic en **Siguiente** y **Finalizar**.
13. Haz clic con el botón derecho del ratón en el usuario SydneyContractor y selecciona **Copiar**.
14. Escribe `BrisbaneContractor` en los campos Nombre completo y Nombre de inicio de sesión de usuario. Haga clic en **Next**.
15. Especifica una contraseña como `Pa55w.rdPa55w.rd` y después confírmala.
16. Haz clic en **Siguiente** y **Finalizar**.
17. Arrastra el usuario MelbourneContractor a la unidad organizativa Melbourne.
18. Si aparece una advertencia sobre objetos móviles, haz clic en **Sí**.
19. Arrastra el usuario BrisbaneContractor a la unidad organizativa Brisbane.
20. Si aparece una advertencia sobre objetos móviles, haz clic en **Sí**.


## Crear el grupo Administradores Sydney

En esta tarea, crearás un nuevo grupo de seguridad denominado Administradores de Sydney. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory.
2.  Haz clic con el botón derecho en la unidad organizativa de Sydney y selecciona **Nuevo** y después **Grupo**.
3.  Escribe `Sydney Administrators` en Nombre de grupo y selecciona **Universal** en Ámbito de grupo. Haga clic en **OK**.
4.  En la unidad organizativa Sydney, haz doble clic en la cuenta de usuario SydneyContractor.
5.  En la pestaña Miembro de, haz clic en **Agregar**.
6.  Escriba `Sydney Administrators`.
7.  Haga clic en **Comprobar nombres**.
8.  Haz clic en **Aceptar** y después en **Aceptar**.

## Configuración de un usuario como usuario protegido

En esta tarea, configurarás la cuenta de usuario SydneyContractor como un usuario protegido. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory (o Centro de administración).
2.  Ve a la unidad organizativa Sydney y haz doble clic en la cuenta de usuario SydneyContractor.
3.  En la pestaña Miembro de, haz clic en **Agregar**.
4.  Escriba `Protected Users`.
5.  Haga clic en **Comprobar nombres**.
6.  Haz clic en **Aceptar** y después en **Aceptar**.

## Delegar permisos de seguridad en una unidad organizativa en un grupo de seguridad

En esta tarea, delegarás la capacidad de restablecer las contraseñas y forzar el cambio de contraseña al grupo Administradores de Sydney a través de cuentas de la unidad organizativa de Sydney. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory.
2.  Hagz clic con el botón derecho en la unidad organizativa de Sydney y haz clic en **Delegar control**.
3.  En la página de bienvenida del asistente para la delegación de control, haz clic en **Siguiente**.
4.  Haz clic en **Agregar** y escribe `Sydney Administrators`.
5.  Haga clic en **Comprobar nombres**.
6.  Haz clic en **Aceptar** y haz clic en **Siguiente**.
7.  En la página Tareas para delegar, selecciona la opción **Restablecer contraseñas de usuario y forzar el cambio de contraseña en el siguiente inicio de sesión**. Haga clic en **Next**.
8.  Haga clic en **Finalizar**

## Configurar el atributo de ciudad para un usuario

En esta tarea, configurarás un atributo de ciudad para una cuenta de usuario y después usarás el atributo Buscar para comprobar que el usuario está presente. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory.
2.  Selecciona la unidad organizativa Sydney, haz clic con el botón derecho en la cuenta de usuario SydneyContractor y haz clic en **Propiedades**.
3.  En la pestaña Dirección de las propiedades del contratista Sydney, establece el campo Ciudad en `Sydney` y haz clic en **Aceptar**.
4.  En Usuarios y equipos de Active Directory, haz clic con el botón derecho en Tailwindtrader.internal y haz clic en **Buscar**.
5.  En la pestaña Avanzado del cuadro de diálogo Buscar usuarios, contactos y grupos, selecciona **Campo**, luego **Usuario** y, por último, **Ciudad**. Establece la condición en **Es (exactamente)**. Establece el valor en **Sydney**. Haga clic en **Buscar ahora**.
6.  Haz clic en **Sí** en la ventana emergente Buscar en el directorio.
7.  Comprueba que el usuario SydneyContractor aparece en los **Resultados de la búsqueda**.
8.  Cierra el cuadro de diálogo Buscar usuarios, contactos y grupos.

## Deshabilitar el usuario del contratista de Melbourne

En esta tarea, deshabilitarás el usuario de contratista Melbourne. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory y después abre la unidad organizativa Melbourne.
2.  En la unidad organizativa Melbourne, haz clic con el botón derecho en **MelbourneContractor** y haz clic en **Deshabilitar cuenta**.
3.  Haga clic en **OK**.

## Restablecer la contraseña del usuario del contratista de Brisbane

En esta tarea, restableces la contraseña del usuario de BrisbaneContractor. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, abre Usuarios y equipos de Active Directory y después abre la unidad organizativa Brisbane.
2.  Haz clic con el botón derecho del ratón en el usuario BrisbaneContractor y selecciona **Restablecer contraseña**.
3.  En el cuadro de diálogo Restablecer contraseña, escribe la contraseña `Pa66w.rdPa66w.rd` dos veces y selecciona **OK**. Vuelva a hacer clic en **Aceptar** en el cuadro de diálogo que te notifica que se ha cambiado la contraseña.
