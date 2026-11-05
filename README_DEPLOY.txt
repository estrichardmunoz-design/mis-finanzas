MIS FINANZAS WEB — PUBLICACIÓN Y ONEDRIVE

QUÉ INCLUYE
- App web adaptable a celular y computador.
- Instalación como acceso directo/PWA desde el navegador.
- Inicio de sesión con Microsoft.
- Sincronización automática con Apps/Mis Finanzas en el OneDrive de la cuenta institucional.
- Alcance previsto: Files.ReadWrite.AppFolder (solo la carpeta de esta app). No se conecta a cuentas bancarias.

IMPORTANTE: este paquete todavía no tiene los identificadores de tu organización ni una dirección web publicada. Por eso no puede iniciar sesión ni sincronizar hasta completar los pasos siguientes. No contiene contraseñas ni secretos.

PUBLICAR EL CÓDIGO (opción sugerida: GitHub Pages)
1. Crea un repositorio público en GitHub llamado mis-finanzas. El repositorio contendrá el código de la app, nunca los movimientos financieros.
2. Sube el contenido de esta carpeta a la raíz del repositorio.
3. Activa GitHub Pages para la rama principal y copia la dirección HTTPS que genera. Esa será la dirección actualizada para PC y celular. Cada actualización del código publicada en el repositorio se verá en esa misma dirección.

REGISTRAR EL ACCESO A ONEDRIVE
4. Entra al centro de administración de Microsoft Entra con tu cuenta institucional y registra una aplicación para “Cuentas de este directorio organizativo solamente”. Si la universidad no permite registrar apps personales, soporte TI debe hacerlo o aprobarlo.
5. En “Autenticación”, agrega una plataforma “Aplicación de página única (SPA)” con la URL HTTPS de GitHub Pages.
6. En “Permisos de API”, agrega Microsoft Graph → Delegados → Files.ReadWrite.AppFolder. Solicita consentimiento administrativo si la universidad lo exige. No concedas Files.ReadWrite.All ni permisos amplios a todo OneDrive.
7. Copia el ID de aplicación y el ID de directorio (tenant) en config.js. Publica ese cambio. Esos dos identificadores no son contraseñas; no introduzcas secretos en una app de navegador.

LLEVAR LOS DATOS EXISTENTES
8. En la versión local que tiene tus movimientos, pulsa “Respaldo” y guarda el JSON.
9. Abre la URL publicada en el PC, entra a Movimientos → Restaurar respaldo, selecciona ese JSON y luego pulsa “Conectar OneDrive”. Inicia sesión con est.richard.munoz@unimilitar.edu.co.
10. Abre la misma URL en el celular, conéctate con la misma cuenta y se cargarán los movimientos. Los cambios se guardan localmente y se envían a OneDrive; al abrir o volver a la app, sincroniza con la nube.
11. Para instalarla en la pantalla de inicio del celular, abre el menú del navegador y elige “Agregar a pantalla de inicio” o “Instalar app”.

La app sincroniza las transacciones en un archivo de datos de su carpeta privada de OneDrive. La URL pública distribuye únicamente el código. Si el tenant institucional bloquea el consentimiento de Files.ReadWrite.AppFolder o el hosting público, soporte TI deberá autorizar esa configuración.
