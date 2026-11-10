# 🌸 AGENDA SIMPLE V2 | CLIENT & APPOINTMENT MANAGEMENT SYSTEM

<p align="center">
  <img src="https://img.shields.io/badge/PYTHON-Django-092E20?style=for-the-badge&logo=django&logoColor=white" />
  <img src="https://img.shields.io/badge/DATABASE-MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white" />
  <img src="https://img.shields.io/badge/FRONTEND-HTML5%20%7C%20CSS3%20%7C%20JS-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
  <img src="https://img.shields.io/badge/VERSION-V2-EC8DB5?style=for-the-badge" />
</p>

<p align="center">
  <b>Una aplicación web para organizar clientes y administrar citas de manera sencilla.</b>
  <br/>
  Desarrollada con Python, Django y MariaDB, con una interfaz personalizada de estilo Pinklatte.
</p>

---

## ◈ 01. SOBRE EL PROYECTO

**Agenda Simple V2** es un sistema web desarrollado con Python y Django, diseñado para facilitar la administración de clientes y la programación de citas desde una plataforma centralizada.

El proyecto permite registrar información personal de los clientes, consultar sus datos, realizar búsquedas, actualizar registros y administrar citas relacionadas con cada cliente.

Cuenta con un sistema de autenticación para controlar el acceso a las secciones principales y una interfaz personalizada con temática visual **Pinklatte**, que incorpora colores pastel, modo claro y oscuro, tarjetas de contenido y elementos adaptables a diferentes tamaños de pantalla.

Su objetivo es ofrecer una herramienta práctica, organizada y fácil de utilizar para gestionar información y mantener un mejor control de las actividades programadas.

## ◈ 02. CARACTERÍSTICAS PRINCIPALES

### 👥 Gestión de clientes

- Registrar nuevos clientes con sus datos personales.
- Consultar el listado de clientes registrados.
- Buscar clientes por nombre, apellido o DNI.
- Editar y actualizar la información existente.
- Eliminar registros cuando no tengan citas relacionadas.
- Validar el correo electrónico y los datos obligatorios.
- Evitar registros duplicados mediante la restricción de DNI único.

### 📅 Gestión de citas

- Asociar citas con clientes registrados.
- Registrar asunto, fecha y hora.
- Administrar información de dirección, referencia y notas desde el modelo.
- Contemplar los estados: Pendiente, Confirmada, Completada y Cancelada.
- Consultar y buscar citas por información del cliente, asunto y estado.
- Ordenar las citas cronológicamente.
- Editar y eliminar registros.

**Nota técnica:** el backend contiene la lógica de gestión de citas, pero el formulario actual requiere ajustes de integración para completar correctamente el registro desde la interfaz.

### 🔐 Autenticación y acceso

- Inicio de sesión mediante el sistema de autenticación de Django.
- Protección de las vistas principales mediante `login_required`.
- Cierre de sesión mediante formulario POST.
- Protección CSRF en los formularios.

### 🎨 Interfaz Pinklatte

- Diseño personalizado con colores pastel.
- Modo claro y modo oscuro.
- Tarjetas con bordes redondeados.
- Botones diferenciados según su función.
- Tipografía Plus Jakarta Sans.
- Favicon personalizado.
- Diseño adaptable para dispositivos móviles.

## ◈ 03. TECNOLOGÍAS UTILIZADAS

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,django,mysql,html,css,js,git,github" />
</p>

| Tecnología | Aplicación |
|:---|:---|
| Python | Lenguaje principal del backend. |
| Django 6.x | Framework para desarrollar la aplicación web. |
| MariaDB 11.8 | Motor de base de datos configurado para el proyecto. |
| mysqlclient | Conector entre Python y la base de datos. |
| HTML5 | Estructura de las páginas web. |
| CSS3 | Estilos, colores y diseño adaptable. |
| JavaScript | Interacciones de la interfaz. |
| Google Fonts | Tipografía Plus Jakarta Sans. |
| Git | Control de versiones. |
| GitHub | Repositorio y almacenamiento del código fuente. |

**Dependencias declaradas en `requirements.txt`:**

```text
Django>=6.0,<7.0
mysqlclient>=2.2
```

## ◈ 04. ARQUITECTURA Y ESTRUCTURA DEL PROYECTO

El proyecto está organizado mediante una estructura modular de Django, separando modelos, vistas, rutas, plantillas y archivos estáticos.

```text
agenda_simple_v2/
│
├── apps/
│   │
│   ├── migrations/
│   │   └── 0001_initial.py
│   │
│   ├── models/
│   │   ├── Cliente.py
│   │   ├── Cita.py
│   │   └── __init__.py
│   │
│   ├── static/
│   │   └── control/
│   │       ├── css/
│   │       │   └── style.css
│   │       ├── js/
│   │       │   └── app.js
│   │       └── img/
│   │           └── gatito.png
│   │
│   ├── templates/
│   │   ├── control/
│   │   │   ├── base.html
│   │   │   ├── inicio.html
│   │   │   ├── login.html
│   │   │   ├── clientes.html
│   │   │   ├── registrar_cliente.html
│   │   │   └── citas.html
│   │   │
│   │   └── index.html
│   │
│   ├── admin.py
│   ├── apps.py
│   ├── urls.py
│   ├── views.py
│   └── tests.py
│
├── config/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── .gitignore
├── manage.py
├── README.md
└── requirements.txt
```

### Organización de los componentes

- **apps/models/:** define las estructuras y relaciones de la base de datos.
- **apps/views.py:** contiene la lógica de procesamiento y gestión de clientes y citas.
- **apps/urls.py:** establece las rutas de los módulos principales.
- **apps/templates/:** almacena las interfaces HTML del sistema.
- **apps/static/:** contiene recursos CSS, JavaScript e imágenes.
- **config/:** almacena la configuración general del proyecto Django.
- **manage.py:** permite ejecutar comandos administrativos y gestionar el proyecto.

