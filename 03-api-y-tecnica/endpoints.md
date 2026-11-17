# 🔌 Documentación de la API REST - AutoMaster

# ⚙️ Guía de Instalación y Despliegue Local

## 1. Requisitos Previos
* **Java Development Kit (JDK):** Versión 17 o superior.
* **Apache Maven:** Versión 3.8+ (o usar el wrapper incluido si aplica).
* **Node.js y npm:** Node.js v18+ LTS.
* **Motor de Base de Datos SQL:** MySQL / MariaDB (según la configuración en `application.properties`).

---

## 2. Configuración de la Base de Datos
1. Inicia tu servidor de base de datos local.
2. Ejecuta el script **`automaster_db.sql`** ubicado en la raíz del repositorio para crear el esquema y cargar los datos iniciales.
3. Abre el archivo `main/resources/application.properties` y verifica que los parámetros de conexión coincidan con tu entorno local:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/automaster_db
   spring.datasource.username=TU_USUARIO
   spring.datasource.password=TU_CONTRASEÑA

   ### 3. Ejecución del Backend (Spring Boot)

1. Abre una terminal en la raíz del proyecto (donde se encuentra `pom.xml`).
2. Compila e instala las dependencias con Maven:
   ```bash
   mvn clean install
   ```
3. Levanta el servidor Spring Boot:
   ```bash
   mvn spring-boot:run
   ```
4. Verifica que el backend esté activo en http://localhost:8080.
5. Puedes explorar la interfaz de Swagger (configurada en `OpenApiConfig.java`) en: http://localhost:8080/swagger-ui.html

### 4. Ejecución del Frontend (React + Vite)

1. Abre una segunda terminal y entra en la carpeta del cliente web:
   ```bash
   cd frontend-web-main
   ```
2. Instala los paquetes definidos en `package.json`:
   ```bash
   npm install
   ```
3. Inicia el servidor de desarrollo de Vite (`vite.config.js`):
   ```bash
   npm run dev
   ```
4. Accede a la aplicación en tu navegador mediante http://localhost:5173.

5. ### 4. `documentacion/03-api-y-tecnica/endpoints.md`

# 🔌 Diccionario de Endpoints (API REST)

Todos los endpoints protegidos requieren enviar el token JWT en la cabecera HTTP:
`Authorization: Bearer <token>`


## 1. Autenticación (`AuthController.java`)

| Método | Ruta | Acceso | Descripción | Cuerpo / Respuesta |
| :--- | :--- | :--- | :--- | :--- |
| `POST` | `/api/auth/login` | Público | Autentica credenciales y devuelve un token JWT. | **Req:** `{ "email": "...", "password": "..." }`<br>**Res:** `200 OK` `{ "token": "eyJ..." }` |
| `POST` | `/api/auth/register` | Público | Registra un nuevo usuario en el sistema. | **Req:** `{ "nombre": "...", "email": "...", "password": "..." }`<br>**Res:** `201 Created` |

---

## 2. Vehículos (`VehiculoController.java`)

| Método | Ruta | Acceso | Descripción |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/vehiculos` | Público | Lista todos los vehículos registrados en el catálogo. |
| `GET` | `/api/vehiculos/{id}` | Público | Obtiene el detalle de un vehículo específico por su ID. |
| `POST` | `/api/vehiculos` | Admin (JWT) | Registra un nuevo vehículo en el inventario. |
| `PUT` | `/api/vehiculos/{id}` | Admin (JWT) | Actualiza los datos de un vehículo existente. |
| `DELETE` | `/api/vehiculos/{id}` | Admin (JWT) | Elimina un vehículo del inventario. |

---

## 3. Categorías (`CategoriaController.java`)

| Método | Ruta | Acceso | Descripción |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/categorias` | Público | Lista todas las categorías de vehículos disponibles. |
| `GET` | `/api/categorias/{id}` | Público | Obtiene información de una categoría por ID. |
| `POST` | `/api/categorias` | Admin (JWT) | Crea una nueva categoría. |
| `PUT` | `/api/categorias/{id}` | Admin (JWT) | Modifica una categoría existente. |
| `DELETE` | `/api/categorias/{id}` | Admin (JWT) | Elimina una categoría. |

---

## 4. Usuarios y Roles (`UsuarioController.java` / `RolController.java`)

| Método | Ruta | Acceso | Descripción |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/usuarios` | Admin (JWT) | Lista los usuarios registrados en el sistema. |
| `GET` | `/api/usuarios/{id}` | Autenticado | Consulta la información de un usuario por ID. |
| `PUT` | `/api/usuarios/{id}` | Autenticado | Actualiza los datos del perfil de usuario. |
| `DELETE` | `/api/usuarios/{id}` | Admin (JWT) | Elimina un usuario del sistema. |
| `GET` | `/api/roles` | Admin (JWT) | Lista los roles disponibles en `RolRepository`. |
