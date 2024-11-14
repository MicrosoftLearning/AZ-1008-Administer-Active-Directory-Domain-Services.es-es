---
lab:
  title: 'Ejercicio: Configuración de operaciones de controlador de dominio'
  module: Guided Project – Administer Active Directory Domain Services
---
En este ejercicio, promoverá un servidor al controlador de dominio, transferirá un rol de FSMO al nuevo controlador de dominio, creará un sitio y agregará una subred al sitio.

## Instalación de Active Directory Domain Services (AD DS) y promoción al controlador de dominio

En esta tarea, promueves el servidor miembro TAILWIND-MBR1 para convertirte en un controlador de dominio en el dominio TAILWINDTRADERS. Para completar la tarea, realiza los siguientes pasos:

1.  Inicia sesión en TAILWIND-MBR1 como TAILWINDTRADERS\\Administrator con la contraseña: `Pa55w.rdPa55w.rd`.
2.  En Administrador de servidores, selecciona el menú Administrar y después **Agregar roles y características**.
3.  En la página Antes de comenzar del Asistente para agregar roles y funciones, haz clic en **Siguiente**.
4.  En la página **Seleccionar tipo de instalación**, selecciona la instalación basada en características o en roles y haz clic en **Siguiente**.
5.  En la página Seleccionar servidor de destino, elige **Seleccionar un servidor del grupo de servidores**, asegúrate de que TAILWIND-MBR1 está seleccionado y haz clic en **Siguiente**.
6.  En la página Seleccionar roles de servidor, selecciona la casilla **Servicios de dominio de Active Directory**. Se abrirá la página Agregar características. Seleccione **Agregar características**. Haga clic en **Next**.
7.  En la página Seleccionar características, haga clic en **Siguiente**.
8.  En la página Servicios de dominio de Active Directory, haz clic en **Siguiente**.
9.  En la página Confirmar selecciones de instalación, haga clic en **Instalar**. Dependiendo de la velocidad del equipo, la instalación puede tardar varios minutos. Una vez completada la instalación, haga clic en **Cerrar**.
10. En el menú Administrador del servidor, selecciona el icono de notificación situado junto a la marca en la esquina superior derecha (como se muestra en la captura de pantalla).

    ![Captura de pantalla del menú administrador del servidor con el icono de alerta mostrado.](./Media/server-manager-menu.png)
13. En el menú que se abre al seleccionar el icono de notificación, selecciona **Promover este servidor a un controlador de dominio**. Esto iniciará el Asistente para configuración de Servicios de dominio de Active Directory.
14. En la página Configuración de implementación, selecciona **Agregar un controlador de dominio a un dominio existente** y asegúrate de que el nombre de dominio está establecido en **tailwindtraders.internal**.
15. Debes volver a autenticar la cuenta de administrador. Seleccione **Cambiar**. Escribe `Administrator` en el nombre de usuario y `Pa55w.rdPa55w.rd` en la contraseña. Haga clic en **OK**. Haga clic en **Next**.
16. En la página Opciones del controlador de dominio, acepta la configuración predeterminada y proporciona la contraseña del modo de restauración de servicios de directorio (DSRM). Para ello, escribe dos veces la siguiente contraseña: `Pa55w.rdPa55w.rd`. Haga clic en **Next**.
17. En la página Opciones de DNS, haz clic en **Siguiente**.
18. En la página Opciones adicionales, haz clic en **Siguiente**.
19. En la página Rutas de acceso, haz clic en **Siguiente**.
20. En la página Revisar opciones, haz clic en **Siguiente**.
21. En la página Comprobación de requisitos previos, haz clic en **Instalar**. La instalación tardará varios minutos en función de la velocidad de la máquina virtual. La máquina virtual se reiniciará.
22. Cuando se reinicie la máquina virtual, inicia sesión como `tailwindtraders\administrator` con la contraseña que has configurado para la cuenta de administrador predeterminada (`Pa55w.rdPa55w.rd`).

## Transferir roles de operaciones de maestro único flexible

En esta tarea, transferirás el rol maestro RID de TAILWIND-DC1 a TAILWIND-MBR1. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-MBR1, en **Herramientas**, abre Usuarios y equipos de Active Directory.<br>
2.  En el panel de navegación, haz clic con el botón derecho en Usuarios y equipos de Active Directory, apunta a **Todas las tareas** y después selecciona **Maestros de operaciones**.
3.  En la pestaña RID, selecciona **Cambiar**, elige **Sí** y después pulsa **Aceptar**.
4.  Haz clic en **Cerrar** para cerrar el cuadro de diálogo Maestros de operaciones.

## Cree un sitio de Active Directory y configure una subred para ese sitio

En esta tarea, se crea un sitio de Active Directory y se configura una subred asociada a dicho sitio. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, inicia sesión como `tailwindtraders\administrator` con la contraseña que has configurado para la cuenta de administrador predeterminada (`Pa55w.rdPa55w.rd`).
2.  Abre Sitios y servicios de Active Directory en el menú Herramientas.
3.  Haz clic con el botón derecho del ratón en Sitios, selecciona **Nuevo sitio** y escribe `Sydney` en nombre del sitio.
4.  Para el Nombre de vínculo, selecciona DEFAULTIPSITELINK y haz clic dos veces en **Aceptar**.
5.  Expanda la carpeta **Sitios** .
6.  Haga clic con el botón derecho del ratón en **Subredes** y seleccione **Nueva subred**.
7.  Como prefijo, escribe `172.16.1.0/24`, selecciona **Sydney** como nombre del sitio y haz clic en **Aceptar**.
8.  Cierre Sitios y servicios de Active Directory.
