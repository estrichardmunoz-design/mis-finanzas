MIS FINANZAS — PUBLICAR Y CONECTAR DESDE CELULAR Y COMPUTADOR

Esta copia utiliza Firebase Spark para guardar los movimientos en línea con una cuenta de correo y contraseña. La misma página se abrirá en ambos dispositivos. La versión anterior no se modifica. Los archivos de la app son públicos en GitHub Pages; cada usuario solo puede leer y modificar sus propios movimientos porque las reglas separan la información por UID.

ANTES DE EMPEZAR
- Se necesita una cuenta Google para abrir Firebase Console y una cuenta GitHub para publicar el código.
- No se requiere tarjeta para permanecer en el plan Spark. No pulses actualizar a Blaze ni vincules facturación.
- Firebase Spark tiene límites gratuitos; si se exceden, el servicio puede pausarse hasta el siguiente ciclo. Consulta https://firebase.google.com/pricing/.
- La cuenta y contraseña que crearás dentro de Mis Finanzas pueden ser un correo personal. No son la clave de Google. Usa una contraseña distinta.
- Nunca publiques contraseñas ni claves de cuenta de servicio. config.js solo lleva la configuración web pública de Firebase.

PASO 1 — CREAR PROYECTO FIREBASE
1. Abre https://console.firebase.google.com/ e inicia sesión con tu cuenta Google.
2. Pulsa “Crear un proyecto” o “Añadir proyecto”. Ponle un nombre sencillo, por ejemplo mis-finanzas-richard.
3. Si pregunta por Google Analytics, puedes dejarlo desactivado para esta app. Continúa y espera a que termine.
4. Mantén el plan Spark gratuito. No agregues facturación.

PASO 2 — REGISTRAR LA APP WEB Y COPIAR CONFIGURACIÓN
1. En el proyecto, pulsa el engranaje junto a “Descripción general del proyecto” → “Configuración del proyecto”.
2. En “Tus aplicaciones”, pulsa el símbolo </> (Web). Nombre: Mis Finanzas. No marques Hosting; la página se publicará en GitHub Pages.
3. Pulsa “Registrar app”. Firebase mostrará un bloque firebaseConfig con apiKey, authDomain, projectId, appId y otros valores.
4. Abre config.js en el repositorio de GitHub y reemplaza los cuatro textos PEGA_AQUI... por los valores exactos de firebaseConfig. Ejemplo: apiKey: "valor", authDomain: "nombre.firebaseapp.com", projectId: "nombre", appId: "1:...:web:...". Conserva las comas y comillas. No copies claves privadas ni datos de cuentas de servicio.
5. Guarda el cambio en GitHub (Commit changes).

PASO 3 — HABILITAR CUENTAS DE CORREO
1. En Firebase, abre “Compilación” → “Authentication” → “Comenzar” si aparece.
2. Abre “Método de acceso” o “Sign-in method”.
3. Selecciona “Correo electrónico/Contraseña”, habilita la primera opción y pulsa “Guardar”. No hace falta habilitar enlaces por correo.

PASO 4 — CREAR BASE Y PROTEGERLA
1. Abre “Compilación” → “Firestore Database” → “Crear base de datos”.
2. Selecciona “Modo de producción”, región cercana disponible y crea la base. La región no se puede cambiar después; elige una de América si está disponible.
3. Abre la pestaña “Reglas”. Reemplaza todo el texto por el contenido del archivo firestore.rules de esta carpeta y pulsa “Publicar”.
4. Esas reglas solo permiten acceso autenticado al espacio de datos cuyo UID coincide con la cuenta conectada. No uses reglas abiertas como `allow read, write: if true`.

PASO 5 — PERMITIR LA DIRECCIÓN DE GITHUB PAGES
1. En GitHub, publica todo el contenido de esta carpeta en la raíz del repositorio mis-finanzas y activa Settings → Pages → Deploy from a branch → main → /(root) → Save.
2. Espera a que GitHub Pages indique que el sitio está publicado. La dirección suele ser https://estrichardmunoz-design.github.io/mis-finanzas/.
3. En Firebase Authentication → Settings → Authorized domains, agrega estrichardmunoz-design.github.io (solo dominio, sin https ni ruta). Guarda si lo solicita.

PASO 6 — USAR EN LOS DOS EQUIPOS
1. Abre la dirección publicada en el PC. Pulsa “Conectar nube” → “Crear cuenta”. Escribe correo y crea una contraseña de al menos seis caracteres. Anótala en un lugar seguro.
2. Si ya tenías movimientos en la versión anterior: en esa app pulsa “Respaldo” para descargar el JSON. En la app Firebase abre “Movimientos” → “Restaurar respaldo”, selecciona el archivo JSON. Después inicia sesión para subirlos.
3. En el celular abre exactamente la misma dirección publicada e inicia sesión con el mismo correo y contraseña. Los movimientos deberán aparecer. Usa “Sincronizar” si necesitas solicitar actualización manual.
4. Para tener un icono, abre el menú del navegador y elige “Agregar a pantalla principal” o “Instalar”. No abras el archivo HTML directamente desde OneDrive: esa copia no comparte base con la página en línea.
5. Descarga Excel desde “Descargar Excel”. También puedes descargar un respaldo JSON desde “Respaldo”. Guarda los respaldos en OneDrive si quieres conservar una copia.

ACTUALIZAR EL PROGRAMA
Cuando se modifique la app, sube los archivos nuevos al mismo repositorio de GitHub. La dirección no cambia. Los movimientos se guardan en Firebase, por eso una actualización del código no debe borrar la base.

Si algo no coincide, envíame una captura de la pantalla (sin mostrar contraseñas ni códigos) y te indico el siguiente paso.