## ◈ 05. DISEÑO DE LA BASE DE DATOS

El sistema trabaja con dos modelos principales relacionados entre sí.

### Tabla: clientes

| Campo | Descripción |
|:---|:---|
| id | Identificador principal. |
| nombre | Nombre del cliente. |
| apellido | Apellido del cliente. |
| correo | Correo electrónico. |
| dni | Documento de identidad único. |
| telefono | Teléfono opcional. |
| created_at | Fecha de creación. |
| updated_at | Fecha de actualización. |

### Tabla: citas

| Campo | Descripción |
|:---|:---|
| id | Identificador principal. |
| cliente_id | Referencia al cliente relacionado. |
| asunto | Motivo de la cita. |
| fecha | Fecha programada. |
| hora | Hora programada. |
| direccion | Dirección de la cita. |
| referencia | Referencia adicional. |
| notas | Información complementaria. |
| estado | Estado actual de la cita. |
| created_at | Fecha de creación. |
| updated_at | Fecha de actualización. |

### Relación entre modelos

```text
       CLIENTES
          │
          │ 1
          │
          │
          │ N
          ▼
         CITAS
```

Un cliente puede tener múltiples citas, pero cada cita está asociada a un único cliente.

Se utiliza `ForeignKey` con `on_delete=models.PROTECT` para proteger los registros relacionados y evitar la eliminación de clientes que todavía tengan citas.

## ◈ 06. INSTALACIÓN Y EJECUCIÓN

### Requisitos previos

Antes de ejecutar el proyecto, asegúrate de tener instalado:

- Python 3.12 o superior.
- MariaDB.
- Git.
- Visual Studio Code (recomendado).

### Paso 1. Clonar el repositorio

```bash
git clone https://github.com/landisperez21-alt/agenda_simple_v2.git
```

### Paso 2. Ingresar al directorio

```bash
cd agenda_simple_v2
```

### Paso 3. Crear un entorno virtual

```bash
python -m venv .venv
```

### Paso 4. Activar el entorno virtual

En Windows PowerShell:

```powershell
.venv\Scripts\activate
```

### Paso 5. Instalar las dependencias

```bash
pip install -r requirements.txt
```

### Paso 6. Configurar MariaDB

Inicia el servicio de MariaDB y crea la base de datos:

```sql
CREATE DATABASE agenda_simple_v2_db
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

Verifica las credenciales de conexión en:

```text
config/settings.py
```

Configura el usuario, contraseña, host y puerto según tu instalación local de MariaDB.

### Paso 7. Ejecutar las migraciones

```bash
python manage.py makemigrations
python manage.py migrate
```

### Paso 8. Crear un usuario administrador

```bash
python manage.py createsuperuser
```

Completa los datos solicitados para crear tus credenciales de acceso.

### Paso 9. Iniciar el servidor

```bash
python manage.py runserver
```

### Paso 10. Abrir el sistema

Ingresa desde tu navegador:

http://127.0.0.1:8000/

## ◈ 07. RUTAS PRINCIPALES DEL SISTEMA

| Ruta | Función |
|:---|:---|
| `/` | Panel principal. |
| `/login/` | Inicio de sesión. |
| `/logout/` | Cierre de sesión. |
| `/clientes/` | Gestión y consulta de clientes. |
| `/citas/` | Gestión y consulta de citas. |
| `/admin/` | Administración de Django. |

Las secciones principales requieren autenticación.

## ◈ 08. VALIDACIONES Y SEGURIDAD

El proyecto incorpora mecanismos para mejorar la integridad de la información:

- Validación de campos obligatorios.
- Verificación del formato del correo electrónico.
- Validación del DNI de ocho dígitos.
- Restricción de DNI duplicados.
- Control de longitudes máximas.
- Protección de registros relacionados mediante `PROTECT`.
- Protección CSRF en formularios POST.
- Autenticación mediante Django.
- Restricción de acceso a vistas privadas.

**Consideración:** antes de desplegar el sistema en producción, se deben proteger las claves y credenciales mediante variables de entorno, desactivar DEBUG y configurar correctamente los hosts permitidos.

## ◈ 09. PROPÓSITO DEL PROYECTO

Los objetivos principales de Agenda Simple V2 son:

- **Organización:** centralizar la información de los clientes en una sola plataforma.
- **Administración:** facilitar el registro, consulta, actualización y eliminación de clientes.
- **Agendamiento:** organizar las citas mediante fechas, horas y clientes relacionados.
- **Integridad:** mantener relaciones consistentes entre los registros de clientes y citas.
- **Accesibilidad:** ofrecer una interfaz intuitiva con una identidad visual personalizada.
- **Seguridad:** controlar el acceso a las funciones principales mediante autenticación.

## ◈ 10. AUTOR Y DESARROLLADOR

<p align="center">
  <b>LANDIS SANCHEZ PEREZ</b>
  <br/>
  Desarrollador de software | Estudiante de Ingeniería de Software con Inteligencia Artificial
  <br/><br/>
  <a href="https://github.com/landisperez21-alt">
    <img src="https://img.shields.io/badge/GitHub-landisperez21--alt-181717?style=for-the-badge&logo=github" />
  </a>
</p>

---

<p align="center">
  <b>BUILDING IDEAS THROUGH TECHNOLOGY.</b>
  <br/>
  <sub>Software Development · Database Management · Web Applications</sub>
  <br/><br/>
  🌸 Agenda Simple V2 — 2026
</p>