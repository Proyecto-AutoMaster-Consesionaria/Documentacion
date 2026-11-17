# 🧪 Plan de Pruebas y Matriz QA — AutoMaster

## 1. Pruebas Automatizadas del Proyecto
El repositorio incluye suites de pruebas en el frontend para validar lógica CRUD y renderizado de componentes:
* **`frontend-web-main/src/datos/operacionesCrud.pruebas.js`:** Valida las operaciones de creación, lectura, actualización y eliminación sobre la estructura de datos local.
* **`frontend-web-main/pruebas/pruebasComponentes.pruebas.jsx`:** Verifica el correcto renderizado e interacción de los componentes React.

---

## 2. Matriz de Pruebas Funcionales e Integración (QA)

| ID | Módulo / Archivo | Caso de Prueba | Datos / Acción | Resultado Esperado | Estado |
| :--- | :--- | :--- | :--- | :--- | :---: |
| **CP-01** | `AuthController.java` | Inicio de sesión con credenciales válidas | Email y contraseña registrados en `automaster_db` | Responde `200 OK` y retorna token JWT válido (`JwtUtil`). | ✅ Aprobado |
| **CP-02** | `AuthController.java` | Inicio de sesión con contraseña incorrecta | Email válido + contraseña errónea | Rechaza el acceso (`401 Unauthorized`) y muestra alerta en `MensajeEstado.jsx`. | ✅ Aprobado |
| **CP-03** | `JwtRequestFilter.java` | Petición a ruta protegida sin token | `POST /api/vehiculos` sin cabecera `Authorization` | Bloquea la petición (`401` / `403`) según `SecurityConfig.java`. | ✅ Aprobado |
| **CP-04** | `VehiculoController.java` | Consulta pública del catálogo | `GET /api/vehiculos` desde `api.js` | Retorna listado JSON de vehículos y los renderiza en `ListaVehiculos.jsx`. | ✅ Aprobado |
| **CP-05** | `InventarioVehiculos.jsx` | Creación de un nuevo vehículo como Admin | Completar formulario con marca, modelo, precio y categoría | Se persiste vía `VehiculoService.java` y aparece en el catálogo público. | ✅ Aprobado |
| **CP-06** | `PaginaCarrito.jsx` | Flujo completo de carrito y compra | Añadir vehículo → Finalizar compra (`PaginaFinalizarCompra.jsx`) | Calcula totales correctamente y muestra comprobante en `PaginaResultadoCompra.jsx`. | ✅ Aprobado |
