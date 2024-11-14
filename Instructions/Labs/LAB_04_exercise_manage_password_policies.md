---
lab:
  title: 'Ejercicio: Administración de directivas de contraseña'
  module: Guided Project – Administer Active Directory Domain Services
---
En este ejercicio, configurará elementos de directiva de grupo relacionados con las directivas de contraseña. Esto incluye la configuración de la directiva de contraseñas de dominio, la creación de una directiva de contraseña más estricta para el grupo Administradores de dominio y la habilitación de la Papelera de reciclaje de Active Directory.

## Configuración de la directiva de contraseñas de dominio

En esta tarea, configurarás la directiva de contraseñas de dominio. Para completar la tarea, realiza los siguientes pasos:

1.  En TAILWIND-DC1, en el menú Herramientas de la consola de Administrador de servidores, abre la consola de administración de directivas de grupo.
2.  En la consola de administración de directivas de grupo, expande el bosque tailwindtraders.internal, la carpeta Dominios y el dominio tailwindtraders.internal.
3.  Haga clic con el botón derecho en **Directiva predeterminada de dominio ** y, después, haga clic en **Editar**.
4.  En el Editor de administración de directivas de grupo, ve a Configuración del equipo\\Directivas\\Configuración de Windows\\Configuración de seguridad\\Directivas de cuenta\\Directiva de contraseñas.
5.  Haz doble clic en el elemento de directiva **Longitud mínima de contraseña**.
6.  Cambia el número mínimo de caracteres a `14`.
7.  Haz clic en **Aceptar** y después cierra la ventana del Editor de administración de directivas de grupo.
8.  Cierre la consola de Administración de directivas de grupo.

## Configuración de una directiva de contraseña específica

En esta tarea, configurarás una directiva de contraseña específica y la aplicarás al grupo Administradores de dominio. Para completar esta tarea, realiza los siguientes pasos en TAILWIND-DC1:

1.  En el menú Herramientas de la consola Administrador de servidores, abre el Centro de administración de Active Directory.
2.  En Información general, haz clic en **Tailwindtraders (local)**.
3.  En el panel tailwindtraders (local), abre el contenedor Sistema.
4.  En el contenedor Sistema, abre el contenedor Configuración de contraseña.
5.  Haz clic con el botón derecho en el contenedor de Configuración de contraseñas, haz clic en **Nuevo,** y después haz clic en **Configuración de contraseñas**.
6.  En el campo Name (Nombre), escriba `Domain Admin Password Policy`.
7.  Establece el campo Precedencia en `1`.
8.  Establece la longitud mínima de contraseña en `16`.
9.  Haga clic en **OK**.
10. Abre la nueva directiva **Directiva de contraseñas de administradores de dominio**.
11. En la sección Directamente se aplica a, haz clic en **Agregar,** y después escribe `Domain Admins`. Haz clic en **Comprobar nombres** y haz clic en **Aceptar**.
12. Haga clic en **OK**.

## Habilitación de Papelera de reciclaje de Active Directory

En esta tarea, se habilita la Papelera de reciclaje de Active Directory. Para completar esta tarea, realiza los siguientes pasos en TAILWIND-DC1:

1.  En el menú Herramientas de la consola Administrador de servidores, abre el Centro de administración de Active Directory.
2.  Haz clic en **Tailwindtraders (local)** en el panel izquierdo.
3.  En el panel derecho, selecciona **Habilitar papelera de reciclaje**.
4.  Haz clic en **Aceptar** para descartar la advertencia.
5.  Haz clic en **Aceptar** para descartar la advertencia sobre la latencia de replicación.
