# 🚗 Sistema de Gestión de Ventas para Concesionario Chevrolet

Sistema web full-stack desarrollado para gestionar diferentes procesos relacionados con la operación y venta de vehículos en un concesionario Chevrolet en Colombia.

El proyecto integra un **frontend desarrollado con React**, un **backend desarrollado con FastAPI** y una **base de datos PostgreSQL**, implementando autenticación, autorización por roles, gestión de clientes y vehículos, ventas, pagos, financiación, generación de facturas en PDF y reportes.

## 📸 Vista previa

> Próximamente se agregarán capturas de pantalla de las principales funcionalidades de la aplicación.

---

## 📌 Funcionalidades principales

* 🔐 Autenticación de usuarios mediante JWT.
* 👥 Gestión de usuarios y roles.
* 👤 Gestión de clientes.
* 🚗 Gestión de vehículos.
* 💰 Registro y gestión de ventas.
* 💳 Gestión de pagos.
* 📄 Generación de facturas en PDF.
* 🔳 Generación de códigos QR.
* 📊 Dashboard y consultas.
* 📈 Generación de reportes de ventas.
* 🛡️ Validación de información.
* ⚠️ Manejo global de excepciones.
* 🔑 Control de acceso según el rol del usuario.

---

## 👤 Roles del sistema

El sistema cuenta con diferentes roles para controlar el acceso a las funcionalidades:

| Rol               | Descripción                                                       |
| ----------------- | ----------------------------------------------------------------- |
| **Superadmin**    | Administración general del sistema.                               |
| **Administrador** | Gestión de las principales operaciones del concesionario.         |
| **Usuario**       | Acceso a las funcionalidades permitidas para usuarios operativos. |
| **Consultas**     | Acceso principalmente orientado a la consulta de información.     |

Los permisos disponibles dependen del rol asignado al usuario.

---

## 🛠️ Tecnologías utilizadas

### Backend

* Python
* FastAPI
* SQLAlchemy
* PostgreSQL
* Pydantic
* JWT
* Uvicorn
* Pillow

### Frontend

* React
* JavaScript
* Vite
* React Router
* Axios
* Tailwind CSS
* SweetAlert2

### Herramientas

* Git
* GitHub
* Visual Studio Code
* DBeaver
* Postman

---

## 🏗️ Arquitectura del proyecto

El proyecto está dividido en dos aplicaciones principales:

```text
Concesionario/
│
├── backend/
│   ├── app/
│   │   ├── config/
│   │   ├── middleware/
│   │   ├── models/
│   │   └── routes/
│   │
│   ├── facturas/
│   ├── main.py
│   └── requirements.txt
│
├── frontend/
│   ├── public/
│   ├── src/
│   ├── package.json
│   └── ...
│
├── .env.example
├── .gitignore
└── README.md
```

### Backend

El backend utiliza una organización modular para separar diferentes responsabilidades de la aplicación:

* `config/`: configuración del proyecto.
* `middleware/`: middleware utilizado por la aplicación.
* `models/`: modelos y entidades de la base de datos.
* `routes/`: endpoints de la API.
* `facturas/`: archivos relacionados con la generación y demostración de facturas.
* `main.py`: punto de entrada de la aplicación.

### Frontend

El frontend está desarrollado con React y Vite y consume los servicios proporcionados por la API REST del backend.

---

## ⚙️ Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/BetancourtRomeroDaniel/Concesionario.git
cd Concesionario
```

### 2. Configurar el backend

Ingresar a la carpeta del backend:

```bash
cd backend
```

Crear un entorno virtual:

```bash
python3 -m venv venv
```

#### Activar el entorno virtual

**macOS / Linux:**

```bash
source venv/bin/activate
```

**Windows:**

```bash
venv\Scripts\activate
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

---

## 🗄️ Configuración de PostgreSQL

El proyecto utiliza **PostgreSQL** como sistema de gestión de base de datos.

Crear una base de datos local, por ejemplo:

```text
concesionario_chevrolet
```

Después, crear el archivo:

```text
backend/.env
```

utilizando `.env.example` como referencia.

Ejemplo:

```env
DATABASE_URL=postgresql://USUARIO:CONTRASEÑA@localhost/NOMBRE_BASE_DATOS

SECRET_KEY=CAMBIAR_ESTA_CLAVE

ALGORITHM=HS256

ACCESS_TOKEN_EXPIRE_MINUTES=60
```

