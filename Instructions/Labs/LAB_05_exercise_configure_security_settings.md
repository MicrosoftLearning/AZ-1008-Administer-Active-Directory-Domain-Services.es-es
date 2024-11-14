---
lab:
  title: 'Ejercicio: Configuración de las opciones de seguridad'
  module: Guided Project – Administer Active Directory Domain Services
---
En este ejercicio, configure los parámetros relacionados con la seguridad, incluida la deshabilitación de la autenticación NTLM para las cuentas de dominio, la auditoría de la actividad de administración de cuentas y la denegación del inicio de sesión como servicio para los miembros de un grupo de seguridad.

## Restricción de la autenticación NTLM

En esta tarea, restringirás la autenticación NTLM. Para completar esta tarea, realiza los siguientes pasos en TAILWIND-DC1:

1.  En el menú Herramientas de la consola de Administrador del servidor, abre la consola de administración de directivas de grupo.
2.  En la consola de administración de directivas de grupo, expande el bosque tailwindtraders.internal, la carpeta Dominios y el dominio tailwindtraders.internal. Después, expande Objetos de directiva de grupo.
3.  Haz clic con el botón derecho del ratón en **Directiva predeterminada de controladores de dominio** y haz clic en **Editar**.
4.  Ve a Configuración del equipo\\Directivas\\Configuración de Windows\\Configuración de seguridad\\Directivas locales\\Opciones de seguridad.
5.  Selecciona y haz doble clic en **Seguridad de red: restringir NTLM: autenticación NTLM en este dominio**.
6.  Haz clic en la casilla **Definir esta configuración de directiva**.
7.  Selecciona el valor **Denegar todo** y haz clic en **Aceptar**.
8.  Haz clic en **Sí** en el cuadro de diálogo Confirmar cambio de configuración.
9.  Cierre el Editor de administración de directivas de grupo.

## Auditar la administración de cuentas de usuario en Sídney

En esta tarea, habilitarás la auditoría de la administración de cuentas de usuario en la unidad organizativa Sydney. Para completar esta tarea, realiza los siguientes pasos en TAILWIND-DC1:

1.  En el menú Herramientas de la consola de Administrador del servidor, elige Consola de administración de directivas de grupo.
2.  En la Consola de administración de directivas de grupo, expande el dominio Tailwindtraders.internal.
3.  Navega hasta la unidad organizativa Sydney, haz clic con el botón derecho y selecciona **Crear un GPO en este dominio y enlazarlo aquí...**.
4.  Asigna al nuevo GPO el nombre `SydneyOUPolicy`.
5.  Haga clic en **Aceptar**
6.  Haz clic con el botón derecho en SydneyOUPolicy y selecciona **Editar**.
7.  Ve a Configuración del equipo\\Directivas\\Configuración de Windows\\Configuración de seguridad\\Configuración avanzada de directivas de auditoría\\Directivas de auditoría\\Administración de cuentas.
8.  Selecciona y haz doble clic en **Auditar administración de cuentas de usuario**.
9.  Haz clic en la casilla **Configurar los siguientes eventos de auditoría**.
10.  Selecciona los valores **Correcto** y **Error** y haz clic en **Aceptar**.
11.  Cierra el Editor de administración de directivas de grupo

## Denegar inicio de sesión como servicio

En esta tarea, configurarás la opción de seguridad Denegar inicio de sesión como servicio. Para completar esta tarea, realiza los siguientes pasos en TAILWIND-DC1:

1.  En el menú Herramientas de la consola de Administrador del servidor, abre la consola de administración de directivas de grupo.
2.  Expande el dominio Tailwindtraders.internal.
3.  Ve a la unidad organizativa Sydney y haz clic con el botón derecho en SydneyOUPolicy. Seleccione **Editar**.
4.  Ve a Configuración del equipo\\Directivas\\Configuración de Windows\\Configuración de seguridad\\Directivas locales\\Asignación de derechos de usuario.
5.  Selecciona y haz doble clic en la directiva **Denegar inicio de sesión como servicio**.
6.  Selecciona la opción **Definir esta directiva**.
7.  Haga clic en **Agregar grupo o usuario**.
8.  Haz clic en **Buscar**, en **Avanzado** y después en **Buscar ahora**.
9.  Selecciona el grupo **Administradores de Sydney**.
10. Haz clic en **Aceptar** hasta que se cierren los cuadros de diálogo (puede requerir cuatro o cinco confirmaciones).
