# 🔌 Documentación de la API REST - AutoMaster

**URL Base (Entorno Docker Local):** `http://localhost:[PUERTO_BACKEND]/api`  
**Autenticación:** Bearer Token (JWT) en el header `Authorization`.

---

## 🚘 Módulo de Vehículos

| Método | Endpoint | Descripción | Acceso |
| :--- | :--- | :--- | :--- |
| `GET` | `/vehiculos` | Obtiene el catálogo completo (admite filtros por marca, año y estado). | Público |
| `GET` | `/vehiculos/:id` | Obtiene el detalle técnico y fotos de un vehículo específico. | Público |
| `POST` | `/vehiculos` | Registra un nuevo vehículo en el inventario. | Admin / Vendedor |
| `PUT` | `/vehiculos/:id` | Actualiza precio, kilometraje o estado (Disponible / Vendido). | Admin / Vendedor |
| `DELETE` | `/vehiculos/:id` | Elimina un vehículo del sistema. | Admin |

### Ejemplo de petición (`POST /vehiculos`)
```json
{
  "marca": "Toyota",
  "modelo": "Corolla Cross",
  "anio": 2025,
  "precio": 22500000,
  "estado": "Nuevo",
  "kilometraje": 0
}