> ⚠️ **Importante:** no subir el archivo `.env` a GitHub. Las credenciales y claves privadas deben mantenerse fuera del repositorio.

---

## ▶️ Ejecutar el backend

Desde la carpeta `backend`:

```bash
uvicorn main:app --reload
```

El backend estará disponible normalmente en:

```text
http://127.0.0.1:8000
```

### Documentación de la API

FastAPI proporciona documentación interactiva mediante Swagger:

```text
http://127.0.0.1:8000/docs
```

---

## 💻 Ejecutar el frontend

Abrir una nueva terminal desde la carpeta raíz del proyecto e ingresar a:

```bash
cd frontend
```

Instalar las dependencias:

```bash
npm install
```

Ejecutar la aplicación:

```bash
npm run dev
```

Otros comandos disponibles:

```bash
npm run build
npm run lint
npm run preview
```

---

## 🗃️ Base de datos

La aplicación utiliza:

* **PostgreSQL** para almacenar la información.
* **SQLAlchemy** como ORM.
* Modelos para representar las principales entidades del sistema.
* Validaciones para controlar la información registrada.

Al iniciar el backend, SQLAlchemy utiliza los modelos importados para crear las tablas que todavía no existan en la base de datos.

---

## 📄 Facturación

El sistema permite generar documentos de factura en formato PDF y códigos QR asociados a las facturas.

Dentro de:

```text
backend/facturas/
```

se encuentran archivos utilizados como datos de demostración del proyecto.

Los datos incluidos en estas facturas son ficticios y se utilizan únicamente con fines académicos y de demostración.

---

## 🔐 Seguridad

El proyecto implementa diferentes mecanismos para proteger la aplicación:

* Autenticación mediante JWT.
* Control de acceso basado en roles.
* Variables de entorno para información sensible.
* `.gitignore` para evitar subir archivos privados.
* Validación de datos.
* Manejo global de excepciones.

---

## 🧪 Pruebas y herramientas de desarrollo

Durante el desarrollo se utilizaron diferentes herramientas para verificar el funcionamiento de la aplicación:

### Postman

Utilizado para probar los endpoints de la API REST, incluyendo operaciones relacionadas con usuarios, clientes, vehículos, ventas y otros recursos.

### DBeaver

Utilizado para administrar y consultar la base de datos PostgreSQL, además de verificar la información almacenada por la aplicación.

### FastAPI Swagger

Utilizado para consultar y probar de forma interactiva los endpoints disponibles en la API.

---

## 🎯 Objetivo del proyecto

El objetivo principal fue desarrollar un sistema web que permitiera digitalizar y organizar diferentes procesos relacionados con la gestión de un concesionario de vehículos.

El desarrollo permitió integrar conocimientos de:

* Desarrollo backend.
* Desarrollo frontend.
* Bases de datos.
* APIs REST.
* Autenticación y autorización.
* Validación de información.
* Generación de documentos.
* Control de versiones con Git y GitHub.

---

## 📚 Aprendizajes

Durante el desarrollo del proyecto se trabajó en la integración de diferentes tecnologías para construir una aplicación web completa, conectando el frontend, backend y base de datos.

También se adquirieron conocimientos prácticos en:

* Organización de proyectos full-stack.
* Desarrollo de APIs REST.
* Integración entre React y FastAPI.
* Manejo de bases de datos PostgreSQL.
* Uso de SQLAlchemy como ORM.
* Autenticación y autorización mediante JWT.
* Manejo de variables de entorno.
* Validación de datos.
* Generación de documentos PDF.
* Pruebas de APIs.
* Control de versiones con Git y GitHub.

---

## 👨‍💻 Autor

**Jeisson Daniel Betancourt Romero**

Estudiante de Ingeniería de Sistemas — ETITC

GitHub: [@BetancourtRomeroDaniel](https://github.com/BetancourtRomeroDaniel)

---

## 📌 Estado del proyecto

Proyecto académico desarrollado como aplicación web full-stack para la gestión de procesos de un concesionario de vehículos.

El proyecto puede continuar evolucionando con nuevas funcionalidades, mejoras de interfaz, pruebas automatizadas y despliegue en un entorno de producción.

