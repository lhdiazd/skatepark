# Skatepark Application

## Descripción

La Municipalidad de Santiago ha lanzado una competencia de Skate para jóvenes aspirantes a los X Games del próximo año. Esta plataforma web permite a los participantes registrarse, iniciar sesión, y gestionar su estado de solicitud. Los administradores pueden aprobar y gestionar los participantes.

## Tecnologías Utilizadas

- **Express**: Framework para construir la API REST.
- **Handlebars**: Motor de plantillas para vistas dinámicas.
- **PostgreSQL**: Base de datos para almacenar la información de los participantes.
- **JWT**: Json Web Token para autenticación y autorización.
- **Express-fileupload**: Middleware para carga de archivos.

## Estructura del Proyecto

```plaintext
/
├── public/                 # Archivos estáticos (CSS, JS, imágenes)
│   ├── uploads/            # Imágenes de perfil
│   ├── css/
│   ├── js/
├── views/                  # Vistas de Handlebars
│   ├── mainLayout/         # Layout principal
│   ├── Home.handlebars     # Lista de participantes
│   ├── Registro.handlebars # Registro de participantes
│   ├── Login.handlebars    # Inicio de sesión
│   ├── Perfil.handlebars   # Modificación de perfil
│   ├── Admin.handlebars    # Administración
├── node_modules/           # Dependencias del proyecto
├── .gitignore              # Archivos ignorados por Git
├── package.json            # Configuración del proyecto
├── server.js               # Archivo principal del servidor
└── consultas.js            # Consultas a la base de datos
```

```sql
CREATE DATABASE skatepark;

CREATE TABLE skaters (
    id SERIAL PRIMARY KEY,
    email VARCHAR(50) NOT NULL,
    nombre VARCHAR(25) NOT NULL,
    password VARCHAR(25) NOT NULL,
    anos_experiencia INT NOT NULL,
    especialidad VARCHAR(50) NOT NULL,
    foto VARCHAR(255) NOT NULL,
    estado BOOLEAN NOT NULL
);

```

```js
const pool = new Pool({
  user: "postgres",
  host: "localhost",
  password: "1234",
  database: "skatepark",
  port: 5432,
});

```
