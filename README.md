# Registro Institucional de Bomberos — Carelmapu

Aplicación web para la Tercera Compañía de Bomberos de Carelmapu. Interfaz HTML/CSS/JavaScript, backend Google Apps Script, almacenamiento en Google Sheets y fotografías en Google Drive.

## Funcionalidades
- Inicio de sesión y roles: Administrador, Oficial y Consulta.
- Hoja de vida individual con fotografía, datos personales, contactos, tipo, situación, código radial y cargo.
- Historial académico: Bombero Inicial, Bombero Operativo, Bombero Profesional y Especialidad.
- Material asignado, estado, identificación y devolución.
- Cargos institucionales solicitados.
- Registro general con búsqueda y filtros.
- Exportación del registro general a Excel y PDF.
- Hoja de vida en PDF con datos, historial académico y material a cargo.
- Tema verde claro y alternancia a tema azul.
- Diseño responsive para escritorio, tablet y móvil.
- Auditoría básica de acciones.

## Instalación en Google Apps Script
1. Crea una hoja de cálculo nueva en Google Sheets.
2. En esa hoja, abre **Extensiones → Apps Script**.
3. Sustituye el contenido de `Code.gs` por el archivo `Code.gs` incluido.
4. Pulsa **+ → HTML** y crea el archivo con el nombre exacto `Index`. Pega el contenido de `Index.html`.
5. Guarda y selecciona la función `setup` en el menú superior. Pulsa **Ejecutar** y autoriza los permisos solicitados. La primera ejecución crea las pestañas `Bomberos`, `Academico`, `Material`, `Usuarios` y `Auditoria`, además de una carpeta de Drive para fotografías.
6. Implementa mediante **Implementar → Nueva implementación → Aplicación web**. Selecciona **Ejecutar como: yo**. Elige quién puede acceder según las reglas de tu institución; evita acceso público si la política institucional no lo autoriza.
7. Abre la URL de la aplicación.

### Acceso inicial
- Usuario: `admin`
- Contraseña temporal: `Cambiar123!`

Inicia sesión y cambia inmediatamente la contraseña desde **Preferencias → Cambiar contraseña**. Después, crea usuarios para los demás integrantes desde **Usuarios y permisos**.

## Roles
- **Administrador:** gestión de usuarios y permisos, creación/edición de registros y eliminación de integrantes.
- **Oficial:** creación y edición de hojas de vida, formación y material; no puede administrar usuarios ni eliminar integrantes.
- **Consulta:** visualización y exportación, sin cambios.

## Importante antes de usar en producción
- Los datos de hoja de vida, RUT, teléfonos, fotografías y contactos de emergencia son datos personales. Limita el acceso a cuentas autorizadas y define un responsable institucional.
- Las fotografías se guardan en Drive. El código intenta compartirlas con acceso de enlace dentro del dominio; si la cuenta es Gmail personal, revisa esa configuración y el acceso efectivo a las fotos.
- El login es una capa de aplicación sencilla. Para uso institucional de alta exigencia, se recomienda autenticar mediante cuentas de Google Workspace, limitar el despliegue al dominio y revisar las políticas de seguridad y retención.
- Exportar a PDF/Excel requiere conexión a Internet para cargar las bibliotecas jsPDF y SheetJS desde CDN.
- La interfaz necesita que Apps Script esté configurado y desplegado para guardar datos. No es una base de datos local ni una aplicación autónoma al abrir el HTML directamente.
- Los cargos y categorías están precargados según el requerimiento entregado; el administrador institucional debe validar denominaciones, procedimientos y permisos antes de la puesta en marcha.

## Archivos
- `Code.gs`: API y lógica de Google Apps Script.
- `Index.html`: aplicación web completa con HTML, CSS y JavaScript.
