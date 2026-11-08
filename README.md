# 🌸 Agenda Simple V2

Sistema web desarrollado con **Django** y base de datos **MariaDB**, diseñado bajo una temática visual **"pinklatte"** (tonos suaves pastel, soporte para modo claro y oscuro, y un favicon personalizado).

---

## ✨ Características Principales
- **Gestión de Clientes:** Permite registrar, editar, buscar y eliminar información de clientes de forma independiente.
- **Gestión de Citas:** Permite programar, verificar fechas/horas y administrar citas asociadas a los clientes.
- **Diseño Aesthetic Pinklatte:** Interfaz limpia y moderna con paleta de colores personalizados en modo claro y modo oscuro.
- **Autenticación Segura:** Control de acceso mediante login y cierre de sesión integrado.

---

## 🛠️ Tecnologías Utilizadas
- **Backend:** Python & Django 6.x
- **Base de datos:** MariaDB 11.8
- **Frontend:** HTML5, CSS3 (Variables CSS personalizadas) y JavaScript
- **Tipografía:** Plus Jakarta Sans

---

## 🚀 Instalación y Configuración Local

Sigue estos pasos para clonar y ejecutar el proyecto en tu entorno local:

1. **Clona el repositorio:**
   ```bash
   git clone [https://github.com/landisperez21-alt/agenda_simple_v2.git](https://github.com/landisperez21-alt/agenda_simple_v2.git)
Crea y activa un entorno virtual:


python -m venv venv
# En Windows:
venv\Scripts\activate
Instala las dependencias:


pip install -r requirements.txt
Realiza las migraciones de la base de datos:


python manage.py migrate
Inicia el servidor de desarrollo:


python manage.py runserver
Abre tu navegador e ingresa a: http://127.0.0.1:8000/

# Autor y Desarrollador:
Proyecto creado, diseñado y desarrollado por Landi (landisperez21-alt), como parte de la implementación de sistemas web modernos y arquitectura con Django. ✨