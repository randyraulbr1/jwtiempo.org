# JW Tiempo - Sistema de Reportes de Predicación

## Descripción del Proyecto

JW Tiempo es un sistema web completo diseñado para gestionar los reportes de predicación de congregaciones de Testigos de Jehová. Permite a los publicadores reportar sus horas de predicación mensualmente y a los ancianos administrar y visualizar las estadísticas de la congregación.

## Características Principales

- **Registro y Autenticación**: Sistema seguro de registro e inicio de sesión para publicadores y ancianos
- **Reportes Mensuales**: Los publicadores pueden enviar sus reportes de predicación con horas, estado y notas
- **Panel de Administración**: Los ancianos pueden ver estadísticas, filtrar por mes/año y gestionar reportes
- **Gestión de Precursores**: Identificación y seguimiento especial de precursores regulares
- **Cierre de Mes**: Función para cerrar automáticamente el mes actual marcando como "no reportó" a quienes no enviaron su reporte
- **Historial de Reportes**: Visualización de los últimos 6 meses de reportes
- **Diseño Responsive**: Interfaz adaptada para dispositivos móviles y de escritorio
- **Estadísticas en Tiempo Real**: Contadores de publicadores, reportes, precursores y horas totales

## Tecnologías Utilizadas

- **HTML5**: Estructura semántica y moderna
- **CSS3**: Estilos avanzados con variables CSS, gradientes y animaciones
- **JavaScript (ES6+)**: Programación moderna con async/await y módulos
- **Firebase Authentication**: Autenticación segura de usuarios
- **Firebase Realtime Database**: Base de datos en tiempo real para almacenar reportes y usuarios

## Instrucciones de Instalación

1. Descarga o clona todos los archivos del proyecto en una carpeta local
2. Asegúrate de tener una conexión a Internet (se requiere para cargar Firebase SDK)
3. Abre `index.html` en un navegador web moderno (Chrome, Firefox, Edge, Safari)
4. No se requiere servidor local, los archivos pueden abrirse directamente desde el sistema de archivos

## Uso del Sistema

### Para Publicadores

1. **Registro**: Accede a "Registrarse" desde la página principal y completa el formulario con tus datos
2. **Inicio de Sesión**: Usa tu correo electrónico y contraseña para acceder
3. **Enviar Reporte**: Cada mes, completa el formulario indicando si predicaste, las horas trabajadas y cualquier nota adicional
4. **Ver Historial**: Consulta tus reportes de los últimos 6 meses

### Para Ancianos (Administradores)

1. **Registro de Admin**: Solicita acceso como administrador y regístrate con el formulario de anciano
2. **Inicio de Sesión**: Accede con tus credenciales de administrador
3. **Panel de Control**: 
   - Selecciona el año y mes que deseas consultar
   - Visualiza estadísticas generales
   - Revisa las tablas de publicadores y precursores
   - Cierra el mes actual cuando sea necesario

## Estructura de Archivos

```
jwtiempo.org/
├── index.html                  # Página principal
├── publicador-login.html       # Login para publicadores
├── publicador-registro.html    # Registro de publicadores
├── publicador-reporte.html     # Formulario de reporte
├── admin-login.html            # Login para administradores
├── admin-registro.html         # Registro de administradores
├── admin.html                  # Panel de administración
├── styles.css                  # Estilos globales
└── README.md                   # Este archivo
```

## Seguridad

- Autenticación mediante Firebase Authentication
- Verificación de permisos de administrador
- Validación de formularios en cliente
- Protección de rutas sensibles

## Autor

Congregación JW

## Licencia

Privado - Uso exclusivo para congregaciones de Testigos de Jehová
