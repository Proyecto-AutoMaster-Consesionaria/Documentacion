# 📋 Requerimientos y Alcance del Sistema — AutoMaster

## 1. Propósito del Sistema
**AutoMaster** es una plataforma web full-stack para la exhibición, gestión de inventario y comercialización de vehículos. El sistema permite a los clientes explorar el catálogo por categorías, revisar ofertas, gestionar su cuenta y simular/realizar compras mediante un carrito, mientras que los administradores gestionan los vehículos, categorías y usuarios desde un panel dedicado.

---

## 2. Roles de Usuario
De acuerdo con el modelo de datos (`Rol.java`, `Usuario.java`) y las reglas de seguridad (`SecurityConfig.java`), se contemplan los siguientes perfiles:

* **Visitante (Público):** Puede navegar por la página de inicio, explorar el catálogo completo, filtrar por categorías, ver ofertas, consultar el detalle técnico de cada vehículo y acceder a la sección de contacto.
* **Cliente Registrado (`ROLE_USER`):** Puede iniciar sesión con credenciales autenticadas mediante JWT, gestionar su perfil de cuenta y completar el flujo de compra desde el carrito.
* **Administrador (`ROLE_ADMIN`):** Tiene acceso al módulo administrativo para realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre el inventario de vehículos, categorías y gestión de roles/usuarios.

---

## 3. Historias de Usuario Principales

| ID | Rol | Historia de Usuario | Módulo / Vista Asociada |
| :--- | :--- | :--- | :--- |
| **HU-01** | Visitante | Como visitante, quiero ver los vehículos destacados y ofertas disponibles para conocer el catálogo inicial. | `PaginaInicio.jsx`, `PaginaOfertas.jsx` |
| **HU-02** | Visitante | Como visitante, quiero filtrar vehículos por categoría y revisar su ficha técnica para comparar opciones. | `PaginaCategorias.jsx`, `PaginaDetalleCategoria.jsx`, `PaginaDetalleVehiculo.jsx` |
| **HU-03** | Cliente | Como cliente, quiero registrarme e iniciar sesión de forma segura para acceder a las funciones de compra y perfil. | `PaginasCuenta.jsx`, `AuthController.java` |
| **HU-04** | Cliente | Como cliente, quiero agregar vehículos al carrito y finalizar mi compra para obtener un comprobante de la operación. | `PaginaCarrito.jsx`, `PaginaFinalizarCompra.jsx`, `PaginaResultadoCompra.jsx` |
| **HU-05** | Administrador | Como administrador, quiero agregar, editar y eliminar vehículos del inventario para mantener el catálogo actualizado. | `PanelAdministracion.jsx`, `ModuloAdministrativo.jsx`, `InventarioVehiculos.jsx` |
| **HU-06** | Administrador | Como administrador, quiero gestionar las categorías disponibles para organizar la clasificación de los vehículos. | `CategoriaController.java`, `CategoriaService.java` |
